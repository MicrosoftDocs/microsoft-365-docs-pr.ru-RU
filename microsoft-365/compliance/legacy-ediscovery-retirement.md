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
description: Обнаружение электронных данных на месте и удержание на месте (и соответствующие командлеты PowerShell) в Exchange Online будут отменены в первой половине 2020. Командлет Search – Mailbox и Advanced eDiscovery версии 1.0 также удаляются за один и тот же период времени.
ms.openlocfilehash: 48dbbd86071f8b07fa3dbf3a699f0d7e085fd50b
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943348"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>Прекращение поддержки устаревших средств обнаружения электронных данных

> [!IMPORTANT]
> Корпорация Майкрософт оценивает ситуацию с общественностью о работоспособности, и мы понимаем, что у наших клиентов возникли проблемы. Мы хотим быть надежными партнерами и ответственными глобальными гражданами. Чтобы упростить одну из многочисленных накладных расходов, мы будем отложить запланированное выбытие для стандартных средств обнаружения электронных данных, описанных в этой статье, на три месяца. **Обновленные даты выбытия показаны ниже.**

В течение нескольких лет корпорация Майкрософт предоставила средства обнаружения электронных данных, которые позволяют выполнять поиск, предварительный просмотр и экспорт содержимого электронной почты из Exchange Online. Тем не менее, эти средства не предоставляют эффективный способ поиска контента, не относящегося к Exchange, в других службах Microsoft 365, таких как группы SharePoint Online и Microsoft 365. Для решения этой вопросы Корпорация Майкрософт предлагает другие средства обнаружения электронных данных, которые помогают искать широкий спектр содержимого Microsoft 365. Мы работаем над внедрением самых последних и мощных функций обнаружения электронных [данных в центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com). Это позволяет организациям отвечать на юридические, внутренние и другие запросы на документы для контента во многих службах Microsoft 365, в том числе Exchange Online.

В результате этой новой и улучшенной функции обнаружения электронных данных в центре соответствия требованиям Microsoft 365 мы проделам следующие функции, связанные с обнаружением электронных данных, и функциональные возможности, связанные с поиском сообщений электронной почты в Exchange Online и Microsoft 365:

- [Обнаружение электронных](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) данных на месте и [удержание на месте](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) в центре администрирования Exchange.

- Командлеты Exchange Online PowerShell, поддерживающие обнаружение электронных данных на месте и удержания на месте (эти командлеты обозначаются как командлеты **-MailboxSearch* ). К ним относятся следующие командлеты:

  - [New — MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-mailboxsearch)

  - [Start — MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-mailboxsearch)

  - [Stop — MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/stop-mailboxsearch)

  - [Set — MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-mailboxsearch)

   > [!NOTE]
   > Командлеты [Get – MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-mailboxsearch) и [retired – MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/remove-mailboxsearch) будут доступны после снятия других командлетов * * * * * * * *, чтобы их можно было использовать для перехода к другим средствам обнаружения и удержания. Однако после определенной даты (указанная ниже) служба поддержки Майкрософт больше не будет поддерживать эти два командлета.

- Командлет [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/search-mailbox?view=exchange-ps) в Exchange Online PowerShell.

- Следующие операции в API веб-служб Exchange:

   - [GetSearchableMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 Advanced eDiscovery 1.0](office-365-advanced-ediscovery.md), которая является первой версией расширенного обнаружения электронных данных, доступ к которым осуществляется с помощью основного случая обнаружения электронных данных в центре безопасности & соответствия требованиям Office 365. Выбытие расширенного обнаружения электронных данных версии 1.0 не влияет на возможность создания и управления основными случаями обнаружения электронных данных.

> [!NOTE]
> Функция обнаружения электронных данных применяется только к облачным версиям Microsoft 365 и Office 365. функции обнаружения электронных данных в локальных версиях Exchange и SharePoint по-прежнему будут поддерживаться до появления дальнейших уведомлений.

В следующих разделах этой статьи приведены рекомендации по каждой из функций, которые будут отменены. Эти сведения, в том числе временные шкалы и альтернативные инструменты, которые можно использовать вместо неотмененного средства.

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>Обнаружение электронных данных на месте и удержание на месте в центре администрирования Exchange 

По мере первоначального объявления 1 июля 2017 в центре администрирования Exchange отключена функция удержания & обнаружения электронных данных на месте. Страница "& обнаружения электронных данных на месте" в центре администрирования Exchange позволяла искать, хранить и экспортировать контент из Exchange Online. Обнаружение электронных данных на месте также позволяет скопировать результаты поиска в почтовый ящик найденных сообщений, чтобы вы или другие менеджеры по обнаружению электронных данных могли просмотреть контент и сделать его доступным для юридических, законодательных и общедоступных запросов.

Так как все эти возможности (за исключением копирования результатов поиска в почтовый ящик найденных сообщений) теперь доступны в центре обеспечения соответствия требованиям и расширенных средствах обнаружения электронных данных в [центре соответствия требованиям microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) (с улучшенными функциональными возможностями, надежностью и поддержкой широкого спектра служб Microsoft 365), рекомендуется приступить к работе с этими средствами как можно скорее. В приведенной ниже таблице перечислены инструменты, которые можно использовать вместо обнаружения электронных данных на месте и хранения на месте.

### <a name="scope-of-affected-organizations"></a>Область затронутых организаций

- Office 365 и Microsoft 365 корпоративный Организации

- Организации Office 365 и Microsoft 365 для образования

- Office 365 и Microsoft 365 правительственные организации; в том числе GCC, GCC High и DoD

- Office 365 Germany

### <a name="timeline-for-retirement"></a>Временная шкала для выбытия

- 1 июля 2020 г.: вы не сможете создавать новые операции поиска и удержания, но вы можете выполнять, редактировать и удалять существующие поисковые запросы на свой риск. Служба поддержки Майкрософт больше не будет хранить & обнаружения электронных данных на месте в центре администрирования Exchange.

- 1 октября 2020 г.: & обнаружения электронных данных на месте хранит функции в центре администрирования Exchange, предназначенные только для чтения. Это означает, что вы можете только удалять существующие поисковые запросы и удержания.

### <a name="alternative-tools"></a>Альтернативные инструменты

В следующей таблице описаны другие средства, которые можно использовать для замены существующих функций, которые будут отменены.

<table>
<thead>
<tr class="header">
<th><strong>Функция</strong></th>
<th><strong>Альтернативное средство</strong></th>
<th><strong>Comments</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Поиск, экспорт и удержание для юридических целей</td>
<td>Основные случаи обнаружения электронных данных в центре соответствия требованиям Microsoft 365 </td>
<td><p>Использование возможностей базовых случаев обнаружения электронных данных обеспечивает функциональную четность для обнаружения электронных данных на месте и удержания на месте. Эта кнопка предоставляет доступ ко следующим командам:</p>
<ul>
<li>
<p>Поиск с масштабированием до миллионов расположений</p>
</li>
<li>
<p>Повышенная надежность поиска, экспорта и размещения содержимого на удержании</p>
</li>
<li>
<p>Поиск контента в Exchange Online, SharePoint Online, OneDrive для бизнеса, Skype для бизнеса, Microsoft Teams, группы Yammer, Microsoft 365, а также другие материалы, хранящиеся в приложениях Office 365</p></li></ul>
<p>Дополнительные сведения: <a href="https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations">Управление юридическими исследованиями в Office 365</a>.</td>
</tr>
<tr class="even">
<td>Хранение для целей хранения</td>
<td>Политики хранения в центре соответствия требованиям Microsoft 365</td>
<td><p>Вы можете использовать политики хранения для хранения контента и при необходимости удалять его по истечении срока хранения. К другим возможностям относятся:</p>
<ul>
<li>
<p>Применение политик ко всей Организации </p>
</li><li>
<p>Применение политик к определенным расположениям контента, например Exchange Online, SharePoint Online, OneDrive для бизнеса, Skype для бизнеса, Microsoft Teams и Office 365 Groups</p></li>
<li>
<p>Применение политик к определенным пользователям</p></li></ul>
<p>Для получения дополнительных сведений см раздел <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies">Обзор политик хранения</a>.</td>
</tr>
<tr class="odd">
<td>Копирование результатов поиска по электронной почте в почтовый ящик обнаружения для просмотра</td><td>Обзор наборов в Advanced eDiscovery версии 2.0</td>
<td><p>Просмотр содержимого в Microsoft 365 никогда не было проще. В наборах рецензирования существует множество замечательных возможностей для сокращения времени и данных, необходимых для проверки, в том числе:</p>
<ul>
<li><p>Выполнение запросов FAST Search и фильтрация содержимого в наборе рецензирования</p></li>
<li><p>Анализ контента в наборе рецензирования; Это включает почтовые потоки, обнаружение почти повторяющихся элементов, анализ тем и прогнозирование кода.</p></li>
<li><p>Добавление тегов к документам в наборе для проверки</p></li>
<li><p>Рекомендации по разметке для определения содержимого полномочий клиента юриста</p></li></ul>
<p>Дополнительные сведения см. в статье <a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Обзор решения Advanced eDiscovery в Microsoft 365</a>.</p>
<p>
<p>Кроме того, вы можете экспортировать результаты поиска в PST-файлы и затем использовать службу импорта Microsoft 365 для импорта PST-файлов в почтовый ящик найденных сообщений. Пошаговые инструкции приведены <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">в разделе Использование отправки по сети для импорта PST-файлов в Office 365</a>.
</tr>
<tr class=even>
  <td>Копирование сообщений из одного почтового ящика в другой</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Назначение разрешений для почтового ящика</a></td>
  <td>Чтобы предоставить пользователю доступ к электронной почте другого пользователя (например, когда сотрудник покидает организацию и вам нужно предоставить другому человеку доступ к электронной почте бывшего сотрудника), мы рекомендуем назначить ему разрешения на доступ к почтовому ящику бывшего сотрудника. Поэтому вместо того чтобы копировать элементы почтового ящика в другой почтовый ящик пользователя или в общий почтовый ящик, просто Назначьте разрешения пользователя на доступ к исходному почтовому ящику.</td>
  
  </tr>
<tr class="odd">
<td>Восстановление элементов из папки "элементы с возможностью восстановления"</td>
  <td><a href="https://docs.microsoft.com/powershell/module/exchange/mailboxes/Restore-RecoverableItems">Restore — RecoverableItems</td>
  <td>Вы можете восстановить в почтовых ящиках навсегда удаленные элементы (также называемые <i>обратимыми</i> элементами), если срок хранения удаленных элементов для элемента не истек. Дополнительные сведения см. <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">в папке "элементы с возможностью восстановления" в Exchange Online</a>.</td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>Вопросы и ответы об обнаружении электронных данных на месте и удержания на месте

**Я использую функцию копирования результатов поиска обнаружения электронных данных на месте & хранящихся в центре администрирования Exchange, чтобы скопировать результаты поиска в почтовый ящик найденных юристов. Какие параметры теперь у меня есть?**

Существует два способа репликации этих функций сегодня. Во-первых, используйте [наборы проверки в Advanced eDiscovery версии 2.0](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set). Для рецензирования наборов доступны многие возможности традиционного просмотра, такие как быстрый поиск документов, маркировка, почтовые потоки, появление дублирующихся групп, анализ тем и прогнозирование кода. Если вы все равно хотите использовать почтовые ящики обнаружения для проверки, второй вариант — экспортировать результаты поиска в PST-файлы, а затем импортировать их в почтовый ящик найденных файлов с помощью [функции импорта PST](use-network-upload-to-import-pst-files.md) -файлов в центре соответствия требованиям корпорации Майкрософт.

**Как контролировать, какие расположения контента (например, почтовые ящики или сайты) могут ли осуществлять поиск в диспетчере обнаружения электронных данных с помощью новых средств?**

Центр соответствия требованиям Microsoft 365 также использует [границы соответствия требованиям](set-up-compliance-boundaries.md) для управления расположением содержимого, которое может выполнять диспетчер обнаружения электронных данных. Ограничения на соответствие требованиям используются в правительственных учреждениях, которые должны оставаться в пределах границ органов или многоязычных компаний, необходимых для использования географических плат.

**Как переместить текущие операции поиска и удержания в центр соответствия требованиям Microsoft 365?**

Можно перенести поиск с обнаружением электронных данных на месте и удержания из центра администрирования Exchange с помощью PowerShell. Инструкции можно найти в разделе [Миграция поиска и удержание из центра администрирования Exchange в центр соответствия требованиям Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2114224).

## <a name="-mailboxsearch-cmdlets"></a>\*Командлеты MailboxSearch

Согласно исходному уведомлению 1 июля 2017 в центре администрирования Exchange функция хранения & обнаружения электронных данных на месте, а также командлеты, соответствующие ** \*** командлетам MailboxSearch, будут отменены. Эти командлеты предоставляют пользователям возможность поиска, хранения и экспорта содержимого почтовых ящиков для юридических, законодательных и общедоступных запросов.

Так как эти возможности теперь доступны в [<span class="underline">центре соответствия требованиям Microsoft 365</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) и Office 365 & безопасности в PowerShell с повышенной производительностью и масштабируемостью, следует использовать эти усовершенствованные командлеты. Эти командлеты включают [<span class="underline"> \*— ComplianceCase</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase), [<span class="underline"> \*ComplianceSearch</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch), [<span class="underline"> \*– caseholdpolicy позволяет</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy), [<span class="underline"> \*caseholdrule позволяет</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule) [<span class="underline"> \*и ComplianceSearchAction</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction).

### <a name="scope-of-affected-organizations"></a>Область затронутых организаций

- Office 365 и Microsoft 365 корпоративный Организации

- Организации Office 365 и Microsoft 365 для образования

- Office 365 и Microsoft 365 правительственные организации; в том числе GCC, GCC High и DoD

- Office 365 Germany

### <a name="timeline"></a>Временная шкала

- 1 июля 2020 г.: вы не сможете использовать командлет **New-MailboxSearch** для создания новых поисков на месте и удержания на месте, но вы по-прежнему можете использовать командлеты для запуска, изменения и удаления существующих поисков и удержания на вашем собственном риске. Служба поддержки Майкрософт больше не будет предоставлять помощь для таких типов поиска и удержаний.

- 1 октября 2020 г.,: как было сказано ранее, функции обнаружения & электронных данных на месте в центре администрирования Exchange на месте будут размещены в режиме только для чтения. Это также означает, что вы не сможете использовать командлеты **New – MailboxSearch**, **Start MailboxSearch**или **Set/MailboxSearch** . Вы сможете получать и удалять существующие поисковые запросы и удержания.

### <a name="alternative-tools"></a>Альтернативные инструменты

В следующей таблице описаны другие средства, которые можно использовать для замены существующих функций, которые будут отменены.

<table>
<thead>
<tr class="header">
<th><strong>Функция</strong></th>
<th><strong>Альтернативные инструменты</strong></th>
<th><strong>Comments</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Поиск и экспорт</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch"><span class="underline">* — ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction"><span class="underline">* — ComplianceSearchAction</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">* — ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Командлеты ComplianceSearch и ComplianceSearchAction работают вместе, чтобы упростить поиск и экспорт контента. Вы можете создать новый поиск и просмотреть оценку поиска с помощью командлетов <strong>New</strong>, <strong>Get</strong>и <strong>Start – ComplianceSearch</strong> . Затем вы можете использовать командлет <strong>New – ComplianceSearchAction</strong> для экспорта результатов поиска. Чтобы скачать результаты поиска на локальный компьютер, вам по-прежнему придется использовать основное средство обнаружения электронных данных в центре соответствия требованиям Microsoft 365.</p>
<p>
<p><strong>Примечание:</strong> При использовании этих командлетов для создания поисковых запросов, не связанных с основным вариантом обнаружения электронных данных, эти запросы будут отображаться на странице " <strong>Поиск контента</strong> " в центре соответствия требованиям Microsoft 365.</p></td>
</tr>
<tr class="even">
<td>Удержание контента в почтовом ящике</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy"><span class="underline">* — Caseholdpolicy позволяет</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule"><span class="underline">* — Caseholdrule позволяет</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">* — ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Удержания в центре соответствия требованиям Microsoft 365 должны быть связаны с ComplianceCase. Сначала создайте регистр соответствия требованиям, а затем создайте Caseholdpolicy позволяет и Caseholdrule позволяет.</p>
<p><strong>Примечание:</strong> Создание Caseholdpolicy позволяет без создания Caseholdrule позволяет будет отрисовывать неработоспособное удержание, пока не будет создано Caseholdrule позволяет и не сопоставлено с Caseholdpolicy позволяет. Для получения дополнительных сведений обратитесь к документации по командлетам.</p></td>
</tr>
<tr class="odd">
<td>Копирование результатов поиска в почтовый ящик обнаружения</td>
<td>Нет</td>
<td>Для этой функции нет прямого замены, так как он не предоставляет доступ ко всем службам Microsoft 365. Ниже приведены вопросы и ответы по альтернативным решениям.</td>
</tr>
  <tr class=even>
  <td>Копирование сообщений из одного почтового ящика в другой</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Назначение разрешений для почтового ящика</a></td>
  <td>Чтобы предоставить пользователю доступ к электронной почте другого пользователя (например, когда сотрудник покидает организацию и вам нужно предоставить другому человеку доступ к электронной почте бывшего сотрудника), мы рекомендуем назначить ему разрешения на доступ к почтовому ящику бывшего сотрудника. Поэтому вместо того чтобы копировать элементы почтового ящика в другой почтовый ящик пользователя или в общий почтовый ящик, просто Назначьте разрешения пользователя на доступ к исходному почтовому ящику.</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>Вопросы и ответы о командлетах ***– MailboxSearch**

**Мы используем копию Поиск для экспорта сообщений электронной почты или мгновенных сообщений в целях других eDiscovery и судебного исследования. Какие еще варианты существуют после прекращения действия этих командлетов?**

[<span class="underline">API Microsoft Graph</span>](https://developer.microsoft.com/en-us/graph) предоставляют ряд методов для извлечения данных для анализа и других целей, которые являются более гибкими и масштабируемыми по сравнению с использованием командлетов ** \*-MailboxSearch** .

**Как перенести Поиск и удержания в центр соответствия требованиям Microsoft 365?**

Можно перенести поиск с обнаружением электронных данных на месте и удержания из центра администрирования Exchange с помощью сценария PowerShell. Дополнительные сведения см. [в статье миграция стандартных поисков электронных данных и удержаний в центр соответствия требованиям Microsoft 365](migrate-legacy-eDiscovery-searches-and-holds.md).

**Когда командлеты будут отменены, можно ли удалить или получить Поиск?**

Да, несмотря на то что мы удаляем возможность создавать и изменять поисковые запросы, вы по-прежнему можете использовать командлеты **Get-MailboxSearch** и **Remove-MailboxSearch** , пока не получите дальнейшие уведомления. Тем не менее, использование этих командлетов будет иметь ответственность за то, что после завершения сроков выбытия и поддержки Майкрософт больше не сможет предоставить помощь.

## <a name="search-mailbox-cmdlet"></a>Командлет Search — Mailbox

Командлет **Search-Mailbox** в Exchange Online PowerShell отменяется из-за того, что в выходных данных командлета, начинающегося с начала, выводится предупреждение, начинающееся с 2018. Командлет **Search — Mailbox** изначально использовался для поиска в почтовом ящике пользователя и очистки вредоносного контента. Для поиска и очистки контента рекомендуется начать с использования командлетов **New – ComplianceSearch** и **New ComplianceSearchAction** в Office 365 & Security. PowerShell центра соответствия требованиям. Для встроенного интерфейса безопасности [<span class="underline">функции microsoft 365 Security</span>](https://docs.microsoft.com/microsoft-365/security/) обеспечивают надежную защиту от угроз для электронной почты и многих других служб Майкрософт.

### <a name="scope-of-affected-organizations"></a>Область затронутых организаций

- Office 365 и Microsoft 365 корпоративный Организации

- Организации Office 365 и Microsoft 365 для образования

- Office 365 и Microsoft 365 правительственные организации; в том числе GCC, GCC High и DoD

- Office 365 Germany

### <a name="timeline"></a>Временная шкала

-  1 июля 2020 г.: командлет **Search — Mailbox** больше не будет доступен, и служба поддержки Майкрософт больше не будет предоставлять помощь.

### <a name="alternative-tools"></a>Альтернативные инструменты

В следующей таблице описаны другие средства, которые можно использовать для замены существующих функций, которые будут отменены.

<table>
<thead>
<tr class="header">
<th><strong>Функция</strong></th>
<th><strong>Альтернативные инструменты</strong></th>
<th><strong>Comments</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Поиск в почтовом ящике</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">* — ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">* — ComplianceSearchAction</span></a></p>
<p></a></p></td>
<td><p>Командлеты ComplianceSearch и ComplianceSearchAction работают вместе, чтобы упростить поиск и экспорт контента. Вы можете создать новый поиск и просмотреть оценку поиска с помощью командлетов <strong>New</strong>, <strong>Get</strong>и <strong>Start – ComplianceSearch</strong> . Затем вы можете использовать команду <strong>New – ComplianceSearchAction – Export</strong> , чтобы экспортировать результаты поиска. Чтобы скачать результаты поиска на локальный компьютер, вам по-прежнему придется использовать основное средство обнаружения электронных данных в центре соответствия требованиям Microsoft 365.</p></p>
</td>
</tr>
<tr class="even">
<td>Удаление сообщений из почтового ящика</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">* — ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">* — ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>Командлеты ComplianceSearch и ComplianceSearchAction работают вместе, чтобы упростить поиск и очистку контента. Вы можете создавать и запускать поиск с помощью командлетов <strong>New – ComplianceSearch</strong> и <strong>New ComplianceSearch</strong> , а затем удалять содержимое можно с помощью команды <strong>New – ComplianceSearchAction/</strong> unpurgetype определяет. Дополнительные сведения см. в статье <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Поиск и удаление сообщений</span></a>.</p>
</td>
</tr>
<tr class="odd">
<td>Удаление групповых сообщений электронной почты из почтового ящика</td>
<td><p><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Настройка политики архивации и удаления для почтовых ящиков</span></a></p>
<p></p></td>
<td><p>Администраторы могут создать политику архивации и удаления, которая автоматически перемещает элементы в архивный почтовый ящик пользователя и автоматически удаляет элементы из почтового ящика.</p>
</td>
</tr>
<tr class="even">
<td>Копирование результатов поиска в почтовый ящик обнаружения</td>
<td> </td>
<td>Для этой функции нет прямого замены, так как он не предоставляет доступ ко всем службам Microsoft 365. Альтернативные решения можно найти в разделе вопросы и ответы в разделе <strong>командлетов * – MailboxSearch</strong> . </td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Операции API веб-служб Exchange

Эти операции в API веб-служб Exchange используются функцией обнаружения электронных данных на месте & хранения в центре администрирования Exchange и соответствующих ** \*командлетов-MailboxSearch** в Exchange Online PowerShell. Они также будут отключены в ходе снятия других средств обнаружения электронных данных.

### <a name="scope-of-affected-organizations"></a>Область затронутых организаций

- Office 365 и Microsoft 365 корпоративный Организации

- Организации Office 365 и Microsoft 365 для образования

- Office 365 и Microsoft 365 правительственные организации; в том числе GCC, GCC High и DoD

- Office 365 Germany

### <a name="timeline"></a>Временная шкала

- 1 июля 2020: операции GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes и GetHoldOnMailboxes больше не будут доступны, и служба поддержки Майкрософт больше не будет предоставлять помощь.

## <a name="advanced-ediscovery-v10"></a>Расширенное обнаружение электронных данных v 1.0

Advanced eDiscovery 1.0, которая является версией расширенного обнаружения электронных данных в базовом варианте обнаружения электронных данных путем нажатия кнопки **переключиться на расширенный режим обнаружения электронных**данных, будет снят. Его функции заменены новым [расширенным решением обнаружения электронных](https://aka.ms/edisco) данных в центре соответствия требованиям Microsoft 365.

Чтобы определить, использует ли ваша организация Расширенное обнаружение электронных данных версии 1.0:

1. Перейдите в [Центр обеспечения безопасности & Office 365](https://protection.office.com).

2. В левой области навигации центра & соответствия требованиям безопасности щелкните **Обнаружение электронных данных > обнаружения электронных**данных и откройте основное дело обнаружения электронных данных.

3. Если вы видите кнопку **Advanced eDiscovery (Advanced eDiscovery** ), то она попытается перейти в 1,0 версию Advanced eDiscovery, которая будет удалена. Возможность создания и управления обращениями в ядре обнаружения электронных данных не затрагивается. Отменяется только возможность добавлять и анализировать данные о делах в Advanced eDiscovery версии 1.0 (нажав кнопку **переключиться на Advanced eDiscovery**).

Новое решение для обнаружения электронных данных в Microsoft 365 (также известное как *Advanced eDiscovery 2.0*) предоставляет все возможности исходного решения, но теперь включает основанный на хранитель подход к идентификации контента в других службах Microsoft 365, сбор этого содержимого и добавление его в набор рецензирования, в котором рецензенты могут использовать преимущества запросов FAST Search, маркировки и анализа, чтобы помочь отключать важные документы. Расширенное обнаружение электронных данных теперь включает в себя улучшенную обработку и собственные средства просмотра для типов файлов Майкрософт и других типов, [здесь](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) перечислены все типы файлов, а также поля, поддерживаемые в [метаданных.](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery) Кроме того, новое расширенное решение обнаружения электронных данных предоставляет мощную функцию управления хранитель, которая позволяет применять удержания к содержимому в различных службах, уведомлять пользователей о удержаниях и отслеживать ответы хранитель, все в рамках расширенного случая обнаружения электронных данных.

Для доступа к расширенной функции обнаружения электронных данных версии 2.0:

1. Перейдите в [центр соответствия требованиям Microsoft 365](https://compliance.microsoft.com).

2. В левой области навигации центра соответствия требованиям Microsoft 365 щелкните **Показать все**, а затем выберите **> обнаружения электронных**данных.

В настоящее время мы рекомендуем начать перевод рабочего процесса обнаружения электронных данных на новые расширенные функции обнаружения электронных данных. Несмотря на то что вы по-прежнему можете получать доступ к Advanced eDiscovery версии 1.0 в существующих случаях, поддержка Майкрософт не обеспечивает поддержку после 1 октября 2020 г. Для получения дополнительных сведений посетите следующую временную шкалу.

### <a name="scope-of-affected-organizations"></a>Область затронутых организаций

- Office 365 и Microsoft 365 корпоративный Организации

- Организации Office 365 и Microsoft 365 для образования

- Office 365 Germany

### <a name="timeline"></a>Временная шкала

- 1 июля 2020 г.: вы не сможете создавать новые расширенные варианты обнаружения электронных данных версии 1.0.

- 1 октября 2020 г.: в любые случаи невозможно добавить новые данные (подготовьте результаты поиска для расширенного обнаружения электронных данных). Вы сможете продолжать работу с данными в существующих случаях на свой риск. Служба поддержки Майкрософт больше не будет предоставлять помощь. 

### <a name="alternative-tools"></a>Альтернативные инструменты

[Расширенное решение обнаружения электронных](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) данных в центре соответствия требованиям Microsoft 365.