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
description: Узнайте, как использовать Azure ExpressRoute с Office 365 и планировать проект сетевой реализации при развертывании с ним.
ms.openlocfilehash: 3691161767aba784039cbf317a51429c9ee6444c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692946"
---
# <a name="azure-expressroute-for-office-365"></a>Azure ExpressRoute для Office 365

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Узнайте, как Azure ExpressRoute используется с Office 365 и как спланировать проект реализации сети, который потребуется при развертывании Azure ExpressRoute для использования с Office 365. Службы инфраструктуры и платформы, работающие в Azure, часто получают преимущества, учитывая сетевую архитектуру и производительность. В таких случаях мы рекомендуем Использовать ExpressRoute для Azure. Предложения программного обеспечения как услуги, такие как Office 365 и Dynamics 365, были построены для безопасного и надежного доступа через Интернет. Вы можете ознакомиться с производительностью и безопасностью в Интернете, а также о том, когда вы можете рассмотреть Azure ExpressRoute для Office 365, в статье "Оценка сетевого подключения [к Office 365".](assessing-network-connectivity.md)

> [!NOTE]
> Для использования ExpressRoute для Office 365 требуется авторизация Майкрософт. Корпорация Майкрософт проверяет каждый запрос клиента и авторизирует ExpressRoute для использования Office 365, если нормативные требования клиента предписывают прямое подключение. Если у вас есть такие требования, укажете выдержку из текста и веб-ссылку на регламент, который вы интерпретируете, чтобы начать проверку Корпорации Майкрософт, в форме запроса [ExpressRoute для Office 365](https://aka.ms/O365ERReview) требуется прямое подключение. Неавторизованные подписки, которые пытаются создать фильтры маршрутов для Office 365, получат сообщение [об ошибке.](https://support.microsoft.com/kb/3181709)

Теперь вы можете добавить прямое сетевое подключение к Office 365 для выбранного сетевого трафика Office 365. Azure ExpressRoute обеспечивает прямое подключение, предсказуемую производительность и предоставляет 99,95 % времени работы для сетевых компонентов Майкрософт. Вам по-прежнему потребуется подключение к Интернету для служб, которые не поддерживаются в Azure ExpressRoute.

## <a name="planning-azure-expressroute-for-office-365"></a>Планирование Azure ExpressRoute для Office 365

Помимо подключения к Интернету, вы можете перенаправить часть сетевого трафика Office 365 через прямое подключение, которое обеспечивает предсказуемость и 99,95 % времени работы SLA для сетевых компонентов Майкрософт. Azure ExpressRoute предоставляет вам это выделенное сетевое подключение к Office 365 и другим облачным службам Майкрософт.

Независимо от того, имеется ли у вас сеть MPLS WAN, ExpressRoute можно добавить в сетевую архитектуру одним из трех способов; через поддерживаемого поставщика расположения облачной службы обмена данными, поставщика подключений "точка-точка" Ethernet или через поставщика подключения MPLS. Посмотрите, [какие поставщики доступны в вашем регионе.](https://azure.microsoft.com/documentation/articles/expressroute-locations/) Прямое подключение ExpressRoute позволяет подключаться к приложениям, описанным в описании служб [Office 365?](azure-expressroute.md#BKMK_WhatDoIGet) ниже. Сетевой трафик для всех остальных приложений и служб будет по-прежнему проходить через Интернет.

Рассмотрим следующую высокоуровневую сетевую схему, на которой показан типичный клиент Office 365, подключающийся к центрам обработки данных Майкрософт через Интернет для доступа ко всем приложениям Майкрософт, таким как Office 365, Центр обновления Windows и TechNet. Клиенты используют аналогичный сетевой путь независимо от того, подключаются ли они из локальной сети или из независимого подключения к Интернету.

![Сетевое подключение Office 365](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

Теперь посмотрите на обновленную схему, на которой изображен клиент Office 365, который использует Интернет и ExpressRoute для подключения к Office 365. Обратите внимание, что для некоторых подключений, таких как общедоступные узлы DNS и сети доставки содержимого, по-прежнему требуется подключение к Интернету. Кроме того, обратите внимание, что пользователи клиента, не расположенные в его здании с подключением ExpressRoute, подключаются через Интернет.

![Подключение Office 365 к ExpressRoute](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

По-прежнему хотите получить дополнительные сведения? Узнайте, как управлять сетевым трафиком с помощью [Azure ExpressRoute для Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) и как настроить [Azure ExpressRoute для Office 365.](https://azure.microsoft.com/documentation/articles/expressroute-faqs/) Мы также добавили 10-часть обучающего цикла [Azure ExpressRoute для Office 365](https://channel9.msdn.com/series/aer) на канале Channel 9, чтобы более подробно объяснить эти концепции.

## <a name="what-office-365-services-are-included"></a>Какие службы Office 365 включены?
<a name="BKMK_WhatDoIGet"> </a>

В следующей таблице перечислены службы Office 365, которые поддерживаются через ExpressRoute. Просмотрите [статью о конечных точках Office 365,](https://aka.ms/o365endpoints) чтобы понять, какие сетевые запросы для этих приложений требуют подключения к Интернету.

|**Включенные приложения**|
|:-----|
|Exchange Online<sup>1</sup> <br/> Exchange Online Protection<sup>1</sup> <br/> Delve<sup>1</sup> <br/> |
|Skype для бизнеса Online<sup>1</sup> <br/> Microsoft Teams <sup>1</sup> <br/> |
|SharePoint Online<sup>1</sup> <br/> OneDrive для бизнеса<sup>1</sup> <br/> Project Online<sup>1</sup> <br/> |
|Портал и общий<sup>доступ 1</sup> <br/> Azure Active Directory (Azure AD) <sup>1</sup> <br/> Azure AD Connect<sup>1</sup> <br/> Office<sup>1</sup> <br/> |

<sup>1</sup> У каждого из этих приложений есть требования к подключению к Интернету, не поддерживаемые в ExpressRoute. Дополнительные сведения см. в статье о конечных точках [Office 365.](https://aka.ms/o365endpoints)

Службы, не включенные в ExpressRoute для Office 365: загрузки приложений Microsoft 365 для корпоративных клиентов, вход локального поставщика удостоверений и служба Office 365 (под управлением 21 Vianet) в Китае.

## <a name="implementing-expressroute-for-office-365"></a>Реализация средства ExpressRoute для Office 365

Реализация ExpressRoute требует привлечения владельцев сети и приложений и требует тщательного планирования, чтобы определить новую архитектуру маршрутиза трафика [сети,](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)требования к пропускной способности, где будет реализована безопасность, высокая доступность и так далее. Чтобы реализовать ExpressRoute, необходимо выполнить:

1. В полной мере необходимо, чтобы ExpressRoute удовлетворял вашим планам подключения к Office 365. Понять, какие приложения будут использовать Интернет или ExpressRoute, и полностью спланировать потребности в пропускной способности, безопасности и высокой доступности в контексте использования Интернета и ExpressRoute для трафика Office 365.

2. Определите расположения для трафика egress и пиринга как для Интернета, так и для трафика ExpressRoute<sup>1.</sup>

3. Определите емкость, необходимую для подключений к Интернету и ExpressRoute.

4. Разпланируйте реализацию безопасности и других стандартных элементов управления периметра<sup>1.</sup>

5. Иметь допустимую учетную запись Microsoft Azure, чтобы подписаться на ExpressRoute.

6. Выберите модель подключения и [утвержденного поставщика.](https://azure.microsoft.com/documentation/articles/expressroute-locations/) Помните, что клиенты могут выбрать несколько моделей подключения или партнеров, и партнер не должен быть тем же, что и существующий сетевой поставщик.

7. Проверьте развертывание, прежде чем направлять трафик в ExpressRoute.

8. При [желании реализуем QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) и оцениваем региональное расширение.

<sup>1.</sup> Важные вопросы производительности. Здесь решения могут существенно повлиять на задержку, которая критически важна для таких приложений, как Skype для бизнеса.

Для получения дополнительных ссылок [воспользуйтесь](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) нашим руководством по маршруту в дополнение к [документации ExpressRoute.](https://azure.microsoft.com/documentation/articles/expressroute-introduction/)

Чтобы приобрести ExpressRoute для Office 365, необходимо работать [](https://azure.microsoft.com/documentation/articles/expressroute-locations/) с одним или более утвержденными поставщиками для предоставления желаемых номеров и размеров с помощью подписки ExpressRoute Premium. Дополнительные лицензии на покупку в Office 365 не существуют.

Вы можете быстро вернуться сюда с помощью этой короткой ссылки: [https://aka.ms/expressrouteoffice365](https://aka.ms/expressrouteoffice365)

Готовы зарегистрироваться в [ExpressRoute для Office 365?](https://aka.ms/ert)

## <a name="related-topics"></a>Статьи по теме

[Оценка сетевого подключения к Office 365](assessing-network-connectivity.md)

[Управление подключением ExpressRoute для Office 365](managing-expressroute-for-connectivity.md)

[Маршрутизация с использованием ExpressRoute для Office 365](routing-with-expressroute.md)

[Планирование сети при использовании ExpressRoute для Office 365](network-planning-with-expressroute.md)

[Реализация ExpressRoute для Office 365](implementing-expressroute.md)

[Использование сообществ BGP в ExpressRoute для сценариев Office 365](bgp-communities-in-expressroute.md)

[Качество мультимедиа и характеристики сетевого подключения в случае Skype для бизнеса Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[Настройка производительности Office 365 с помощью базовых показателей и журнала производительности](performance-tuning-using-baselines-and-history.md)

[План устранения проблем с производительностью Office 365](performance-troubleshooting-plan.md)

[URL-адреса и диапазоны IP-адресов для Office 365](urls-and-ip-address-ranges.md)

[Сеть Office 365 и настройка производительности](network-planning-and-performance.md)

## <a name="see-also"></a>См. также

[Обзор Microsoft 365 корпоративный](microsoft-365-overview.md)
