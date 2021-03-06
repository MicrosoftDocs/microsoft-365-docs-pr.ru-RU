---
title: 'Обзор: раздельное VPN-туннелирование в Office 365'
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/22/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: Руководство по использованию раздельного VPN-туннелирования в Office 365 для оптимизации подключения Office 365 для удаленных пользователей.
ms.openlocfilehash: c92599469431732136637cee2bb6a029c4eb4037
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259251"
---
# <a name="optimize-office-365-connectivity-for-remote-users-using-vpn-split-tunneling"></a>Оптимизация подключения Office 365 для удаленных пользователей с использованием VPN-туннелирования
<!---
>[!NOTE]
>This topic is part of a set of topics that address Office 365 optimization for remote users.
>- For VPN split tunnel implementation guidance, see [Implementing VPN split tunneling for Office 365](microsoft-365-vpn-implement-split-tunnel.md).
>- For information about optimizing Office 365 worldwide tenant performance for users in China, see [Office 365 performance optimization for China users](microsoft-365-networking-china.md).
-->

Для **клиентов,** которые подключают свои удаленные рабочие устройства к корпоративной сети или облачной инфраструктуре через VPN, Корпорация Майкрософт рекомендует, чтобы ключевые  сценарии Office 365 Microsoft Teams, **SharePoint Online** и **Exchange Online** были перенапорчены по конфигурации vpn-раздельного туннеля. Это становится особенно важным в качестве стратегии первой строки, облегчаемой дальнейшей производительности сотрудников во время крупномасштабных внутренних событий, таких как кризис COVID-19.

![Конфигурация Split Tunnel VPN](../media/vpn-split-tunneling/vpn-model-2.png)

_Рисунок 1: Решение VPN с разделенным туннелем с определенными исключениями Office 365, отправленными непосредственно в службу. Весь другой трафик проходит через VPN-туннель независимо от пункта назначения._

Суть этого подхода заключается в том, чтобы предоставить предприятиям простой метод снижения риска насыщения инфраструктуры VPN и существенного повышения производительности Office 365 в кратчайшие сроки. Конфигурирование VPN-клиентов для обеспечения возможности пропускания наиболее критически важного трафика Office 365 в обход VPN-туннеля обеспечивает следующие преимущества:

- Немедленно устраняет основную причину большинства проблем производительности и емкости сети, о которых сообщают клиенты, в архитектурах корпоративной VPN, влияющих на работу пользователей Office 365
  
  Рекомендуемое решение специально предназначено для конечных точек службы Office 365, отнесенных к категории **Оптимизировать** в разделе [URL-адреса и диапазоны IP-адресов Office 365](./urls-and-ip-address-ranges.md). Трафик в эти конечные точки очень чувствителен к задержке и управлению пропускной способностью, и его обход VPN-тоннеля может значительно повысить производительность конечного пользователя, а также снизить нагрузку на корпоративную сеть. Соединения Office 365, которые не составляют большую часть полосы пропускания или воздействия на пользователя, могут по-прежнему маршрутизироваться через VPN-туннель вместе с остальным интернет-трафиком. Для получения дополнительной информации см. [Стратегию VPN с разделенным туннелем](#the-vpn-split-tunnel-strategy).

- Клиенты могут быстро настраивать, тестировать и внедрять их без дополнительных требований к инфраструктуре или приложениям.

  В зависимости от платформы VPN и сетевой архитектуры, внедрение может занять всего несколько часов. Дополнительные сведения см. в статье [Внедрение раздельного VPN-туннелирования](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling).

- Сохраняет состояние безопасности реализации VPN клиента, не меняя способ маршрутизации других соединений, включая трафик в Интернет

  Рекомендуемая конфигурация следует принципу **наименьших привилегий** для исключений трафика VPN и позволяет клиентам реализовать VPN с разделенным туннелем, не подвергая пользователей или инфраструктуру дополнительным рискам безопасности. Сетевой трафик, который Office 365 конечные точки, шифруется, проверяется на целостность стеками Office клиентских приложений и в области IP-адресов, посвященных Office 365 службам, которые закалены как на уровне приложений, так и на уровне сети. Дополнительные сведения см. в разделе [Альтернативные способы обеспечения профессионалами безопасности и ИТ-отделом современных средств управления безопасностью в современных уникальных сценариях удаленной работы (блог Microsoft Security Team)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/).

- Поддерживается большинством корпоративных VPN-платформ

  Microsoft продолжает сотрудничать с отраслевыми партнерами, производящими коммерческие решения VPN, чтобы помочь партнерам разработать целевые руководства и шаблоны конфигурации для своих решений в соответствии с приведенными выше рекомендациями. Для получения дополнительной информации см. [Руководства HOWTO для распространенных платформ VPN](microsoft-365-vpn-implement-split-tunnel.md#howto-guides-for-common-vpn-platforms).

>[!TIP]
>Microsoft рекомендует сосредоточить конфигурацию VPN с разделенным туннелем на задокументированных выделенных диапазонах IP-адресов для служб Office 365. Конфигурации разделенного туннеля на основе FQDN или AppID, хотя и возможны на определенных клиентских платформах VPN, могут не полностью покрывать ключевые сценарии Office 365 и могут конфликтовать с правилами маршрутизации VPN на основе IP. По этой причине Microsoft не рекомендует использовать полные доменные имена Office 365 для настройки VPN с разделенным туннелем. Использование конфигурации FQDN может быть полезно в других связанных сценариях, таких как настройки файла .pac или для реализации обхода прокси.

Полное руководство по внедрению см. в статье [Внедрение раздельного VPN-туннелирования для Office 365](microsoft-365-vpn-implement-split-tunnel.md).

Для пошагового процесса настройки Microsoft 365 удаленных сотрудников см. в перенастройке инфраструктуры [для удаленной работы](..\solutions\empower-people-to-work-remotely.md)

## <a name="the-vpn-split-tunnel-strategy"></a>Стратегия VPN с разделением туннелей

Традиционные корпоративные сети часто разрабатываются для безопасной работы в мире, предшествующем облачным вычислениям, где наиболее важные данные, службы, приложения размещаются в локальной сети и напрямую подключаются к внутренней корпоративной сети, как и большинство пользователей. Таким образом, сетевая инфраструктура построена вокруг этих элементов в том, что филиалы подключены к головному офису через сети _многопротокольной коммутации по меткам (MPLS)_, а удаленные пользователи должны подключаться к корпоративной сети через VPN для доступа как к конечным точкам помещений, так и к Интернету. В этой модели весь трафик от удаленных пользователей проходит через корпоративную сеть и направляется в облачную службу через общую выходную точку.

![Принудительная настройка VPN](../media/vpn-split-tunneling/vpn-model-1.png)

_Рисунок 2: Общее решение VPN для удаленных пользователей, когда весь трафик возвращается в корпоративную сеть независимо от места назначения_

По мере перемещения данных и приложений в облако эта модель стала менее эффективной, поскольку она быстро становится громоздкой, дорогостоящей и непосчитаемой, что значительно влияет на производительность и эффективность работы сети пользователей и ограничивает возможности организации адаптироваться к меняющимся потребностям. Многочисленные клиенты Майкрософт сообщали, что несколько лет назад 80% сетевого трафика было внутренним, но в 2020 году 80% плюс трафик подключается к внешнему облачному ресурсу.

Кризис COVID-19 усугубил эту проблему и потребовал немедленных решений для подавляющего большинства организаций. Многие клиенты обнаружили, что модель принудительной VPN не масштабируется или не обеспечивает достаточную производительность для 100% сценариев удаленной работы, таких как тот, который потребовался в результате этого кризиса. Для эффективной работы этих организаций необходимы быстрые решения.

Для службы Office 365 Microsoft разработала требования к подключению для службы с учетом этой проблемы, в которой целенаправленный, жестко управляемый и относительно статический набор конечных точек службы можно оптимизировать очень просто и быстро, чтобы обеспечить высокую производительность для пользователей, доступ к службе, а также снизить нагрузку на инфраструктуру VPN, чтобы она может использоваться трафиком, который по-прежнему требует этого.

Office 365 разделяет обязательные конечные точки для Office 365 на три категории: **оптимизация**, **разрешение** и **по умолчанию**. Конечные точки с меткой **Оптимизация** находятся в центре нашего внимания и имеют следующие характеристики:

- Находятся ли Microsoft в собственности и управляются конечными точками, размещенными на инфраструктуре Microsoft
- Предназначены для основных рабочих нагрузок Office 365, таких как Exchange Online, SharePoint Online, Skype для бизнеса Online и Microsoft Teams
- Есть IP-адреса
- Низкий уровень изменений и, как ожидается, останется небольшим числом (в настоящее время 20 IP-подсетей)
- Чувствительны к большой громкости и / или задержке
- Могут иметь необходимые элементы безопасности, предоставляемые в сервисе, а не встроенные в сеть
- На его долю приходится около 70-80% объема трафика службы Office 365

Этот ограниченный набор конечных точек можно выделить из принудительного VPN-туннеля и безопасно и напрямую отправить в службу Office 365 через локальный интерфейс пользователя. Это называется **раздельное туннелирование**.

Такие элементы безопасности, как DLP, защита av, проверка подлинности и управление доступом, могут быть доставлены гораздо эффективнее в отношении этих конечных точек на разных уровнях службы. Так как мы также отвлекаем основную часть объема трафика от решения VPN, это освободит емкость VPN для критически важного для бизнеса трафика, который по-прежнему зависит от него. Это также должно устранить необходимость во многих случаях проходить длительную и дорогостоящую программу обновления, чтобы справиться с этим новым способом работы.

![Сведения Tunnel конфигурации VPN](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

_Рисунок 3: Решение VPN с разделенным туннелем с определенными исключениями Office 365, отправленными непосредственно в службу. Весь остальной трафик возвращается обратно в корпоративную сеть независимо от пункта назначения._

С точки зрения безопасности, у Microsoft есть множество функций безопасности, которые можно использовать для обеспечения аналогичной или даже улучшенной безопасности, чем при встроенной проверке локальных стеков безопасности. Сообщение в блоге группы безопасности Microsoft [Альтернативные способы обеспечения профессионалами безопасности и ИТ-отделом современных средств управления безопасностью в современных уникальных сценариях удаленной работы](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) содержит четкое описание доступных функций, и в этой статье вы найдете более подробное руководство. Вы также можете прочитать о внедрении раздельного VPN-туннелирования Microsoft в статье [Запуск по VPN: как Microsoft поддерживает подключение своих удаленных сотрудников](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv).

Во многих случаях эта реализация может быть достигнута за считанные часы, что позволяет быстро решить одну из самых насущных проблем, с которыми сталкиваются организации, поскольку они быстро переходят к полномасштабной удаленной работе. Руководство по внедрению VPN с разделением туннелей см. в статье [Внедрение раздельного VPN-туннелирования для Office 365](microsoft-365-vpn-implement-split-tunnel.md).

## <a name="related-topics"></a>Статьи по теме

[Внедрение раздельного VPN-туннелирования для Office 365](microsoft-365-vpn-implement-split-tunnel.md)

[Оптимизация производительности Office 365 для пользователей Китая](microsoft-365-networking-china.md)

[Альтернативные пути для специалистов по безопасности и ИТ для достижения современных мер безопасности в современных уникальных сценариях удаленной работы (блог Microsoft Security Team)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Улучшение производительности VPN в Майкрософт: использование VPN-профилей Windows 10 для разрешения автоматических подключений](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[Запуск по VPN: как Microsoft поддерживает подключение своих удаленных сотрудников](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Принципы сетевого подключения к Office 365](microsoft-365-network-connectivity-principles.md)

[Доступ к сетевому подключению Office 365](assessing-network-connectivity.md)

[Проверка возможности подключения Microsoft 365](https://aka.ms/netonboard)