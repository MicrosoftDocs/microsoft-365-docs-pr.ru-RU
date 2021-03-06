---
title: Настройка границ соответствия требованиям для расследований по обнаружению электронных обнаружений
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: Узнайте, как использовать границы соответствия требованиям для создания логических границ, которые контролируют расположения контента пользователей, которые менеджер по обнаружению электронных данных может искать в Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: be857277d36d95ac1cd974ccb0c87f2048798450
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194713"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a>Настройка границ соответствия требованиям для расследований по обнаружению электронных обнаружений

Руководство в этой статье может применяться при использовании core eDiscovery или Advanced eDiscovery для управления расследованиями.

Границы соответствия требованиям создают логические границы в организации, управляющей расположениями контента пользователей (такими как почтовые ящики, OneDrive учетные записи и сайты SharePoint), которые могут искать руководители eDiscovery. Кроме того, управление границами соответствия требованиям, которые могут получать доступ к случаям электронного открытия, используемым для управления юридическими, людскими ресурсами или другими расследованиями в вашей организации. Часто необходимо соблюдать границы соответствия требованиям для многонациональных корпораций, которые должны соблюдать географические правила и правила, а также для правительств, которые часто делятся на различные учреждения. В Microsoft 365, границы соответствия требованиям помогают выполнять эти требования при выполнении поиска контента и управлении расследованиями при обнаружении электронных данных.
  
В следующем примере мы объясняем, как работают границы соответствия требованиям.
  
![Границы соответствия требованиям состоят из фильтров разрешений поиска, которые контролируют доступ к агентствам и группам ролей администратора, которые контролируют доступ к делам об обнаружении электронных обнаружений](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
В этом примере Contoso LTD — это организация, состоящая из двух дочерних предприятий, Fourth Coffee и Coho Winery. Бизнес требует, чтобы яслям и следователям по электронной почте можно было искать только Exchange почтовые ящики, OneDrive учетные записи и SharePoint сайты в своем агентстве. Кроме того, руководители и следователи по обнаружению электронных сообщений могут видеть в своем агентстве только случаи, когда они работают с электронными данными, и они могут получать доступ только к тем случаям, в которые они входит. Кроме того, в этом сценарии следователи не могут разместить расположения контента на удержание или экспортировать контент из дела. Вот как границы соответствия требованиям соответствуют этим требованиям.
  
- Функции фильтрации разрешений поиска в поиске контента контролируют расположения контента, которые могут искать руководители и следователи по поиску электронных поисков. Это означает, что менеджеры по обнаружению электронных данных и исследователи из учреждения Fourth Coffee могут искать содержимое только в дочерней компании Fourth Coffee. Такое же ограничение применяется к дочерней компании Coho Winery.

- [Группы ролей](assign-ediscovery-permissions.md#rbac-roles-related-to-ediscovery) предоставляют следующие функции для границ соответствия требованиям:

  - Управление, которые могут видеть случаи электронного разыскного дела в Центр соответствия требованиям Microsoft 365. Это означает, что менеджеры по обнаружению электронных данных и следователи могут видеть дела обнаружения электронных данных только в своих учреждениях.

  - Управление, назначив участников делу об обнаружении электронных обнаружений. Это означает, что менеджеры по обнаружению электронных данных и следователи могут назначать участников только тем делам, участниками которых сами являются.

  - Управление задачами, связанными с электронным открытием, которые участники могут выполнять, добавляя или удаляя роли, назначающие определенные разрешения.

Вот процесс настройки границ соответствия требованиям.
  
[Шаг 1. Определение атрибута пользователя для определения учреждений](#step-1-identify-a-user-attribute-to-define-your-agencies)

[Шаг 2. Создание группы ролей для каждого учреждения](#step-2-create-a-role-group-for-each-agency)

[Шаг 3. Создание фильтра разрешений поиска для обеспечения соблюдения границы соответствия требованиям.](#step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[Шаг 4. Создание дела об обнаружении электронных сообщений для внутриуровных расследований](#step-4-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a>Перед настройками границ соответствия требованиям

- Пользователям должна быть назначена Exchange Online лицензия. Чтобы убедиться в этом, используйте [комлет Get-User](/powershell/module/exchange/get-user) в Exchange Online PowerShell.

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>Шаг 1. Определение атрибута пользователя для определения учреждений

Первым шагом является выбор атрибута, который будет определять ваши учреждения. Этот атрибут используется для создания фильтра разрешений поиска, который ограничивает диспетчера поиска электронных данных для поиска только расположения контента пользователей, которым назначено определенное значение для этого атрибута. Например, предположим, что Contoso решает использовать атрибут **Department.** Значение для этого атрибута для пользователей в дочерней компании Fourth Coffee будет и значение для пользователей в дочерней компании  `FourthCoffee`  Coho Winery `CohoWinery` будет . В шаге 3 вы используете эту пару  `attribute:value` *(например, Department:FourthCoffee)* для ограничения расположения пользовательского контента, которое могут искать руководители eDiscovery. 
  
Вот несколько примеров атрибутов пользователей, которые можно использовать для границ соответствия требованиям:
  
- Организация

- CustomAttribute1 - CustomAttribute15

- Отдел

- Кабинет

- CountryOrRegion (код страны с двумя буквами)

Полный список см. в полном списке поддерживаемых фильтров [почтовых ящиков.](/powershell/exchange/recipientfilter-properties#filterable-recipient-properties)

## <a name="step-2-create-a-role-group-for-each-agency"></a>Шаг 2. Создание группы ролей для каждого учреждения

Следующий шаг — создание групп ролей в Центре & безопасности, которые будут согласовываться с вашими учреждениями. Мы рекомендуем создать группу ролей путем копирования встроенной группы менеджеров по обнаружению электронных данных, добавления соответствующих участников и удаления ролей, которые могут быть не применимы к вашим потребностям. Дополнительные сведения о ролях, связанных с электронным открытием, см. в дополнительных сведениях о присвоении разрешений на [открытие электронных данных.](assign-ediscovery-permissions.md)
  
Чтобы создать группы ролей, перейдите на страницу **Разрешения** в Центре безопасности и соответствия требованиям и создайте группу ролей для каждой команды в каждом учреждении, которая будет использовать ограничения для соответствия требованиям и дела обнаружения электронных данных для управления расследованиями.
  
С помощью сценария границ соответствия требованиям Contoso необходимо создать четыре группы ролей и добавить в каждую из них соответствующие члены.
  
- Менеджеры по обнаружению электронных данных Fourth Coffee

- Следователи Fourth Coffee

- Менеджеры по обнаружению электронных данных Coho Winery

- Следователи Coho Winery
  
Чтобы соответствовать требованиям сценария границ соответствия требованиям Contoso,  вы  также удалите роли удержания и экспорта из групп ролей следователей, чтобы не допустить размещения ведерок в расположениях контента и экспорта контента из дела.

## <a name="step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>Шаг 3. Создание фильтра разрешений поиска для обеспечения соблюдения границы соответствия требованиям.

После создания групп ролей для каждого учреждения следующим шагом является создание фильтров разрешений поиска, которые связывают каждую группу ролей с конкретным агентством и определяют границу соответствия требованиям. Необходимо создать один фильтр разрешений поиска для каждого учреждения. Дополнительные сведения о создании фильтров разрешений безопасности см. в дополнительных сведениях о настройке разрешений [фильтрации для поиска контента.](permissions-filtering-for-content-search.md)
  
Вот синтаксис, используемый для создания фильтра разрешений поиска, используемой для границ соответствия требованиям.

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "Site_Path -like '<SharePointURL>*'" -Action <Action>
```

Вот описание каждого параметра в команде:
  
- `FilterName`: Указывает имя фильтра. Используйте имя, в котором описывается или идентифицируется агентство, в котором используется фильтр.

- `Users`: Указывает пользователей или группы, которые получают этот фильтр, применяемый к выполняемым ими поисковым действиям. Для границ соответствия требованиям этот параметр указывает группы ролей (созданные в шаге 3) в созданном вами агентстве фильтра. Обратите внимание, что это параметр с несколькими значениями, поэтому можно включить одну или несколько групп ролей, разделенных запятой.

- `Filters`: Указывает критерии поиска фильтра. Для границ соответствия требованиям необходимо определить следующие фильтры. Каждое из них применяется к расположению контента.

    - `Mailbox`: Указывает почтовые ящики или OneDrive учетные записи, которые могут искать группы ролей, определенные в `Users` параметре. Этот фильтр позволяет членам группы ролей искать только почтовые ящики или OneDrive учетные записи в определенном агентстве; например, `"Mailbox_Department -eq 'FourthCoffee'"` .

    - `Site_Path`: Указывает SharePoint сайты, которые могут искать группы ролей, определенные в `Users` параметре. *SharePointURL* указывает сайты в агентстве, которые могут искать участники группы ролей. Пример: `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`. Обратите `Site` внимание, `Site_Path` что фильтры подключены **оператором или оператором.**

     > [!NOTE]
     > Синтаксис для `Filters` параметра включает список *фильтров.* Список фильтров — это фильтр, который включает фильтр почтовых ящиков и фильтр пути сайта, разделенный запятой. В предыдущем примере обратите внимание, что запятая разделяет Mailbox_MailboxPropertyName **и** **Site_Path** `-Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "Site_Path -like '<SharePointURL>*'"` : . При обработке этого фильтра во время поиска контента из списка фильтров создаются два фильтра разрешений поиска: один фильтр почтовых ящиков и SharePoint фильтр. Альтернативой использованию списка фильтров будет создание двух отдельных фильтров разрешений поиска для каждого учреждения: один фильтр разрешений поиска для атрибута почтового ящика и один фильтр для атрибутов SharePoint сайта. В любом случае результаты будут одинаковыми. Использование списка фильтров или создание отдельных фильтров разрешений поиска — это вопрос предпочтений.

- `Action`: Указывает тип действия поиска, к который применяется фильтр. Например, фильтр применяется только в том случае, если участники группы ролей, определенные в  `-Action Search` `Users` параметре, запускают поиск. В этом случае фильтр не будет применяться при экспорте результатов поиска. Для границ соответствия требованиям используйте фильтр для всех  `-Action All` действий поиска. 

    Список действий поиска см. в разделе "New-ComplianceSecurityFilter" в разделе Настройка разрешений фильтрации [для поиска контента.](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)

Вот примеры двух фильтров разрешений поиска, которые будут созданы для поддержки сценария с ограничениями для соответствия требованиям Contoso. Оба этих примера включают список фильтров, разделенных запятой, в котором фильтры почтовых ящиков и сайтов включены в один фильтр разрешений поиска и разделяются запятой.
  
### <a name="fourth-coffee"></a>Четвертый кофе

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

### <a name="coho-winery"></a>Винодельня Кохо

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-4-create-an-ediscovery-case-for-intra-agency-investigations"></a>Шаг 4. Создание дела об обнаружении электронных сообщений для внутриуровных расследований

На заключительном этапе необходимо создать случай или Advanced eDiscovery core eDiscovery в Центр соответствия требованиям Microsoft 365, а затем добавить группу ролей, созданную в шаге 2 в качестве участника дела. Это приводит к двум важным характеристикам использования границ соответствия требованиям:
  
- Только члены группы ролей, добавленной в дело, смогут видеть и получать доступ к делу в Центре & безопасности. Например, если роль четвертой группы следователей по кофе является единственным участником дела, члены группы ролей менеджеров по обнаружению четвертого кофе (или члены любой другой группы ролей) не смогут увидеть или получить доступ к делу.

- Если член группы ролей, назначенной делу, выполняет поиск, связанный с делом, он сможет искать расположения контента только в своем агентстве (которое определяется фильтром разрешений поиска, созданным в шаге 3.)

Чтобы создать случай и назначить участников:

1. Перейдите на **страницу Core eDiscovery** **или Advanced eDiscovery** в Центр соответствия требованиям Microsoft 365 и создайте случай.

2. В списке случаев щелкните имя созданного случая.

3. Добавление групп ролей в качестве участников в дело. Инструкции см. в одной из следующих статей:

   - [Добавление участников в дело core eDiscovery](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)

   - [Добавление участников в Advanced eDiscovery случае](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

> [!NOTE]
> При добавлении группы ролей в дело можно добавить только группы ролей, в которые вы входите.

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>Поиск и экспорт контента в средах Multi-Geo

Фильтры разрешений поиска также могут управлять маршрутией экспорта контента и поиском центра обработки данных при поиске местоположений контента [в SharePoint с поддержкой нескольких регионов среде.](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)
  
- **Экспорт результатов поиска:** Результаты поиска можно экспортировать из почтовых Exchange, SharePoint сайтов и OneDrive из определенного центра обработки данных. Это означает, что вы можете указать расположение центра обработки данных, из которое будут экспортироваться результаты поиска.

    Используйте параметр **Region** для коммлетов **New-ComplianceSecurityFilter** или **Set-ComplianceSecurityFilter** для создания или изменения центра обработки данных, через который будет проходить экспорт.
  
    |**Значение параметра**|**Расположение центра обработки данных**|
    |:-----|:-----|
    |NAM  <br/> |Северная Америка (центр обработки данных в США)  <br/> |
    |EUR  <br/> |Европа  <br/> |
    |APC  <br/> |Азиатско-Тихоокеанский регион  <br/> |
    |CAN <br/> |Канада|
    |||

- **Поиск контента маршрутов:** Вы можете маршрутить поиск контента SharePoint сайтов и OneDrive учетных записей в спутниковый центр обработки данных. Это означает, что вы можете указать расположение центра обработки данных, где будет вестись поиск.

    Используйте одно из следующих значений для параметра **Region** для управления расположением центра обработки данных, в которое выполняется поиск при поиске SharePoint сайтов и OneDrive учетных записей. 
  
    |**Значение параметра**|**Расположения маршрутов центра обработки данных для SharePoint**|
    |:-----|:-----|
    |NAM  <br/> |Россия  <br/> |
    |EUR  <br/> |Европа  <br/> |
    |APC  <br/> |Азиатско-Тихоокеанский регион  <br/> |
    |CAN  <br/> |Россия  <br/> |
    |AUS  <br/> |Азиатско-Тихоокеанский регион  <br/> |
    |KOR  <br/> |Центр обработки данных по умолчанию организации  <br/> |
    |GBR  <br/> |Европа  <br/> |
    |JPN  <br/> |Азиатско-Тихоокеанский регион  <br/> |
    |IND  <br/> |Азиатско-Тихоокеанский регион  <br/> |
    |LAM  <br/> |Россия  <br/> |
    |NOR  <br/> |Европа |
    |BRA  <br/> |Центр обработки данных в Северной Америке |
    |||

   Если не указать параметр **Region** для фильтра разрешений поиска, будет искаться основной SharePoint области организации. Результаты поиска экспортируются в ближайший центр обработки данных.

   Чтобы упростить концепцию, параметр **Region** управляет центром обработки данных, используемым для поиска контента в SharePoint и OneDrive. Это не относится к поиску контента в Exchange, поскольку Exchange поиска контента не связаны географическим расположением центра обработки данных. Кроме того, одно и то же значение параметра **Region** может также диктовать центр обработки данных, через который проходит экспорт. Это часто необходимо для управления перемещением данных по географическим бортам.

> [!NOTE]
> Если вы используете Advanced eDiscovery, параметр **Region** не контролирует область, из которую экспортируются данные. Данные экспортируются из центрального расположения организации. Кроме того, поиск контента в SharePoint и OneDrive не связан географическим расположением центра обработки данных. Все центра обработки данных находятся в поиске. Дополнительные сведения о Advanced eDiscovery см. в [обзоре решения Advanced eDiscovery в Microsoft 365.](overview-ediscovery-20.md)

Вот примеры использования параметра **Region** при создании фильтров разрешений поиска для границ соответствия требованиям. Это предполагает, что дочерняя компания Fourth Coffee расположена в Северной Америке, а coho Winery — в Европе. 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'" -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'" -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

При поиске и экспорте контента в многоэкранных средах следует помнить о следующих вещах.
  
- Параметр **Регион** не управляет поиском в почтовых ящиках Exchange. Все центра обработки данных будут искаться при поиске почтовых ящиков. Чтобы ограничить область поиска Exchange почтовых ящиков, используйте параметр **Filters** при создании или изменении фильтра разрешений поиска.

- Если менеджеру по поиску электронных данных необходимо искать в нескольких SharePoint регионах, необходимо создать другую учетную запись пользователя для этого диспетчера электронных данных, чтобы использовать в фильтре разрешений поиска, чтобы указать регион, в котором SharePoint или OneDrive учетные записи. Дополнительные сведения о настройке этого раздела см. в разделе "Поиск контента в SharePoint с поддержкой нескольких регионов среде" в [разделе Поиск контента.](content-search-reference.md#searching-for-content-in-a-sharepoint-multi-geo-environment)

- При поиске контента в SharePoint и OneDrive параметр **Region** направляет поиск в основное или спутниковое расположение, где диспетчер по обнаружению электронных данных будет проводить исследования по обнаружению электронных данных. Если менеджер по поиску электронных SharePoint и OneDrive сайтов за пределами региона, указанного в фильтре разрешений поиска, результаты поиска не возвращаются.

- При экспорте результатов поиска из core eDiscovery содержимое из всех местоположений контента (включая Exchange, Skype для бизнеса, SharePoint, OneDrive и другие службы, которые можно искать с помощью средства поиска контента), загружается в расположение служба хранилища Azure в центре обработки данных, указанном параметром **Region.** Это помогает организациям поддерживать соответствие требованиям, не разрешая экспортировать контент через контролируемые границы. Если в фильтре разрешений поиска не указана область, содержимое загружается в основной центр обработки данных организации.

  При экспорте контента из Advanced eDiscovery вы не можете управлять загрузкой контента с помощью **параметра Region.** Содержимое загружается в служба хранилища Azure в центре обработки данных в центре организации. Список географических расположений, основанных на вашем центральном расположении, см. в Microsoft 365 [конфигурации multi-Geo eDiscovery.](../enterprise/multi-geo-ediscovery-configuration.md)

- Чтобы добавить или изменить область, можно изменить существующий фильтр разрешений поиска, выстроив следующую команду:

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a>Использование границ соответствия требованиям для SharePoint узлов

[SharePoint часто](/sharepoint/dev/features/hub-site/hub-site-overview) совпадают с географическими или агентской границами, которые следуют за границами соответствия требованиям eDiscovery. Это означает, что вы можете использовать свойство ID сайта концентратора для создания границы соответствия требованиям. Чтобы сделать это, используйте комлет [Get-SPOHubSite](/powershell/module/sharepoint-online/get-spohubsite#examples) в SharePoint Online PowerShell для получения SiteId для сайта-концентратора, а затем используйте это значение для свойства department ID для создания фильтра разрешений на поиск.

Используйте следующий синтаксис для создания фильтра разрешений поиска для SharePoint узла:

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'" -Action ALL
```

Вот пример создания фильтра разрешений на поиск для сайта концентратора для агентства Виноделия Кохо:

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'" -Action ALL
```

## <a name="compliance-boundary-limitations"></a>Ограничения границ соответствия требованиям

Следует помнить о следующих ограничениях при управлении случаями и расследованиями, которые используют границы соответствия требованиям.
  
- При создании и выполнении поиска можно выбрать расположения содержимого, которые находятся за пределами вашего учреждения. Однако из-за фильтра разрешений поиска содержимое из этих мест не включается в результаты поиска.

- Границы соответствия требованиям не применяются к удерживаниям в случаях с электронным открытием. Это означает, что менеджер по обнаружению электронных данных в одном учреждении может разместить пользователя в другом учреждении на удержании. Однако ограничение для соответствия требованиям будет принудительно применено, если менеджер по обнаружению электронных данных выполняет поиск в расположениях содержимого пользователя, помещенного на удержание. Это означает, что менеджер по обнаружению электронных данных не сможет выполнять поиск в расположениях содержимого пользователя, хотя и может поместить пользователя на удержание.

    Кроме того, статистика удержания будет применяться только к расположениям содержимого в учреждении.

- Если вам назначен фильтр разрешений поиска (почтовый ящик или фильтр сайта) и вы пытаетесь экспортировать неиндексы для поиска, который включает все SharePoint сайты в вашей организации, вы получите следующее сообщение об ошибке: `Unable to execute the task. Reason: The scope options UnindexedItemsOnly or BothIndexedandUnindexedItems are not allowed when the executing user has a compliance security filter applied` . Если вам назначен фильтр разрешений поиска и вы хотите экспортировать неиндексуалные элементы из SharePoint, вам придется повторно перезаключать поиск и включить определенные SharePoint сайты для поиска. В противном случае вы сможете экспортировать индексные элементы только из поиска, который включает все SharePoint сайты. Дополнительные сведения о параметрах при экспорте результатов поиска см. в материалах [поиска Export Content.](export-search-results.md#step-1-prepare-search-results-for-export)

- Фильтры разрешений поиска не применяются к общедоступным папкам Exchange.

## <a name="more-information"></a>Дополнительная информация

- Если почтовый ящик отозвал лицензию или удален, пользователь больше не будет рассматриваться в пределах границы соответствия требованиям. Если при удалении в почтовом ящике было размещено удержание, содержимое, сохраненное в почтовом ящике, по-прежнему подвергается ограничению соответствия требованиям или фильтру разрешений на поиск.

- Если для пользователя реализованы фильтры ограничений соответствия требованиям и разрешений на поиск, рекомендуется не удалять почтовый ящик пользователя, а не OneDrive учетную запись. Другими словами, если вы удалите почтовый ящик пользователя, необходимо также удалить учетную запись OneDrive пользователя, так как mailbox_RecipientFilter используется для применения фильтра разрешений на поиск для OneDrive.

- Границы соответствия требованиям и фильтры разрешений на поиск зависят от атрибутов, штампующих содержимое в Exchange, OneDrive и SharePoint и последующей индексации этого штампованного контента.

- Мы не рекомендуем использовать фильтры исключения (например, фильтр разрешений поиска) для границы соответствия требованиям на основе `-not()` контента. Использование фильтра исключения может иметь неожиданные результаты, если содержимое с недавно обновленными атрибутами не индексировали.

## <a name="frequently-asked-questions"></a>Вопросы и ответы

**Кто можно создавать и управлять фильтрами разрешений поиска (с помощью New-ComplianceSecurityFilter и Set-ComplianceSecurityFilter)?**
  
Чтобы создать, просмотреть и изменить фильтры разрешений поиска, необходимо быть членом группы ролей управления организацией в Центр соответствия требованиям Microsoft 365.
  
**Если менеджеру по обнаружению электронных сообщений назначено несколько групп ролей, охватывающих несколько учреждений, как они ищут контент в одном учреждении или другом?**
  
Менеджер по обнаружению электронных данных может добавлять в поисковый запрос параметры, ограничивающие поиск в определенном агентстве. Например, если организация указала свойство **CustomAttribute10** для дифференцированных учреждений, они могут примкнуть к запросу поиска следующее для поиска почтовых ящиков и OneDrive учетных записей в определенном учреждении: `CustomAttribute10:<value>` .
  
**Что произойдет, если будет изменено значение атрибута, используемого в качестве атрибута соответствия требованиям в фильтре разрешений поиска?**
  
Фильтрация разрешений поиска занимает до трех дней, чтобы обеспечить соблюдение границы соответствия требованиям, если будет изменено значение атрибута, используемого в фильтре. Например, в сценарии Contoso предположим, что пользователь в агентстве Fourth Coffee передается в агентство Винодельни Кохо. В результате значение атрибута **Department** на объекте пользователя меняется с *FourthCoffee* на *CohoWinery.* В этой ситуации четвертое открытие кофе и инвесторы будут получать результаты поиска для этого пользователя в течение трех дней после изменения атрибута. Кроме того, это занимает до трех дней, прежде чем менеджеры и следователи coho Winery eDiscovery получат результаты поиска для пользователя.
  
**Может ли менеджер по обнаружению электронных обнаружений видеть содержимое из двух отдельных границ соответствия требованиям?**
  
Да, это можно сделать при поиске Exchange почтовых ящиков, добавив диспетчера поиска электронных сообщений в группы ролей, которые имеют видимость для обоих учреждений. Однако при поиске SharePoint сайтов и OneDrive учетных записей диспетчер по обнаружению электронных данных может искать контент в различных границах соответствия требованиям, только если учреждения находятся в одном регионе или географическом расположении. **Примечание:** Это ограничение для сайтов не применяется в Advanced eDiscovery, так как поиск контента в SharePoint и OneDrive не связан географическим расположением.
  
**Работают ли фильтры разрешений поиска для хранения данных об обнаружении электронных данных, Microsoft 365 политик хранения или DLP?**
  
Нет, не сейчас.
  
**Если указать регион для управления экспортом контента, но у меня нет SharePoint организации в этом регионе, можно ли SharePoint?**
  
Если область, указанная в фильтре разрешений поиска, не существует в организации, область по умолчанию будет искаться.
  
**Какое максимальное количество фильтров разрешений поиска может быть создано в организации?**
  
Количество фильтров разрешений поиска, которые могут быть созданы в организации, не ограничивается. Однако производительность поиска будет влиять при более чем 100 фильтрах разрешений поиска. Чтобы количество фильтров разрешений поиска в организации было как можно меньше, создайте фильтры, которые по возможности объединяют правила для Exchange, SharePoint и OneDrive в один фильтр разрешений поиска.
