---
title: Azure ExpressRoute для Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/5/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 6d2534a2-c19c-4a99-be5e-33a0cee5d3bd
description: Узнайте, как использовать Azure ExpressRoute с Office 365 и спланируйте проект сетевой реализации при развертывании с ним.
ms.openlocfilehash: 7e44feefd375088d2fef36c7e7859e242c1a30aa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905360"
---
# <a name="azure-expressroute-for-office-365"></a>Azure ExpressRoute для Office 365

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Узнайте, как Azure ExpressRoute используется в Office 365 и как планировать проект сетевой реализации, который потребуется при развертывании Azure ExpressRoute для использования в Office 365. Службы инфраструктуры и платформы, работающие в Azure, часто выиграют от решения проблем сетевой архитектуры и производительности. В этих случаях рекомендуется использовать ExpressRoute для Azure. Программное обеспечение как служба, например Office 365 и Dynamics 365, было построено для безопасного и надежного доступа через Интернет. О производительности и безопасности в Интернете и о том, когда можно рассмотреть Azure ExpressRoute для Office 365, можно прочитать в статье Оценка сетевого подключения [Office 365.](assessing-network-connectivity.md)

> [!NOTE]
> Для использования ExpressRoute для Office 365 требуется авторизация Корпорации Майкрософт. Корпорация Майкрософт проверяет каждый запрос клиента и разрешает использование ExpressRoute для Office 365, когда нормативные требования клиента предписывают прямое подключение. Если у вас есть такие требования, пожалуйста, укажете текстовое отрывок и веб-ссылку на регулирование, которое вы интерпретируете, чтобы означать, что в форме запроса [ExpressRoute для Office 365](https://aka.ms/O365ERReview) требуется прямое подключение для начала проверки Майкрософт. Несанкционированные подписки, которые пытаются создать фильтры маршрутов для Office 365, получат сообщение [об ошибке.](https://support.microsoft.com/kb/3181709)

Теперь можно добавить прямое сетевое подключение к Office 365 для выбранного сетевого трафика Office 365. Azure ExpressRoute обеспечивает прямое подключение, предсказуемую производительность и обеспечивает 99,95% времени работы компонентов сети Майкрософт. Для служб, которые не поддерживаются в Azure ExpressRoute, по-прежнему потребуется подключение к Интернету.

## <a name="planning-azure-expressroute-for-office-365"></a>Планирование Azure ExpressRoute для Office 365

Помимо подключения к Интернету, вы можете перенаправить подмножество сетевого трафика Office 365 по прямому подключению, которое обеспечивает предсказуемость и 99,95% времени простоя SLA для компонентов сети Майкрософт. Azure ExpressRoute предоставляет вам это выделенное сетевое подключение к Office 365 и другим облачным службам Майкрософт.

Независимо от того, имеется ли у вас существующий WAN MPLS, ExpressRoute можно добавить в архитектуру сети одним из трех способов; через поддерживаемого поставщика совместной расположения облачной биржи, поставщика точечного подключения Ethernet или через поставщика подключения MPLS. Узнайте, [какие поставщики доступны в вашем регионе.](/azure/expressroute/expressroute-locations) Прямое подключение ExpressRoute позволит подключаться к приложениям, описанным в том, какие службы [Office 365 включены?](azure-expressroute.md#BKMK_WhatDoIGet) ниже. Сетевой трафик для всех других приложений и служб будет по-прежнему проходить через Интернет.

Рассмотрим следующую схему сети высокого уровня, на которой показан типичный клиент Office 365, подключающийся к центрам обработки данных Майкрософт через Интернет для доступа ко всем приложениям Майкрософт, таким как Office 365, Windows Update и TechNet. Клиенты используют аналогичный сетевой путь независимо от того, подключаются ли они к локальной сети или независимо от подключения к Интернету.

![Подключение к сети Office 365](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

Теперь посмотрите на обновленную схему, на которой изображен клиент Office 365, который использует интернет и ExpressRoute для подключения к Office 365. Обратите внимание, что для некоторых подключений, таких как общедоступные узлы DNS и Сети доставки контента, по-прежнему требуется подключение к Интернету. Кроме того, обратите внимание, что пользователи, которые не находятся в подключенной к ExpressRoute здании, подключаются через Интернет.

![Подключение Office 365 с ExpressRoute](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

Все еще хотите получить дополнительные сведения? Узнайте, как управлять сетевым трафиком с [помощью Azure ExpressRoute для Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) и узнайте, как настроить [Azure ExpressRoute для Office 365.](/azure/expressroute/expressroute-faqs) Мы также записали 10-ю часть учебной серии [Azure ExpressRoute для Office 365 на](https://channel9.msdn.com/series/aer) 9-м канале, чтобы более подробно объяснить эти понятия.

## <a name="what-office-365-services-are-included"></a>Какие службы Office 365 включены?
<a name="BKMK_WhatDoIGet"> </a>

В следующей таблице перечислены службы Office 365, поддерживаемые в ExpressRoute. Просмотрите [статью Конечные точки Office 365,](./urls-and-ip-address-ranges.md) чтобы понять, какие сетевые запросы для этих приложений требуют подключения к Интернету.

|**Включенные приложения**|
|:-----|
|Exchange Online<sup>1</sup> <br/> Exchange Online Protection<sup>1</sup> <br/> Delve<sup>1</sup> <br/> |
|Skype для бизнеса Online<sup>1</sup> <br/> Microsoft Teams <sup>1</sup> <br/> |
|SharePoint Online<sup>1</sup> <br/> OneDrive для бизнеса<sup>1</sup> <br/> Project Online<sup>1</sup> <br/> |
|Портал и общий<sup>1</sup> <br/> Azure Active Directory (Azure AD) <sup>1</sup> <br/> Azure AD Connect<sup>1</sup> <br/> Office<sup>1</sup> <br/> |

<sup>1 Каждое</sup> из этих приложений имеет требования к подключению к Интернету, не поддерживаемые в ExpressRoute, см. в статье Конечные точки [Office 365](./urls-and-ip-address-ranges.md) для получения дополнительных сведений.

Службы, не включенные в ExpressRoute для Office 365, это приложения Microsoft 365 для загрузки корпоративных клиентов, вход поставщика удостоверений на локальном уровне и служба Office 365 (управляется 21 Vianet) в Китае.

## <a name="implementing-expressroute-for-office-365"></a>Реализация средства ExpressRoute для Office 365

Реализация ExpressRoute требует участия владельцев сетей и приложений и требует тщательного планирования, чтобы определить новую архитектуру маршрутов [сети,](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)требования к пропускной способности, где будет реализована безопасность, высокая доступность и так далее. Чтобы реализовать ExpressRoute, необходимо:

1. Полное понимание потребности ExpressRoute в планировании подключения Office 365. Поймите, какие приложения будут использовать Интернет или ExpressRoute, и полностью спланируйте свои сетевые возможности, безопасность и высокие потребности в доступности в контексте использования как интернета, так и expressRoute для трафика Office 365.

2. Определите расположения egress и peering как для интернета, так и для трафика ExpressRoute<sup>1</sup>.

3. Определите емкость, необходимую для подключения к Интернету и ExpressRoute.

4. У вас есть план для реализации безопасности и других стандартных элементов управления периметром<sup>1</sup>.

5. Чтобы подписаться на ExpressRoute, необходимо иметь допустимую учетную запись Microsoft Azure.

6. Выберите модель подключения и [утвержденный поставщик.](/azure/expressroute/expressroute-locations) Помните, что клиенты могут выбрать несколько моделей подключения или партнеров, и партнер не должен быть таким же, как существующий поставщик сети.

7. Проверка развертывания перед тем, как направлять трафик в ExpressRoute.

8. Необязательно [внедрять QoS и](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) оценивать региональное расширение.

<sup>1</sup> Важные соображения производительности. Решения здесь могут резко повлиять на задержку, которая имеет решающее значение для таких приложений, как Skype для бизнеса.

Дополнительные ссылки можно использовать в [руководстве по](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) маршрутике в дополнение к документации [ExpressRoute.](/azure/expressroute/expressroute-introduction)

Чтобы приобрести ExpressRoute для Office 365, необходимо работать [](/azure/expressroute/expressroute-locations) с одним или более утвержденными поставщиками для предоставления нужных схем номеров и размеров с помощью подписки ExpressRoute Premium. Дополнительных лицензий на покупку в Office 365 нет.

Вы можете быстро вернуться сюда с помощью этой короткой ссылки: [https://aka.ms/expressrouteoffice365]()

Готовый к регистрации [для ExpressRoute для Office 365?](https://aka.ms/ert)

## <a name="related-topics"></a>Статьи по теме

[Оценка сетевого подключения к Office 365](assessing-network-connectivity.md)

[Управление подключением ExpressRoute для Office 365](managing-expressroute-for-connectivity.md)

[Маршрутизация с использованием ExpressRoute для Office 365](routing-with-expressroute.md)

[Планирование сети при использовании ExpressRoute для Office 365](network-planning-with-expressroute.md)

[Реализация ExpressRoute для Office 365](implementing-expressroute.md)

[Использование сообществ BGP в сценариях ExpressRoute для Office 365](bgp-communities-in-expressroute.md)

[Качество мультимедиа и характеристики сетевого подключения в случае Skype для бизнеса Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[Настройка производительности Office 365 с помощью базовых показателей и журнала производительности](performance-tuning-using-baselines-and-history.md)

[План устранения проблем с производительностью Office 365](performance-troubleshooting-plan.md)

[URL-адреса и диапазоны IP-адресов для Office 365](urls-and-ip-address-ranges.md)

[Сеть Office 365 и настройка производительности](network-planning-and-performance.md)

## <a name="see-also"></a>См. также

[Обзор Microsoft 365 корпоративный](microsoft-365-overview.md)