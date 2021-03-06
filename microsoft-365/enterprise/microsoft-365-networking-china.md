---
title: Microsoft 365 глобальной оптимизации производительности клиентов для пользователей Китая
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/17/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
search.appverid: MET150
f1.keywords:
- NOCSH
description: В этой статье данная статья содержит рекомендации по оптимизации производительности сети для китайских пользователей глобальных Microsoft 365 клиентов.
ms.openlocfilehash: f48b552dec72d78e2429aedf6a3834dba6c7590a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844506"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Microsoft 365 глобальной оптимизации производительности клиентов для пользователей Китая

> [!IMPORTANT]
> Это руководство конкретно для сценариев использования, в которых корпоративные Microsoft 365 **пользователи,** расположенные в Китае, подключаются к глобальному Microsoft 365 **клиента**. Это руководство **не распространяется** на клиентов в Office 365 21Vianet.

Для предприятий с глобальными Microsoft 365 и корпоративным присутствием в Китае производительность Microsoft 365 для китайских пользователей может быть осложнена факторами, уникальными для интернет-архитектуры China Telco.

Интернет-провайдеры Китая регулируют оффшорные подключения к глобальному общественному Интернету, которые проходят через устройства периметра, которые подвержены высокой загруженности трансграничной сети. Такая перегрузка создает потерю пакетов и задержку для всего интернет-трафика, который идет в Китай и из него.

![Microsoft 365 трафика — неоптимизированный](../media/O365-networking/China-O365-unoptimized.png)

Потеря и задержка пакетов отрицательно влияют на производительность сетевых служб, особенно служб, требующих больших обменов данными (например, больших передач файлов) или требующих производительности в режиме реального времени (аудио- и видео-приложений).

Цель этого раздела заключается в предоставлении наилучших методов для смягчения воздействия перегрузки китайской трансграничной сети на Microsoft 365 служб. В этом разделе не решается других распространенных проблем производительности на последней миле, таких как проблемы с высокой задержкой пакетов из-за сложной маршрутной маршрутики в китайских перевозчиках.

## <a name="corporate-network-best-practices"></a>Лучшие практики корпоративной сети

Многие предприятия с глобальными Microsoft 365 и пользователями в Китае реализовали частные сети, которые осуществляют корпоративный сетевой трафик между расположениями офисов Китая и оффшорными расположениями по всему миру. Эти предприятия могут использовать эту сетевую инфраструктуру, чтобы избежать перегрузки трансграничной сети и оптимизировать Microsoft 365 обслуживания в Китае.

> [!IMPORTANT]
> Как и во всех частных реализациях WAN, необходимо всегда обращаться к нормативным требованиям для вашей страны и/или региона, чтобы убедиться, что конфигурация сети соответствует требованиям.

В качестве первого шага крайне важно следовать нашим ориентирам по сетевому планированию и настройке производительности для [Microsoft 365.](./network-planning-and-performance.md) Основной целью должно быть предотвращение доступа к глобальным Microsoft 365 из Интернета в Китае, если это возможно.

- Использование существующей частной сети для Microsoft 365 сетевого трафика между китайскими офисными сетями и оффшорными расположениями, которые отступят в общедоступный Интернет за пределами Китая. Почти любое расположение за пределами Китая обеспечит явное преимущество. Администраторы сети могут дополнительно оптимизировать работу, отступая в областях с низкой задержкой подключения к [глобальной сети Майкрософт.](/azure/networking/microsoft-global-network) Примерами являются Гонконг, Япония и Южная Корея.
- Настройка пользовательских устройств для доступа к корпоративной сети через VPN-подключение, Microsoft 365 трафика для транзита частной оффшорной ссылки корпоративной сети. Убедитесь, что VPN-клиенты либо не настроены на использование раздельного туннелинга, либо устройства пользователей настроены для игнорирования раздельного Microsoft 365 трафика. Дополнительные сведения об оптимизации подключения VPN для Teams и трафика мультимедиа в режиме реального времени см. [в этом разделе.](#optimizing-microsoft-teams-meetings-network-performance-for-users-in-china)
- Настройте сеть для маршрутов Microsoft 365 трафика по частной оффшорной ссылке. Если необходимо свести к минимуму объем трафика по закрытой ссылке, вы можете выбрать только  конечные  точки маршрута в категории **Оптимизируйте** и разрешить запросы разрешить и по умолчанию конечные точки для транзита через Интернет. Это позволит повысить производительность и свести к минимуму потребление пропускной способности, ограничив оптимизированный трафик критически важными службами, которые наиболее чувствительны к высокой задержке и потере пакетов.
- Если это возможно, используйте UDP вместо TCP для потокового трафика в прямом эфире, например для Teams. UDP обеспечивает более живая производительность потокового мультимедиа, чем TCP.

Сведения о том, как выборочно Microsoft 365 трафика, см. в Office 365 [конечных точек.](managing-office-365-endpoints.md) Список всех URL-адресов Office 365 и IP-адресов см. в Office 365 [URL-адресов и ip-адресов.](urls-and-ip-address-ranges.md)

![Microsoft 365 трафика — оптимизирован](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>Пользовательские методы

Пользователи в Китае, которые подключаются к глобальным Microsoft 365 из удаленных местоположений, таких как дома, кафе, гостиницы и филиалы, не подключенные к корпоративным сетям, могут испытывать неудовлетворительную производительность сети, так как трафик между их устройствами и Microsoft 365 должен пересекать перенапорченные трансграничные сети Китая.

Если трансграничные частные сети и/или VPN-доступ в корпоративную сеть не являются вариантом, проблемы производительности для каждого пользователя по-прежнему могут быть смягчаемы путем обучения пользователей из Китая следовать этим лучшим практикам.

- Используйте Office клиенты, поддерживаюющие кэшинг (например, Outlook, Teams, OneDrive и т. д.), и избегая веб-клиентов. Office клиентского кэшинга и функции автономного доступа могут значительно снизить влияние перегрузки сети и задержки.
- Если клиент Microsoft 365 настроен с помощью функции аудиоконференций, Teams пользователи могут присоединяться к собраниям через общедоступные телефонные сети с переключениями (PSTN).  Дополнительные сведения см. [в аудиоконференциях в Office 365.](/microsoftteams/audio-conferencing-in-office-365)
- Если у пользователей возникли проблемы с производительностью сети, они должны сообщить в ИТ-отдел об устранении неполадок и при подозрении на неполадки с Microsoft 365 службами. Не все проблемы вызваны производительностью трансграничной сети.

## <a name="optimizing-microsoft-teams-meetings-network-performance-for-users-in-china"></a>Оптимизация Microsoft Teams собраний для пользователей в Китае

Для организаций с глобальными Microsoft 365 клиентами и присутствием в Китае Microsoft 365 клиентов для китайских пользователей может быть осложнена факторами, уникальными для китайской интернет-архитектуры. Многие компании и школы сообщили о хороших результатах, следуя этому указанию. Однако область действия ограничивается расположениями пользовательской сети, которые находятся под контролем установки ИТ-сетей, например расположения офисов или конечных точек дома и мобильных устройств с подключением VPN. Microsoft Teams часто используются из внешних мест, таких как домашние офисы, мобильные пункты, на дороге и в кафе. Поскольку вызовы и собрания зависят от трафика мультимедиа в режиме реального времени, эти Teams особенно чувствительны к перегрузке сети.

В результате Корпорация Майкрософт в партнерстве с поставщиками телекоммуникаций для переноса трафика мультимедиа Teams и Skype для бизнеса Online в режиме реального времени с использованием более качественного, льготного сетевого пути между внутренними и общедоступными подключениями к Интернету в Китае и службами Teams и Skype в глобальном облаке Microsoft 365. Эта возможность приводит к более чем десятикратному улучшению потери пакетов и других ключевых показателей, которые влияют на пользовательский опыт.

>[!IMPORTANT]
>В настоящее время эти улучшения не касается участия в собраниях Microsoft Live Events, таких как крупные собрания вещания или стили "ратуши" с Teams или Microsoft Stream. Чтобы просмотреть собрание Live Events, пользователям в Китае необходимо использовать частную сеть или решение SDWAN/VPN. Тем не менее, улучшения сети будут приносить пользу пользователям, которые представляют или производят собрание Live Events, так как этот опыт выступает в качестве регулярного собрания Teams для производителя или презента.

### <a name="organization-network-best-practices-for-teams-meetings"></a>Наилучшие методы организации для Teams собраний

Необходимо подумать о том, как использовать эти улучшения сети, учитывая, что в предыдущем руководстве необходимо рассмотреть возможность расширения частной сети, чтобы избежать перегрузки трансграничной сети. Существует два общих варианта для организаций офисных сетей:

1. Ничего нового не делать. Продолжайте следовать прежним указаниям об обходе частных сетей, чтобы избежать перегрузок через границу. Teams медиа-трафик в режиме реального времени будет использовать эту установку, как и раньше.
2. Реализация шаблона split/hybrid.
   - Используйте предыдущее руководство для всех трафика, помеченных для оптимизации, кроме Teams собраний и вызова трафика мультимедиа в режиме реального времени.
   - Маршрут Teams собрания и вызова трафика мультимедиа в режиме реального времени через общедоступный Интернет. Следующие сведения см. в следующих сведениях об определении сетевого трафика сети мультимедиа в режиме реального времени.

Отправка Teams аудио- и видеопотока в режиме реального времени через общедоступный Интернет, использующий более высокое качество подключения, может привести к значительной экономии средств, так как это бесплатно, а не оплата для отправки этого трафика через частную сеть. Могут быть аналогичные дополнительные преимущества, если пользователи также используют SDWAN или VPN-клиенты. Некоторые организации также могут предпочитать, чтобы больше их данных пересекали общеуголовые подключения к Интернету в качестве общей практики.

Те же параметры могут применяться к конфигурациям SDWAN или VPN. Например, пользователь использует SDWAN или VPN для Microsoft 365 трафика в корпоративную сеть, а затем использует частное расширение этой сети, чтобы избежать перегрузок через границу. Теперь SDWAN или VPN пользователя можно настроить, чтобы исключить Teams собрания и вызова трафика в режиме реального времени из маршрутизов VPN. Эта конфигурация VPN называется раздельным туннелем. Дополнительные сведения см. в Office 365 vpn [split tunneling.](/microsoft-365/enterprise/microsoft-365-vpn-implement-split-tunnel)

Вы также можете продолжать использовать SDWAN или VPN для Microsoft 365 трафика, в том числе для Microsoft Teams трафика в режиме реального времени. У Корпорации Майкрософт нет рекомендаций по использованию решений SDWAN или VPN.

### <a name="home-mobile-and-user-network-best-practices-for-teams-meetings"></a>Лучшие практики домашней, мобильной и пользовательской сети для Teams собраний

Пользователи в Китае могут воспользоваться этими улучшениями, просто подключившись к государственной службе Интернета в Китае с помощью наземного или мобильного подключения. Teams аудио- и видеопоток в режиме реального времени в общественном интернете напрямую зависит от улучшения подключения и качества.

Однако данные других служб Microsoft 365 и другого трафика в Teams, таких как чат или файлы, напрямую не будут получать выгоду от этих улучшений. Пользователи за пределами сети организации могут по-прежнему испытывать неудовлетворительную производительность для этого трафика. Как говорится в этой статье, эти эффекты можно смягчить с помощью VPN или SDWAN. Кроме того, пользователи могут использовать богатые клиенты настольных компьютеров через веб-клиентов, которые поддерживают кэшинг в приложении для смягчения проблем с сетью.

### <a name="identifying-teams-real-time-media-network-traffic"></a>Определение Teams сетевого трафика в режиме реального времени

Для настройки сетевого устройства или установки VPN/SDWAN необходимо исключить только Teams аудио- и видеопоток в режиме реального времени. Сведения о трафике можно найти для ID 11 в официальном списке URL Office 365 url-адресов и [IP-адресов.](urls-and-ip-address-ranges.md#skype-for-business-online-and-microsoft-teams) Все остальные конфигурации сети должны оставаться как есть.

Корпорация Майкрософт постоянно работает над улучшением Microsoft 365 и производительности клиентов в максимально широком диапазоне сетевых архитектур и характеристик. Посетите [техническую Office 365](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking) сетевых Community, чтобы начать или присоединиться к беседе, найти ресурсы и отправить запросы на функции и предложения

## <a name="related-topics"></a>Статьи по теме

[Планирование сети и настройка производительности для Microsoft 365](./network-planning-and-performance.md)

[Принципы сетевого подключения к Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Управление конечными точками Office 365](managing-office-365-endpoints.md)

[URL-адреса и диапазоны IP-адресов для Office 365](urls-and-ip-address-ranges.md)

[Глобальная сеть Майкрософт](/azure/networking/microsoft-global-network)
