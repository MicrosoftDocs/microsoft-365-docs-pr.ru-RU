---
title: Новые возможности Microsoft 365 Defender
description: Список новых функций и функций в Microsoft 365 Defender
keywords: новые возможности защиты от угроз (Майкрософт), общедоступная, возможности, доступные, новые возможности
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 8e66c734151e7476d7c54bd050891a1bffb17b3c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932026"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Новые возможности Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> Хотите испытать Microsoft 365 Defender? Вы можете [оценить его в лабораторной среде](https://aka.ms/mtp-trial-lab) или запустить [пилотный проект в производственной среде.](https://aka.ms/m365d-pilotplaybook)
>

Следующие функции доступны в последнем выпуске Microsoft 365 Defender.

RSS-канал: получите уведомление при обновлении этой страницы, скопируйте и в pasting следующий URL-адрес в вашем канале чтения:
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
> Хотите испытать Microsoft 365 Defender? Вы можете [оценить его в лабораторной среде](https://aka.ms/mtp-trial-lab) или запустить [пилотный проект в производственной среде](https://aka.ms/m365d-pilotplaybook)
>

## <a name="september-2020"></a>Сентябрь 2020 г.
- [Таблица IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) <br> Поиск событий с использованием локального контроллера домена под управлением Active Directory (AD). В [этой таблице схемы advanced hunting](advanced-hunting-overview.md) охватывается ряд событий, связанных с удостоверением, и системных событий на контроллере домена.
- [Функция AssignedIPAddresses()](advanced-hunting-assignedipaddresses-function.md) <br> Используйте эту функцию в расширенных запросах на поиск, чтобы быстро получить последние IP-адреса, присвоенные устройству, или последние IP-адреса за определенное время.

## <a name="july-2020"></a>Июль 2020 г.
- [Функция FileProfile()](advanced-hunting-fileprofile-function.md) <br> Используйте эту функцию в расширенных запросах поиска, чтобы обогатить результаты с помощью полной информации о файле.
- [Таблицы удостоверений и приложений](advanced-hunting-schema-tables.md)<br> Просмотр событий проверки подлинности, запросов Active Directory и действий, связанных с приложениями, с помощью таблиц [IdentityLogonEvents,](advanced-hunting-identitylogonevents-table.md) [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)и [AppFileEvents](advanced-hunting-appfileevents-table.md) в схеме advanced hunting.
- [Запуск слежения](advanced-hunting-go-hunt.md)<br> Быстро соводите с расследования инцидента на проверку конкретного события, пользователя, устройства или других типов сущности в расширенных охотах.

## <a name="june-2020"></a>Июнь 2020 г.
- Канал Twitter <br> Получите последние сведения о безопасности, аналитику угроз, новости о продуктах и другие сведения прямо на информационной панели.
- [Таблица схемы EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) <br> Включите сведения о действиях после доставки сообщений электронной почты в расширенные поисковые запросы.
- [Проверка записей в расширенных охотах](advanced-hunting-query-results.md#drill-down-from-query-results) <br> Быстро проверьте записи в результатах запроса с помощью новой панели сведений.

## <a name="may-2020"></a>Май 2020 г.
- [Настраиваемое обнаружение](custom-detections-overview.md) <br> Используйте расширенные поисковые запросы для создания пользовательских правил обнаружения, которые автоматически отслеживают события безопасности и состояния системы и реагируют на них.

## <a name="february-2020"></a>Февраль 2020 г.
- [Инциденты](incidents-overview.md) <br> Точно знаете, с чего началась атака, и другие сведения, которые помогут вам определить степень атаки.
- [Автоматизированный анализ угроз и реагирование на них](mtp-autoir.md) <br> Благодаря AIR служба обеспечения безопасности может значительно повысить потенциал вашей организации по работе с оповещениями безопасности и инцидентами.
- [Усовершенствования для расширенных охот](advanced-hunting-overview.md) <br> Упреждающий поиск угроз в современной рабочей области с помощью языка запросов Kusto и оптимизированной для безопасности схемы.

## <a name="march-2019"></a>Март 2019 г.
- Расширенная охота на угрозы <br> На этой странице вы найдете различные возможности поиска, которые повлияют на угрозы, влияющие на электронную почту, данные, устройства и удостоверения.
- [Оценка безопасности (Майкрософт)](microsoft-secure-score.md) <br> Измерение уровня безопасности организации с более высоким числом, указывающим на дополнительные действия по улучшению. Следуя рекомендациям по оценке безопасности, можно защитить организацию от угроз. 
- [Отчеты](monitoring-and-reporting.md) <br>  Содержит ряд карточек, охватывающих различные области, которые аналитики безопасности и администраторы отслеживают в рамках своей ежедневной работы.
