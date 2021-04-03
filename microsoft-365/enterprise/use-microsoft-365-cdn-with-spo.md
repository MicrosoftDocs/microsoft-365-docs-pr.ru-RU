---
title: Используйте сеть доставки контента Office 365 (CDN) с SharePoint Online
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
description: Узнайте, как использовать сеть доставки контента Office 365 (CDN) для ускорения доставки ресурсов SharePoint Online.
ms.openlocfilehash: 6819f627d3590cd2739b36cb1bc303f197d6aaa5
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570409"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a>Использование сети доставки содержимого Office 365 с SharePoint Online

Вы можете использовать встроенную сеть доставки содержимого (CDN) Office 365 для размещения статических ресурсов, чтобы повысить производительность страниц SharePoint Online. Сеть CDN Office 365 повышает производительность путем кэширования статических ресурсов ближе к браузерам, которые их запрашивают, что повышает скорость скачиваний и снижает задержку. Кроме того, CDN Office 365 использует [протокол HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) для улучшения сжатия и http pipelining. Служба CDN Office 365 входит в состав подписки на SharePoint Online.

> [!NOTE]
> CdN Office 365 доступен только для клиентов в облаке **Production** (по всему миру). Клиенты в облаках правительства США, Китая и Германии в настоящее время не поддерживают CDN Office 365.

Сети доставки содержимого Office 365 состоит из нескольких сетей CDN, позволяющих размещать статические ресурсы в нескольких расположениях или _источниках_ и использовать их из глобальных высокоскоростных сетей. В зависимости от типа содержимого, которое необходимо разместить в сети CDN Office 365, можно добавить **общедоступные** источники, **закрытые** источники или оба варианта. Дополнительные [сведения](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) о различиях между государственными и частными происхождениями см. в дополнительных сведениях о том, должно ли каждое происхождение быть общедоступным или частным.

![Концептуальная схема CDN Office 365](../media/O365-CDN/o365-cdn-flow-transparent.svg "Концептуальная схема CDN Office 365")

Если вы уже знакомы с тем, как работают cdNs, необходимо выполнить только несколько действий, чтобы включить CDN Office 365 для клиента. В этом разделе описывается, как. Ознакомьтесь с информацией о том, как начать размещение статических активов.

> [!TIP]
> Существуют другие cdNs, которые можно использовать с Office 365 для специализированных сценариев использования, но не обсуждаются в этой теме, так как они не находятся за рамками CDN Office 365. Дополнительные сведения см. [в других cdNs Microsoft.](content-delivery-networks.md#other-microsoft-cdns)

 **Возвращайся к [планированию сети и настройке производительности для Office 365.](./network-planning-and-performance.md)**

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a>Обзор работы с CDN Office 365 в SharePoint Online

Чтобы настроить CDN Office 365 для организации, выполните следующие основные действия:

+ [Планирование развертывания CDN Office 365](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + [Определите, какие статические активы необходимо установить в CDN.](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Определите, где нужно хранить свои активы.](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets) Это расположение может быть сайтом SharePoint, библиотекой или папкой и называется _происхождением._
  + [Выберите, должно ли каждое происхождение быть общедоступным или частным.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) Можно добавить несколько источников как общедоступных, так и частных типов.

+ Настройка и настройка CDN с помощью PowerShell или CLI SharePoint Online

  + [Настройка и настройка CDN с помощью оболочки управления SharePoint Online](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [Настройка и настройка CDN с помощью PnP PowerShell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [Настройка и настройка CDN с помощью CLI Office 365](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  Когда вы выполните этот шаг, у вас будет:

  + Включен cdN для вашей организации.
  + Добавлены истоки, определяющие каждое происхождение как общедоступные или частные.

После установки можно управлять [CDN Office 365](use-microsoft-365-cdn-with-spo.md#CDNManage) с течением времени:
  
+ Добавление, обновление и удаление активов
+ Добавление и удаление истоков
+ Настройка политик CDN
+ При необходимости отключение CDN

Наконец, см. в выпуске Использование ресурсов [CDN,](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) чтобы узнать о доступе к вашим cdN-активам как из государственного, так и из частного происхождения.

Инструкции по решению распространенных проблем см. в инструкции по устранению неполадок [cdN Office 365.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)

## <a name="plan-for-deployment-of-the-office-365-cdn"></a>Планирование развертывания CDN Office 365

Перед развертыванием CDN Office 365 для клиента Office 365 необходимо учитывать следующие факторы в процессе планирования.

  + [Определение статических активов, которые необходимо установить в CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Определите, где нужно хранить свои активы](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [Выберите, должно ли каждое происхождение быть общедоступным или закрытым.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<a name="CDNAssets"> </a>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a>Определение статических активов, которые необходимо установить в CDN

В общем, CDNs наиболее эффективны для размещения статических активов _или_ активов, которые не очень часто изменяются. Хорошим правилом является определение файлов, которые соответствуют некоторым или всем этим условиям:

+ Статические файлы, встроенные в страницу (например, сценарии и изображения), которые могут иметь существенное инкрементное влияние на время загрузки страницы.
+ Большие файлы, такие как исполняемые и файлы установки
+ Библиотеки ресурсов, поддерживают клиентский код

Например, небольшие файлы, которые неоднократно запрашиваются, например изображения сайтов и сценарии, могут значительно повысить производительность отрисовки сайтов и постепенно снизить нагрузку на сайты SharePoint Online при добавлении их в cdN-источник. Более крупные файлы, такие как исполняемые установки, могут быть скачаны из CDN, что положительно сказывается на производительности и последующем снижении нагрузки на сайте SharePoint Online, даже если к ним не доступны так часто.

Улучшение производительности на основе каждого файла зависит от многих факторов, включая близость клиента к ближайшей конечной точке CDN, временные условия в локальной сети и т. д. Многие статические файлы довольно малы и могут быть загружены из Office 365 менее чем за секунду. Однако веб-страница может содержать множество встроенных файлов совокупным временем загрузки в несколько секунд. Обслуживание этих файлов из CDN может значительно сократить общее время загрузки страницы. Узнайте, [какие результаты обеспечивает CDN?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) в примере.

<a name="CDNStoreAssets"> </a>
### <a name="determine-where-you-want-to-store-your-assets"></a>Определите, где нужно хранить свои активы

CDN извлекает ваши активы из расположения, называемого _происхождением._ Происхождение может быть веб-сайтОм SharePoint, библиотекой документов или папкой, доступной по URL-адресу. У вас есть большая гибкость при указании истоков для организации. Например, можно указать несколько источников или одно происхождение, куда необходимо поместить все ресурсы CDN. Вы можете выбрать общедоступные или частные истоки для вашей организации. Большинство организаций будут выбирать для реализации сочетания этих двух.

Вы можете создать новый контейнер для истоков, таких как папки или библиотеки документов, и добавить файлы, которые необходимо сделать доступными из CDN. Это хороший подход, если у вас есть определенный набор активов, которые вы хотите быть доступными из CDN, и хотите ограничить набор cdN-активов только этими файлами в контейнере.

Вы также можете настроить существующую коллекцию сайтов, сайт, библиотеку или папку в качестве источника, что сделает все подходящие активы в контейнере доступными из CDN. Перед добавлением существующего контейнера в качестве источника важно убедиться, что вы осведомлены о его содержимом и разрешениях, чтобы не случайно подвергать ресурсы анонимному доступу или неавторизованным пользователям.

Вы можете определить _политики CDN,_ чтобы исключить содержимое в истоках из CDN. Политики CDN исключают активы государственного или частного  происхождения по атрибутам, таким как тип файла и классификация _сайтов,_ и применяются для всех истоков cdnType (частных или общедоступных), которые указаны в политике. Например, если вы добавляете частное происхождение, состоящее из сайта с несколькими подмитами, можно определить политику, исключаемую сайты, помеченные как **Конфиденциальные,** чтобы содержимое сайтов с примененной классификацией не было подается из CDN. Политика будет применяться к контенту из _всех_ частных истоков, добавленных в CDN.
  
Имейте в виду, что чем больше количество истоков, тем больше влияние на время обработки запросов службой CDN. Рекомендуем максимально ограничить количество истоков.
  
<a name="CDNOriginChoosePublicPrivate"> </a>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a>Выберите, должно ли каждое происхождение быть общедоступным или закрытым.

При определении источника указывается, следует ли сделать его общедоступным _или_ _закрытым._ Доступ к активам CDN в общедоступных источниках анонимный, а контент CDN частного происхождения обеспечивается динамически созданными маркерами для большей безопасности. Независимо от того, какой из вариантов вы выбираете, Корпорация Майкрософт делает все, что необходимо для вас, когда речь заходит об администрировании самого CDN. Кроме того, вы можете изменить свое решение позже, после того как вы настроите CDN и идентифицировали свои истоки.

Как общедоступные, так и частные параметры обеспечивают аналогичные преимущества производительности, но каждый из них имеет уникальные атрибуты и преимущества.

**Общедоступные** истоки в CDN Office 365 доступны анонимно, а к общедоступным активам может получить доступ любой, у кого есть URL-адрес актива. Так как доступ к содержимому в общедоступных источниках является анонимным, следует использовать их только для кэширования неконфиденциального общего содержимого, например файлов JavaScript, скриптов, значков и изображений.

**Частные** истоки в CDN Office 365 предоставляют частный доступ к пользовательскому контенту, такому как библиотеки документов SharePoint Online, сайты и собственные изображения. Доступ к контенту частного происхождения обеспечивается динамически созданными маркерами, поэтому доступ к нему могут получить только пользователи с разрешениями на исходную библиотеку документов или расположение хранилища. Частные истоки CDN Office 365 можно использовать только для контента SharePoint Online, а получить доступ к активам частного происхождения можно только через перенаправление с клиента SharePoint Online.

Подробнее о том, как работает доступ CDN к активам частного происхождения, читайте в публикации "Использование активов [в частном происхождении".](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a>Атрибуты и преимущества размещения активов в общедоступных источниках
  
+ Ресурсы, предоставляемые из общедоступного источника, доступны всем анонимно.
    > [!IMPORTANT]
    > Никогда не следует разместить ресурсы, содержащие сведения о пользователях или которые считаются конфиденциальными для организации в публичном происхождении.

+ Если удалить ресурс из общедоступного источника, он может оставаться доступным в кэше до 30 дней. Однако ссылки на ресурс в сети CDN станут недействительными в течение 15 минут.

+ При размещении таблиц стилей (CSS-файлов) в общедоступном источнике можно использовать в коде относительные пути и URI. Это означает, что вы можете ссылаться на расположение фоновых изображений и других объектов относительно расположения ресурса, который вызывает его.

+ Хотя вы можете создать URL-адрес общего происхождения, следует действовать с осторожностью и убедиться, что вы используете свойство контекста страницы и следуйте указаниям для этого. Это связано с тем, что если сеть CDN станет недоступна, то URL-адрес не будет автоматически указывать на вашу организацию в SharePoint Online, что может привести к неработоспособности ссылок и другим ошибкам. Url-адрес также подлежит изменению, поэтому он не должен быть просто жестко закодироваться к текущему значению.

+ Типы файлов по умолчанию, включенные для общедоступных истоков, являются .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff и .woff2. Можно указать дополнительные типы файлов.

+ Можно настроить политику, чтобы исключить активы, которые были определены в классификациях сайтов, которые указаны. Например, вы можете исключать все ресурсы, отмеченные как "конфиденциальные" или "с ограниченным доступом", даже если они относятся к разрешенным типам файлов и находятся в общедоступном источнике.

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a>Атрибуты и преимущества размещения активов в частном происхождении

+ Частные истоки можно использовать только для активов SharePoint Online.

+ Пользователи могут получить доступ к активам частного происхождения только в том случае, если у них есть разрешения на доступ к контейнеру. Анонимный доступ к таким ресурсам запрещен.

+ Активы частного происхождения должны быть переданы из клиента SharePoint Online. Прямой доступ к частным cdN-активам не работает.

+ Если вы удалите актив из частного происхождения, актив может оставаться доступным в течение часа из кэша; однако в течение 15 минут после удаления актива ссылки на актив в CDN будут признаны недействительными.

+ По умолчанию для частных источников включены типы файлов GIF, ICO, JPEG, JPG, JS и PNG. Можно указать дополнительные типы файлов.

+ Как и с общедоступными истоками, можно настроить политику, чтобы исключить активы, которые были определены классификациями сайтов, которые вы указываете, даже если вы используете поддиальды, чтобы включить все активы в папку или библиотеку документов.

Дополнительные сведения о том, зачем использовать CDN Office 365, общие концепции CDN и другие CDN Майкрософт, которые можно использовать с клиентом Office 365, см. в статью [Content Delivery Networks.](content-delivery-networks.md)

### <a name="default-cdn-origins"></a>Происхождение CDN по умолчанию

Если не указать обратное, Office 365 устанавливает для вас некоторые истоки по умолчанию, если вы включаете CDN Office 365. Если изначально вы решите не добавлять их, вы можете добавить эти истоки после завершения установки. Если вы не понимаете последствия пропуска установки истоков по умолчанию и не имеете для этого конкретной причины, вы должны разрешить их создавать, когда вы включаете CDN.
  
Частные истоки CDN по умолчанию:
  
+ \*/userphoto.aspx
+ \*/siteassets

Общедоступные истоки CDN по умолчанию:
  
+ \*/masterpage
+ \*/библиотека стилей
+ \*/clientsideassets

> [!NOTE]
> _clientsideassets_ — это общедоступный источник по умолчанию, который был добавлен в службу CDN Office 365 в декабре 2017 г. Это происхождение должно присутствовать для того, чтобы решения SharePoint Framework в CDN работали. Если вы включили CDN Office 365 до декабря 2017 г. или пропустили установку истоков по умолчанию при включении CDN, можно вручную добавить это начало. Дополнительные сведения см. в [раздел Моя клиентская веб-часть или решение SharePoint Framework не работает.](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)

<a name="CDNSetupinPShell"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a>Настройка и настройка CDN Office 365 с помощью оболочки управления SharePoint Online

Процедуры в этом разделе требуют, чтобы вы использовали оболочку управления SharePoint Online для подключения к SharePoint Online. Инструкции см. в статье [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

Выполните эти действия, чтобы настроить CDN для организации активов в SharePoint Online с помощью оболочки управления SharePoint Online.

<details>
  <summary>Щелкните, чтобы развернуть</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Включить организацию для использования CDN Office 365

Прежде чем вносить изменения в параметры CDN клиента, необходимо получить текущее состояние закрытой конфигурации CDN в клиенте Office 365. Подключение к клиенту с помощью оболочки управления SharePoint Online:

```powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

Теперь используйте **комлет Get-SPOTenantCdnEnabled** для получения параметров состояния CDN у клиента:

```powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

Состояние CDN для указанного CdnType выводит на экран.

Используйте **комлет Set-SPOTenantCdnEnabled,** чтобы позволить организации использовать CDN Office 365. Вы можете включить организацию для использования общедоступных истоков, частных и одновременно обоих. Можно также настроить CDN, чтобы пропустить настройку истоков по умолчанию при его впусте. Вы всегда можете добавить эти истоки позже, как описано в этой теме.
  
В Windows PowerShell SharePoint Online:

```powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Например, чтобы позволить организации использовать общедоступные и частные истоки, введите следующую команду:

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

Чтобы позволить организации использовать как общедоступные, так и частные истоки, но пропустить настройку истоков по умолчанию, введите следующую команду:

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Сведения о происхождении по умолчанию, которые предусмотрены по умолчанию при встройки [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) Office 365, и о потенциальном влиянии пропуска установки истоков по умолчанию см. в истоках CDN по умолчанию.

Чтобы позволить организации использовать общедоступные истоки, введите следующую команду:

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

Чтобы позволить организации использовать частные истоки, введите следующую команду:

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

Дополнительные сведения об этом комлете см. в этой ленте [Set-SPOTenantCdnEnabled.](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)

<a name="Office365CDNforSPOFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Измените список типов файлов, чтобы включить их в CDN Office 365 (необязательный)

> [!TIP]
> При определении типов файлов с помощью комлета **Set-SPOTenantCdnPolicy** переопределяется определенный список. Если вы хотите добавить в список дополнительные типы файлов, сначала используйте этот список, чтобы узнать, какие типы файлов уже разрешены, и включите их в список вместе с новыми.
  
Для определения типов статических файлов, которые могут быть организованы государственным и частным происхождением в CDN, используйте коммюлет **Set-SPOTenantCdnPolicy.** По умолчанию разрешены общие типы активов, например .css, .gif, .jpg и .js.

В Windows PowerShell SharePoint Online:

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Например, чтобы включить CDN для хозяйских файлов .css и .png, необходимо ввести команду:

```powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Чтобы узнать, какие типы файлов в настоящее время разрешены CDN, используйте **cmdlet Get-SPOTenantCdnPolicies:**

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Дополнительные сведения об этих cmdlets см. в [set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) и [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).

<a name="Office365CDNforSPOSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Измените список классификаций сайтов, которые необходимо исключить из CDN Office 365 (необязательный)

> [!TIP]
> При исключении классификации сайтов с помощью комлета **Set-SPOTenantCdnPolicy** переопределяется определенный список. Если вы хотите исключить дополнительные классификации сайтов, сначала используйте cmdlet, чтобы узнать, какие классификации уже исключены, а затем добавить их вместе с новыми.

Чтобы исключить классификации сайтов, которые не должны быть доступны в сети CDN, используйте командлет **Set-SPOTenantCdnPolicy**. По умолчанию не исключаются никакие классификации сайтов.

В Windows PowerShell SharePoint Online:

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

Чтобы узнать, какие классификации сайтов в настоящее время ограничены, используйте см. в **рубриках Get-SPOTenantCdnPolicies:**

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Свойства, которые будут _возвращены: IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ и _ExcludeIfNoScriptDisabled._

Свойство _IncludeFileExtensions_ содержит список расширений файлов, которые будут подаваться из CDN.

> [!NOTE]
> Расширения файлов по умолчанию отличаются между общедоступными и закрытыми.

Свойство _ExcludeRestrictedSiteClassifications_ содержит классификации сайтов, которые необходимо исключить из CDN. Например, можно исключить сайты, помеченные как **Конфиденциальные,** чтобы содержимое сайтов с применяемой классификацией не обслуживалось из CDN.

Свойство _ExcludeIfNoScriptDisabled_ исключает контент из CDN на основе параметров атрибута _NoScript_ на уровне сайта. По умолчанию для _атрибута NoScript_ устанавливается значение **Включено** для _современных_ сайтов и **отключено для** _классических_ сайтов. Это зависит от параметров клиента.

Дополнительные сведения об этих cmdlets см. в [set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) и [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).

<a name="Office365CDNforSPOOriginPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Добавление источника для ваших активов

Чтобы определить происхождение, используйте кодлет **Add-SPOTenantCdnOrigin.** Вы можете определить несколько источников. Источник — это URL-адрес, указывающий на библиотеку или папку в SharePoint, содержащую ресурсы, которые требуется размещать в сети CDN.
  
> [!IMPORTANT]
> Никогда не следует разместить ресурсы, содержащие сведения о пользователях или которые считаются конфиденциальными для организации в публичном происхождении.

```powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

Значение пути _—_ это относительный путь к библиотеке или папке, которая содержит активы. Помимо относительных путей, можно использовать подстановочные знаки. Origins поддерживает подкарды, предварительно заранее заранее примыкает к URL-адресу. Это позволяет создавать истоки, охватывающие несколько сайтов. Например, чтобы включить все активы в папку masterpages для всех сайтов в качестве общедоступных в cdN, введите следующую команду:

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ Модификатор под диктовки * может использоваться только в начале пути и будет соответствовать всем сегментам URL-адресов по **/** указанному URL-адресу.
+ Путь может указать на библиотеку документов, папку или сайт. Например, путь _*/site1 будет_ соответствовать всем библиотекам документов на сайте.

Можно добавить происхождение с определенным относительным путем. Невозможно добавить начало с помощью полного пути.

В этом примере добавляется частное происхождение библиотеки siteassets на определенном сайте:

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

В этом примере добавляется частное происхождение _папки1_ в библиотеке ресурсов сайтов коллекции сайтов:

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Если на пути есть пробел, можно либо окружить путь двойными кавычками, либо заменить пространство url-адресом, кодировка которого составляет %20. В следующих примерах добавлено частное происхождение папки _1_ в библиотеке ресурсов сайтов коллекции сайтов:

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Дополнительные сведения об этой команде и ее синтаксис см. в [обзоре Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).

> [!NOTE]
> В частных источниках ресурсы, общие для происхождения, должны иметь крупную версию, опубликованную до того, как к ним можно получить доступ из CDN.
  
После запуска команды система синхронизирует конфигурацию через центр обработки данных. Это может занять до 15 минут.

<a name="ExamplePublicOrigin"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Пример: Настройка общедоступных страниц и библиотеки стилей для SharePoint Online

Обычно эти истоки устанавливаются для вас по умолчанию, когда вы включаете CDN Office 365. Однако, если вы хотите включить их вручную, выполните эти действия.
  
+ Чтобы определить библиотеку стилей как публичное происхождение, используйте смедлет **Add-SPOTenantCdnOrigin.**

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Для определения магистральных страниц как общедоступных страниц используйте смедлет **Add-SPOTenantCdnOrigin.**

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Дополнительные сведения об этой команде и ее синтаксис см. в [обзоре Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).

После запуска команды система синхронизирует конфигурацию через центр обработки данных. Это может занять до 15 минут.

<a name="ExamplePrivateOrigin"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Пример: Настройка частного происхождения для активов сайта, страниц сайта и публикации изображений для SharePoint Online

+ Чтобы определить папку активов сайта как частное происхождение, используйте смлет **Add-SPOTenantCdnOrigin.**

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Чтобы определить папку страниц сайта как частное происхождение, используйте кодлет **Add-SPOTenantCdnOrigin.**

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Чтобы определить папку изображений публикации как частное происхождение, используйте кодлет **Add-SPOTenantCdnOrigin.**

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Дополнительные сведения об этой команде и ее синтаксис см. в [обзоре Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).

После запуска команды система синхронизирует конфигурацию через центр обработки данных. Это может занять до 15 минут.

<a name="ExamplePrivateOriginSiteCollection"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Пример: Настройка частного происхождения для коллекции сайтов для SharePoint Online

Чтобы определить коллекцию сайтов как частное происхождение, используйте смлет **Add-SPOTenantCdnOrigin.** Например,

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Дополнительные сведения об этой команде и ее синтаксис см. в [обзоре Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).
  
После запуска команды система синхронизирует конфигурацию через центр обработки данных. Вы можете увидеть ожидаемое сообщение _Конфигурация,_ которое ожидается по мере подключения клиента SharePoint Online к службе CDN. Это может занять до 15 минут.

<a name="CDNManage"> </a>
### <a name="manage-the-office-365-cdn"></a>Управление CDN Office 365

После настройки CDN можно внести изменения в конфигурацию при обновлении контента или изменении потребностей, как описано в этом разделе.
  
<a name="Office365CDNforSPOaddremoveasset"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Добавление, обновление или удаление активов из CDN Office 365

После завершения действий по настройке можно добавлять новые активы и обновлять или удалять существующие активы, когда захотите. Просто внести изменения в ресурсы в папке или библиотеке SharePoint, которые вы определили в качестве источника. При добавлении нового актива он сразу же будет доступен через CDN. Однако при обновлении актива для распространения и распространения новой копии в CDN может занять до 15 минут.
  
Если вам нужно получить расположение источника, можно использовать **комлет Get-SPOTenantCdnOrigins.** Сведения об использовании этого комлета см. в сайте [Get-SPOTenantCdnOrigins.](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins)

<a name="Office365CDNforSPORemoveOriginPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Удаление источника из CDN Office 365

Вы можете удалить доступ к папке или библиотеке SharePoint, которые были определены в качестве источника. Для этого используйте комлет **Remove-SPOTenantCdnOrigin.**

```powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Сведения об использовании этого cmdlet см. в см. в этой ленте [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).

<a name="Office365CDNforSPOModifyOrigin"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Изменение источника в CDN Office 365

Вы не можете изменить созданное происхождение. Вместо этого удалите начало и добавьте новый. Дополнительные сведения см. в статью Удаление источника из [CDN Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) и добавление источника [для ваших активов.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Отключение CDN Office 365

Чтобы отключить CDN для организации, используйте комлет **Set-SPOTenantCdnEnabled.** Если для CDN включены как общедоступные, так и частные истоки, необходимо выполнить этот код дважды, как показано в следующих примерах.
  
Чтобы отключить использование общедоступных истоков в CDN, введите следующую команду:

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

Чтобы отключить использование личных истоков в CDN, введите следующую команду:

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

Дополнительные сведения об этом комлете см. в этой ленте [Set-SPOTenantCdnEnabled.](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)

</details>

<a name="CDNSetupinPnPPosh"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a>Настройка и настройка CDN Office 365 с помощью PnP PowerShell

Процедуры в этом разделе требуют, чтобы вы использовали PnP PowerShell для подключения к SharePoint Online. Инструкции см. в [инструкции "Начало работы с PnP PowerShell".](https://github.com/SharePoint/PnP-PowerShell#getting-started)

Выполните эти действия, чтобы настроить CDN для хозяйского хозяйского актива в SharePoint Online с помощью PnP PowerShell.

<details>
  <summary>Щелкните, чтобы развернуть</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Включить организацию для использования CDN Office 365

Прежде чем вносить изменения в параметры CDN клиента, необходимо получить текущее состояние закрытой конфигурации CDN в клиенте Office 365. Подключение к клиенту с помощью PnP PowerShell:

```powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

Теперь используйте **комлет Get-PnPTenantCdnEnabled** для получения параметров состояния CDN у клиента:

```powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

Состояние CDN для указанного CdnType выводит на экран.

Используйте **комлет Set-PnPTenantCdnEnabled,** чтобы позволить организации использовать CDN Office 365. Вы можете включить организацию для использования общедоступных и частных истоков одновременно. Можно также настроить CDN, чтобы пропустить настройку истоков по умолчанию при его впусте. Вы всегда можете добавить эти истоки позже, как описано в этой теме.
  
В PnP PowerShell:

```powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Например, чтобы позволить организации использовать общедоступные и частные истоки, введите следующую команду:

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

Чтобы позволить организации использовать как общедоступные, так и частные истоки, но пропустить настройку истоков по умолчанию, введите следующую команду:

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Сведения о происхождении по умолчанию, которые предусмотрены по умолчанию при встройки [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) Office 365, и о потенциальном влиянии пропуска установки истоков по умолчанию см. в истоках CDN по умолчанию.

Чтобы позволить организации использовать общедоступные истоки, введите следующую команду:

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

Чтобы позволить организации использовать частные истоки, введите следующую команду:

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

Дополнительные сведения об этом комлете см. в дополнительных сведениях [set-PnPTenantCdnEnabled.](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)

<a name="Office365CDNforPnPPoshFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Измените список типов файлов, чтобы включить их в CDN Office 365 (необязательный)

> [!TIP]
> При определении типов файлов с помощью комлета **Set-PnPTenantCdnPolicy** переопределяется определенный список. Если вы хотите добавить в список дополнительные типы файлов, сначала используйте этот список, чтобы узнать, какие типы файлов уже разрешены, и включите их в список вместе с новыми.
  
Для определения типов статических файлов, которые могут быть организованы государственными и частными истоками в CDN, используйте коммюлет **Set-PnPTenantCdnPolicy.** По умолчанию разрешены общие типы активов, например .css, .gif, .jpg и .js.

В PnP PowerShell:

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Например, чтобы включить CDN для хозяйских файлов .css и .png, необходимо ввести команду:

```powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Чтобы узнать, какие типы файлов в настоящее время разрешены CDN, используйте **cmdlet Get-PnPTenantCdnPolicies:**

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Дополнительные сведения об этих cmdlets см. в [set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) и [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).

<a name="Office365CDNforPnPPoshSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Измените список классификаций сайтов, которые необходимо исключить из CDN Office 365 (необязательный)

> [!TIP]
> При исключении классификаций сайтов с помощью комлета **Set-PnPTenantCdnPolicy** переопределяется определенный список. Если вы хотите исключить дополнительные классификации сайтов, сначала используйте cmdlet, чтобы узнать, какие классификации уже исключены, а затем добавить их вместе с новыми.

Используйте **комлет Set-PnPTenantCdnPolicy,** чтобы исключить классификации сайтов, которые не требуется делать доступными в CDN. По умолчанию не исключаются никакие классификации сайтов.

В PnP PowerShell:

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

Чтобы узнать, какие классификации сайтов в настоящее время ограничены, используйте **кодлет Get-PnPTenantCdnPolicies:**

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Свойства, которые будут _возвращены: IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ и _ExcludeIfNoScriptDisabled._

Свойство _IncludeFileExtensions_ содержит список расширений файлов, которые будут подаваться из CDN.

> [!NOTE]
> Расширения файлов по умолчанию отличаются между общедоступными и закрытыми.

Свойство _ExcludeRestrictedSiteClassifications_ содержит классификации сайтов, которые необходимо исключить из CDN. Например, можно исключить сайты, помеченные как **Конфиденциальные,** чтобы содержимое сайтов с применяемой классификацией не обслуживалось из CDN.

Свойство _ExcludeIfNoScriptDisabled_ исключает контент из CDN на основе параметров атрибута _NoScript_ на уровне сайта. По умолчанию для _атрибута NoScript_ устанавливается значение **Включено** для _современных_ сайтов и **отключено для** _классических_ сайтов. Это зависит от параметров клиента.

Дополнительные сведения об этих cmdlets см. в [set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) и [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).

<a name="Office365CDNforSPOOriginPnPPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Добавление источника для ваших активов

Чтобы определить происхождение, используйте кодлет **Add-PnPTenantCdnOrigin.** Вы можете определить несколько источников. Источник — это URL-адрес, указывающий на библиотеку или папку в SharePoint, содержащую ресурсы, которые требуется размещать в сети CDN.
  
> [!IMPORTANT]
> Никогда не следует разместить ресурсы, содержащие сведения о пользователях или которые считаются конфиденциальными для организации в публичном происхождении.

```powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

Значение пути _—_ это относительный путь к библиотеке или папке, которая содержит активы. Помимо относительных путей, можно использовать подстановочные знаки. Origins поддерживает подкарды, предварительно заранее заранее примыкает к URL-адресу. Это позволяет создавать истоки, охватывающие несколько сайтов. Например, чтобы включить все активы в папку masterpages для всех сайтов в качестве общедоступных в cdN, введите следующую команду:

```powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ Модификатор под диктовки * может использоваться только в начале пути и будет соответствовать всем сегментам URL-адресов по **/** указанному URL-адресу.
+ Путь может указать на библиотеку документов, папку или сайт. Например, путь _*/site1 будет_ соответствовать всем библиотекам документов на сайте.

Можно добавить происхождение с определенным относительным путем. Невозможно добавить начало с помощью полного пути.

В этом примере добавляется частное происхождение библиотеки ресурсов сайта на определенном сайте:

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

В этом примере добавляется частное происхождение _папки1_ в библиотеке ресурсов сайтов коллекции сайтов:

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Если на пути есть пробел, можно либо окружить путь двойными кавычками, либо заменить пространство url-адресом, кодировка которого составляет %20. В следующих примерах добавлено частное происхождение папки _1_ в библиотеке ресурсов сайтов коллекции сайтов:

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Дополнительные сведения об этой команде и ее синтаксис см. в [добавлении-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

> [!NOTE]
> В частных источниках ресурсы, общие для происхождения, должны иметь крупную версию, опубликованную до того, как к ним можно получить доступ из CDN.
  
После запуска команды система синхронизирует конфигурацию через центр обработки данных. Это может занять до 15 минут.

<a name="ExamplePublicOriginPnPPosh"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Пример: Настройка общедоступных страниц и библиотеки стилей для SharePoint Online

Обычно эти истоки устанавливаются для вас по умолчанию, когда вы включаете CDN Office 365. Однако, если вы хотите включить их вручную, выполните эти действия.
  
+ Чтобы определить библиотеку стилей как общедоступный, используйте кодлет **Add-PnPTenantCdnOrigin.**

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Для определения магистральных страниц как общедоступных страниц используйте кодлет **Add-PnPTenantCdnOrigin.**

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Дополнительные сведения об этой команде и ее синтаксис см. в [добавлении-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

После запуска команды система синхронизирует конфигурацию через центр обработки данных. Это может занять до 15 минут.

<a name="ExamplePrivateOriginPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Пример: Настройка частного происхождения для активов сайта, страниц сайта и публикации изображений для SharePoint Online

+ Чтобы определить папку активов сайта как частное происхождение, используйте кодлет **Add-PnPTenantCdnOrigin.**

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Чтобы определить папку страниц сайта как частное происхождение, используйте кодлет **Add-PnPTenantCdnOrigin.**

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Чтобы определить папку изображений публикации как частное происхождение, используйте кодлет **Add-PnPTenantCdnOrigin.**

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Дополнительные сведения об этой команде и ее синтаксис см. в [добавлении-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

После запуска команды система синхронизирует конфигурацию через центр обработки данных. Это может занять до 15 минут.

<a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Пример: Настройка частного происхождения для коллекции сайтов для SharePoint Online

Чтобы определить коллекцию сайтов как частное происхождение, используйте кодлет **Add-PnPTenantCdnOrigin.** Например,

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Дополнительные сведения об этой команде и ее синтаксис см. в [добавлении-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).
  
После запуска команды система синхронизирует конфигурацию через центр обработки данных. Вы можете увидеть ожидаемое сообщение _Конфигурация,_ которое ожидается по мере подключения клиента SharePoint Online к службе CDN. Это может занять до 15 минут.

<a name="CDNManagePnPPosh"> </a>
### <a name="manage-the-office-365-cdn"></a>Управление CDN Office 365

После настройки CDN можно внести изменения в конфигурацию при обновлении контента или изменении потребностей, как описано в этом разделе.
  
<a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Добавление, обновление или удаление активов из CDN Office 365

После завершения действий по настройке можно добавлять новые активы и обновлять или удалять существующие активы, когда захотите. Просто внести изменения в ресурсы в папке или библиотеке SharePoint, которые вы определили в качестве источника. При добавлении нового актива он сразу же будет доступен через CDN. Однако при обновлении актива для распространения и распространения новой копии в CDN может занять до 15 минут.
  
Если вам нужно получить расположение источника, можно использовать **комлет Get-PnPTenantCdnOrigin.** Сведения об использовании этого комлета см. в [сайте Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).

<a name="Office365CDNforSPORemoveOriginPnPPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Удаление источника из CDN Office 365

Вы можете удалить доступ к папке или библиотеке SharePoint, которые были определены в качестве источника. Для этого используйте комлет **Remove-PnPTenantCdnOrigin.**

```powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Сведения о том, как использовать этот комлет, см. в этой брошюре [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).

<a name="Office365CDNforSPOModifyOriginPnPPosh"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Изменение источника в CDN Office 365

Вы не можете изменить созданное происхождение. Вместо этого удалите начало и добавьте новый. Дополнительные сведения см. в статью Удаление источника из [CDN Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) и добавление источника [для ваших активов.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Отключение CDN Office 365

Чтобы отключить CDN для организации, используйте комлет **Set-PnPTenantCdnEnabled.** Если для CDN включены как общедоступные, так и частные истоки, необходимо выполнить этот код дважды, как показано в следующих примерах.
  
Чтобы отключить использование общедоступных истоков в CDN, введите следующую команду:

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

Чтобы отключить использование личных истоков в CDN, введите следующую команду:

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

Дополнительные сведения об этом комлете см. в дополнительных сведениях [set-PnPTenantCdnEnabled.](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)

</details>

<a name="CDNSetupinCLI"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a>Установка и настройка сети CDN Office 365 с помощью интерфейса командной строки Office 365:

Процедуры в этом разделе требуют установки [CLI Office 365.](https://aka.ms/o365cli) Далее подключите клиента Office 365 с помощью команды [входа.](https://pnp.github.io/office365-cli/cmd/login/)

Выполните эти действия, чтобы настроить CDN для пребывания активов в SharePoint Online с помощью CLI Office 365.

<details>
  <summary>Щелкните, чтобы развернуть</summary>

### <a name="enable-the-office-365-cdn"></a>Включить CDN Office 365

Вы можете управлять состоянием сети CDN Office 365 в клиенте с помощью команды [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/).

Чтобы включить в клиенте общедоступную сеть CDN Office 365, выполните следующую команду:

```cli
spo cdn set --type Public --enabled true
```

Чтобы включить CDN SharePoint Office 365, выполните:

```cli
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a>Просмотр текущего состояния сети CDN Office 365

Чтобы проверить, включен или отключен определенный тип CDN Office 365, используйте [команду spo cdn get.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)

Чтобы проверить, включена ли общедоступная сеть CDN Office 365, выполните следующую команду:

```cli
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a>Просмотр истоков CDN Office 365

Чтобы просмотреть список настроенных в данный момент общедоступных источников CDN Office 365, выполните следующую команду:

```cli
spo cdn origin list --type Public
```

Сведения [о происхождении](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) по умолчанию, которые будут предусмотрены по умолчанию при внии CDN Office 365, см. в истоках CDN по умолчанию.

### <a name="add-an-office-365-cdn-origin"></a>Добавление источника CDN Office 365

> [!IMPORTANT]
> Никогда не следует разместить ресурсы, которые считаются конфиденциальными для организации, в библиотеку документов SharePoint, настроенную как общедоступный источник.

Чтобы определить источник CDN, используйте команду [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/). Вы можете определить несколько источников. Источник — это URL-адрес, указывающий на библиотеку или папку в SharePoint, содержащую ресурсы, которые требуется размещать в сети CDN.

```cli
spo cdn origin add --type [Public | Private] --origin <path>
```

Где `path` находится относительный путь к папке с активами. Помимо относительных путей, можно использовать подстановочные знаки.

Чтобы включить все активы в **Галерею основных** страниц всех сайтов как общедоступные, выполните:

```cli
spo cdn origin add --type Public --origin */masterpage
```

Чтобы настроить частный источник для определенного семейства веб-сайтов, выполните следующую команду:

```cli
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> После добавления источника CDN может понадобиться до 15 минут, чтобы получить файлы через службу CDN. Вы можете проверить, включен ли тот или иной источник, с помощью команды [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/).

### <a name="remove-an-office-365-cdn-origin"></a>Удаление источника CDN Office 365

Чтобы удалить источник CDN для указанного типа CDN, используйте команду [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/).

Чтобы удалить общедоступный источник из конфигурации CDN, выполните:

```cli
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> Удаление происхождения CDN не влияет на файлы, хранимые в любой библиотеке документов, соответствующие этому происхождению. Если эти активы ссылались с помощью URL-адреса SharePoint, SharePoint автоматически переключается на исходный URL-адрес, указывав на библиотеку документов. Если же ссылки на активы были указаны с помощью общедоступных URL-адресов CDN, то удаление источника перебьет ссылку, и вам потребуется вручную изменить их.

### <a name="modify-an-office-365-cdn-origin"></a>Изменение происхождения CDN Office 365

Изменить имеющийся источник CDN невозможно. Вместо этого следует удалить определенный ранее источник CDN с помощью команды `spo cdn origin remove` и добавить новый с помощью команды `spo cdn origin add`.

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a>Измените типы файлов, чтобы включить их в CDN Office 365

По умолчанию в CDN включаются следующие типы файлов: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff и .woff2_. Если требуется включить в сеть CDN дополнительные типы файлов, вы можете изменить конфигурацию CDN с помощью команды [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/).

> [!NOTE]
> При изменении списка типов файлов перезаписывается текущий список. Если требуется включить дополнительные типы файлов, сперва используйте команду [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/), чтобы узнать, какие типы файлов настроены в текущий момент.

Чтобы добавить _тип файла JSON_ в список типов файлов по умолчанию, включенных в общедоступный CDN, выполните:

```cli
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a>Изменение списка классификаций сайтов, которые требуется исключить из сети CDN Office 365

Чтобы исключить классификации сайтов, которые не должны быть доступны в сети CDN, используйте команду [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/). По умолчанию не исключаются никакие классификации сайтов.

> [!NOTE]
> При изменении списка исключаемых классификаций сайтов перезаписывается текущий список. Если требуется исключить дополнительные классификации сайтов, сперва используйте команду [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/), чтобы узнать, какие классификации настроены в текущий момент.

Чтобы исключить сайты, классифицируются _как HBI_ из общедоступных CDN, выполните

```cli
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a>Отключение CDN Office 365

Чтобы отключить сеть CDN Office 365, используйте команду `spo cdn set`. Пример:

```cli
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a>Использование ресурсов CDN

Теперь, когда вы включили CDN и настроенные истоки и политики, можно приступить к использованию ресурсов CDN.

Этот раздел поможет вам понять, как использовать URL-адреса CDN на страницах и контенте SharePoint, чтобы SharePoint перенаправляла запросы на активы как государственного, так и частного происхождения в CDN.

+ [Обновление ссылок на ресурсы CDN](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [Использование ресурсов в общедоступных источниках](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [Использование активов в частном происхождении](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

Сведения об использовании CDN для размещения клиентских веб-частей см. в разделе Host [your client-side web part from Office 365 CDN (Hello World part 4).](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)

> [!NOTE]
> Если вы добавим _папку ClientSideAssets_ в частный список истоков **CDN,** пользовательские веб-части, на которые будет организовано CDN, не будут отрисовки. Файлы, используемые веб-частями SPFX, могут использовать только общедоступные CDN, а папка ClientSideAssets является по умолчанию для общедоступных CDN. 

### <a name="updating-links-to-cdn-assets"></a>Обновление ссылок на ресурсы CDN

Чтобы использовать добавленные в источник ресурсы, просто обновив ссылки на исходный файл с помощью пути к файлу в начале.

+ Изменить страницу или контент, содержащий ссылки на активы, добавленные в источник. Вы также можете использовать один из нескольких методов глобального поиска и замены ссылок на веб-сайт или коллекцию сайтов, если вы хотите обновить ссылку на данный актив везде, где он появится.
+ Для каждой ссылки на актив в источнике замените путь путем к файлу в происхождении CDN. Можно использовать относительные пути.
+ Сохранение страницы или контента.

Например, рассмотрим изображение _/site/SiteAssets/images/image.png_, которое вы скопировали в папку библиотеки документов _/site/CDN_origins/public/_. Чтобы использовать актив CDN, замените исходный путь к расположению файла изображений путем к источнику, чтобы сделать новый _URL-адрес /site/CDN_origins/public/image.png_.

Если вы хотите использовать полный URL-адрес актива вместо относительного пути, сострой ссылку так:

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> В общем, не следует жестко кодировать URL-адреса непосредственно к активам в CDN. Однако при необходимости можно вручную создавать URL-адреса для активов в общедоступных источниках. Дополнительные сведения см. в [выпуске Url-адресов CDN hardcoding для общедоступных активов.](use-microsoft-365-cdn-with-spo.md)

Чтобы узнать о том, как убедиться в том, что ресурсы обслуживаются из CDN, см. в руб. Как подтвердить, что ресурсы обслуживаются [cdN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) в деле устранения неполадок [cdN Office 365.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)

### <a name="using-assets-in-public-origins"></a>Использование ресурсов в общедоступных источниках

Функция **публикации** в SharePoint Online автоматически переписывала URL-адреса активов, хранимых в общедоступных источниках, в их эквиваленты CDN, чтобы активы обслуживались из службы CDN вместо SharePoint.

Если ваше происхождение находится на сайте с включенной функцией Публикации, а активы, которые необходимо разгрузить в CDN, находятся в одной из следующих категорий, SharePoint автоматически переписывание URL-адресов для активов в происхождении при условии, что актив не был исключен политикой CDN.

Ниже представлен обзор ссылок, которые автоматически заменяет функция публикации в SharePoint.

+ URL-адреса IMG-, LINK- и CSS-файлов в HTML-откликах классической страницы публикации.
  + Это относится и к изображениям, добавленным авторами в HTML-содержимом страницы.
+ URL-адреса изображений в веб-части "Слайд-шоу библиотеки рисунков".
+ Поля изображений в результатах работы REST API SPList (RenderListDataAsStream).
  + Используйте новое свойство _ImageFieldsToTryRewriteToCdnUrls_ для предоставления разделенного запятой списка полей
  + Поддерживает поля гиперссылки и поля PublishingImage
+ Renditions изображений SharePoint

Следующая схема иллюстрирует рабочий процесс, когда SharePoint получает запрос на страницу, содержащую активы из общего происхождения.

![Схема рабочего процесса: ирисовка активов CDN Office 365 из общего происхождения](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Рабочий процесс: ирисовка активов CDN Office 365 из общего происхождения")

> [!TIP]
> Если вы хотите отключить автоматическое переписывание определенных URL-адресов на странице, вы можете проверить страницу и добавить параметр строки **запроса? NoAutoReWrites=true** в конце каждой ссылки, отключаемой.

#### <a name="constructing-cdn-urls-for-public-assets"></a>Создание URL-адресов CDN для общедоступных активов

Если  функция Публикации не включена для общего происхождения или актив не является одним из типов ссылок, поддерживаемых функцией автоматического перезаписи службы CDN, можно вручную создать URL-адреса для расположения ресурсов CDN и использовать эти URL-адреса в контенте.

> [!NOTE]
> Нельзя жестко кодировать или создавать URL-адреса CDN для активов частного происхождения, так как необходимый маркер доступа, формирующий последний раздел URL-адреса, создается во время запроса ресурса. Вы можете создать URL-адрес для общедоступных CDN, и URL-адрес не должен быть жестко закодироваться, так как он подлежит изменению.

Для общедоступных ресурсов CDN формат URL-адресов будет выглядеть следующим образом:

```http
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

Замените **TenantHostName** именем клиента. Пример.

```http
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

> [!NOTE]
> Свойство контекста страницы должно использоваться для построения префикса вместо жесткого кодирования https://publiccdn.sharepointonline.com ". URL-адрес подлежит изменению и не должен быть жестко закодироваться. Если вы используете шаблоны отображения с помощью Classic SharePoint Online, вы можете использовать свойство "window._spPageContextInfo.publicCdnBaseUrl" в шаблоне отображения для префикса URL-адреса. Если вы являетсяе веб-частями SPFx для современной и классической SharePoint, вы можете использовать свойство this.context.pageContext.legacyPageContext.publicCdnBaseUrl" (this.context.pageContext.legacyPageContext.publicCdnBaseUrl). При этом будет предоставляться префикс, чтобы если он был изменен, то реализация обновляется вместе с ним. В качестве примера для SPFx URL-адрес можно построить с помощью свойства "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "relativeURL для элемента". См. [в тексте Использование CDN в клиентском коде,](https://youtu.be/IH1RbQlbhIA) который является частью серии производительности [1 сезона](https://aka.ms/sppnp-perfvideos)


### <a name="using-assets-in-private-origins"></a>Использование активов в частном происхождении

Для использования активов в частном происхождении не требуется дополнительная конфигурация. SharePoint Online автоматически переписывал URL-адреса для активов частного происхождения, поэтому запросы на эти активы всегда будут подаваться из CDN. Невозможно вручную создавать URL-адреса для активов CDN в частном происхождении, так как эти URL-адреса содержат маркеры, которые должны быть автоматически созданы SharePoint Online во время запроса актива.

Доступ к активам частного происхождения защищен динамически созданными маркерами на основе разрешений пользователей на происхождение с оговорками, описанными в следующих разделах. Пользователи должны иметь по крайней мере **доступ** к истокам для отображения контента cdN.

Следующая схема иллюстрирует рабочий процесс, когда SharePoint получает запрос на страницу, содержащую активы частного происхождения.

![Схема рабочего процесса: ирисовка активов CDN Office 365 из частного происхождения](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Рабочий процесс: ирисовка активов CDN Office 365 из частного происхождения")

#### <a name="token-based-authorization-in-private-origins"></a>Авторизация на основе маркеров в частном происхождении

Доступ к активам частного происхождения в CDN Office 365 предоставляется маркерами, созданными SharePoint Online. Пользователям, у которых уже есть разрешение на доступ к папке или библиотеке, назначенной происхождением, автоматически выдают маркеры, которые позволяют пользователю получать доступ к файлу на основе уровня разрешений. Эти маркеры доступа действительны в течение 30-90 минут после их получения, чтобы предотвратить атаки повтора маркеров.

После получения маркера доступа SharePoint Online возвращает клиенту настраиваемый URI, содержащий два параметра авторизации _(маркер_ авторизации края) и _овсяный_ (маркер авторизации происхождения). Структура каждого маркера —< времени действия в формате времени эпохи _>__<'secure signature'>_. Например,

```http
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> Любой, кто владеет маркером, может получить доступ к ресурсу cdN. Однако URL-адреса, содержащие эти маркеры доступа, делятся только по HTTPS, поэтому если URL-адрес явно не будет доступен конечному пользователю до истечения срока действия маркера, актив будет недоступен для неавторизованных пользователей.

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a>Разрешения на уровне элементов не поддерживаются для активов в частном происхождении

Важно отметить, что SharePoint Online не поддерживает разрешения на уровне элементов для активов частного происхождения. Например, для файла, расположенного по адресу, пользователи имеют эффективный доступ к файлу с учетом `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` следующих условий:

|User  |Разрешения  |Эффективный доступ  |
|---------|---------|---------|
|Пользователь 1     |Имеет доступ к папке1         |Доступ к image1.jpg из CDN         |
|Пользователь 2     |Не имеет доступа к папке1         |Не удается image1.jpg из CDN         |
|Пользователь 3     |Не имеет доступа к папке1, но имеет явное разрешение на доступ к image1.jpg в SharePoint Online         |Можно получить доступ к image1.jpg непосредственно из SharePoint Online, но не из CDN         |
|Пользователь 4     |Имеет доступ к папке1, но ему явно было отказано в доступе к image1.jpg SharePoint Online         |Не удается получить доступ к активу из SharePoint Online, но может получить доступ к активу из CDN, несмотря на то, что ему было отказано в доступе к файлу в SharePoint Online         |

<a name="CDNTroubleshooting"> </a>
## <a name="troubleshooting-the-office-365-cdn"></a>Устранение неполадок cdN Office 365

<a name="CDNConfirm"> </a>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a>Как подтвердить, что ресурсы обслуживаются cdN?

После того как вы добавили ссылки на ресурсы CDN на страницу, вы можете подтвердить, что актив обслуживается из CDN, просматривая страницу, щелкнув правой кнопкой мыши по изображению после отрисовки и просмотрев URL-адрес изображения.

Вы также можете использовать средства разработчика браузера для просмотра URL-адреса для каждого актива на странице или с помощью средства трассировки сторонних сетей.

> [!NOTE]
> Если вы используете сетевой инструмент, например Fiddler, чтобы протестировать свои активы вне отрисовки актива со страницы SharePoint, необходимо вручную добавить загонщика ссылок "Referer:" в запрос GET, где URL-адрес является корневым URL-адресом клиента `https://yourdomain.sharepoint.com` SharePoint Online.

Невозможно протестировать URL-адреса CDN непосредственно в веб-браузере, так как должен быть ссылщик из SharePoint Online. Однако если добавить URL-адрес актива CDN на страницу SharePoint, а затем открыть страницу в браузере, на странице будет отрисован актив CDN.

Дополнительные сведения об использовании средств разработчика в браузере Microsoft Edge см. в [веб-сайте Microsoft Edge Developer Tools.](/microsoft-edge/devtools-guide)

Чтобы просмотреть короткое видео, размещенное на youTube-канале Шаблоны и практики разработчика [SharePoint,](https://aka.ms/sppnp-videos) демонстрирующее, как убедиться, что ваш CDN работает, см. в раздел Проверка использования [CDN](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)и обеспечение оптимального подключения к сети.

### <a name="why-are-assets-from-a-new-origin-unavailable"></a>Почему недоступны активы нового происхождения?
Активы нового происхождения не будут сразу доступны для использования, так как для регистрации требуется время для распространения через CDN и для отправки активов из происхождения в хранилище CDN. Время, необходимое для того, чтобы активы были доступны в CDN, зависит от того, сколько ресурсов и размеров файлов.

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a>Моя клиентская веб-часть или решение SharePoint Framework не работают

Когда вы включаете CDN Office 365 для общедоступных истоков, служба CDN автоматически создает эти истоки по умолчанию:

+ */MASTERPAGE
+ */STYLE LIBRARY
+ */CLIENTSIDEASSETS

Если происхождение */clientsideassets отсутствует, решения SharePoint Framework сбой, и не создаются предупреждения или сообщения об ошибке. Это происхождение может быть пропущено либо из-за включения CDN с параметром _-NoDefaultOrigins,_ заданным $true, либо потому, что происхождение было удалено вручную. 

Вы можете проверить, какие истоки присутствуют со следующей командой PowerShell:

```powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

Или вы можете проверить cLI Office 365:

```cli
spo cdn origin list
```

Чтобы добавить начало в PowerShell:

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

Чтобы добавить источник в CLI Office 365:

```cli
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a>Какие модули PowerShell и оболочки CLI необходимы для работы с CDN Office 365?

Вы можете работать с CDN Office 365 с помощью модуля PowerShell командной оболочки **SharePoint Online** или **CLI Office 365.**

+ [Начало работы с командной консолью SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [Установка Office 365 CLI](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a>См. также

[Сети доставки содержимого](./content-delivery-networks.md)

[Планирование сети и настройка производительности для Office 365](./network-planning-and-performance.md)

[Серия производительности SharePoint — видеосерия CDN Office 365](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)