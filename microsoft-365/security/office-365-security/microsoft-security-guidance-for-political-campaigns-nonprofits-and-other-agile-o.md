---
title: Руководство по безопасности (Майкрософт) для политических кампаний и некоммерческих организаций
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MET150
ms.custom:
- Strat_O365_Enterprise
- seo-marvel-apr2020
ms.assetid: 10d1004b-42b6-4e2b-aaa2-18ddd9118f64
description: Сводка. Руководство по планированию и реализации для быстроразвивающихся организаций с высокой вероятностью возникновения угроз безопасности.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e7d16f63b808edc008022b17d20461df6cd30e75
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150776"
---
# <a name="microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-organizations"></a>Руководство по безопасности (Майкрософт) для политических кампаний, некоммерческих и других динамических организаций

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender для Office 365 (план 1 и план 2)](https://go.microsoft.com/fwlink/?linkid=2148715)

 **Сводка.** Руководство по планированию и реализации для быстроразвивающихся организаций с высокой вероятностью возникновения угроз безопасности.

Если у вас динамичная организация, небольшая команда ИТ-специалистов, а профиль угроз выше среднего, это руководство — именно то, что вам нужно. Здесь вы узнаете, как быстро создать среду с основными облачным службами, куда изначально входят и элементы управления безопасностью. В этом руководстве приводятся рекомендации по защите данных, электронной почты и удостоверений, а также по организации безопасного доступа с мобильных устройств.

## <a name="security-solution-guidance"></a>Руководство по безопасности

В этом руководстве описано, как реализовать безопасную облачную среду. Это руководство может использовать любая организация. В него входят дополнительные справочные сведения для организации с гибкими возможностями работы с доступом BYOD и учетными записями гостей. Его можно взять за основу при разработке собственной среды. Отзывы можно отправлять по адресу [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).

****

|Элемент|Описание|
|---|---|
|**Руководство по безопасности (Майкрософт) для политических кампаний** <br> [![Эскиз для набора мини-постеров.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf) <br> [PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf) \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)|В этом руководстве в качестве примера приведена организация, проводящая политические кампании. Используйте это руководство в качестве отправной точки для любой среды.|
|**Руководство по безопасности (Майкрософт) для некоммерческих организаций** <br> [![Эскиз для скачиваемого файла](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf) <br> [PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf) \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)|В это руководство внесены незначительные изменения, благодаря которым оно подходит некоммерческим организациям. Например, рассмотрены планы Office 365 для некоммерческих организаций. Техническое руководство ничем не отличается от такового для организаций, проводящих политические кампании.|
|

## <a name="test-lab-guides"></a>Руководства по лаборатории тестирования

Чтобы создать среду разработки и тестирования для этого решения, используйте следующие руководства:

- [Настройка групп и пользователей в случае среды разработки и тестирования для политической кампании](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

  Создайте пробные подписки на Office 365 и EMS, а затем создайте группы и пользователей для типичной политической кампании.

- [Создание сайтов групп в среде разработки и тестирования для политической кампании](create-team-sites-in-a-political-campaign-dev-test-environment.md)

  Создайте четыре сайта группы SharePoint Online с уровнями безопасности "Для внутреннего пользования", "Для личного пользования", "Конфиденциально" и "Строго конфиденциально".

Дополнительные функции безопасности для демонстрации или доказательства правильности концепции см. в статье [Руководства по лаборатории тестирования Office 365](https://aka.ms/o365tlgs).

## <a name="see-also"></a>См. также

[Руководства по лабораториям тестирования (TLG) для принятия облачных решений](https://docs.microsoft.com/microsoft-365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[Ресурсы, посвященные ИТ-архитектуре Microsoft Cloud](https://docs.microsoft.com/microsoft-365/solutions/cloud-architecture-models)
