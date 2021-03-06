---
title: Взаимодействие служб групп
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Взаимодействие служб групп
ms.openlocfilehash: f9b0d7ca61d55e3d23aa94577fc8257073b26675
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539207"
---
# <a name="groups-services-interactions"></a>Взаимодействие служб групп

Microsoft 365 Группы предоставляют общую структуру для ряда служб и рабочих нагрузок в платформе Microsoft 365 для доставки подключенного опыта для конечных пользователей. По своей сути существует Microsoft 365 группа, которая предоставляет:

- Способ управления членством (Azure AD)
- Место для обмена сообщениями и бесед (Exchange почтовый ящик, Microsoft Teams, Yammer)
- Место хранения файлов (SharePoint)
- Календарь планирования (Exchange)
- Записная книжка для записи записей (OneNote)

На этапе создания группы также предусмотрен ряд других ресурсов, однако они не видны до первого доступа из службы:

- Совет по управлению групповыми задачами (Планировщик)
- Рабочее пространство для отчетов (Power BI)
- Область общих видео (Microsoft Stream)
- Область общих форм (Forms)

В Microsoft 365 другие службы могут взаимодействовать с Microsoft 365 группами, чтобы предоставлять дополнительные функциональные возможности и возможности участникам группы.
Примеры этого:

- Power Apps для приложений
- Power Automate для рабочего процесса
- Project веб и дорожная карта для управления проектами на основе водопада
- Teams для разговоров на основе каналов
- Yammer для интересуемого сообщества

## <a name="user-interactions-with-groups"></a>Взаимодействие пользователей с группами

Microsoft 365 Группы могут создаваться и управляться из различных интерфейсов, как администраторов, так и конечных пользователей. 

### <a name="administrative-experiences"></a>Администрирование

Администраторы могут создавать и управлять группами Microsoft 365 из нескольких центров администрирования рабочей нагрузки, интерфейсов командной строки, поддерживаюющих сценарии, а также настраиваемые приложения, взаимодействующие с Graph API. Исключением являются только Yammer группы, которые должны создаваться из Yammer веб-интерфейса.

**Связанные параметры**

В различных административных интерфейсах, которые могут управлять групповыми настройками, существует несколько перекрытий, о которых следует знать.

**Центр администрирования Microsoft 365**

В центре администрирования Microsoft 365 по умолчанию включен гостевой доступ к Группам, а также возможность разрешить владельцам добавлять гостей. Дополнительные элементы управления на уровне организации для групп из этого центра администрирования недоступны.

**Центр администрирования Azure AD**

Центр администрирования Azure AD позволяет определить, могут ли пользователи создавать группы или назначать владельцев на порталах Azure, а также параметры политики истечения срока действия и именования.

Центр администрирования также предоставляет ряд мер по контролю приглашений гостей, которые выходят за пределы центра администрирования Microsoft 365, например возможность ограничения возможности приглашения гостей, не владея их владельцами.

**SharePoint**

SharePoint сайты создаются с группами безопасности Owner, Member и Visitor, а первые два совпадают с их Microsoft 365 group. Хотя членство для SharePoint веб-сайтов, как правило, управляется связанной группой Microsoft 365, она не является бидиректорной связью. Любые изменения в членстве на уровне Microsoft 365 отражаются в SharePoint, однако если членство изменено в группе SharePoint, это не отражается в Microsoft 365 группе.

### <a name="user-experiences"></a>Пользовательские впечатления

Конечные пользователи могут создавать группы из нескольких служб в Microsoft 365, а в других они могут делиться только с группой.

Следующие службы позволяют создавать группы конечными пользователями:
                         
Outlook Планировщик Project веб-SharePoint Stream Microsoft Teams Yammer

**Ограничение создания группы**

Распространенный подход к борьбе с разрастаемой командой заключается в ограничении возможностей их создания пользователями. Это можно сделать, ограничив создание групп. Это влияет на возможность создания групп из других служб, где это может потребоваться конечному пользователю. Microsoft 365 Группы не поддерживают возможность ограничения создания групп из одних приложений или служб, разрешая их другим.

Опыт ограничения создания групп варьируется между приложениями и службами:


|Приложение или служба|Интерфейс|
|:-------------|:---------|
|Outlook|**Новый параметр группы** удаляется из нового меню на странице people|
|Планировщик|**Новый план** объясняет, что создание группы отключено, и предлагает добавить план в существующую группу|
|Project веб-карты и roadmap|**Создание группового** меню объясняет, что создание группы ограничено, и предлагает использовать существующую группу.|
|SharePoint|По-прежнему можно создать сайт группы, не подключенный к группе.|
|Stream|**Параметр Group** не появляется в меню **Create**.|
|Teams|Пользователь не может создать команду с новой группой, но может создать группу, которая использует существующую группу.<br><br>**Создание кнопки команды** заменяется **командой Create team из группы.**|
|Yammer|**Создание группового** параметра удаляется из основной навигации групп и сообществ.|

## <a name="services-interactions-with-groups"></a>Взаимодействие служб с группами

См. в Microsoft 365 групп информацию о различных типах групп, о том, как они создаются и управляются, и несколько рекомендаций по управлению.

[![Эскиз инфографики групп](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)

[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)

В следующей таблице представлен обзор взаимодействия Microsoft 365 групп с различными службами:

|Продукт|Функции|Делает службу<br>существуют без группы?|Может ли служба<br>создать группу?|Удаление<br>экземпляр удалить группу?|
|:---|:---|:---|:---|:---|
|Azure AD|Членство, элементы управления группой, гости|Да|Да|Да|
|Exchange|Календарь, почтовый ящик|Да|Да|Да|
|Forms|Form|Да|Нет|Нет|
|OneNote|Notebook|Да|Нет|Нет|
|Планировщик|Доска задач|Нет|Да|Да|
|Power Apps приложение|Приложение.|Да|Нет|Нет|
|Power Automate|Рабочий процесс|Да|Нет|Нет|
|Power BI (классический)|Workspace|Нет|Да|Да|
|Power BI (новое)|Workspace|Да|Нет|Да|
|Project в Интернете|Project плана|Да|Да|Нет|
|Стратегия|Стратегия|Да|Да|Нет|
|SharePoint|Site|Да|Да|Да|
|Stream|Канал, видео|Да|Да|Да|
|Teams|Команда|Нет|Да|Да|
|Yammer|Group|Да|Да|Да|

Хотя в таблице выше представлен краткий обзор групповых взаимодействий с Microsoft 365 службами, необходимо понимать ряд нюансов и тонкости. В следующих разделах подробно изуметь конкретные рабочие нагрузки и их взаимодействие с группами.

## <a name="azure-ad"></a>Azure AD

Azure AD предоставляет возможности управления удостоверениями в Microsoft 365.

**Ключевые функции, предоставляемые группам**

- Участие в группе
- Политика именования
- Политика прекращения действия
- Гости
- Ограничение создания группы

**Может ли Azure AD создать группу?**

Да, Microsoft 365 группы можно создавать из Azure AD либо через веб-портал администрирования, через PowerShell, либо Graph API.

**Существует ли Azure AD без группы?**

Да, Azure AD выполняет большое количество служб, которые не имеют отношения к Microsoft 365 Groups. Каждая Microsoft 365 представлена как объект в Azure AD.

**Может ли быть несколько экземпляров Azure AD для группы?**

Нет, существует только один экземпляр Azure AD.

**Можно ли связывать Azure AD с несколькими группами?**

Да, так как Azure AD — это платформа, которая предоставляет службу членства в группе.

**Может ли связь Azure AD с групповой переменой?**

Нет, Azure AD — это платформа, на которой существуют группы.

**Удаление экземпляра удаляет группу?**

Удаление группы в Azure AD удаляет соответствующие службы и контент, связанные с группой.

## <a name="teams"></a>Teams

Teams это рабочее пространство, в центре которой находится чат, направленное на повышение эффективности совместной работы путем предоставления сингулярного интерфейса для взаимодействия с различными службами Майкрософт и сторонних служб.

По умолчанию при создания группы почтовый ящик и календарь, связанные с группой Microsoft 365, скрыты как из глобального списка адресов в Exchange, так и Outlook. Это может быть переопределено администратором вручную, если пользователь хочет использовать Outlook и Teams в одной Microsoft 365 Group.

**Ключевые функции, предоставляемые группам**

- Беседы
- Вкладки & каналов
- Собрания

**Можно Teams группу?**

Да, создание новой группы создаст новую Microsoft 365 группу. Также можно создать группу для существующей группы, которая в настоящее время не имеет ее.

**Существуют ли группы без группы?**

Нет, группа не может существовать без группы.

**Может ли быть несколько групп в группе?**

Нет, отношения между командой и группой 1:1.

**Можно ли связывать команду с несколькими группами?**

Нет, сама команда может быть связана только с одной группой.

**Может ли измениться связь группы с группой?**

Нет, группу можно связывать только с группой, с которой она изначально была связана.

**Удаление группы удаляет группу?**

Да, удаление группы в Microsoft Teams удаляет группу, связанные с группой службы и контент.

## <a name="exchange"></a>Exchange

Exchange Online предоставляет функции обмена сообщениями, календаря, контактов и связанных с ними функций. В контексте группы связан только один ресурс, в отличие от целого экземпляра службы.

**Ключевые функции, предоставляемые группам**

- Почтовый ящик и календарь
- Возможность отправки по электронной почте всем участникам группы
- служба хранилища беседы Teams каналов для целей eDiscovery, комментарии Planner

**Можно Exchange группу?**

Да, можно создать группу из центра администрирования Exchange Online, а также из Outlook. Кроме того, можно Exchange списки рассылки в Microsoft 365 группы.

**Существует ли Exchange без группы?**

Да, Exchange Online предоставляет ряд служб, включая общие почтовые ящики и календари, без какой-либо групповой связи.

**Может ли быть несколько экземпляров Exchange почтовых ящиков или календарей для одной группы?**

Нет, может быть только один Exchange Online почтовый ящик и календарь для группы.

**Можно Exchange почтовые ящики и календари с несколькими группами?**

Нет, почтовый ящик и календарь имеют отношение 1:1 к группе. Можно делиться почтовым ящиком с другими пользователями или группами, однако это не создает никакой формы ассоциации служб.

**Может ли Exchange почтовый ящик или связь календаря с групповой переменой?**

Нет, почтовый ящик и календарь нельзя изменить на другую группу. Однако содержимое может быть перемещено из одного почтового ящика в другой Outlook или с помощью сторонних средств.

**Удаление почтового ящика удаляет группу?**

Да, удаление почтового ящика в Exchange удаляет группу, а также связанные с группой службы и контент.

## <a name="forms"></a>Forms

Forms предоставляет веб-опросы и викторины.

**Ключевые функции, предоставляемые группам**

- Владение формами

**Может ли Forms создать группу?**

Нет, Forms не может создать группу.

**Существуют ли формы без группы?**

Да, опросы и викторины можно создавать непосредственно в учетной записи конечного пользователя.

**Может ли быть несколько форм в группе?**

Да, может быть несколько форм, связанных с группой.

**Можно ли связывать формы с несколькими группами?**

Нет, форму можно связывать только с одной группой.

**Может ли связь формы с групповой переменой?**

Нет, если форма связана с группой (либо создается непосредственно внутри, либо передается от физического лица), ее нельзя переносить в другую группу.

**Удаление формы удаляет группу?**

Нет, удалить группу из интерфейса Forms невозможно, только отдельные формы.

## <a name="onenote"></a>OneNote

OneNote — это цифровое приложение для записных записей. Записная OneNote, созданная с группой, — это файл на связанном сайте SharePoint, а не служба, связанная с группой.

**Ключевые функции, предоставляемые группам**

- Общий блокнот (хранимый в библиотеке, связанной с SharePoint группы)

**Можно OneNote группу?**

Нет, OneNote приложение не может создать группу.

**Существуют OneNote без группы?**

Да, записные книжки можно создавать непосредственно в OneDrive или в других общих расположениях.

**Может ли быть несколько OneNote для группы?**

Да, записная книжка создается по умолчанию и можно добавлять другие, однако любая ссылка на OneNote из служб, связанных с группой, всегда будет переходить к записной книжке по умолчанию.

**Можно ли OneNote с несколькими группами?**

Нет, записная книжка хранится в связанной с группой библиотеке SharePoint сайта и связана с различными интерфейсами. Однако его можно совместно использовать с другими группами таким же образом, как и с отдельными лицами.

**Может ли связь ноутбука с группой измениться?**

Нет, сама записная книжка связана с группой и может напрямую получать доступ к другим службам, подключенным к группе, однако содержимое можно перемещать из одной записной книжки в другую в OneNote приложении.

**Удаление записной книжки удаляет группу?**

Нет, однако если OneNote записная книжка удалена, в некоторых службах, связанных с группой, могут быть нарушены ссылки.

## <a name="planner"></a>Планировщик

Planner — это облегченная служба управления групповыми задачами.

**Ключевые функции, предоставляемые группам**

- Совет по управлению групповыми задачами

**Может ли планировщик создать группу?**

Да, создание плана создаст новую группу.

**Существует ли доска планировщика без группы?**

Нет, план должен быть связан с группой.

**Может ли быть несколько планов для группы?**

Да, в группе может быть несколько планов.

**Можно ли связывать план с несколькими группами?**

Нет, для определения доступа для плана зависит только членство в группе.

**Может ли связь плана с групповой переменой?**

Нет, однако копирование плана создает новую группу.

> [!NOTE]
> Группа, созданная любым другим приложением, не будет автоматически показываться в Planner для пользователя. Для первоначального доступа к доске необходимо открыть его из другого группового интерфейса, например Outlook.

**Удаление плана удаляет группу?**

Да, удаление плана позволит удалить службы и контент, связанные с группой.

## <a name="power-apps"></a>Power Apps

Power Apps предоставляет холст для разработки приложений без кода.

**Ключевые функции, предоставляемые группам**

- Приложения можно совместно использовать с группой, которая будет запускаться и изменяться

**Можно Power Apps группу?**

Нет, Power Apps не удается создать Microsoft 365 группу.

**Существуют ли Power Apps без группы?**

Да, приложения можно создавать в пределах Power Apps и находиться в учетной записи создателей до публикации или общего опубликования.

**Может ли быть несколько приложений в группе?**

Да, в группе может быть несколько приложений.

**Можно ли связывать приложения с несколькими группами?**

Да, приложение можно совместно использовать с несколькими группами.

**Может ли связь приложения с группой измениться?**

Да, поскольку связь между Power Apps и группой Microsoft 365 делится только — приложение по-прежнему находится с создателем.

> [!IMPORTANT]
> [Группы должны быть включены для обеспечения безопасности, прежде чем приложения могут быть общими с ними.](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)

**Удаляет ли приложение группу?**

Нет, приложения не подключены к группе, кроме общего с ними.

## <a name="power-automate"></a>Power Automate

Power Automate (ранее Microsoft Flow) предоставляет рабочий процесс и службы автоматизации.

**Ключевые функции, предоставляемые группам**

- Рабочий процесс можно совместно использовать для запуска и изменения группы.

**Можно Power Automate группу?**

Нет, Power Automate не может создать группу Microsoft 365 в контексте связи с ней.

Однако можно создать поток, который выполняет различные операции, такие как создание группы безопасности Azure AD или обновление членства Microsoft 365 группы.

**Существуют ли потоки без группы?**

Да, потоки можно создавать в пределах Power Automate и находиться в учетной записи создателей до общего или опубликованного.

**Может ли быть несколько потоков на одну группу?**

Да, может быть несколько потоков, общих с группой.

**Можно ли связывать поток с несколькими группами?**

Да, поток можно совместно использовать с несколькими группами.

**Может ли связь потока с группой измениться?**

Да, поскольку связь между Power Automate и группой Microsoft 365 является совместной, поток по-прежнему находится с создателем.

**Удаление потока удаляет группу?**

Нет, как Power Apps, потоки не подключены к группе, кроме общего с ними.

## <a name="power-bi-classic"></a>Power BI (классический)

Power BI предоставляет интерактивные информационные панели и отчеты, управляемые данными.

**Ключевые функции, предоставляемые группам**

- Отчеты о данных

**Можно Power BI группу?**

Да, создание классического рабочего пространства создаст Microsoft 365 группу.

**Существует ли Power BI классическое рабочее пространство без группы?**

Нет, [классическое рабочее пространство в Power BI должно быть связано с группой](/power-bi/collaborate-share/service-collaborate-power-bi-workspace).

**Может ли быть несколько Power BI в группе?**

Нет, связь между классическим рабочее пространство и группой 1:1.

**Можно ли связывать рабочее пространство с несколькими группами?**

Технически нет, хотя классическое рабочее пространство создается вместе с группой, содержимое можно совместно использовать за пределами группы с пользователями и группами безопасности.

**Может ли измениться связь рабочей области с групповой группой?**

Нет, классическое рабочее пространство само связано с Группой, однако содержимое может быть перемещено из одного рабочего пространства в другое в интерфейсе Power BI или путем локального экспорта содержимого.

**Удаление рабочей области удаляет группу?**

Да, удаление рабочего пространства в Power BI удаляет групповые и групповые службы и контент.

## <a name="power-bi-new"></a>Power BI (новое)

Power BI предоставляет интерактивные информационные панели и отчеты, управляемые данными.

При создании нового рабочего пространства Power BI не создает группу Microsoft 365, создавая группу любыми другими средствами, создает новое (не классическое) рабочее пространство в Power BI.

**Ключевые функции, предоставляемые группам**

- Отчеты о данных

**Можно Power BI группу?**

Нет, невозможно создать группу Microsoft 365 из нового Power BI интерфейса.

**Существует ли новое Power BI без группы?**

Да, существует возможность создания отчетов и рабочей области в Power BI, не связанных с Microsoft 365 группами.

**Может ли быть несколько пространств работы в группе?**

Да, [несколько созданных Power BI могут быть общими для одной группы.](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace)

**Можно ли связывать рабочее пространство с несколькими группами?**

Нет, рабочее пространство, созданное Power BI, может быть связано только с одной группой.

**Может ли связь рабочей области с групповой переменой?**

Да и нет. Рабочее пространство, созданное Power BI, может быть связано только с одной группой одновременно, но может изменить связь в любое время. Рабочее пространство, созданное Power BI группы, постоянно связано с этой группой.

**Удаление рабочей области удаляет группу?**

Да, удаление рабочего пространства в Power BI удаляет службы и контент, связанные с группой.

## <a name="project-for-the-web"></a>Project в Интернете

Project веб-сайте предоставляет возможность создания планов проектов, диаграмм Gantt и дорожных карт.
Ключевые функции, предоставляемые группам.

- Project планы

**Можно Project веб-создать группу?**

Да, можно создать новую группу Microsoft 365 непосредственно из Project веб-сайта.

**Существуют ли проекты без группы?**

Да, проекты могут существовать без связи с Microsoft 365 группой, однако для назначения задач требуется объединение групп.

**Может ли быть несколько проектов в группе?**

Да, можно подключить несколько проектов в одной группе.

**Можно ли связывать проект с несколькими группами?**

Нет, проект можно связывать только с одной группой.

**Может ли связь проекта с группой измениться?**

Нет, после того как связь с группой установлена, она не может измениться.

**Удаляет ли проект группу?**

Нет, удаление проекта в Project веб-страницы не удаляет группу.

## <a name="roadmap"></a>Стратегия

Дорожная карта предоставляет возможность создания дорожных карт проектов с Project веб-Project Online.

**Ключевые функции, предоставляемые группам**

- Project дорожную карту

**Может ли roadmap создать группу?**

Да, можно создать новую группу Microsoft 365 непосредственно из дорожной карты.

**Существует ли дорожная карта без группы?**

Да, дорожные карты могут существовать без связи с Microsoft 365 группой, однако для совместного использования дорожной карты требуется объединение групп.

**Может ли быть несколько дорожных карт для группы?**

Да, можно подключить несколько дорожных карт к одной группе.

**Можно ли связывать дорожную карту с несколькими группами?**

Нет, дорожная карта может быть связана только с одной группой.

**Может ли дорожная карта изменить связь с групповой группой?**

Нет, после того как связь с группой установлена, она не может измениться.

**Удаляет ли дорожная карта удаление группы?**

Нет, удаление дорожной карты не удаляет группу.

## <a name="sharepoint"></a>SharePoint

SharePoint — это веб-платформа управления контентом, которая предоставляет, помимо прочего, службы хранения для ряда Microsoft 365 служб.

**Ключевые функции, предоставляемые группам**

- Библиотека документов
- Библиотека для хранения OneNote ноутбука
- служба хранилища Teams вики-файлов

**Можно SharePoint группу?**

Да, создание сайта группы в SharePoint создаст группу Microsoft 365 по умолчанию. Также можно создать группу и, необязательно, группу для существующего сайта.

**Существуют ли SharePoint сайты без группы?**

Да, SharePoint предлагает ряд не связанных с группой служб и сайтов, таких как сайты связи и концентраторов. 

**Может ли быть несколько сайтов в группе?**

Нет, в группе может быть только один сайт. Частные каналы в Teams используют дополнительные сайты, не подключенные к группе.

**Можно ли связывать сайты с несколькими группами?**

Технически нет, но в то время как сайт создается с группой, контент можно совместно использовать с другими группами.

**Может ли связь сайта с группой измениться?**

Нет, сам сайт связан с группой, однако содержимое можно перемещать с одного сайта на другой в интерфейсе SharePoint, экспортировать контент локально или с помощью сторонних средств.

**Удаление сайта удаляет группу?**

Да, удаление сайта в SharePoint удаляет групповые и групповые службы и контент.

## <a name="stream"></a>Stream

Microsoft Stream — это платформа видеохостинга и обмена данными.

**Ключевые функции, предоставляемые группам**

- Хранение видео
- Teams собрания
- Видеоканалы

**Может ли Stream создать группу?**

Да, можно создать новую группу Microsoft 365 непосредственно из Stream.

**Существует ли Stream без группы?**

Да, видеоканалы и видео могут существовать в Stream без связи с группой.

**Может ли быть несколько видео и каналов для группы?**

Да, в каждой группе может быть несколько видео и каналов.

**Можно ли связывать видео или канал с несколькими группами?**

Да, в то время как видео или канал создается с группой, его можно совместно использовать с другими группами.

**Может ли его связь с группой измениться?**

Да и нет; Видео в Stream принадлежат исходному загрузителю или регистратору собраний и поэтому могут быть связаны с любой группой, однако видеоканалы могут быть связаны только с группой, в какой они изначально были созданы.

**Удаление видео или каналов удаляет группу?**

Нет, удаление видео или каналов не удаляет группу. Однако удаление самой группы в Stream удаляет связанные с группой службы и контент, за исключением фактических видео.

## <a name="yammer"></a>Yammer

Yammer является корпоративной социальной платформой, предназначенной для содействия вовлечению сообщества в организации и между ними.

Создание сообщества (ранее известного как "группа") в Yammer создает почтовый ящик, но в настоящее время это не используется.

Группа Microsoft 365, связанная с Yammer, не может использоваться с группой в Microsoft Teams.

**Ключевые функции, предоставляемые группам**

- Область беседы

**Можно Yammer группу Microsoft 365?**

Да, создание новой группы в Yammer создаст новую группу Microsoft 365, если платформы подключены и пользователь имеет возможность создать группу.

Группа Yammer с связанной группой Microsoft 365 не может быть создана ни в интерфейсе, ни в службе, кроме Yammer самой.

**Существует ли Yammer группа без Microsoft 365 группы?**

Да, можно создать группу Yammer без Microsoft 365 группы.

Если платформа Yammer не подключена к Microsoft 365 группам или у пользователей нет возможности создать группу Microsoft 365, Yammer группы создаются без Microsoft 365 группы.

**Может ли быть несколько Yammer групп в Microsoft 365 группу?**

Нет, отношение между Yammer и группой Microsoft 365 1:1.

**Можно ли Yammer группу с несколькими Microsoft 365 группами?**

Нет, Yammer группу можно связывать только с одной Microsoft 365 группой. Публикации могут быть общими или перенесены в другие Yammer группы.

**Может ли Yammer связь группы с изменением Microsoft 365 группы?**

Нет, Yammer группу можно связывать только с группой Microsoft 365, с которой она изначально была связана.

**Удаляет ли Yammer группу Microsoft 365 группу?**

Да, удаление группы в Yammer будет удалять связанные службы и контент группы Майкрософт и связанные с ними службы.

## <a name="related-topics"></a>Статьи по теме

[Пошаговая пошаговая работа по планированию управления совместной работой](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Создание плана управления совместной работой](collaboration-governance-first.md)