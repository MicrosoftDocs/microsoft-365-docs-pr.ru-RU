---
title: Использование сети доставки содержимого (CDN) Office 365 с SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: Узнайте, как использовать сеть доставки содержимого (CDN) Office 365 для ускорения доставки ресурсов SharePoint Online.
ms.openlocfilehash: 0ef7922f4e8881065f97a5fdeb4f21242c2b6467
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692979"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a>Использование сети доставки содержимого Office 365 с SharePoint Online

Вы можете использовать встроенную сеть доставки содержимого (CDN) Office 365 для размещения статических ресурсов, чтобы повысить производительность страниц SharePoint Online. Сеть CDN Office 365 повышает производительность путем кэширования статических ресурсов ближе к браузерам, которые их запрашивают, что повышает скорость скачиваний и снижает задержку. Кроме того, cdN Office 365 использует [протокол HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) для улучшения сжатия и конвейерной работы HTTP. Служба CDN Office 365 входит в состав подписки на SharePoint Online.

> [!NOTE]
> Сеть CDN Office 365 доступна только для клиентов в облаке **Production** (по всему миру). Клиенты в облаках для правительства США, Китая и Германии в настоящее время не поддерживают CDN Office 365.

Сети доставки содержимого Office 365 состоит из нескольких сетей CDN, позволяющих размещать статические ресурсы в нескольких расположениях или _источниках_ и использовать их из глобальных высокоскоростных сетей. В зависимости от типа содержимого, которое необходимо разместить в сети CDN Office 365, можно добавить **общедоступные** источники, **закрытые** источники или оба варианта. Дополнительные [сведения о](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) различиях между общедоступными и частными источниками см. в под вопросе "Выбор того, должен ли каждый источник быть общедоступным или частным".

![Концептуальная схема CDN Office 365](../media/O365-CDN/o365-cdn-flow-transparent.svg "Концептуальная схема CDN Office 365")

Если вы уже знакомы с работой CDN, вам нужно выполнить всего несколько действий, чтобы включить CDN Office 365 для своего клиента. В этом разделе описывается, как это сделать. Сведения о том, как начать размещение статических ресурсов, можно найти в этом документе.

> [!TIP]
> Существуют и другие сети CDN, которые можно использовать с Office 365 для специальных сценариев использования, но не обсуждаются в этом разделе, так как они не находятся за пределами сети CDN Office 365. Дополнительные сведения [см. в других CDNs Майкрософт.](content-delivery-networks.md#other-microsoft-cdns)

 **Вернуться к [планированию сети и настройке производительности для Office 365.](https://aka.ms/tune)**

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a>Обзор работы с сетью CDN Office 365 в SharePoint Online

Чтобы настроить CDN Office 365 для организации, выполните следующие основные действия.

+ [Планирование развертывания CDN Office 365](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + [Определите, какие статические ресурсы необходимо установить в CDN.](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Определите, где вы хотите хранить активы.](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets) Это расположение может быть сайтом, библиотекой или папкой SharePoint и называется _началом._
  + [Выберите, должен ли каждый источник быть общедоступным или частным.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) Можно добавить несколько источников как общедоступных, так и частных типов.

+ Настройка сети CDN с помощью PowerShell или sharePoint Online CLI

  + [Настройка сети CDN с помощью оболочки управления SharePoint Online](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [Настройка и настройка CDN с помощью PnP PowerShell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [Настройка и настройка CDN с помощью Office 365 CLI](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  После выполнения этого шага у вас будут:

  + Включена CDN для организации.
  + Добавлены ваши источника, определяющие каждый источник как общедоступный или частный.

После настройки вы сможете управлять [CDN Office 365](use-microsoft-365-cdn-with-spo.md#CDNManage) с помощью:
  
+ Добавление, обновление и удаление активов
+ Добавление и удаление источника
+ Настройка политик CDN
+ При необходимости отключать CDN

Наконец, [см. информацию](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) об использовании ресурсов CDN для получения доступа к своим активам CDN как из общедоступных, так и из частных источниках.

Инструкции по устранению распространенных проблем см. в руководстве по устранению неполадок [в CDN Office 365.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)

## <a name="plan-for-deployment-of-the-office-365-cdn"></a>Планирование развертывания CDN Office 365

Перед развертыванием CDN Office 365 для клиента Office 365 необходимо учесть следующие факторы в процессе планирования.

  + [Определение статических ресурсов, которые необходимо установить в CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Определение места хранения активов](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [Выберите, должен ли каждый источник быть общедоступным или частным](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<a name="CDNAssets"> </a>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a>Определение статических ресурсов, которые необходимо установить в CDN

Как правило, CDNs наиболее эффективны для размещения статических ресурсов или _ресурсов,_ которые не изменяются очень часто. Хорошим правилом является определение файлов, которые соответствуют некоторым или всем из этих условий:

+ Статические файлы, внедренные в страницу (например, сценарии и изображения), которые могут существенно повлиять на время загрузки страницы
+ Большие файлы, такие как исполняемые файлы и файлы установки
+ Библиотеки ресурсов, которые поддерживают клиентский код

Например, небольшие файлы, которые постоянно запрашиваются, например изображения сайта и сценарии, могут значительно повысить производительность отображения сайта и постепенно снизить нагрузку на сайты SharePoint Online при добавлении их в источник CDN. Большие файлы, такие как исполняемые файлы установки, можно загрузить из сети CDN, что положительно влияет на производительность и последующее снижение нагрузки на сайт SharePoint Online, даже если к ним не используется так часто.

Повышение производительности для каждого файла зависит от многих факторов, включая близость клиента к ближайшей конечной точке CDN, временные условия в локальной сети и т. д. Многие статические файлы довольно маленькие, и их можно скачать из Office 365 менее чем за секунду. Однако веб-страница может содержать много внедренных файлов с накопительным временем загрузки в несколько секунд. Обслуживание этих файлов из СЕТИ CDN может значительно сократить общее время загрузки страницы. Посмотрите, [какие показатели производительности обеспечивает CDN?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) Например.

<a name="CDNStoreAssets"> </a>
### <a name="determine-where-you-want-to-store-your-assets"></a>Определение места хранения активов

CDN извлекает ресурсы из расположения, называемого _началом._ Источником может быть сайт SharePoint, библиотека документов или папка, доступная по URL-адресу. У вас есть большая гибкость при указании источника для организации. Например, можно указать несколько источников или один источник, в который необходимо поместить все ресурсы CDN. Вы можете выбрать как общедоступные, так и частные источника для вашей организации. Большинство организаций предпочитают реализовать сочетание этих двух вариантов.

Вы можете создать новый контейнер для своего источника, например папок или библиотек документов, и добавить файлы, которые вы хотите сделать доступными из CDN. Это хороший подход, если у вас есть определенный набор ресурсов, которые вы хотите получить из CDN и хотите ограничить набор ресурсов CDN только теми файлами в контейнере.

Можно также настроить существующее коллекцию веб-сайтов, сайт, библиотеку или папку в качестве источника, что сделает все доступные ресурсы в контейнере доступными из СЕТИ CDN. Перед добавлением существующего контейнера в качестве источника важно убедиться, что вы в курсе его содержимого и разрешений, чтобы случайно не дать доступ к активам анонимным пользователям или неавторизованным пользователям.

Вы можете определить политики _CDN,_ чтобы исключить содержимое в источниках из CDN. Политики CDN исключают ресурсы в общедоступных или частных источниках по атрибутам, таким как тип файла и классификация _сайтов,_ и применяются к всем источникам CdnType (закрытого или открытого), задаемого в политике.  Например, при добавлении частного источника, состоящего из сайта, который содержит несколько подсайтов, можно определить политику исключения сайтов, помеченных как конфиденциальные, чтобы контент с сайтов с примененной классификацией не обслуживался из сети CDN.  Политика будет применяться к контенту из _всех частных_ источниках, добавленных в CDN.
  
Помните, что чем больше количество источников, тем больше влияние на время обработки запросов службой CDN. Рекомендуется максимально ограничить количество источников.
  
<a name="CDNOriginChoosePublicPrivate"> </a>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a>Выберите, должен ли каждый источник быть общедоступным или частным

При определении источника указывается, следует ли сделать его общедоступным _или_ _частным._ Доступ к активам CDN в общедоступных источниках является анонимным, а содержимое CDN в частных источниках защищено динамически созданными маркерами для большей безопасности. Независимо от того, какой вариант вы выберете, Корпорация Майкрософт делает все возможное для вас, когда речь идет об администрировании самой CDN. Кроме того, вы можете изменить свое решение позже, после того как настроите CDN и настроите свои происхождение.

Как общедоступные, так и частные варианты обеспечивают одинаковый рост производительности, но каждый из них имеет уникальные атрибуты и преимущества.

**Общедоступные** источники в сети CDN Office 365 доступны анонимно, а к общедоступным активам может получить доступ любой, у кого есть URL-адрес актива. Так как доступ к содержимому в общедоступных источниках является анонимным, следует использовать их только для кэширования неконфиденциального общего содержимого, например файлов JavaScript, скриптов, значков и изображений.

**Частные** источника в сети CDN Office 365 предоставляют закрытый доступ к пользовательскому контенту, например библиотекам документов SharePoint Online, сайтам и проприетарным изображениям. Доступ к контенту в частных источниках защищен динамически созданными маркерами, поэтому доступ к нему могут получить только пользователи с разрешениями на доступ к исходной библиотеке документов или месту хранения. Частные источника в сети CDN Office 365 можно использовать только для контента SharePoint Online, и доступ к активам в частных источниках можно получить только через перенаправление из клиента SharePoint Online.

Подробнее о том, как работает доступ к активам в частном источнике в СЕТИ CDN, можно узнать в документе "Использование ресурсов [в частных источниках".](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a>Атрибуты и преимущества размещения активов в общедоступных источниках
  
+ Ресурсы, предоставляемые из общедоступного источника, доступны всем анонимно.
    > [!IMPORTANT]
    > Никогда не следует разместить ресурсы, которые содержат сведения о пользователе или считаются конфиденциальными для вашей организации, в общедоступных источниках.
+ Если удалить ресурс из общедоступного источника, он может оставаться доступным в кэше до 30 дней. Однако ссылки на ресурс в сети CDN станут недействительными в течение 15 минут.
+ При размещении таблиц стилей (CSS-файлов) в общедоступном источнике можно использовать в коде относительные пути и URI. Это означает, что вы можете ссылаться на расположение фоновых изображений и других объектов относительно расположения ресурса, который вызывает его.
+ Вы можете жестко задать URL-адрес общедоступного источника, но это не рекомендуется. Это связано с тем, что если сеть CDN станет недоступна, то URL-адрес не будет автоматически указывать на вашу организацию в SharePoint Online, что может привести к неработоспособности ссылок и другим ошибкам.
+ Типы файлов по умолчанию, включенные в общедоступные источника: CSS, EOT, GIF, ICO, JPEG, JPG, JS, MAP, PNG, SVG, TTF, WOFF и WOFF2. Можно указать дополнительные типы файлов.
+ Вы можете настроить политику, чтобы исключить ресурсы, выявленные по заданной классификации сайтов. Например, вы можете исключать все ресурсы, отмеченные как "конфиденциальные" или "с ограниченным доступом", даже если они относятся к разрешенным типам файлов и находятся в общедоступном источнике.

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a>Атрибуты и преимущества размещения активов в частных источниках

+ Частные источника можно использовать только для активов SharePoint Online.
+ Пользователи могут получить доступ к активам только из частного источника, если у них есть разрешения на доступ к контейнеру. Анонимный доступ к таким ресурсам запрещен.
+ Ресурсы в частных источниках должны быть переданы из клиента SharePoint Online. Прямой доступ к частным активам CDN не работает.
+ Если удалить ресурс из частного источника, актив может оставаться доступным в течение часа из кэша; Однако ссылки на ресурс в CDN будут недействительны в течение 15 минут после удаления актива.
+ По умолчанию для частных источников включены типы файлов GIF, ICO, JPEG, JPG, JS и PNG. Можно указать дополнительные типы файлов.
+ Как и в случае с общедоступными источниками, можно настроить политику для исключения активов, которые определены в классификациях сайтов, которые указываются, даже если вы используете поддиаптер для всех ресурсов в папке или библиотеке документов.

Дополнительные сведения о том, зачем использовать сеть CDN Office 365, общие концепции CDN и другие [](content-delivery-networks.md)сети CDN Майкрософт, которые можно использовать с клиентом Office 365, см. в подсетях доставки содержимого.

### <a name="default-cdn-origins"></a>Источника CDN по умолчанию

Если вы не указали иное, Office 365 настраивает некоторые стандартные источника для вас, когда вы включаете CDN Office 365. Если изначально вы решили не заполнять их, вы можете добавить эти источника после завершения настройки. Если вы не понимаете последствия пропуска настройки источника по умолчанию и не имеете особой причины для этого, следует разрешить их создавать при в сети CDN.
  
Частные источника CDN по умолчанию:
  
+ \*/userphoto.aspx
+ \*/siteassets

Общедоступные источника CDN по умолчанию:
  
+ \*/masterpage
+ \*/style library
+ \*/clientsideassets

> [!NOTE]
> _clientsideassets_ — это общедоступный источник по умолчанию, который был добавлен в службу CDN Office 365 в декабре 2017 г. Этот источник должен присутствовать, чтобы решения SharePoint Framework в CDN работали. Если вы включили CDN Office 365 до декабря 2017 г. или пропустили настройку источника по умолчанию при включив CDN, вы можете вручную добавить этот источник. Дополнительные сведения см. в сведениях о том, как не работает моя клиентская веб-часть или решение [SharePoint Framework.](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)

<a name="CDNSetupinPShell"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a>Настройка сети CDN Office 365 с помощью оболочки управления SharePoint Online

Процедуры в этом разделе требуют использования оболочки управления SharePoint Online для подключения к SharePoint Online. Инструкции см. в статье [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

Выполните следующие действия, чтобы настроить СЕТЬ CDN для организации активов в SharePoint Online с помощью оболочки управления SharePoint Online.

<details>
  <summary>Щелкните, чтобы развернуть</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Включить в организации использование CDN Office 365

Перед внесением изменений в параметры сети CDN клиента необходимо получить текущее состояние конфигурации частной сети CDN в клиенте Office 365. Подключитесь к вашему арендатору с помощью оболочки управления SharePoint Online:

``` powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

Теперь используйте для извлечения параметров состояния CDN из клиента с помощью cmdlet **Get-SPOTenantCdnEnabled:**

``` powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

Состояние CDN для указанного CdnType будет выводит на экран.

Используйте для организации использование CDN Office 365 с помощьюлета **Set-SPOTenantCdnEnabled.** Вы можете позволить организации использовать общедоступные, частные или оба источника одновременно. Кроме того, можно настроить CDN так, чтобы она пропускала установку источника по умолчанию при ее в сети. Вы всегда можете добавить эти источника позже, как описано в этом разделе.
  
В Windows Powershell для SharePoint Online:

``` powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Например, чтобы позволить организации использовать как общедоступные, так и частные источника, введите следующую команду:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

Чтобы позволить организации использовать как общедоступные, так и частные источника, но пропустить настройку источника по умолчанию, введите следующую команду:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

В [источниках CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) по умолчанию вы можете получить сведения об источниках, которые по умолчанию одежные при в сети CDN Office 365, а также о возможном влиянии пропуска настройки источника по умолчанию.

Чтобы позволить организации использовать общедоступные источника, введите следующую команду:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

Чтобы позволить организации использовать частные источника, введите следующую команду:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

Дополнительные сведения об этомлете см. в подстроке [Set-SPOTenantCdnEnabled.](https://technet.microsoft.com/library/mt790765.aspx)

<a name="Office365CDNforSPOFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Изменение списка типов файлов для включаемой в CDN Office 365 (необязательно)

> [!TIP]
> При определении типов файлов с помощью **cmdlet Set-SPOTenantCdnPolicy** переопределяется текущий список. Если вы хотите добавить в список дополнительные типы файлов, сначала используйте этот cmdlet, чтобы узнать, какие типы файлов уже разрешены, и включите их в список вместе с новыми.
  
С помощью **cmdlet Set-SPOTenantCdnPolicy** определите статические типы файлов, которые могут быть установлены общедоступными и частными источниками в CDN. По умолчанию разрешены общие типы активов, например CSS, GIF, JPG и JS.

В Windows PowerShell sharePoint Online:

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Например, чтобы включить CDN для хост-файлов CSS и PNG, необходимо ввести команду:

``` powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Чтобы узнать, какие типы файлов в настоящее время разрешены CDN, используйте **cmdlet Get-SPOTenantCdnPolicies:**

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Дополнительные сведения об этих cmdlets см. в [настройках Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) и [Get-SPOTenantCdnPolicies.](https://technet.microsoft.com/library/mt800838.aspx)

<a name="Office365CDNforSPOSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Изменение списка классификаций сайтов, которые необходимо исключить из сети CDN Office 365 (необязательно)

> [!TIP]
> При исключении классификаций сайтов с помощью **cmdlet Set-SPOTenantCdnPolicy** переопределяется текущий определенный список. Если вы хотите исключить дополнительные классификации сайтов, сначала используйте его, чтобы узнать, какие классификации уже исключены, а затем добавьте их вместе с новыми.

Чтобы исключить классификации сайтов, которые не должны быть доступны в сети CDN, используйте командлет **Set-SPOTenantCdnPolicy**. По умолчанию не исключаются никакие классификации сайтов.

В Windows PowerShell sharePoint Online:

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

Чтобы узнать, какие классификации сайтов в настоящее время ограничены, используйте **cmdlet Get-SPOTenantCdnPolicies:**

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Будут возвращены следующие _свойства: IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ и _ExcludeIfNoScriptDisabled._

Свойство _IncludeFileExtensions_ содержит список расширений файлов, которые будут обслуживаться из CDN.

> [!NOTE]
> Расширения файлов по умолчанию отличаются между общедоступными и частными.

Свойство _ExcludeRestrictedSiteClassifications_ содержит классификации сайтов, которые необходимо исключить из CDN. Например, можно исключить сайты, помеченные как конфиденциальные, чтобы контент сайтов с примененной классификацией не обслуживался из сети CDN. 

Свойство _ExcludeIfNoScriptDisabled_ исключает контент из СЕТИ CDN на основе параметров атрибута _NoScript_ на уровне сайта. По умолчанию атрибут _NoScript_ имеет значение **Enabled** _для_ современных сайтов и **Disabled для** _классических_ сайтов. Это зависит от параметров клиента.

Дополнительные сведения об этих cmdlets см. в [настройках Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) и [Get-SPOTenantCdnPolicies.](https://technet.microsoft.com/library/mt800838.aspx)

<a name="Office365CDNforSPOOriginPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Добавление источника для активов

Чтобы определить источник, используйте **cmdlet Add-SPOTenantCdnOrigin.** Вы можете определить несколько источников. Источник — это URL-адрес, указывающий на библиотеку или папку в SharePoint, содержащую ресурсы, которые требуется размещать в сети CDN.
  
> [!IMPORTANT]
> Никогда не следует разместить ресурсы, которые содержат сведения о пользователе или считаются конфиденциальными для вашей организации, в общедоступных источниках.

``` powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

Значение пути _— это_ относительный путь к библиотеке или папке, в которую входят активы. Помимо относительных путей, можно использовать подстановочные знаки. В источниках поддерживаются поддиапцы в начале URL-адреса. Это позволяет создавать источника, охватывающие несколько сайтов. Например, чтобы включить все ресурсы в папку masterpages для всех сайтов в качестве общего источника в сети CDN, введите следующую команду:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ Модификатор с подданными знаками * можно использовать только в начале пути и будет соответствовать всем сегментам URL-адресов по **/** указанному URL-адресу.
+ Путь может указать на библиотеку документов, папку или сайт. Например, путь _*/site1_ будет соответствовать всем библиотекам документов на сайте.

Вы можете добавить источник с определенным относительным путем. Нельзя добавить источник с использованием полного пути.

В этом примере добавляется частный источник библиотеки siteassets на определенном сайте:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

В этом примере добавляется частный источник папки _folder1_ в библиотеке активов сайта этого сайта:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Если путь имеет пробел, его можно либо заместить двойными кавычками, либо заменить пробел кодировка URL-адреса %20. В следующих примерах добавляется частный источник папки _1_ в библиотеке активов сайта этого веб-сайта:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Дополнительные сведения об этой команде и ее синтаксис см. в под названием [Add-SPOTenantCdnOrigin.](https://technet.microsoft.com/library/mt790772.aspx)

> [!NOTE]
> В частных источниках для доступа к активам из источника должна быть опубликована основная версия.
  
После запуска команды система синхронизирует конфигурацию между центрами обработки данных. Это может занять до 15 минут.

<a name="ExamplePublicOrigin"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Пример. Настройка общего источника для этастерных страниц и библиотеки стилей для SharePoint Online

Как правило, эти источника задаются для вас по умолчанию при в том случае, если вы включаете CDN Office 365. Однако если вы хотите включить их вручную, выполните следующие действия.
  
+ Чтобы определить библиотеку стилей как общедоступный источник, используйте cmdlet **Add-SPOTenantCdnOrigin.**

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Чтобы определить эталонные страницы в качестве общедоступных, используйте для этого cmdlet **Add-SPOTenantCdnOrigin.**

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Дополнительные сведения об этой команде и ее синтаксис см. в под названием [Add-SPOTenantCdnOrigin.](https://technet.microsoft.com/library/mt790772.aspx)

После запуска команды система синхронизирует конфигурацию между центрами обработки данных. Это может занять до 15 минут.

<a name="ExamplePrivateOrigin"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Пример. Настройка частного источника для ресурсов сайта, страниц сайта и изображений публикации для SharePoint Online

+ Чтобы определить папку ресурсов сайта как частный источник, используйте для этого cmdlet **Add-SPOTenantCdnOrigin.**

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Чтобы определить папку страниц сайта как частный источник, используйте для этого cmdlet **Add-SPOTenantCdnOrigin.**

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Чтобы определить папку опубликованных изображений как частный источник, используйте для определения папки изображений публикации с помощью cmdlet **Add-SPOTenantCdnOrigin.**

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Дополнительные сведения об этой команде и ее синтаксис см. в под названием [Add-SPOTenantCdnOrigin.](https://technet.microsoft.com/library/mt790772.aspx)

После запуска команды система синхронизирует конфигурацию между центрами обработки данных. Это может занять до 15 минут.

<a name="ExamplePrivateOriginSiteCollection"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Пример. Настройка частного источника для коллекции веб-сайтов для SharePoint Online

Чтобы определить коллекцию веб-сайтов как частный источник, используйте для этого cmdlet **Add-SPOTenantCdnOrigin.** Пример:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Дополнительные сведения об этой команде и ее синтаксис см. в под названием [Add-SPOTenantCdnOrigin.](https://technet.microsoft.com/library/mt790772.aspx)
  
После запуска команды система синхронизирует конфигурацию между центрами обработки данных. Вы можете увидеть _ожидающих_ сообщений о конфигурации, которые ожидаются по мере подключения клиента SharePoint Online к службе CDN. Это может занять до 15 минут.

<a name="CDNManage"> </a>
### <a name="manage-the-office-365-cdn"></a>Управление CDN Office 365

Настроив CDN, вы можете внести изменения в конфигурацию при обновлении содержимого или изменении потребностей, как описано в этом разделе.
  
<a name="Office365CDNforSPOaddremoveasset"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Добавление, обновление и удаление ресурсов из CDN Office 365

После завершения действий по настройке можно добавлять новые активы, а также обновлять или удалять существующие активы, когда это необходимо. Просто внести изменения в ресурсы в папке или библиотеке SharePoint, которые вы определили как источник. При добавлении нового актива он сразу же будет доступен через CDN. Однако при обновлении актива распространение новой копии и ее распространение в CDN займет до 15 минут.
  
Если вам нужно получить расположение источника, можно использовать **cmdlet Get-SPOTenantCdnOrigins.** Сведения об использовании этого cmdlet см. в сведениях [о get-SPOTenantCdnOrigins.](https://technet.microsoft.com/library/mt790770.aspx)

<a name="Office365CDNforSPORemoveOriginPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Удаление источника из CDN Office 365

Можно удалить доступ к папке или библиотеке SharePoint, которые определены как источник. Для этого используйте cmdlet **Remove-SPOTenantCdnOrigin.**

``` powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Сведения об использовании этого cmdlet см. в [remove-SPOTenantCdnOrigin.](https://technet.microsoft.com/library/mt790761.aspx)

<a name="Office365CDNforSPOModifyOrigin"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Изменение источника в CDN Office 365

Вы не можете изменить созданный источник. Вместо этого удалите источник и добавьте новый. Дополнительные сведения см. в сведениях о том, как удалить источник из [CDN Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) и добавить источник [ресурсов.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Отключение CDN Office 365

Используйте для отключения CDN для организации с помощью **cmdlet Set-SPOTenantCdnEnabled.** Если для CDN включены как общедоступные, так и частные источника, необходимо выполнить его дважды, как показано в следующих примерах.
  
Чтобы отключить использование общедоступных источника в CDN, введите следующую команду:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

Чтобы отключить использование частных источника в CDN, введите следующую команду:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

Дополнительные сведения об этомлете см. в подстроке [Set-SPOTenantCdnEnabled.](https://technet.microsoft.com/library/mt790765.aspx)

</details>

<a name="CDNSetupinPnPPosh"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a>Настройка и настройка CDN Office 365 с помощью PnP PowerShell

В процедурах этого раздела для подключения к SharePoint Online необходимо использовать PnP PowerShell. Инструкции см. в [инструкциях по началу работы с PnP PowerShell.](https://github.com/SharePoint/PnP-PowerShell#getting-started)

Выполните указанные здесь действия, чтобы настроить сеть CDN для работы с активами в SharePoint Online с помощью PnP PowerShell.

<details>
  <summary>Щелкните, чтобы развернуть</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Включить в организации использование CDN Office 365

Перед внесением изменений в параметры сети CDN клиента необходимо получить текущее состояние конфигурации частной сети CDN в клиенте Office 365. Подключите клиент с помощью PnP PowerShell:

``` powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

Теперь с помощью **get-PnPTenantCdnEnabled** извлекает параметры состояния CDN из клиента:

``` powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

Состояние CDN для указанного CdnType будет выводит на экран.

Используйте для организации использование CDN Office 365 с помощьюлета **Set-PnPTenantCdnEnabled.** Вы можете позволить организации одновременно использовать общедоступные, частные или оба источника. Кроме того, можно настроить CDN так, чтобы она пропускала установку источника по умолчанию при ее в сети. Вы всегда можете добавить эти источника позже, как описано в этом разделе.
  
В PnP PowerShell:

``` powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Например, чтобы позволить организации использовать как общедоступные, так и частные источника, введите следующую команду:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

Чтобы позволить организации использовать как общедоступные, так и частные источника, но пропустить настройку источника по умолчанию, введите следующую команду:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

В [источниках CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) по умолчанию вы можете получить сведения об источниках, которые по умолчанию одежные при в сети CDN Office 365, а также о возможном влиянии пропуска настройки источника по умолчанию.

Чтобы позволить организации использовать общедоступные источника, введите следующую команду:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

Чтобы позволить организации использовать частные источника, введите следующую команду:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

Дополнительные сведения об этомлете см. в подстроке [Set-PnPTenantCdnEnabled.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)

<a name="Office365CDNforPnPPoshFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Изменение списка типов файлов для включаемой в CDN Office 365 (необязательно)

> [!TIP]
> При определении типов файлов с помощью **cmdlet Set-PnPTenantCdnPolicy** переопределяется текущий список. Если вы хотите добавить в список дополнительные типы файлов, сначала используйте этот cmdlet, чтобы узнать, какие типы файлов уже разрешены, и включите их в список вместе с новыми.
  
С помощью **cmdlet Set-PnPTenantCdnPolicy** определите статические типы файлов, которые могут быть установлены общедоступными и частными источниками в CDN. По умолчанию разрешены общие типы активов, например CSS, GIF, JPG и JS.

В PnP PowerShell:

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Например, чтобы включить CDN для хост-файлов CSS и PNG, необходимо ввести команду:

``` powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Чтобы узнать, какие типы файлов в настоящее время разрешены CDN, используйте **cmdlet Get-PnPTenantCdnPolicies:**

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Дополнительные сведения об этих cmdlets см. в [настройках Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) и [Get-PnPTenantCdnPolicies.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)

<a name="Office365CDNforPnPPoshSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Изменение списка классификаций сайтов, которые необходимо исключить из сети CDN Office 365 (необязательно)

> [!TIP]
> При исключении классификаций сайтов с помощью **cmdlet Set-PnPTenantCdnPolicy** переопределяется текущий определенный список. Если вы хотите исключить дополнительные классификации сайтов, сначала используйте его, чтобы узнать, какие классификации уже исключены, а затем добавьте их вместе с новыми.

Чтобы **исключить** классификации сайтов, которые не требуется делать доступными через CDN, используйте для исключения классификаций сайтов, которые не должны быть доступны через CDN. По умолчанию не исключаются никакие классификации сайтов.

В PnP PowerShell:

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

Чтобы узнать, какие классификации сайтов в настоящее время ограничены, используйте **cmdlet Get-PnPTenantCdnPolicies:**

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Будут возвращены следующие _свойства: IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ и _ExcludeIfNoScriptDisabled._

Свойство _IncludeFileExtensions_ содержит список расширений файлов, которые будут обслуживаться из CDN.

> [!NOTE]
> Расширения файлов по умолчанию отличаются между общедоступными и частными.

Свойство _ExcludeRestrictedSiteClassifications_ содержит классификации сайтов, которые необходимо исключить из CDN. Например, можно исключить сайты, помеченные как конфиденциальные, чтобы контент сайтов с примененной классификацией не обслуживался из сети CDN. 

Свойство _ExcludeIfNoScriptDisabled_ исключает контент из СЕТИ CDN на основе параметров атрибута _NoScript_ на уровне сайта. По умолчанию атрибут _NoScript_ имеет значение **Enabled** _для_ современных сайтов и **Disabled для** _классических_ сайтов. Это зависит от параметров клиента.

Дополнительные сведения об этих cmdlets см. в [настройках Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) и [Get-PnPTenantCdnPolicies.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)

<a name="Office365CDNforSPOOriginPnPPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Добавление источника для активов

Чтобы определить источник, используйте **cmdlet Add-PnPTenantCdnOrigin.** Вы можете определить несколько источников. Источник — это URL-адрес, указывающий на библиотеку или папку в SharePoint, содержащую ресурсы, которые требуется размещать в сети CDN.
  
> [!IMPORTANT]
> Никогда не следует разместить ресурсы, которые содержат сведения о пользователе или считаются конфиденциальными для вашей организации, в общедоступных источниках.

``` powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

Значение пути _— это_ относительный путь к библиотеке или папке, в которую входят активы. Помимо относительных путей, можно использовать подстановочные знаки. В источниках поддерживаются поддиапцы в начале URL-адреса. Это позволяет создавать источника, охватывающие несколько сайтов. Например, чтобы включить все ресурсы в папку masterpages для всех сайтов в качестве общего источника в сети CDN, введите следующую команду:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ Модификатор с подданными знаками * можно использовать только в начале пути и будет соответствовать всем сегментам URL-адресов по **/** указанному URL-адресу.
+ Путь может указать на библиотеку документов, папку или сайт. Например, путь _*/site1_ будет соответствовать всем библиотекам документов на сайте.

Вы можете добавить источник с определенным относительным путем. Нельзя добавить источник с использованием полного пути.

В этом примере добавляется частный источник библиотеки активов сайта на определенном сайте:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

В этом примере добавляется частный источник папки _folder1_ в библиотеке активов сайта этого сайта:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Если путь имеет пробел, его можно либо заместить двойными кавычками, либо заменить пробел кодировка URL-адреса %20. В следующих примерах добавляется частный источник папки _1_ в библиотеке активов сайта этого веб-сайта:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Дополнительные сведения об этой команде и ее синтаксис см. в под названием [Add-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)

> [!NOTE]
> В частных источниках для доступа к активам из источника должна быть опубликована основная версия.
  
После запуска команды система синхронизирует конфигурацию между центрами обработки данных. Это может занять до 15 минут.

<a name="ExamplePublicOriginPnPPosh"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Пример. Настройка общего источника для этастерных страниц и библиотеки стилей для SharePoint Online

Как правило, эти источника задаются для вас по умолчанию при в том случае, если вы включаете CDN Office 365. Однако если вы хотите включить их вручную, выполните следующие действия.
  
+ Чтобы определить библиотеку стилей как общедоступный источник, используйте для этого cmdlet **Add-PnPTenantCdnOrigin.**

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Используйте для определения эталонных страниц в качестве общедоступных источника с помощью **cmdlet Add-PnPTenantCdnOrigin.**

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Дополнительные сведения об этой команде и ее синтаксис см. в под названием [Add-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)

После запуска команды система синхронизирует конфигурацию между центрами обработки данных. Это может занять до 15 минут.

<a name="ExamplePrivateOriginPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Пример. Настройка частного источника для ресурсов сайта, страниц сайта и изображений публикации для SharePoint Online

+ Чтобы определить папку ресурсов сайта как частный источник, используйте для этого cmdlet **Add-PnPTenantCdnOrigin.**

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Чтобы определить папку страниц сайта в качестве частного источника, используйте **cmdlet Add-PnPTenantCdnOrigin.**

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Чтобы определить папку изображений публикации как частный источник, используйте для этого cmdlet **Add-PnPTenantCdnOrigin.**

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Дополнительные сведения об этой команде и ее синтаксис см. в под названием [Add-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)

После запуска команды система синхронизирует конфигурацию между центрами обработки данных. Это может занять до 15 минут.

<a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Пример. Настройка частного источника для коллекции веб-сайтов для SharePoint Online

Чтобы определить коллекцию веб-сайтов как частный источник, используйте для этого **cmdlet Add-PnPTenantCdnOrigin.** Пример:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Дополнительные сведения об этой команде и ее синтаксис см. в под названием [Add-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)
  
После запуска команды система синхронизирует конфигурацию между центрами обработки данных. Вы можете увидеть _ожидающих_ сообщений о конфигурации, которые ожидаются по мере подключения клиента SharePoint Online к службе CDN. Это может занять до 15 минут.

<a name="CDNManagePnPPosh"> </a>
### <a name="manage-the-office-365-cdn"></a>Управление CDN Office 365

Настроив CDN, вы можете внести изменения в конфигурацию при обновлении содержимого или изменении потребностей, как описано в этом разделе.
  
<a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Добавление, обновление и удаление ресурсов из CDN Office 365

После завершения действий по настройке можно добавлять новые активы, а также обновлять или удалять существующие активы, когда это необходимо. Просто внести изменения в ресурсы в папке или библиотеке SharePoint, которые вы определили как источник. При добавлении нового актива он сразу же будет доступен через CDN. Однако при обновлении актива распространение новой копии и ее распространение в CDN займет до 15 минут.
  
Если вам нужно получить расположение источника, можно использовать **cmdlet Get-PnPTenantCdnOrigin.** Сведения об использовании этого cmdlet см. в подтипе [Get-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)

<a name="Office365CDNforSPORemoveOriginPnPPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Удаление источника из CDN Office 365

Можно удалить доступ к папке или библиотеке SharePoint, которые определены как источник. Для этого используйте **cmdlet Remove-PnPTenantCdnOrigin.**

``` powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Сведения о том, как использовать этот cmdlet, см. в [remove-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).

<a name="Office365CDNforSPOModifyOriginPnPPosh"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Изменение источника в CDN Office 365

Вы не можете изменить созданный источник. Вместо этого удалите источник и добавьте новый. Дополнительные сведения см. в сведениях о том, как удалить источник из [CDN Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) и добавить источник [ресурсов.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Отключение CDN Office 365

Используйте для отключения CDN для организации с помощью **cmdlet Set-PnPTenantCdnEnabled.** Если для CDN включены как общедоступные, так и частные источника, необходимо выполнить его дважды, как показано в следующих примерах.
  
Чтобы отключить использование общедоступных источника в CDN, введите следующую команду:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

Чтобы отключить использование частных источника в CDN, введите следующую команду:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

Дополнительные сведения об этомлете см. в подстроке [Set-PnPTenantCdnEnabled.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)

</details>

<a name="CDNSetupinCLI"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a>Установка и настройка сети CDN Office 365 с помощью интерфейса командной строки Office 365:

Для процедур в этом разделе необходимо установить [Office 365 CLI.](https://aka.ms/o365cli) Затем подключите клиент Office 365 с помощью команды [входа.](https://pnp.github.io/office365-cli/cmd/login/)

Выполните указанные действия, чтобы настроить сеть CDN для работы с активами в SharePoint Online с помощью Office 365 CLI.

<details>
  <summary>Щелкните, чтобы развернуть</summary>

### <a name="enable-the-office-365-cdn"></a>Включить CDN Office 365

Вы можете управлять состоянием сети CDN Office 365 в клиенте с помощью команды [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/).

Чтобы включить в клиенте общедоступную сеть CDN Office 365, выполните следующую команду:

```sh
spo cdn set --type Public --enabled true
```

Чтобы включить CDN Office 365 SharePoint, выполните 3:

```sh
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a>Просмотр текущего состояния сети CDN Office 365

Чтобы проверить, включен ли определенный тип CDN Office 365, используйте команду [получения spo cdn.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)

Чтобы проверить, включена ли общедоступная сеть CDN Office 365, выполните следующую команду:

```sh
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a>Просмотр источника CDN Office 365

Чтобы просмотреть список настроенных в данный момент общедоступных источников CDN Office 365, выполните следующую команду:

```sh
spo cdn origin list --type Public
```

В [источниках CDN по](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) умолчанию вы можете получить сведения об источниках, которые по умолчанию являются резервами при ветвии CDN Office 365.

### <a name="add-an-office-365-cdn-origin"></a>Добавление источника CDN Office 365

> [!IMPORTANT]
> Никогда не следует разместить ресурсы, которые считаются конфиденциальными для вашей организации, в библиотеку документов SharePoint, настроенную как общедоступный источник.

Чтобы определить источник CDN, используйте команду [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/). Вы можете определить несколько источников. Источник — это URL-адрес, указывающий на библиотеку или папку в SharePoint, содержащую ресурсы, которые требуется размещать в сети CDN.

```sh
spo cdn origin add --type [Public | Private] --origin <path>
```

Где `path` находится относительный путь к папке с активами. Помимо относительных путей, можно использовать подстановочные знаки.

Чтобы включить все ресурсы в галерею **этастерных страниц** для всех сайтов в качестве общедоступных, выполните следующие реализации:

```sh
spo cdn origin add --type Public --origin */masterpage
```

Чтобы настроить частный источник для определенного семейства веб-сайтов, выполните следующую команду:

```sh
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> После добавления источника CDN может понадобиться до 15 минут, чтобы получить файлы через службу CDN. Вы можете проверить, включен ли тот или иной источник, с помощью команды [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/).

### <a name="remove-an-office-365-cdn-origin"></a>Удаление источника CDN Office 365

Чтобы удалить источник CDN для указанного типа CDN, используйте команду [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/).

Чтобы удалить общедоступный источник из конфигурации CDN, выполните ок.

```sh
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> Удаление источника CDN не влияет на файлы, хранимые в любой библиотеке документов, которая соответствует этому источнику. Если на эти ресурсы ссылались с помощью URL-адреса SharePoint, SharePoint автоматически вернется к исходному URL-адресу, указывав на библиотеку документов. Однако если ссылки на ресурсы были указаны с использованием URL-адреса общедоступных CDN, удаление источника разрывает ссылку, и вам потребуется вручную изменить их.

### <a name="modify-an-office-365-cdn-origin"></a>Изменение источника CDN Office 365

Изменить имеющийся источник CDN невозможно. Вместо этого следует удалить определенный ранее источник CDN с помощью команды `spo cdn origin remove` и добавить новый с помощью команды `spo cdn origin add`.

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a>Изменение типов файлов для включаемой в CDN Office 365

По умолчанию в CDN включены следующие типы файлов: _CSS, EOT, GIF, ICO, JPEG, JPG, JS, MAP, PNG, SVG, TTF, WOFF и WOFF2._ Если требуется включить в сеть CDN дополнительные типы файлов, вы можете изменить конфигурацию CDN с помощью команды [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/).

> [!NOTE]
> При изменении списка типов файлов перезаписывается текущий список. Если требуется включить дополнительные типы файлов, сперва используйте команду [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/), чтобы узнать, какие типы файлов настроены в текущий момент.

Чтобы добавить _тип файла JSON_ в список типов файлов по умолчанию, включенных в обную CDN, выполните 2.

```sh
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a>Изменение списка классификаций сайтов, которые требуется исключить из сети CDN Office 365

Чтобы исключить классификации сайтов, которые не должны быть доступны в сети CDN, используйте команду [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/). По умолчанию не исключаются никакие классификации сайтов.

> [!NOTE]
> При изменении списка исключаемых классификаций сайтов перезаписывается текущий список. Если требуется исключить дополнительные классификации сайтов, сперва используйте команду [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/), чтобы узнать, какие классификации настроены в текущий момент.

Чтобы исключить сайты, классифицированные как _HBI,_ из публичной сети CDN, выполните

```sh
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a>Отключение CDN Office 365

Чтобы отключить сеть CDN Office 365, используйте команду `spo cdn set`. Пример:

```sh
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a>Использование ресурсов CDN

Теперь, когда вы включили CDN и настроили источника и политики, можно приступить к использованию ресурсов CDN.

Этот раздел поможет вам понять, как использовать URL-адреса CDN на страницах и содержимом SharePoint, чтобы SharePoint перенаправляет запросы на ресурсы из общедоступных и частных источниках в CDN.

+ [Обновление ссылок на ресурсы CDN](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [Использование ресурсов в общедоступных источниках](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [Использование ресурсов в частных источниках](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

Сведения об использовании СЕТИ CDN для размещения клиентских веб-частей см. в разделе "Размещение клиентской веб-части из сети [CDN Office 365 (Hello World, часть 4)](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)".

> [!NOTE]
> Если добавить папку _ClientSideAssets_  в частный список источников CDN, пользовательские веб-части, в которые будет добавлена сеть CDN, не будут отрисовки. Файлы, используемые веб-частями SPFX, могут использовать только общедоступные сети CDN, а папка ClientSideAssets является источником по умолчанию для общедоступных CDN. 

### <a name="updating-links-to-cdn-assets"></a>Обновление ссылок на ресурсы CDN

Чтобы использовать ресурсы, добавленные в источник, необходимо просто обновить ссылки на исходный файл с путем к файлу в источнике.

+ Изменить страницу или контент, содержащий ссылки на ресурсы, добавленные в источник. Вы также можете использовать один из нескольких методов для глобального поиска и замены ссылок на сайт или введите в коллекцию веб-сайтов, если вы хотите обновить ссылку на заданный актив везде, где она отображается.
+ Для каждой ссылки на ресурс в источнике замените путь путем к файлу в источнике CDN. Можно использовать относительные пути.
+ Сохраните страницу или содержимое.

Например, рассмотрим изображение _/site/SiteAssets/images/image.png,_ которое вы скопировали в папку библиотеки документов _/site/CDN_origins/public/_. Чтобы использовать ресурс CDN, замените исходный путь к расположению файла изображения путем к источнику, чтобы новый URL-адрес _/site/CDN_origins/public/image.png_.

Если вы хотите использовать полный URL-адрес актива вместо относительного пути, состройка ссылки выглядит так:

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> Как правило, не следует жестко кодировать URL-адреса непосредственно к активам в CDN. Однако при необходимости вы можете вручную создать URL-адреса для ресурсов в общедоступных источниках. Дополнительные сведения см. в [url-адресах cdn hardcoding для общедоступных активов.](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets)

Чтобы узнать, как проверить, обслуживаются ли ресурсы из CDN, см. раздел "Как проверить, обслуживаются ли ресурсы в [CDN?"](use-microsoft-365-cdn-with-spo.md#CDNConfirm) в разделе "Устранение неполадок в [CDN Office 365".](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)

### <a name="using-assets-in-public-origins"></a>Использование ресурсов в общедоступных источниках

Функция  публикации в SharePoint Online автоматически переозначает URL-адреса активов, хранимые в общедоступных источниках, в их эквиваленты CDN, чтобы ресурсы обслуживались из службы CDN, а не Из SharePoint.

Если ваш источник находится на сайте с включенной функцией публикации, а ресурсы, которые вы хотите разгрузить в CDN, находятся в одной из следующих категорий, SharePoint автоматически переопишет URL-адреса ресурсов в источнике, если актив не был исключен политикой CDN.

Ниже представлен обзор ссылок, которые автоматически заменяет функция публикации в SharePoint.

+ URL-адреса IMG-, LINK- и CSS-файлов в HTML-откликах классической страницы публикации.
  + Это относится и к изображениям, добавленным авторами в HTML-содержимом страницы.
+ URL-адреса изображений в веб-части "Слайд-шоу библиотеки рисунков".
+ Поля изображений в результатах работы REST API SPList (RenderListDataAsStream).
  + Использование нового свойства _ImageFieldsToTryRewriteToCdnUrls_ для предоставления списка полей, разделенных запятой
  + Поддерживает поля гиперссылки и поля PublishingImage
+ Представление изображений SharePoint

На следующей схеме показано, как работает рабочий процесс, когда SharePoint получает запрос на страницу, содержащую ресурсы из публичного источника.

![Схема рабочего процесса: искомые ресурсы CDN Office 365 из публичного источника](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Рабочий процесс: искомые ресурсы CDN Office 365 из публичного источника")

> [!TIP]
> Если вы хотите отключить автоматическое переописывание для определенных URL-адресов на странице, вы можете найти страницу и добавить параметр строки **запроса? NoAutoReWrites=true** в конце каждой ссылки, отключаемой.

#### <a name="hardcoding-cdn-urls-for-public-assets"></a>Жесткое задание URL-адресов CDN для общедоступных активов

Если  функция публикации не включена для общего источника или ресурс не является одним из типов ссылок, поддерживаемых функцией автоматического перезаписи службы CDN, можно вручную создать URL-адреса в расположении ресурсов CDN и использовать эти URL-адреса в содержимом.

> [!NOTE]
> Невозможно жестко закодировать URL-адреса CDN для ресурсов в частном источнике, так как необходимый маркер доступа, формирующий последний раздел URL-адреса, создается во время запроса ресурса.

Для общедоступных ресурсов CDN формат URL-адреса будет выглядеть следующим образом:

``` html
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

Замените **TenantHostName** именем клиента. Пример.

``` html
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

### <a name="using-assets-in-private-origins"></a>Использование ресурсов в частных источниках

Для использования активов в частных источниках не требуется дополнительная настройка. SharePoint Online автоматически переописает URL-адреса для активов в частных источниках, чтобы запросы на эти ресурсы всегда обслуживались из сети CDN. Невозможно вручную создавать URL-адреса для ресурсов CDN в частных источниках, так как эти URL-адреса содержат маркеры, которые должны автоматически создаваться SharePoint Online во время запроса актива.

Доступ к активам в частных источниках защищен динамически созданными маркерами на основе разрешений пользователя на доступ к источнику с оговорками, описанными в следующих разделах. Пользователи должны иметь по крайней мере **доступ** на чтение к источникам, чтобы CDN отрисовыла содержимое.

На следующей схеме показано, как работает рабочий процесс, когда SharePoint получает запрос страницы, содержащей ресурсы из частного источника.

![Схема рабочего процесса: искомые ресурсы CDN Office 365 из частного источника](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Рабочий процесс: искомые ресурсы CDN Office 365 из частного источника")

#### <a name="token-based-authorization-in-private-origins"></a>Авторизация на основе маркеров в частных источниках

Доступ к активам в частных источниках в сети CDN Office 365 предоставляется маркерами, созданными SharePoint Online. Пользователям, у которых уже есть разрешение на доступ к папке или библиотеке, указанной в источнике, автоматически назначаются маркеры, которые позволяют пользователю получать доступ к файлу на основе их уровня разрешений. Эти маркеры доступа действительны в течение 30–90 минут после их сгенерирований для предотвращения атак с повтором маркеров.

После сгенерирования маркера доступа SharePoint Online возвращает настраиваемый URI клиенту, содержащим два параметра авторизации _(_ edge authorization token) и _oat_ (маркер авторизации источника). Структура каждого маркера< срок действия в формате времени >__< в формате >_._ Пример:

``` html
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> Любой, кто владеет маркером, может получить доступ к ресурсу в сети CDN. Однако URL-адреса, содержащие эти маркеры доступа, доступны только по протоколу HTTPS, поэтому если конечный пользователь явным образом не поделился URL-адресом до истечения срока действия маркера, ресурс будет недоступен неавторизованным пользователям.

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a>Разрешения на уровне элементов не поддерживаются для активов в частных источниках

Важно отметить, что SharePoint Online не поддерживает разрешения на уровне элементов для активов в частных источниках. Например, для файла, расположенного по адресу, пользователи имеют эффективный доступ к файлу при `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` следующих условиях:

|Пользователь  |Permissions  |Эффективный доступ  |
|---------|---------|---------|
|Пользователь 1     |Имеет доступ к папке1         |Доступ к image1.jpg из сети CDN         |
|Пользователь 2     |Не имеет доступа к папке1         |Не удается получить image1.jpg из сети CDN         |
|Пользователь 3     |Не имеет доступа к папке1, но ему предоставлено явное разрешение на доступ к image1.jpg в SharePoint Online         |Доступ к ресурсу image1.jpg непосредственно из SharePoint Online, но не из сети CDN         |
|Пользователь 4     |Имеет доступ к папке1, но ему явным образом отказано в доступе к image1.jpg в SharePoint Online         |Не удается получить доступ к активу из SharePoint Online, но он может получить доступ из СЕТИ CDN несмотря на то, что ему отказано в доступе к файлу в SharePoint Online         |

<a name="CDNTroubleshooting"> </a>
## <a name="troubleshooting-the-office-365-cdn"></a>Устранение неполадок в CDN Office 365

<a name="CDNConfirm"> </a>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a>Как подтвердить, что ресурсы обслуживаются CDN?

После того как вы добавили ссылки на ресурсы CDN на страницу, вы можете подтвердить, что ресурс обслуживается из CDN, перейдите на страницу, щелкнув правой кнопкой мыши изображение после его отрисовки и просмотрев URL-адрес изображения.

Вы также можете использовать средства разработчика браузера для просмотра URL-адреса для каждого актива на странице или использовать стороне средство трассировки сети.

> [!NOTE]
> Если вы используете сетевое средство, например Fiddler, для тестирования ресурсов вне отображения актива со страницы SharePoint, необходимо вручную добавить загон "Referer:" в запрос GET, где URL-адрес является корневым URL-адресом клиента `https://yourdomain.sharepoint.com` SharePoint Online.

Вы не можете тестировать URL-адреса CDN непосредственно в веб-браузере, так как у вас должен быть ссылка из SharePoint Online. Однако если добавить URL-адрес ресурсов CDN на страницу SharePoint, а затем открыть страницу в браузере, ресурс CDN будет отрисован на странице.

Дополнительные сведения об использовании средств разработчика в браузере Microsoft Edge см. в средстве [разработчика Microsoft Edge.](https://docs.microsoft.com/microsoft-edge/devtools-guide)

Чтобы посмотреть короткое видео, размещенное в канале [SharePoint Developer Patterns and Practices YouTube,](https://aka.ms/sppnp-videos) демонстрирующее, как проверить работу сети CDN, см. раздел "Проверка использования [сети CDN](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)и обеспечение оптимального сетевого подключения".

### <a name="why-are-assets-from-a-new-origin-unavailable"></a>Почему ресурсы из нового источника недоступны?
Ресурсы в новых источниках не сразу станут доступны для использования, так как регистрация проходит через CDN и загружается из источника в хранилище CDN. Время, необходимое для того, чтобы активы были доступны в CDN, зависит от того, сколько ресурсов и размеров файлов.

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a>Не работает клиентская веб-часть или решение SharePoint Framework

Когда вы включаете CDN Office 365 для общедоступных источниках, служба CDN автоматически создает эти источника по умолчанию:

+ */MASTERPAGE
+ */STYLE LIBRARY
+ */CLIENTSIDEASSETS

Если отсутствует источник */clientsideassets, решения SharePoint Framework не будут работать, и предупреждения или сообщения об ошибках не будут созданы. Этот источник может отключаться либо из-за включения CDN с параметром _-NoDefaultOrigins,_ установленным **$true,** либо из-за того, что источник был удален вручную.

Чтобы узнать, какие источникы присутствуют, можно использовать следующую команду PowerShell:

``` powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

Или вы можете проверить office 365 CLI:

``` powershell
spo cdn origin list
```

Чтобы добавить источник в PowerShell:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

Чтобы добавить источник в Office 365 CLI:

``` powershell
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a>Какие модули PowerShell и оболочки CLI необходимы для работы с CDN Office 365?

Вы можете работать с сетью CDN Office 365 с помощью модуля PowerShell командной оболочки **SharePoint Online** или **office 365 CLI.**

+ [Начало работы с командной консолью SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [Установка Office 365 CLI](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a>См. также

[Сети доставки содержимого](https://aka.ms/o365cdns)

[Планирование сети и настройка производительности для Office 365](https://aka.ms/tune)

[Серия о производительности SharePoint — серия видео о сети CDN Office 365](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
