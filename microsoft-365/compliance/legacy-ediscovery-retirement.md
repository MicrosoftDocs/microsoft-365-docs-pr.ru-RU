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
description: In-Place eDiscovery и In-Place Hold (и соответствующие cmdlets PowerShell) в Exchange Online будут отменены в первой половине 2020 г. Также Search-Mailbox и Advanced eDiscovery v1.0 в течение того же периода времени.
ms.openlocfilehash: 97be285ae348b018866e3f91f92be523b03e6616
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055072"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>Прекращение поддержки устаревших средств обнаружения электронных данных

> [!IMPORTANT]
> Функциональные возможности устаревших средств электронного разыскного анализа, описанные в этой статье, либо удалены из службы Microsoft 365, либо по-прежнему доступны, но больше не поддерживаются. Все доступные функции могут быть удалены без уведомления. Если вы по-прежнему используете любой из этих устаревших средств, рассмотрите возможность перехода к средствам электронного Центр соответствия требованиям Microsoft 365 или к одному из альтернативных средств, описанных в этой статье.

На протяжении многих лет корпорация Майкрософт предоставляла средства для поиска, предварительного просмотра и экспорта контента электронной почты из Exchange Online. Однако эти средства больше не предоставляют эффективный способ поиска контента Exchange других Microsoft 365, таких как SharePoint Online и Microsoft 365 Groups. Чтобы решить эту проблему, Корпорация Майкрософт предлагает другие средства для поиска электронных Microsoft 365. И мы работали над включением наиболее актуальных и мощных функций электронного разыскных открытий в [Центр соответствия требованиям Microsoft 365](https://compliance.microsoft.com). Это позволяет организациям отвечать на запросы юридических, внутренних и других документов для контента во многих Microsoft 365, включая Exchange Online.

В результате этой новой и улучшенной функции поиска электронных сообщений в Центр соответствия требованиям Microsoft 365 мы удаляем следующие функции и функции, связанные с электронным открытием, связанные с поиском контента электронной почты в Exchange Online и Microsoft 365:

- [Открытие электронных данных](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) на [](/exchange/security-and-compliance/create-or-remove-in-place-holds) месте и удерживает на месте в центре Exchange администрирования.

- Эти Exchange Online PowerShell, поддерживающие In-Place eDiscovery и In-Place Holds (эти cmdlets совместно идентифицированы как **-MailboxSearch).* Это включает в себя следующие cmdlets:

  - [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](/powershell/module/exchange/stop-mailboxsearch)

  - [Set-MailboxSearch](/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > [Комлеты Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch) и [Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) будут доступны после того, как будут отменены другие cmdlets ****-MailboxSearch*** для того, чтобы вы могли использовать их, чтобы помочь в переходе к другим средствам eDiscovery и удержанию. Однако после определенной даты (приведенной ниже) поддержка Майкрософт больше не будет поддерживать эти два cmdlets.

- Комлет [Search-Mailbox](/powershell/module/exchange/search-mailbox) в Exchange Online PowerShell.

- Следующие операции в API Exchange веб-служб:

   - [GetSearchableMailboxes](/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 Advanced eDiscovery v1.0](./overview-ediscovery-20.md), которая является первой версией Advanced eDiscovery, доступ к которой имеется в случае с core eDiscovery в центре Office 365 безопасности & соответствия требованиям. Выход из Advanced eDiscovery v1.0 не влияет на возможность создания и управления делами по обнаружению основных электронных обнаружений.

> [!NOTE]
> Удаляемая функция eDiscovery применяется только к облачным версиям Microsoft 365 и Office 365. Функции eDiscovery в локальной версии Exchange и SharePoint будут поддерживаться до дальнейшего уведомления.

В следующих разделах этой статьи представлены рекомендации по каждой удаляемой функции. Эти сведения, включая временные данные и альтернативные средства, которые можно использовать вместо отключаемого средства.

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>In-Place и In-Place в центре администрирования Exchange 

В первоначальном объявлении от 1 июля 2017 г. функция In-Place eDiscovery & Hold в центре администрирования Exchange администрирования (EAC) будет отменена. Страница In-Place eDiscovery & в EAC позволяет искать, удерживать и экспортировать контент из Exchange Online. In-Place eDiscovery также позволит скопировать результаты поиска в почтовый ящик обнаружения, чтобы вы или другие менеджеры по обнаружению могли просмотреть контент и сделать его доступным для юридических, нормативных и общедоступных запросов.

Поскольку все эти возможности (за исключением копирования результатов поиска в почтовый ящик обнаружения) теперь доступны в средствах поиска контента, обнаружения электронных данных и Advanced eDiscovery в [Центр соответствия требованиям Microsoft 365](./microsoft-365-compliance-center.md) (с улучшенной функциональностью, надежностью и поддержкой широкого спектра служб Microsoft 365), рекомендуем как можно скорее приступить к использованию этих средств. Чтобы помочь вам в переходе к другим средствам электронной информации, в таблице ниже перечислены средства, которые можно использовать вместо In-Place и In-Place Hold.

### <a name="scope-of-affected-organizations"></a>Область затронутых организаций

- Office 365 и Microsoft 365 корпоративный организаций

- Office 365 и Microsoft 365 для образования организаций

- Office 365 и Microsoft 365 государственных организаций; это включает GCC, GCC High и DoD

- Office 365 Germany

### <a name="timeline-for-retirement"></a>Сроки выхода на пенсию

- 1 июля 2020 г. Вы не сможете создавать новые поиски и удерживает, но вы все равно можете запускать, изменять и удалять существующие поиски на свой собственный риск. Поддержка Майкрософт больше не In-Place электронных & в EAC.

- 1 октября 2020 г. Функция In-Place eDiscovery & удерживает функции в EAC, будет размещена в режиме только для чтения. Это означает, что вы сможете удалить существующие поиски и удерживает.

### <a name="alternative-tools"></a>Альтернативные средства

В следующей таблице описываются другие средства, которые можно использовать для замены уже отошедшего функционала.

<table>
<thead>
<tr class="header">
<th>функциональность.</th>
<th>Альтернативный инструмент</th>
<th>Комментарии</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Поиск, экспорт и удержание в юридических целях</td>
<td>Основные случаи электронных обнаружений в Центр соответствия требованиям Microsoft 365 </td>
<td><p>Использование возможностей основных дел по обнаружению электронных обнаружений обеспечивает функциональный паритет для In-Place и In-Place удерживает. В том числе:</p>
<ul>
<li>
<p>Масштабы поиска до миллионов местоположений</p>
</li>
<li>
<p>Более высокая надежность поиска, экспорта и размещения контента на удержание</p>
</li>
<li>
<p>Поиск контента для Exchange Online, SharePoint Online, OneDrive для бизнеса, Skype для бизнеса, Microsoft Teams, Yammer Groups, Microsoft 365 Groups и другого контента, Office 365 приложениях</p></li></ul>
</td>
</tr>
<tr class="even">
<td>Удержание для целей хранения</td>
<td>Политики хранения в Центр соответствия требованиям Microsoft 365</td>
<td><p>Политики хранения можно использовать для сохранения контента и при желании удалить его по истечении срока хранения. Другие возможности:</p>
<ul>
<li>
<p>Применение политик для всей организации </p>
</li><li>
<p>Применение политик к определенным расположениям контента, таким как Exchange Online, SharePoint Online, OneDrive для бизнеса, Skype для бизнеса, Microsoft Teams и Office 365 групп</p></li>
<li>
<p>Применение политик к конкретным пользователям</p></li></ul>
<p>Дополнительные сведения см. <a href="/microsoft-365/compliance/retention-policies">в дополнительных сведениях о политиках хранения и метки хранения.</a></td>
</tr>
<tr class="odd">
<td>Скопируйте результаты поиска электронной почты в почтовый ящик обнаружения для проверки</td><td>Наборы обзоров в Advanced eDiscovery v2.0</td>
<td><p>Просмотр контента в Microsoft 365 никогда не был проще. Наборы обзоров имеют множество возможностей, которые помогут сократить время и данные, необходимые для проверки, в том числе:</p>
<ul>
<li><p>Выполнение быстрых поисковых запросов и фильтрация контента в наборе обзоров</p></li>
<li><p>Анализ контента в наборе обзоров; это включает в себя потоковую отправку электронной почты, почти дубликат обнаружения, анализ тем и прогнозирование кодирования</p></li>
<li><p>Добавление тегов к документам в наборе для проверки</p></li>
<li><p>Пометка предложений, которые помогут определить содержимое клиентских привилегий адвоката</p></li></ul>
<p>Дополнительные сведения см. в статье <a href="/microsoft-365/compliance/overview-ediscovery-20">Обзор решения Advanced eDiscovery в Microsoft 365</a>.</p>
<p>
<p>Кроме того, можно экспортировать результаты поиска в PST-файлы, а затем Microsoft 365 службу импорта для импорта PSTs в почтовый ящик обнаружения. Пошаговая инструкция см. в инструкции Использование сетевой загрузки для импорта <a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">PST-файлов в Office 365.</a>
</tr>
<tr class=even>
  <td>Копирование сообщений из одного почтового ящика в другой почтовый ящик</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Назначение разрешений почтовому ящику</a></td>
  <td>Чтобы предоставить пользователю доступ к электронной почте другого пользователя (например, когда сотрудник покидает организацию и вам необходимо предоставить другому лицу доступ к электронной почте бывшего сотрудника), мы рекомендуем назначить этому лицу разрешения на доступ к почтовому ящику бывшего сотрудника. Поэтому вместо копирования элементов почтовых ящиков в другой почтовый ящик пользователя или общий почтовый ящик просто назначьте пользователю разрешения, необходимые для доступа к исходным почтовым ящикам.</td>
  
  </tr>
<tr class="odd">
<td>Восстановление элементов из папки "Извлекаемые элементы"</td>
  <td><a href="/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>Вы можете восстановить постоянно удаленные элементы <i></i> (также известные как мягкие удаленные элементы) в почтовых ящиках до тех пор, пока срок хранения удаленных элементов для элемента не истек. Дополнительные сведения см. в папке <a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">"Извлекаемые элементы" в Exchange Online.</a></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>FAQs about In-Place eDiscovery and In-Place Holds

**Я использую функции результатов поиска In-Place обнаружения & в EAC для копирования результатов поиска в почтовый ящик обнаружения для проверки адвокатами. Какие возможности у меня есть сейчас?**

Существует два способа репликации этой функции на сегодняшний день. Во-первых, используйте [наборы обзоров в Advanced eDiscovery v2.0](./view-documents-in-review-set.md). Наборы обзоров имеют множество одинаковых возможностей, которые вы видите в традиционном инструменте проверки, таких как быстрый поиск документов, метки, потоки электронной почты, рядом с дублирующей группировкой, анализ тем и прогностическое кодирование. Если вы по-прежнему хотите использовать почтовые ящики обнаружения для проверки, второй вариант — экспорт результатов поиска в PST-файлы, а затем импорт PST-файлов в почтовый ящик обнаружения с помощью функции [импорта PST](use-network-upload-to-import-pst-files.md) в центре соответствия требованиям Майкрософт.

**Как управлять расположениями контента (например, почтовыми ящиками или сайтами), которые может искать менеджер по обнаружению электронных сообщений с помощью новых средств?**

В Центр соответствия требованиям Microsoft 365 также используются границы соответствия требованиям для [управления](set-up-compliance-boundaries.md) расположениями контента, которые может искать диспетчер по обнаружению электронных обнаружений. Границы соответствия требованиям являются полезными для государственных организаций, которые должны находиться в пределах границ учреждений или многонациональных корпораций, необходимых для соблюдения географических границ.

**Как переместить текущий поиск и удерживает его в Центр соответствия требованиям Microsoft 365?**

С помощью PowerShell можно перенести In-Place поиск и удерживает их из EAC. Инструкции см. в [инструкции Перенос поисков](./migrate-legacy-ediscovery-searches-and-holds.md)и удерживаний из EAC в Центр соответствия требованиям Microsoft 365.

## <a name="-mailboxsearch-cmdlets"></a>\*-MailboxSearch cmdlets

В исходном уведомлении, объявленном 1 июля 2017 г. в центре администрирования Exchange, функция In-Place eDiscovery & Hold и соответствующие **\* cmdlets -MailboxSearch** будут отменены. Эти cmdlets предоставляют пользователям возможность поиска, удержания и экспорта контента почтовых ящиков для юридических, нормативных и общедоступных запросов.

Поскольку эти возможности теперь доступны в [<span class="underline">центре Центр соответствия требованиям Microsoft 365</span>](./microsoft-365-compliance-center.md) и Office 365 безопасности & PowerShell с улучшенной производительностью и масштабируемостью, следует использовать эти улучшенные команды. Эти cmdlets включают [<span class="underline"> \* -ComplianceCase</span>](/powershell/module/exchange/get-compliancecase), [<span class="underline"> \* -ComplianceSearch</span>](/powershell/module/exchange/get-compliancesearch), [<span class="underline"> \* -CaseHoldPolicy</span>](/powershell/module/exchange/get-caseholdpolicy), [<span class="underline"> \* -CaseHoldRule</span>](/powershell/module/exchange/get-caseholdrule), и [<span class="underline"> \* -ComplianceSearchAction</span>](/powershell/module/exchange/get-compliancesearchaction).

### <a name="scope-of-affected-organizations"></a>Область затронутых организаций

- Office 365 и Microsoft 365 корпоративный организаций

- Office 365 и Microsoft 365 для образования организаций

- Office 365 и Microsoft 365 государственных организаций; это включает GCC, GCC High и DoD

- Office 365 Germany

### <a name="timeline"></a>Временная шкала

- 1 июля 2020 г. Вы не сможете использовать **New-MailboxSearch** для создания новых поисков In-Place электронных данных и In-Place удерживает, но вы по-прежнему можете использовать cmdlets для запуска, редактирования и удаления существующих поисков и удерживается на свой собственный риск. Microsoft Support больше не будет предоставлять помощь для этих типов поиска и удерживает.

- 1 октября 2020 г. Как уже говорилось, функция In-Place eDiscovery & Содержит функции в EAC будет размещена в режиме только для чтения. Это также означает, что вы не сможете использовать **cmdlets New-MailboxSearch,** **Start-MailboxSearch** или **Set-MailboxSearch.** Вы сможете получить и удалить существующие поиски и удерживает.

### <a name="alternative-tools"></a>Альтернативные средства

В следующей таблице описываются другие средства, которые можно использовать для замены уже отошедшего функционала.

<table>
<thead>
<tr class="header">
<th>функциональность.</th>
<th>Альтернативные средства</th>
<th>Комментарии</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Поиск и экспорт</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Чтобы помочь поиску и экспорту контента, совместно работают между собой cmdlets ComplianceSearch и ComplianceSearchAction. Вы можете создать новый поиск и просмотреть оценку поиска с помощью кодлетов <strong>New-</strong>, <strong>Get-</strong>и <strong>Start-ComplianceSearch.</strong> Затем вы можете экспортировать результаты поиска с помощью <strong>cmdlet New-ComplianceSearchAction.</strong> Для загрузки результатов поиска на локальный компьютер вам все равно придется использовать основной инструмент для Центр соответствия требованиям Microsoft 365 поиска.</p>
<p>
<p><strong>Примечание:</strong> Если эти кодлеты используются для создания поисков, не связанных с базовым случаем поиска, <strong></strong> эти поиски будут размещены на странице поиска контента в Центр соответствия требованиям Microsoft 365.</p></td>
</tr>
<tr class="even">
<td>Удержание контента в почтовом ящике</td>
<td><p><a href="/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Удерживание в Центр соответствия требованиям Microsoft 365 должно быть связано с complianceCase. Сначала создайте случай соответствия требованиям, а затем создайте CaseHoldPolicy и CaseHoldRule.</p>
<p><strong>Примечание:</strong> Создание CaseHoldPolicy без создания CaseHoldRule сделает удержание неоперабельным до создания CaseHoldRule и его связи с CaseHoldPolicy. Дополнительные сведения см. в документации по cmdlet.</p></td>
</tr>
<tr class="odd">
<td>Копирование результатов поиска в почтовый ящик обнаружения</td>
<td>Нет.</td>
<td>Прямой замены этой функции нет, так как она не предоставляет доступ ко всем Microsoft 365 службам. Ниже приведены следующие вопросы по альтернативным решениям.</td>
</tr>
  <tr class=even>
  <td>Копирование сообщений из одного почтового ящика в другой почтовый ящик</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Назначение разрешений почтовому ящику</a></td>
  <td>Чтобы предоставить пользователю доступ к электронной почте другого пользователя (например, когда сотрудник покидает организацию и вам необходимо предоставить другому лицу доступ к электронной почте бывшего сотрудника), мы рекомендуем назначить этому лицу разрешения на доступ к почтовому ящику бывшего сотрудника. Поэтому вместо копирования элементов почтовых ящиков в другой почтовый ящик пользователя или общий почтовый ящик просто назначьте пользователю разрешения на доступ к исходным почтовым ящикам.</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>FaQs about ***-MailboxSearch cmdlets**

**Мы используем copy Search для экспорта сообщений электронной почты или мгновенных сообщений для целей других расследований и юридических расследований. Какие еще варианты у нас есть после того, как эти комлеты будут отменены?**

API [<span class="underline">microsoft Graph</span>](https://developer.microsoft.com/en-us/graph) предоставляют ряд методов для извлечения данных для анализа и других целей, которые гораздо более устойчивы и масштабируемы, чем с помощью **\* cmdlets -MailboxSearch.**

**Как перенести поиск и перейти на Центр соответствия требованиям Microsoft 365?**

С помощью скрипта PowerShell можно перенести In-Place поиск и удерживает их из центра администрирования Exchange. Дополнительные сведения см. в дополнительных сведениях о миграции [устаревших](migrate-legacy-eDiscovery-searches-and-holds.md)поисков по электронной информации и о том, как Центр соответствия требованиям Microsoft 365.

**После того как эти кодлеты будут отменены, смогу ли я удалить или получить поиск?**

Да, хотя мы удаляем возможность создания и изменения поиска, вы все равно сможете использовать **Get-MailboxSearch** и **Remove-MailboxSearch** до дальнейшего уведомления. Однако использование этих cmdlets будет на свой собственный риск после даты выхода на пенсию и Microsoft Support больше не сможет предоставить помощь.

## <a name="search-mailbox-cmdlet"></a>Search-Mailbox cmdlet

В  2018 г. в Exchange Online PowerShell см. в предупреждении, объявленном в выводе cmdlet, который был объявлен в начале 2018 г. Изначально для поиска почтового ящика пользователя и очистки вредоносного контента использовался комлет **Search-Mailbox.** Для поиска и очистки контента рекомендуется начать использовать в Office 365 Security & **PowerShell cmdlets New-ComplianceSearch** и **New-ComplianceSearchAction.** Для встроенной системы безопасности функции [<span class="underline">безопасности</span>](../security/index.yml) Microsoft 365 надежной защиты от угроз для электронной почты и многих других службы Майкрософт.

### <a name="scope-of-affected-organizations"></a>Область затронутых организаций

- Office 365 и Microsoft 365 корпоративный организаций

- Office 365 и Microsoft 365 для образования организаций

- Office 365 и Microsoft 365 государственных организаций; это включает GCC, GCC High и DoD

- Office 365 Germany

### <a name="timeline"></a>Временная шкала

-  1 июля 2020 г.: теперь не будет доступен кодлет **Search-Mailbox,** а поддержка Майкрософт больше не будет предоставлять помощь.

### <a name="alternative-tools"></a>Альтернативные средства

В следующей таблице описываются другие средства, которые можно использовать для замены уже отошедшего функционала.

<table>
<thead>
<tr class="header">
<th>функциональность.</th>
<th>Альтернативные средства</th>
<th>Комментарии</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Поиск почтового ящика</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></a></p></td>
<td><p>Чтобы помочь поиску и экспорту контента, совместно работают между собой cmdlets ComplianceSearch и ComplianceSearchAction. Вы можете создать новый поиск и просмотреть оценку поиска с помощью кодлетов <strong>New-</strong>, <strong>Get-</strong>и <strong>Start-ComplianceSearch.</strong> Затем вы можете использовать команду <strong>New-ComplianceSearchAction-Export</strong> для экспорта результатов поиска. Для загрузки результатов поиска на локальный компьютер вам все равно придется использовать основной инструмент для Центр соответствия требованиям Microsoft 365 поиска.</p></p>
</td>
</tr>
<tr class="even">
<td>Удаление массовой электронной почты из почтового ящика</td>
<td><p><a href="/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes"><span class="underline">Настройка политики архивации и удаления для почтовых ящиков</span></a></p>
<p></p></td>
<td><p>Администраторы могут создать политику архивации и удаления, которая автоматически перемещает элементы в архивный почтовый ящик пользователя и автоматически удаляет элементы из почтового ящика.</p>
</td>
</tr>
<tr class="even">
<td>Копирование результатов поиска в почтовый ящик обнаружения</td>
<td> </td>
<td>Прямой замены этой функции нет, так как она не предоставляет доступ ко всем Microsoft 365 службам. В разделе <strong>*-MailboxSearch cmdlets</strong> см. в разделе FAQs для альтернативных решений. </td>
</tr>
<tr class=odd>
  <td>Копирование сообщений из одного почтового ящика в другой почтовый ящик</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Назначение разрешений почтовому ящику</a></td>
  <td>Чтобы предоставить пользователю доступ к электронной почте другого пользователя (например, когда сотрудник покидает организацию и вам необходимо предоставить другому лицу доступ к электронной почте бывшего сотрудника), мы рекомендуем назначить этому лицу разрешения на доступ к почтовому ящику бывшего сотрудника. Поэтому вместо копирования элементов почтовых ящиков в другой почтовый ящик пользователя или общий почтовый ящик просто назначьте пользователю разрешение на доступ к исходным почтовым ящикам.</td>
</tr>
<tr class=even>
  <td>Очистка сообщений из почтового ящика</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>Для поиска и очистки контента совместно работают комлеты ComplianceSearch и ComplianceSearchAction. Можно создать и запустить поиск с помощью командлетов <strong>New-ComplianceSearch</strong> и <strong>New-ComplianceSearch,</strong> а затем очистить содержимое с помощью команды <strong>New-ComplianceSearchAction -PurgeType.</strong> Дополнительные сведения см. в <a href="/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">публикации Поиск и удаление сообщений.</span></a></p>
</td>
</tr>
<tr class="odd"> 
<td>Очистка сообщений из почтового ящика</td>
<td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Назначение разрешений почтовому ящику</a></td>
<td>Чтобы очистить сообщения от почтового ящика, назначьте администратору разрешения на доступ к почтовому ящику сотрудника. Сообщения могут быть удалены и переработаны по мере необходимости, воспользовавшись встроенными возможностями поиска и просмотра в Outlook.</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Exchange Операции API веб-служб

Эти операции в API Exchange веб-служб используются функцией In-Place eDiscovery & Holds в центре администрирования Exchange и соответствующими **\* cmdlets -MailboxSearch** в Exchange Online PowerShell. Кроме того, они будут отменены в рамках выхода на пенсию других устаревших средств электронного разыскного анализа.

### <a name="scope-of-affected-organizations"></a>Область затронутых организаций

- Office 365 и Microsoft 365 корпоративный организаций

- Office 365 и Microsoft 365 для образования организаций

- Office 365 и Microsoft 365 государственных организаций; это включает GCC, GCC High и DoD

- Office 365 Germany

### <a name="timeline"></a>Временная шкала

- 1 июля 2020 г. Операции GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes и GetHoldOnMailboxes больше не будут доступны, а поддержка Майкрософт больше не будет предоставлять помощь.

## <a name="advanced-ediscovery-v10"></a>Advanced eDiscovery v1.0

Advanced eDiscovery v1.0, которая является версией Advanced eDiscovery, доступной в случае с основными данными об обнаружении электронных данных, нажав кнопку Переключатель на **Advanced eDiscovery,** в настоящее время снята. Его функциональность была заменена новым решением Advanced eDiscovery [в](./ediscovery.md) Центр соответствия требованиям Microsoft 365.

Чтобы определить, использует ли ваша организация Advanced eDiscovery v1.0:

1. Перейдите в [центр Office 365 безопасности & соответствия](https://protection.office.com)требованиям.

2. В левой области навигации Центра & безопасности нажмите кнопку **eDiscovery > eDiscovery** и откройте дело core eDiscovery.

3. Если вы видите **кнопку Переключатель** Advanced eDiscovery, щелкнув ее, вы перейдете к версии 1.0 Advanced eDiscovery, которая в настоящее время отключена. Возможность создания и управления случаями в core eDiscovery не будет затронута. Отключается только возможность добавления и анализа данных Advanced eDiscovery v1.0 (щелкнув **переключатель** Advanced eDiscovery).

Новое решение Advanced eDiscovery в Microsoft 365 (также известное как *Advanced eDiscovery v2.0)* предоставляет все возможности исходного решения, но теперь включает в себя основанный на хранителях подход к идентификации контента в других службах Microsoft 365, сбору этого контента, а затем добавлению его в набор отзывов, где рецензенты могут использовать функции быстрого поиска, меток и аналитики, чтобы помочь отбирать соответствующие документы. Advanced eDiscovery теперь включает улучшенную обработку и родных зрителей для типов файлов Microsoft и [](./supported-filetypes-ediscovery20.md) не Microsoft, полный список типов файлов здесь и поддерживаемые поля метаданных [здесь](./document-metadata-fields-in-advanced-ediscovery.md). Кроме того, новое Advanced eDiscovery предоставляет мощную функцию управления хранением, которая позволяет применять содержимого в различных службах, уведомлять пользователей о держимых и отслеживать ответы хранителя, все в Advanced eDiscovery случае.

Доступ к Advanced eDiscovery 2.0:

1. Перейдите в [Центр соответствия требованиям Microsoft 365](https://compliance.microsoft.com).

2. В левой области навигации Центра соответствия требованиям Microsoft 365 нажмите **Показать все** и выберите **Обнаружение электронных данных > Дополнительно**.

В это время рекомендуется приступить к переходу рабочего процесса по обнаружению электронных Advanced eDiscovery функций. При необходимости можно архивировать Advanced eDiscovery 1.0, экспортировать контент и хранить его в автономном режиме. Несмотря на то, что до 31 декабря 2020 г. вы сможете получить доступ к Advanced eDiscovery v1.0, поддержка Майкрософт не будет предоставляться после 1 октября 2020 г. Дополнительные сведения см. в следующей временной шкале.

### <a name="scope-of-affected-organizations"></a>Область затронутых организаций

- Office 365 и Microsoft 365 корпоративный организаций

- Office 365 и Microsoft 365 для образования организаций

- Office 365 и Microsoft 365 государственных организаций; это включает GCC, GCC High и DoD

- Office 365 Germany

### <a name="timeline"></a>Временная шкала

- 1 июля 2020 г. Вы не сможете создать новые Advanced eDiscovery v1.0.

- 1 октября 2020 г. Вы не сможете добавлять новые данные (подготовка результатов поиска для Advanced eDiscovery) в любые случаи. Вы сможете продолжать работать с данными в существующих случаях на свой собственный риск. Поддержка Майкрософт больше не будет предоставлять помощь. 

- 31 декабря 2020 г. Вы не сможете получить доступ к Advanced eDiscovery 1.0.

### <a name="alternative-tools"></a>Альтернативные средства

Решение [Advanced eDiscovery](./overview-ediscovery-20.md) в Центр соответствия требованиям Microsoft 365.