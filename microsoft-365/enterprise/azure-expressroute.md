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
description: Узнайте, как использовать Azure ExpressRoute с Office 365 и запланировать проект реализации сети, если вы развертываете его.
ms.openlocfilehash: 3691161767aba784039cbf317a51429c9ee6444c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692946"
---
# <a name="azure-expressroute-for-office-365"></a>Azure ExpressRoute для Office 365

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Узнайте, как использовать Azure ExpressRoute с Office 365 и как спланировать проект реализации сети, который будет необходим при развертывании Azure ExpressRoute для использования с Office 365. Службы инфраструктуры и платформ, работающие в Azure, часто получают преимущества, устраняя сетевую архитектуру и вопросы производительности. В таких случаях рекомендуется использовать ExpressRoute для Azure. Программное обеспечение в виде таких служб, как Office 365 и Dynamics 365, были созданы для надежного и надежного доступа через Интернет. Вы можете прочитать сведения о производительности и безопасности Интернета, а также о том, как вы можете использовать Azure ExpressRoute для Office 365 в статье [Оценка сетевого подключения office 365](assessing-network-connectivity.md).

> [!NOTE]
> Для использования ExpressRoute для Office 365 требуется авторизация Майкрософт. Корпорация Майкрософт изучает все запросы клиентов и авторизует ExpressRoute для Office 365, когда нормативное требование клиента требует прямого подключения. Если у вас есть такие требования, укажите фрагмент текста и веб-ссылку для оценки, означающие, что в форме веб- [запросов ExpressRoute для Office 365](https://aka.ms/O365ERReview) требуется прямое подключение для начала рецензирования Майкрософт. Неавторизованные подписки, пытающиеся создать фильтры маршрутов для Office 365, получат [сообщение об ошибке](https://support.microsoft.com/kb/3181709).

Теперь вы можете добавить прямое сетевое подключение к Office 365 для выбранного сетевого трафика Office 365. Azure ExpressRoute обеспечивает прямое подключение, предсказуемую производительность и приступает к соглашению об условиях работоспособности 99,95% для сетевых компонентов Майкрософт. Для служб, которые не поддерживаются в Azure ExpressRoute, по-прежнему потребуется подключение к Интернету.

## <a name="planning-azure-expressroute-for-office-365"></a>Планирование ExpressRoute в Azure для Office 365

В дополнение к подключению к Интернету можно направить подмножество сетевого трафика Office 365 по прямому подключению, которое обеспечивает предсказуемость и соглашение об уровне обслуживания 99,95% для сетевых компонентов Майкрософт. Azure ExpressRoute предоставляет вам это выделенное сетевое подключение к Office 365 и другим облачным службам Майкрософт.

Независимо от того, есть ли у вас Глобальная сеть MPLS, она может быть добавлена в сетевую архитектуру одним из трех способов. с помощью поддерживаемого облачного поставщика облачного расположения Exchange, поставщика подключения к точкам Ethernet или поставщика подключения MPLS. Узнайте [, какие поставщики доступны в вашем регионе](https://azure.microsoft.com/documentation/articles/expressroute-locations/). Подключение по прямому ExpressRoute позволит обеспечить подключение к приложениям, описанным в разделе [какие службы Office 365 включены?](azure-expressroute.md#BKMK_WhatDoIGet) Сетевой трафик для всех других приложений и служб по прежнему будет проходить через Интернет.

Рассмотрим следующую схему сети высокого уровня, которая показывает типичный клиент Office 365, который подключается к центрам обработки данных Майкрософт через Интернет для доступа ко всем приложениям Майкрософт, таким как Office 365, Windows Update и TechNet. Клиенты используют аналогичный сетевой путь независимо от того, подключены ли они из локальной сети или из независимого подключения к Интернету.

![Сетевое подключение к Office 365](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

Теперь взгляните на обновленную схему, в которой показано, как подключиться к Office 365 для пользователей Office 365, использующих Интернет и ExpressRoute. Обратите внимание на то, что для некоторых подключений, таких как общедоступные службы DNS и сеть доставки контента, по-прежнему требуется подключение к Интернету. Кроме того, обратите внимание на то, что пользователи клиента, не расположенные в вашем здании с подключением ExpressRoute, подключаются через Интернет.

![Подключение к Office 365 с помощью ExpressRoute](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

По-прежнему требуются дополнительные сведения? Узнайте, как [управлять сетевым трафиком с помощью Azure expressroute для office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) и Узнайте, как [настроить Azure ExpressRoute для Office 365](https://azure.microsoft.com/documentation/articles/expressroute-faqs/). Мы также записали 10 частей [Azure ExpressRoute для Office 365](https://channel9.msdn.com/series/aer) на канале 9, чтобы более тщательно объяснить концепции.

## <a name="what-office-365-services-are-included"></a>Какие службы Office 365 включены?
<a name="BKMK_WhatDoIGet"> </a>

В следующей таблице перечислены службы Office 365, поддерживаемые в ExpressRoute. Ознакомьтесь со [статьей "конечные точки Office 365](https://aka.ms/o365endpoints) ", чтобы узнать, какие сетевые запросы для этих приложений требуют подключения к Интернету.

|**Включенные приложения**|
|:-----|
|Exchange Online<sup>1</sup> <br/> Exchange Online Protection<sup>1</sup> <br/> Delve<sup>1</sup> <br/> |
|Skype для бизнеса Online<sup>1</sup> <br/> Microsoft Teams <sup>1</sup> <br/> |
|SharePoint Online<sup>1</sup> <br/> OneDrive для бизнеса<sup>1</sup> <br/> Project Online<sup>1</sup> <br/> |
|Портал и общий<sup>1</sup> <br/> Azure Active Directory (Azure AD) <sup>1</sup> <br/> Azure AD Connect<sup>1</sup> <br/> Office<sup>1</sup> <br/> |

<sup>1</sup> для каждого из этих приложений требования к подключению к Интернету не поддерживаются в ExpressRoute. Дополнительные сведения см. в [статье по конечным точкам Office 365](https://aka.ms/o365endpoints) .

Службы, не включенные в ExpressRoute для Office 365, представляют собой приложения Microsoft 365 для загрузки корпоративных клиентов, входа в систему локального поставщика удостоверений и службы Office 365 (под управлением 21 ВИАНЕТ) в Китае.

## <a name="implementing-expressroute-for-office-365"></a>Реализация средства ExpressRoute для Office 365

Для реализации ExpressRoute требуется привлечение владельцев сети и приложений, а также необходимость тщательного планирования для определения новой [архитектуры сетевой маршрутизации](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408), требований к пропускной способности, в том случае, когда безопасность будет реализована, высокой доступности и т. д. Для реализации ExpressRoute необходимо выполнить следующие действия:

1. Полностью разобраться в необходимости ExpressRoute в вашем планировании подключения к Office 365. Сведения о том, какие приложения будут использовать Интернет или ExpressRoute, и полностью запланируйте требования к емкости сети, безопасности и высокой доступности в контексте использования Интернета и ExpressRoute для трафика Office 365.

2. Определите расположение исходящих и равноправных узлов как для Интернета, так и для трафика ExpressRoute<sup>1</sup>.

3. Определите мощность, необходимую для подключений к Интернету и ExpressRoute.

4. Создайте план для реализации безопасности и других стандартных элементов управления периметра<sup>1</sup>.

5. Иметь действительную учетную запись Microsoft Azure для подписки на ExpressRoute.

6. Выберите модель подключения и [утвержденного поставщика](https://azure.microsoft.com/documentation/articles/expressroute-locations/). Имейте в виду, что пользователи могут выбрать несколько моделей или партнеров по подключению, а партнер не должен совпадать с существующим поставщиком сети.

7. Проверка развертывания до направления трафика в ExpressRoute.

8. При необходимости [реализуйте QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) и оцените региональные расширения.

<sup>1</sup> важное замечание относительно производительности. Решения здесь могут значительно повлиять на задержку, что является критически важным для таких приложений, как Skype для бизнеса.

Для дополнительных рекомендаций используйте наше [руководство по маршрутизации](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) в дополнение к [документации ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/).

Чтобы приобрести ExpressRoute для Office 365, вам потребуется работать с одним или несколькими [утвержденными поставщиками](https://azure.microsoft.com/documentation/articles/expressroute-locations/) , чтобы подготовить нужные номера и размеры к подписке ExpressRoute Premium. Нет дополнительных лицензий, которые можно приобрести в Office 365.

Вы можете быстро вернуться сюда с помощью этой короткой ссылки: [https://aka.ms/expressrouteoffice365](https://aka.ms/expressrouteoffice365)

Готовы к регистрации в [ExpressRoute для Office 365](https://aka.ms/ert)?

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
