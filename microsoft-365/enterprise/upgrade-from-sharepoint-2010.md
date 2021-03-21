---
title: Переход с SharePoint 2010
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/13/2020
audience: ITPro
ms.topic: conceptual
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- WSU140
- OSU140
ms.assetid: 985a357f-6db7-401f-bf7a-1bafdf1f312c
f1.keywords:
- NOCSH
description: Поиск сведений и ресурсов для обновления с SharePoint 2010 и Sharepoint Server 2010. Поддержка для обеих сторон заканчивается 13 апреля 2021 г.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4fa82fb0e382a244cdc126609ac62d17280b9702
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925336"
---
# <a name="upgrading-from-sharepoint-2010"></a>Переход с SharePoint 2010

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Microsoft SharePoint 2010 и SharePoint Server 2010 достигнут конца поддержки **13 апреля 2021 г.** В этой статье данная статья предоставляет ресурсы для переноса существующих данных SharePoint Server 2010 в SharePoint Online в Microsoft 365 или обновления локальной среды SharePoint Server 2010.

## <a name="what-is-end-of-support"></a>Чем *заканчивается поддержка?*

Большинство продуктов Майкрософт имеют жизненный цикл поддержки, в ходе которого они получают новые функции, исправления ошибок, исправления безопасности и так далее. После даты окончания поддержки продукт не перестает работать, но Microsoft больше не предоставляет:

- Техническая поддержка проблем, которые могут возникнуть.

- Ошибка устраняет проблемы, которые могут повлиять на стабильность и доступность сервера.

- Устранение уязвимостей, которые могут сделать сервер уязвимым для нарушений безопасности.

- Обновления часовой зоны.

Это означает, что для продукта не будет никаких обновлений, исправлений или исправлений (в том числе исправлений и исправлений). Служба поддержки Майкрософт полностью перенацелит свои усилия по поддержке на более последние версии.

В конце поддержки подходов SharePoint Server 2010 удалите данные, которые больше не нужны, прежде чем обновить продукт и перенести важные данные.

> [!NOTE]
> Жизненный цикл программного обеспечения обычно длится десять лет с начального выпуска. [Поставщики решений](https://go.microsoft.com/fwlink/?linkid=841249) Майкрософт могут помочь вам перейти на следующую версию программного обеспечения или перейти на миграцию в Microsoft 365 (или обе). Убедитесь, что вам известны даты окончания поддержки критически важных технологий, особенно для версии Microsoft SQL Server, используемой с SharePoint. Дополнительные сведения см. в [ок. Исправленная политика жизненного цикла.](https://support.microsoft.com/help/14085)

## <a name="plan-ahead"></a>Планирование заранее

Проверьте даты окончания поддержки на сайте [жизненного цикла продукта.](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010) Планирование обновлений или миграций с помощью этих дат. Помните, что *ваш продукт не перестает работать в* указанную дату. Но так как после этой даты установка не будет исправлена, необходимо спланировать плавный переход к следующей версии продукта.

Эта матрица помогает заметь курс среди параметров миграции:

|Конец продукта поддержки|Хороший |Лучший|
|---|---|---|
|SharePoint Server 2010|SharePoint Server 2013 (локально)|SharePoint Online|
||Гибрид SharePoint Server 2013 с SharePoint Online|SharePoint Server 2016 (локально)|
|||Гибридный поиск в облаке SharePoint|

Если вы выберете вариант на низком конце шкалы (хороший), вам необходимо приступить к планированию еще одного обновления вскоре после переноса из SharePoint Server 2010.

Вот три пути, которые можно принять, чтобы избежать окончания поддержки SharePoint Server 2010.

![Пути обновления SharePoint Server 2010](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> Окончание поддержки SharePoint Server 2010 и SharePoint Foundation 2010 запланировано на 13 апреля 2021 г. Но не забудьте проверить сайт [жизненного цикла](https://support.microsoft.com/lifecycle) продукта на наиболее актуальные даты.

## <a name="whats-next"></a>Что дальше?

SharePoint Server 2013 и SharePoint Foundation 2013 могут быть установлены на собственных серверах. Или вы можете использовать SharePoint Online, которая является онлайн-службой, которая является частью Microsoft 365. Вы можете выбрать:

- Миграция в SharePoint Online.

- Обновление локального сервера SharePoint Server или SharePoint Foundation.

- У обоих из вышеперечисленного.

- Реализация [гибридного решения SharePoint.](/sharepoint/hybrid/hybrid)

Рассмотрим скрытые затраты на обслуживание фермы серверов, включая обслуживание или перенос настроек и обновление оборудования. Если вы учитывали эти факторы, будет проще обновить локальное обновление. Если вы запустите ферму на устаревших серверах SharePoint Server без тяжелой настройки, вы можете воспользоваться запланированной миграцией в SharePoint Online. В локальной среде SharePoint Server можно также рассмотреть возможность переноса некоторых данных в SharePoint Online для уменьшения накладных расходов на управление оборудованием.

> [!NOTE]
> Администраторы SharePoint могут создавать подписку Microsoft 365, создавать новые сайты SharePoint Online, а затем чисто отключаться от SharePoint Server 2010, отводя только необходимые документы на свежие сайты. Затем любые оставшиеся данные можно истощать с сайта SharePoint Server 2010 в локальном архиве.

|SharePoint Online|Локальное помещение SharePoint Server|
|---|---|
|Высокая стоимость во времени (планирование/выполнение/проверка)|Высокая стоимость во времени (планирование/выполнение/проверка)|
|Более низкая стоимость в фондах (без покупок оборудования)|Более высокая стоимость средств (покупки оборудования)|
|Разовая стоимость миграции|Однократная повторяемая стоимость для будущей миграции|
|Низкая общая стоимость владения/обслуживания|Высокая общая стоимость владения/обслуживания|

Разовая перенастройка в Microsoft 365 будет стоить дороже, если вы организуете данные и решаете, что взять в облако и что оставить. Но после переноса данных будущие обновления будут автоматически, так как вам больше не потребуется управлять обновлениями оборудования и программного обеспечения. И время работы фермы будет засвеяно соглашением об уровне [служб Майкрософт (SLA).](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)

### <a name="migrate-to-sharepoint-online"></a>Миграция на SharePoint Online

Убедитесь, что SharePoint Online предлагает все необходимые функции. См. [описание службы SharePoint.](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description)

Вы не можете перейти напрямую из SharePoint Server 2010 (или SharePoint Foundation 2010) в SharePoint Online. Большая часть работы по миграции вручную. Но на этом этапе вы можете подрезать данные и сайты, которые больше не нужны перед перемещением. Другие данные можно архивировать в хранилище. 

Помните, что SharePoint Server 2010 и SharePoint Foundation 2010 не перестанут работать в конце поддержки. Таким образом, администраторы могут иметь период, когда SharePoint по-прежнему работает, если их клиенты забывают переместить некоторые из своих данных.

Если вы переназначитесь до SharePoint Server 2013 или SharePoint Server 2016 и решите поместить данные в SharePoint Online, вы можете использовать API миграции [SharePoint](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) для переноса информации в OneDrive для бизнеса.

|Преимущество SharePoint Online|Недостаток SharePoint Online|
|---|---|
|Корпорация Майкрософт поставляет оборудование SPO и все аппаратные средства администрирования.|Доступные функции могут отличаться между локальной и SPO-серверами SharePoint Server.|
|Вы глобальный администратор подписки и можете назначать администраторов на сайты SPO.|Некоторые действия, доступные администратору фермы в локальном сервере SharePoint Server, не существуют (или не являются необходимыми) в роли администратора SharePoint в Microsoft 365. Но администрирование SharePoint, администрирование коллекций сайтов и владение сайтом являются локальными для вашей организации.|
|Корпорация Майкрософт применяет исправления, исправления и обновления к основному оборудованию и программному обеспечению, в том числе к SQL серверам, на которых выполняется SharePoint Online.|Так как в службе нет доступа к основному файловой системе, настройка ограничена.|
|Корпорация Майкрософт публикует [соглашения на уровне служб](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) и быстро перемещается для устранения инцидентов на уровне служб.|Резервное копирование и восстановление и другие параметры восстановления автоматизированы службой SharePoint Online. Резервное копирование перезаписано, если не используется.|
|Тестирование безопасности и настройка производительности сервера непрерывно осуществляются в службе Корпорацией Майкрософт.|Службой устанавливаются изменения пользовательского интерфейса и других функций SharePoint, которые могут быть отключены или отключены.|
|Microsoft 365 отвечает многим отраслевым стандартам: [предложения по обеспечению соответствия требованиям Майкрософт.](/compliance/regulatory/offering-home)|[Помощь FastTrack](https://go.microsoft.com/fwlink/?linkid=518597) для миграции ограничена.  <br/> Большая часть обновления будет вручную или через API миграции SPO, описанный в дорожной карте [контента sharePoint Online и OneDrive migration Content.](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)|
|Инженеры службы поддержки Майкрософт и сотрудники центра обработки данных не имеют неограниченного доступа администратора к подписке.|Дополнительные затраты могут быть, если необходимо обновить инфраструктуру оборудования для поддержки более новой версии SharePoint или если для обновления требуется дополнительная ферма.|
|Поставщики решений могут помочь с разовой работой по переносу данных в SharePoint Online.|Не все изменения в SharePoint Online находятся в пределах вашего управления. После переноса изменения в меню, библиотеках и других функций могут временно повлиять на доступность использования.|
|Продукты в Интернете обновляются автоматически по всей службе. Возможности могут обесцениться, но нет истинного конца жизненного цикла поддержки.|Для SharePoint Server или SharePoint Foundation существует жизненный цикл, а также SQL серверов.|

Если вы решили создать новый сайт Microsoft 365 и вручную переносите на него данные по мере необходимости, проверьте [параметры Microsoft 365.](https://www.microsoft.com/microsoft-365/)

### <a name="upgrade-sharepoint-server-on-premises"></a>Обновление локального сервера SharePoint Server

В SharePoint Server 2019 обновления должны идти *последовательно.* Нет способа обновиться с SharePoint Server 2010 до SharePoint Server 2016 или напрямую до SharePoint 2019. Путь последовательного обновления:

- SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

Это займет время и планирование, чтобы следовать всему пути от SharePoint 2010 до SharePoint Server 2016. Обновление связано с затратами на оборудование (SQL серверы также должны быть обновлены), программного обеспечения и администрирования. Кроме того, может потребоваться обновить или даже отказаться от настроек. Убедитесь, что перед обновлением фермы SharePoint Server необходимо документировать критически важные настройки.

> [!NOTE]
> Можно сохранить ферму SharePoint 2010, установить ферму SharePoint Server 2016 на новом оборудовании (поэтому отдельные фермы работают бок о бок), а затем спланировать и выполнить ручную миграцию контента (например, для скачивания и повторной загрузки контента). Но для этих ручных ходов существуют потенциальные подводные камни, например документы 2010 г., имеющие текущую последнюю измененную учетную запись с псевдонимом учетной записи, которая перемещается вручную. Некоторые работы необходимо проделать заранее, например воссоздать сайты, подвиды, разрешения и структуры списков. Перед обновлением необходимо очистить среду. Рассмотрите, какие данные можно переместить в хранилище или больше не нужно. Это может снизить влияние миграции. Будьте уверены, что существующая ферма будет функциональной перед обновлением и (конечно) перед выводом из эксплуатации!

Не забудьте просмотреть поддерживаемые и неподдержку путей *обновления:*

- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12)).

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)

Если у вас *есть настройки,* важно планировать каждый шаг на пути миграции:

- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14)).

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)

|Локальное преимущество|Недостаток локальной|
|---|---|
|Полный контроль всех аспектов фермы SharePoint (и ее SQL) с серверного оборудования.|Все перерывы и исправления являются ответственностью вашей компании. Но вы можете привлечь платную поддержку Майкрософт, если ваш продукт не был в прошлом конце поддержки.|
|Полный набор функций локального сервера SharePoint Server с возможностью подключения локальной фермы к подписке SharePoint Online с помощью гибридной.|Обновление, исправления, исправления, обновления оборудования и все обслуживание SharePoint Server и SQL фермы управляются локально.|
|Полный доступ для более больших параметров настройки, чем с SharePoint Online.|[Предложения по обеспечению соответствия](/compliance/regulatory/offering-home) требованиям Майкрософт должны настраиваться вручную локально.|
|Тестирование безопасности и настройка производительности сервера осуществляются в вашем помещении под вашим контролем.|Microsoft 365 может сделать доступными функции SharePoint Online, которые не пересекались с Локальной службой SharePoint Server.|
|Поставщики решений могут помочь перенести данные в следующую версию SharePoint Server (и далее).|Сайты SharePoint Server не будут автоматически использовать [сертификаты SSL/TLS,](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) как это видно в SharePoint Online.|
|Полный контроль над соглашениями именования, резервного копирования и восстановления и другими вариантами восстановления в локальном сервере SharePoint Server.|Локальное помещение SharePoint Server чувствительно к жизненным циклам продукта.|

### <a name="upgrade-resources"></a>Обновление ресурсов

Начните с сравнения требований к оборудованию и программному обеспечению. Если текущая среда не соответствует основным требованиям, может потребоваться сначала обновить оборудование фермы или SQL серверов. 

Вы можете переместить некоторые сайты на "вечнозеленое" оборудование SharePoint Online. После оценки выполните поддерживаемые пути обновления и методы.

- *Требования к оборудованию и программному обеспечению для:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *Границы и ограничения программного обеспечения для:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)

- *Обзор процесса обновления для:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-hybrid-solution-with-sharepoint-online-and-sharepoint-server-on-premises"></a>Создание гибридного решения с локальной сетью SharePoint Online и SharePoint Server

Гибридная настройка обеспечивает наилучшее как локальное, так и интерактивное решение для некоторых потребностей миграции. Вы можете подключить фермы SharePoint Server 2013, 2016 или 2019 к SharePoint Online, чтобы создать гибрид SharePoint: Узнайте о гибридных решениях [SharePoint.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

Если гибридная ферма SharePoint Server является вашей целью миграции, пойми, какие сайты и пользователи должны перемещаться в Интернете и какие должны оставаться локально. Ранжирование содержимого фермы SharePoint Server как высокое, среднее или низкое влияние на вашу компанию может помочь с этим решением. Вам может потребоваться только поделиться учетными записями пользователей для входа и индексом поиска SharePoint Server в SharePoint Online. Но этот фактор может быть неясным, пока вы не посмотрите, как используются сайты. Если позже ваша компания примет решение перенести все содержимое в SharePoint Online, вы можете переместить все оставшиеся учетные записи и данные в Интернете и списание локальной фермы. Управление и администрирование фермы SharePoint будет происходить с помощью консолей Microsoft 365 с этого момента.

Не забудьте ознакомиться с существующими типами гибридов и настроить подключение между локальной фермой SharePoint и подпиской на Microsoft 365.

|Вариант|Описание|
|---|---|
|[Предложения по обеспечению соответствия требованиям Корпорации Майкрософт.](/compliance/regulatory/offering-home)|[Помощь FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) для миграции ограничена.<br/><br/> Большая часть обновления будет вручную или через API миграции SPO, описанный в дорожной карте [контента sharePoint Online и OneDrive migration Content.](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)|
|Инженеры службы поддержки Майкрософт и сотрудники центра обработки данных не имеют неограниченного доступа администратора к подписке.|При необходимости обновления инфраструктуры оборудования для поддержки более новой версии SharePoint или необходимости вторичной фермы могут возникнуть дополнительные затраты.|
|Партнеры могут помочь при одновом переносе данных в SharePoint Online.||
|Продукты в Интернете обновляются автоматически по всей службе. Возможности могут обесцениться, но нет истинного конца поддержки.||

Если вы решили создать новый сайт Microsoft 365 и вручную перенести на него данные по мере необходимости, проверьте [параметры Microsoft 365.](https://www.microsoft.com/microsoft-365/)

### <a name="upgrade-sharepoint-server-on-premises"></a>Обновление локального сервера SharePoint Server

В SharePoint Upgrades нет способа пропустить версии. Это означает, что обновления идут последовательно:

- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

Чтобы пройти весь путь от SharePoint 2007 до SharePoint Server 2016, это будет означать значительные затраты времени и будет включать оборудование (также необходимо обновить SQL серверов), программное обеспечение и расходы на администрирование. Настройки необходимо обновить или отказаться от них, в зависимости от критичности функции.

> [!NOTE]
> Можно сохранить ферму SharePoint 2007, установить ферму SharePoint Server 2016 на новом оборудовании (поэтому отдельные фермы работают бок о бок), а затем спланировать и выполнить ручную миграцию контента (например, для скачивания и повторной загрузки контента). Но у этих ручных ходов есть некоторые недостатки, например перемещения документов, заменяющих последнюю измененную учетную запись псевдонимом учетной записи, которая перемещается вручную. Заранее необходимо проделать большую работу, например воссоздать сайты, подвиды, разрешения и структуры списков. В любом случае рассмотрите, какие данные можно переместить в хранилище или больше не нужно, чтобы уменьшить влияние миграции.

Убедитесь, что перед обновлением необходимо очистить среду. Будьте уверены, что существующая ферма будет функциональной перед обновлением и, конечно, перед выводом из эксплуатации!

Не забудьте просмотреть поддерживаемые и неподдержку путей *обновления:*

- [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12)).

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)

Если у вас *есть настройки,* важно спланировать обновление для каждого шага на пути миграции:

- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))

- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14)).

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)

|Локальное pro|Локальное con|
|---|---|
|Полный контроль всех аспектов фермы SharePoint с серверного оборудования.|Все перерывы и исправления являются ответственностью вашей компании. (Но вы можете привлечь платную поддержку Майкрософт, если ваш продукт не был в прошлом конце поддержки.)|
|Полный набор функций локального сервера SharePoint Server с возможностью подключения локальной фермы к подписке SharePoint Online с помощью гибридной.|Обновление, исправления, исправления безопасности и все обслуживание управляемых локальной службы SharePoint Server.|
|Полный доступ для большей настройки.|[Предложения по обеспечению соответствия](/compliance/regulatory/offering-home) требованиям Майкрософт должны настраиваться вручную локально.|
|Тестирование безопасности и настройка производительности сервера осуществляются в вашем помещении под вашим контролем.|Microsoft 365 может сделать функции доступными для SharePoint Online, которые не пересекались с локальной службой SharePoint Server.|
|Партнеры могут помочь перенести данные в следующую версию SharePoint Server (и далее).|Сайты SharePoint Server не будут автоматически использовать [сертификаты SSL/TLS,](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) как это видно в SharePoint Online.|
|Полный контроль над соглашениями именования, резервного копирования и восстановления и другими вариантами восстановления в локальном сервере SharePoint Server.|Локальное помещение SharePoint Server чувствительно к жизненным циклам продукта.|

### <a name="upgrade-resources"></a>Обновление ресурсов

Начните с того, что вы отвечаете требованиям к оборудованию и программному обеспечению, а затем выполните поддерживаемые методы обновления.

- *Требования к оборудованию и программному обеспечению для:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *Границы и ограничения программного обеспечения для:*

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)

- *Обзор процесса обновления для:*

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Создание гибридного решения SharePoint между SharePoint Online и локальной сетью

Если ответ на ваши потребности в миграции находится где-то между управлением, предлагаемым локально, и более низкой стоимостью владения, предложенной SharePoint Online, вы можете подключить фермы SharePoint Server 2013 или 2016 к SharePoint Online с помощью гибридов. [Узнайте о гибридных решениях SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

Если вы решите, что гибридная ферма SharePoint Server принесет пользу вашему бизнесу, ознакомьтесь с существующими типами гибридов и настройкой подключения между локальной фермой SharePoint и подпиской на Microsoft 365.

Возможно, вам нужно создать среду разработчиков и тестов Microsoft 365, которую можно настроить с помощью руководств [по тестовой лаборатории.](m365-enterprise-test-lab-guides.md) После получения пробной или приобретенной подписки на Microsoft 365 можно создать коллекции сайтов, веб-сайты и библиотеки документов в SharePoint Online, в которые можно перенести данные. Вы можете перенести его вручную с помощью API миграции или, если вы хотите перенести содержимое сайта в OneDrive для бизнеса, с помощью гибридного мастера.

> [!NOTE]
> Чтобы использовать гибридный вариант, ферму SharePoint Server 2010 необходимо сначала обновить локально до SharePoint Server 2013 или 2016. SharePoint Foundation 2010 и SharePoint Foundation 2013 не поддерживают гибридные подключения к SharePoint Online.

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Сводка параметров для клиентов и серверов Office 2010 и Windows 7

Визуальное представление возможностей обновления, миграции и перехода на облачные решения для клиентов и серверов Office 2010, а также Windows 7 см. на плакате [Прекращение поддержки](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Завершение поддержки клиентов и серверов Office 2010 и плаката Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

На этом плакате показано, как избежать клиентских и серверных продуктов Office 2010 и окончания поддержки Windows 7, а в Microsoft 365 Enterprise выделены предпочтительные пути и поддержка опций.

Вы также можете [скачать](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) этот плакат и распечатать его в формате букв, юридических или таблоидов (11 x 17).

## <a name="related-articles"></a>Статьи по теме

[Ресурсы, которые помогут обновить серверы и клиенты Office 2007 или 2010](upgrade-from-office-2010-servers-and-products.md)

[Overview of the upgrade process from SharePoint 2010 to SharePoint 2013](/SharePoint/upgrade-and-update/overview-of-the-upgrade-process-from-sharepoint-2010-to-sharepoint-2013)

[Рекомендации по обновлению SharePoint 2010 до SharePoint 2013](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013)

[Устранение неполадок при обновлении баз данных в SharePoint 2013](/SharePoint/upgrade-and-update/troubleshoot-database-upgrade-issues-in-sharepoint-2013)

[Поиск поставщиков решений Майкрософт, которые помогут в обновлении](https://go.microsoft.com/fwlink/?linkid=841249)

[Обновленная политика обслуживания продукта SharePoint 2013](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-2013)

[Обновленная политика обслуживания продукта SharePoint Server 2016](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-server-2016)