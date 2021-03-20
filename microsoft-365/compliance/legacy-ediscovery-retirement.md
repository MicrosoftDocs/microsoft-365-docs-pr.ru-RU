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
description: In-Place eDiscovery и In-Place Hold (и соответствующие cmdlets PowerShell) в Exchange Online будут отменены в первой половине 2020 г. Кроме Search-Mailbox и advanced eDiscovery v1.0 в течение того же периода времени также отодвигаются.
ms.openlocfilehash: 48a20b9e73c5379325afb715a86c4945385fd0b9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903609"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>Прекращение поддержки устаревших средств обнаружения электронных данных

> [!IMPORTANT]
> Корпорация Майкрософт оценивает состояние общественного здравоохранения, и мы понимаем, как это влияет на наших клиентов. Мы хотим быть сильными партнерами и ответственными глобальными гражданами. Чтобы облегчить одно из многочисленных проблем, с которыми вы столкнулись, мы замедлим запланированный выход на пенсию для устаревших средств электронного разыскных открытий, описанных в этой статье, на три месяца. **Обновленные даты выхода на пенсию приведены ниже.**

На протяжении многих лет корпорация Майкрософт предоставляла средства для поиска, предварительного просмотра и экспорта контента электронной почты из Exchange Online. Однако эти средства больше не предоставляют эффективный способ поиска контента без Exchange в других службах Microsoft 365, таких как SharePoint Online и Microsoft 365 Groups. Чтобы решить эту проблему, Корпорация Майкрософт предлагает другие средства для поиска электронной информации, которые помогут вам найти широкий выбор контента Microsoft 365. И мы упорно работаем над включением наиболее актуальных и мощных функций по обнаружению электронных данных в центре соответствия [требованиям Microsoft 365.](https://compliance.microsoft.com) Это позволяет организациям отвечать на юридические, внутренние и другие запросы на контент во многих службах Microsoft 365, включая Exchange Online.

В результате этой новой и улучшенной функции по обнаружению электронных данных в центре соответствия требованиям Microsoft 365 мы удаляем следующие функции и функции, связанные с электронным открытием, связанные с поиском контента электронной почты в Exchange Online и Microsoft 365:

- [Открытие электронных данных на месте](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) и удерживает на месте [в](/exchange/security-and-compliance/create-or-remove-in-place-holds) центре администрирования Exchange.

- Комлеты Exchange Online PowerShell, поддерживающие In-Place eDiscovery и In-Place Holds (эти cmdlets совместно идентифицированы как **-MailboxSearch).* Это включает в себя следующие cmdlets:

  - [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](/powershell/module/exchange/stop-mailboxsearch)

  - [Set-MailboxSearch](/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > [Комлеты Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch) и [Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) будут доступны после того, как будут отменены другие cmdlets ****-MailboxSearch*** для того, чтобы вы могли использовать их, чтобы помочь в переходе к другим средствам eDiscovery и удержанию. Однако после определенной даты (приведенной ниже) поддержка Майкрософт больше не будет поддерживать эти два cmdlets.

- Комлет [Search-Mailbox](/powershell/module/exchange/search-mailbox) в Exchange Online PowerShell.

- Следующие операции в API веб-служб Exchange:

   - [GetSearchableMailboxes](/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 Advanced eDiscovery v1.0](./overview-ediscovery-20.md), которая является первой версией advanced eDiscovery, доступ к которой имеется в случае с core eDiscovery в Центре обеспечения безопасности Office 365 & соответствия требованиям. Выход на пенсию advanced eDiscovery v1.0 не влияет на возможность создания и управления делами по обнаружению основных электронных обнаружений.

> [!NOTE]
> Удаляемая функция по обнаружению электронных данных применяется только к облачным версиям Microsoft 365 и Office 365. Функции eDiscovery в локальной версии Exchange и SharePoint будут поддерживаться до дальнейшего уведомления.

В следующих разделах этой статьи представлены рекомендации по каждой удаляемой функции. Эти сведения, включая временные данные и альтернативные средства, которые можно использовать вместо отключаемого средства.

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>In-Place и In-Place в центре администрирования Exchange 

По первоначальному объявлению от 1 июля 2017 г. функция In-Place eDiscovery & Hold в центре администрирования Exchange (EAC) будет отменена. Страница In-Place eDiscovery & в EAC позволяет искать, удерживать и экспортировать контент из Exchange Online. In-Place eDiscovery также позволит скопировать результаты поиска в почтовый ящик обнаружения, чтобы вы или другие менеджеры по обнаружению могли просмотреть контент и сделать его доступным для юридических, нормативных и общедоступных запросов.

Поскольку все эти возможности (за исключением копирования результатов поиска в почтовый ящик обнаружения) теперь доступны в средствах поиска контента, обнаружения электронных данных и расширенных электронных данных в центре соответствия требованиям Microsoft 365 (с улучшенной функциональностью, надежностью и поддержкой широкого спектра служб Microsoft [365),](./microsoft-365-compliance-center.md) рекомендуется как можно скорее приступить к использованию этих средств. Чтобы помочь вам в переходе к другим средствам электронной информации, в таблице ниже перечислены средства, которые можно использовать вместо In-Place и In-Place Hold.

### <a name="scope-of-affected-organizations"></a>Область затронутых организаций

- Организации Office 365 и Microsoft 365 Корпоративные

- Организации Office 365 и Microsoft 365 Education

- Государственные организации Office 365 и Microsoft 365; это включает GCC, GCC High и DoD

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
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Поиск, экспорт и удержание в юридических целях</td>
<td>Основные случаи проверки электронных данных в центре соответствия требованиям Microsoft 365 </td>
<td><p>Использование возможностей основных дел по обнаружению электронных обнаружений обеспечивает функциональный паритет для In-Place и In-Place удерживает. Эта кнопка предоставляет доступ ко следующим командам:</p>
<ul>
<li>
<p>Масштабы поиска до миллионов местоположений</p>
</li>
<li>
<p>Более высокая надежность поиска, экспорта и размещения контента на удержание</p>
</li>
<li>
<p>Поиск контента для Exchange Online, SharePoint Online, OneDrive для бизнеса, Skype для бизнеса, Microsoft Teams, Yammer Groups, Microsoft 365 Groups и другого контента, хранимого в приложениях Office 365</p></li></ul>
</td>
</tr>
<tr class="even">
<td>Удержание для целей хранения</td>
<td>Политики хранения в центре соответствия требованиям Microsoft 365</td>
<td><p>Политики хранения можно использовать для сохранения контента и при желании удалить его по истечении срока хранения. Другие возможности:</p>
<ul>
<li>
<p>Применение политик для всей организации </p>
</li><li>
<p>Применение политик к определенным расположениям контента, таким как Exchange Online, SharePoint Online, OneDrive для бизнеса, Skype для бизнеса, Microsoft Teams и Группы Office 365</p></li>
<li>
<p>Применение политик к конкретным пользователям</p></li></ul>
<p>Дополнительные сведения см. <a href="/microsoft-365/compliance/retention-policies">в дополнительных сведениях о политиках хранения и метки хранения.</a></td>
</tr>
<tr class="odd">
<td>Скопируйте результаты поиска электронной почты в почтовый ящик обнаружения для проверки</td><td>Наборы обзоров в advanced eDiscovery v2.0</td>
<td><p>Просмотр контента в Microsoft 365 никогда не был проще. Наборы обзоров имеют множество возможностей, которые помогут сократить время и данные, необходимые для проверки, в том числе:</p>
<ul>
<li><p>Выполнение быстрых поисковых запросов и фильтрация контента в наборе обзоров</p></li>
<li><p>Анализ контента в наборе обзоров; это включает в себя потоковую отправку электронной почты, почти дубликат обнаружения, анализ тем и прогнозирование кодирования</p></li>
<li><p>Добавление тегов к документам в наборе для проверки</p></li>
<li><p>Пометка предложений, которые помогут определить содержимое клиентских привилегий адвоката</p></li></ul>
<p>Дополнительные сведения см. в статье <a href="/microsoft-365/compliance/overview-ediscovery-20">Обзор решения Advanced eDiscovery в Microsoft 365</a>.</p>
<p>
<p>Кроме того, вы можете экспортировать результаты поиска в PST-файлы, а затем использовать службу Импорта Microsoft 365 для импорта PSTs в почтовый ящик обнаружения. Пошаговая инструкция см. в инструкции Использование сетевой загрузки для <a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">импорта PST-файлов в Office 365.</a>
</tr>
<tr class=even>
  <td>Копирование сообщений из одного почтового ящика в другой почтовый ящик</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Назначение разрешений почтовому ящику</a></td>
  <td>Чтобы предоставить пользователю доступ к электронной почте другого пользователя (например, когда сотрудник покидает организацию и вам необходимо предоставить другому лицу доступ к электронной почте бывшего сотрудника), мы рекомендуем назначить этому лицу разрешения на доступ к почтовому ящику бывшего сотрудника. Поэтому вместо копирования элементов почтовых ящиков в другой почтовый ящик пользователя или общий почтовый ящик просто назначьте пользователю разрешения на доступ к исходным почтовым ящикам.</td>
  
  </tr>
<tr class="odd">
<td>Восстановление элементов из папки "Извлекаемые элементы"</td>
  <td><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>Вы можете восстановить постоянно удаленные элементы <i></i> (также известные как мягкие удаленные элементы) в почтовых ящиках до тех пор, пока срок хранения удаленных элементов для элемента не истек. Дополнительные сведения см. в папке <a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">"Извлекаемые элементы" в Exchange Online.</a></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>FAQs about In-Place eDiscovery and In-Place Holds

**Я использую функции результатов поиска In-Place обнаружения & в EAC для копирования результатов поиска в почтовый ящик обнаружения для проверки адвокатами. Какие возможности у меня есть сейчас?**

Существует два способа репликации этой функции на сегодняшний день. Во-первых, необходимо использовать [наборы обзоров в advanced eDiscovery v2.0.](./view-documents-in-review-set.md) Наборы обзоров имеют множество одинаковых возможностей, которые вы видите в традиционном инструменте проверки, таких как быстрый поиск документов, метки, потоки электронной почты, рядом с дублирующей группировкой, анализ тем и прогностическое кодирование. Если вы по-прежнему хотите использовать почтовые ящики обнаружения для проверки, второй вариант — экспорт результатов поиска в PST-файлы, а затем импорт PST-файлов в почтовый ящик обнаружения с помощью функции [импорта PST](use-network-upload-to-import-pst-files.md) в центре соответствия требованиям Майкрософт.

**Как управлять расположениями контента (например, почтовыми ящиками или сайтами), которые может искать менеджер по обнаружению электронных сообщений с помощью новых средств?**

Центр соответствия требованиям Microsoft 365 также использует границы соответствия требованиям для управления расположениями контента, которые может искать диспетчер по обнаружению электронных данных. [](set-up-compliance-boundaries.md) Границы соответствия требованиям являются полезными для государственных организаций, которые должны находиться в пределах границ учреждений или многонациональных корпораций, необходимых для соблюдения географических границ.

**Как переместить текущий поиск и удерживание в центре соответствия требованиям Microsoft 365?**

С помощью PowerShell можно перенести In-Place поиск и удерживает их из EAC. Инструкции см. в инструкции Перенос поиска и удерживания из Центра обработки данных в Центр соответствия [требованиям Microsoft 365.](./migrate-legacy-ediscovery-searches-and-holds.md)

## <a name="-mailboxsearch-cmdlets"></a>\*-MailboxSearch cmdlets

В первоначальном уведомлении, объявленном 1 июля 2017 г. в центре администрирования Exchange, функция In-Place eDiscovery & Hold и соответствующие **\* cmdlets -MailboxSearch** будут отменены. Эти cmdlets предоставляют пользователям возможность поиска, удержания и экспорта контента почтовых ящиков для юридических, нормативных и общедоступных запросов.

Поскольку эти возможности теперь доступны в центре соответствия требованиям [<span class="underline">Microsoft 365</span>](./microsoft-365-compliance-center.md) и Office 365 & Центре соответствия требованиям PowerShell с улучшенной производительностью и масштабируемостью, следует использовать эти улучшенные команды. Эти cmdlets включают [<span class="underline"> \* -ComplianceCase</span>](/powershell/module/exchange/get-compliancecase), [<span class="underline"> \* -ComplianceSearch</span>](/powershell/module/exchange/get-compliancesearch), [<span class="underline"> \* -CaseHoldPolicy</span>](/powershell/module/exchange/get-caseholdpolicy), [<span class="underline"> \* -CaseHoldRule</span>](/powershell/module/exchange/get-caseholdrule), и [<span class="underline"> \* -ComplianceSearchAction</span>](/powershell/module/exchange/get-compliancesearchaction).

### <a name="scope-of-affected-organizations"></a>Область затронутых организаций

- Организации Office 365 и Microsoft 365 Корпоративные

- Организации Office 365 и Microsoft 365 Education

- Государственные организации Office 365 и Microsoft 365; это включает GCC, GCC High и DoD

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
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Поиск и экспорт</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Чтобы помочь поиску и экспорту контента, совместно работают между собой cmdlets ComplianceSearch и ComplianceSearchAction. Вы можете создать новый поиск и просмотреть оценку поиска с помощью кодлетов <strong>New-</strong>, <strong>Get-</strong>и <strong>Start-ComplianceSearch.</strong> Затем вы можете экспортировать результаты поиска с помощью <strong>cmdlet New-ComplianceSearchAction.</strong> Для загрузки результатов поиска на локальный компьютер вам все равно придется использовать основной инструмент для поиска в центре соответствия требованиям Microsoft 365.</p>
<p>
<p><strong>Примечание:</strong> Если вы используете эти кодлеты для создания поисков, не связанных с основным делом об <strong></strong> обнаружении электронных данных, эти поиски будут размещены на странице поиска контента в центре соответствия требованиям Microsoft 365.</p></td>
</tr>
<tr class="even">
<td>Удержание контента в почтовом ящике</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Удерживание в центре соответствия требованиям Microsoft 365 должно быть связано с complianceCase. Сначала создайте случай соответствия требованиям, а затем создайте CaseHoldPolicy и CaseHoldRule.</p>
<p><strong>Примечание:</strong> Создание CaseHoldPolicy без создания CaseHoldRule сделает удержание неоперабельным до создания CaseHoldRule и его связи с CaseHoldPolicy. Дополнительные сведения см. в документации по cmdlet.</p></td>
</tr>
<tr class="odd">
<td>Копирование результатов поиска в почтовый ящик обнаружения</td>
<td>Нет</td>
<td>Прямой замены этой функции нет, так как она не обеспечивает доступ ко всем службам Microsoft 365. Ниже приведены следующие вопросы по альтернативным решениям.</td>
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

API [<span class="underline">Microsoft Graph</span>](https://developer.microsoft.com/en-us/graph) предоставляют ряд методов для извлечения данных для анализа и других целей, которые гораздо более устойчивы и масштабируемы, чем с помощью **\* cmdlets -MailboxSearch.**

**Как перенести поиск и удерживание в центре соответствия требованиям Microsoft 365?**

С помощью сценария PowerShell можно перенести In-Place поиск и удерживает их из центра администрирования Exchange. Дополнительные сведения см. в дополнительных сведениях о переносе устаревших поисков по электронным данным и о переносе их в центр соответствия [требованиям Microsoft 365.](migrate-legacy-eDiscovery-searches-and-holds.md)

**После того как эти кодлеты будут отменены, смогу ли я удалить или получить поиск?**

Да, хотя мы удаляем возможность создания и изменения поиска, вы все равно сможете использовать **Get-MailboxSearch** и **Remove-MailboxSearch** до дальнейшего уведомления. Однако использование этих cmdlets будет на свой собственный риск после даты выхода на пенсию и Microsoft Support больше не сможет предоставить помощь.

## <a name="search-mailbox-cmdlet"></a>Search-Mailbox cmdlet

В **exchange Online PowerShell** в настоящее время отставку, как было объявлено в предупреждении в выводах cmdlet, начиная с 2018 г. Изначально для поиска почтового ящика пользователя и очистки вредоносного контента использовался комлет **Search-Mailbox.** Для поиска и очистки контента рекомендуется начать использовать в Office 365 & **PowerSearch** и **New-ComplianceSearchAction.** Для встроенной системы безопасности функции [<span class="underline">безопасности Microsoft 365</span>](../security/index.yml) обеспечивают надежную защиту от угроз для электронной почты и многих других служб Майкрософт.

### <a name="scope-of-affected-organizations"></a>Область затронутых организаций

- Организации Office 365 и Microsoft 365 Корпоративные

- Организации Office 365 и Microsoft 365 Education

- Государственные организации Office 365 и Microsoft 365; это включает GCC, GCC High и DoD

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
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Поиск почтового ящика</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></a></p></td>
<td><p>Чтобы помочь поиску и экспорту контента, совместно работают между собой cmdlets ComplianceSearch и ComplianceSearchAction. Вы можете создать новый поиск и просмотреть оценку поиска с помощью кодлетов <strong>New-</strong>, <strong>Get-</strong>и <strong>Start-ComplianceSearch.</strong> Затем вы можете использовать команду <strong>New-ComplianceSearchAction-Export</strong> для экспорта результатов поиска. Для загрузки результатов поиска на локальный компьютер вам все равно придется использовать основной инструмент для поиска в центре соответствия требованиям Microsoft 365.</p></p>
</td>
</tr>
<tr class="even">
<td>Удаление массовой электронной почты из почтового ящика</td>
<td><p><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Настройка политики архивации и удаления для почтовых ящиков</span></a></p>
<p></p></td>
<td><p>Администраторы могут создать политику архивации и удаления, которая автоматически перемещает элементы в архивный почтовый ящик пользователя и автоматически удаляет элементы из почтового ящика.</p>
</td>
</tr>
<tr class="even">
<td>Копирование результатов поиска в почтовый ящик обнаружения</td>
<td> </td>
<td>Прямой замены этой функции нет, так как она не обеспечивает доступ ко всем службам Microsoft 365. В разделе <strong>*-MailboxSearch cmdlets</strong> см. в разделе FAQs для альтернативных решений. </td>
</tr>
<tr class=odd>
  <td>Копирование сообщений из одного почтового ящика в другой почтовый ящик</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Назначение разрешений почтовому ящику</a></td>
  <td>Чтобы предоставить пользователю доступ к электронной почте другого пользователя (например, когда сотрудник покидает организацию и вам необходимо предоставить другому лицу доступ к электронной почте бывшего сотрудника), мы рекомендуем назначить этому лицу разрешения на доступ к почтовому ящику бывшего сотрудника. Поэтому вместо копирования элементов почтовых ящиков в другой почтовый ящик пользователя или общий почтовый ящик просто назначьте пользователю разрешения на доступ к исходным почтовым ящикам.</td>
</tr>
<tr class=even>
  <td>Очистка сообщений из почтового ящика</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>Для поиска и очистки контента совместно работают комлеты ComplianceSearch и ComplianceSearchAction. Можно создать и запустить поиск с помощью командлетов <strong>New-ComplianceSearch</strong> и <strong>New-ComplianceSearch,</strong> а затем очистить содержимое с помощью команды <strong>New-ComplianceSearchAction -PurgeType.</strong> Дополнительные сведения см. в <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">публикации Поиск и удаление сообщений.</span></a></p>
</td>
</tr>
<tr class="odd"> 
<td>Очистка сообщений из почтового ящика</td>
<td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Назначение разрешений почтовому ящику</a></td>
<td>Чтобы очистить сообщения от почтового ящика, назначьте администратору разрешения на доступ к почтовому ящику сотрудника. Сообщения могут быть удалены и переработаны по мере необходимости, воспользовавшись встроенными возможностями поиска и просмотра в Outlook.</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Операции API API веб-служб Exchange

Эти операции в API веб-служб Exchange используются функцией In-Place eDiscovery & Holds в центре администрирования Exchange и соответствующими **\* cmdlets -MailboxSearch** в Exchange Online PowerShell. Кроме того, они будут отменены в рамках выхода на пенсию других устаревших средств электронного разыскного анализа.

### <a name="scope-of-affected-organizations"></a>Область затронутых организаций

- Организации Office 365 и Microsoft 365 Корпоративные

- Организации Office 365 и Microsoft 365 Education

- Государственные организации Office 365 и Microsoft 365; это включает GCC, GCC High и DoD

- Office 365 Germany

### <a name="timeline"></a>Временная шкала

- 1 июля 2020 г. Операции GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes и GetHoldOnMailboxes больше не будут доступны, а поддержка Майкрософт больше не будет предоставлять помощь.

## <a name="advanced-ediscovery-v10"></a>Advanced eDiscovery v1.0

Advanced eDiscovery v1.0, которая является версией advanced eDiscovery, доступной в случае с основными данными об обнаружении электронных данных, нажав кнопку Переключатель на **advanced eDiscovery,** уходит в отставку. Его функции были заменены новым решением [advanced eDiscovery](./ediscovery.md) в центре соответствия требованиям Microsoft 365.

Чтобы определить, использует ли ваша организация advanced eDiscovery v1.0:

1. Перейдите в Центр безопасности [Office 365 & соответствия](https://protection.office.com)требованиям.

2. В левой области навигации Центра & безопасности нажмите кнопку **eDiscovery > eDiscovery** и откройте дело core eDiscovery.

3. Если вы видите кнопку **Switch to Advanced eDiscovery,** щелкнув ее, вы перейдете к версии 1.0 advanced eDiscovery, которая в настоящее время отменена. Возможность создания и управления случаями в core eDiscovery не будет затронута. В advanced eDiscovery v1.0 (щелкнув переключатель на **advanced eDiscovery)** отключается только возможность добавления и анализа данных о случаях.

Новое решение advanced eDiscovery в Microsoft 365 (также известное как *Advanced eDiscovery v2.0)* предоставляет все возможности исходного решения, но теперь включает в себя основанный на хранителях подход к идентификации контента в других службах Microsoft 365, сбору этого контента, а затем добавлению его в набор отзывов, где рецензенты могут использовать быстрые поисковые запросы, метки и функции аналитики, чтобы помочь отбирать соответствующие документы. Advanced eDiscovery now includes improved processing and native viewers for both Microsoft and non-Microsoft file types, a full list of file types is [here](./supported-filetypes-ediscovery20.md) and supported metadata fields [are here.](./document-metadata-fields-in-advanced-ediscovery.md) Кроме того, новое решение advanced eDiscovery предоставляет мощную функцию управления хранением, которая позволяет применять содержимого в различных службах, уведомлять пользователей о держимых и отслеживать ответы хранителя, все в случае расширенных электронных данных.

Чтобы получить доступ к advanced eDiscovery v2.0:

1. Перейдите в [центр соответствия требованиям Microsoft 365.](https://compliance.microsoft.com)

2. В левой области навигации Центра соответствия требованиям Microsoft 365 нажмите кнопку **Показать** все, а затем нажмите **кнопку eDiscovery > Advanced**.

В это время рекомендуется приступить к переходу рабочего процесса по обнаружению электронных обнаружений на новую функцию advanced eDiscovery. При необходимости можно заархивировать дела Advanced eDiscovery 1.0, экспортировать контент и хранить его в автономном режиме. Несмотря на то, что до 31 декабря 2020 г. вы сможете получить доступ к advanced eDiscovery v1.0, поддержка Майкрософт не будет предоставляться после 1 октября 2020 г. Дополнительные сведения см. в следующей временной шкале.

### <a name="scope-of-affected-organizations"></a>Область затронутых организаций

- Организации Office 365 и Microsoft 365 Корпоративные

- Организации Office 365 и Microsoft 365 Education

- Государственные организации Office 365 и Microsoft 365; это включает GCC, GCC High и DoD

- Office 365 Germany

### <a name="timeline"></a>Временная шкала

- 1 июля 2020 г. Вы не сможете создать новые случаи advanced eDiscovery v1.0.

- 1 октября 2020 г. Вы не сможете добавлять новые данные (подготовка результатов поиска для предварительного поиска электронных данных) в любые случаи. Вы сможете продолжать работать с данными в существующих случаях на свой собственный риск. Поддержка Майкрософт больше не будет предоставлять помощь. 

- 31 декабря 2020 г. Вы не сможете получить доступ к делам Advanced eDiscovery v1.0.

### <a name="alternative-tools"></a>Альтернативные средства

Решение [advanced eDiscovery](./overview-ediscovery-20.md) в центре соответствия требованиям Microsoft 365.