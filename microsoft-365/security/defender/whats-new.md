---
title: Новые возможности Microsoft 365 Defender
description: Списки новых функций и функций в Microsoft 365 Defender
keywords: что нового в Microsoft 365 Defender, ga, как правило, доступны, возможности, доступные, новые
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 582116047900fc5f28d5580398cf5c065e6a3e23
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2021
ms.locfileid: "53053027"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Новые возможности Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> Хотите попробовать Microsoft 365 Defender? Вы можете [оценить его в лабораторной среде](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) или [запустить пилотный проект в производственной среде](m365d-pilot.md?ocid=cx-evalpilot).
>

Следующие функции обычно доступны (GA) в последнем выпуске Microsoft 365 Defender.

RSS-канал. Получите уведомление об обновлении этой страницы путем копирования и вклейки следующего URL-адреса в читателя каналов:
```http
/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

## <a name="april-2021"></a>Апрель 2021 г.
- Microsoft 365 Defender<br> Теперь доступен [Microsoft 365 Defender](https://security.microsoft.com) улучшенный портал. Этот новый опыт объединяет Defender for Endpoint, Defender for Office 365, Defender for Identity и другие в единый портал. Это новый дом для управления средствами управления безопасностью. [Узнайте о новых возможностях](./overview-security-center.md).

- [Microsoft 365 Defender отчет об аналитике угроз](threat-analytics.md)<br>
 Аналитика угроз помогает вам реагировать на активные атаки и свести их к минимуму. Вы также можете узнать о попытках атаки, заблокированных Microsoft 365 Defender решениями, и принять превентивные меры, которые смягчают риск дальнейшего воздействия и повышения устойчивости. В рамках единой системы безопасности аналитика угроз теперь доступна для Microsoft Defender для конечной точки и Microsoft Defender для Office владельцев лицензий E5.

## <a name="march-2021"></a>Март 2021 г.
- [Таблица CloudAppEvents](advanced-hunting-cloudappevents-table.md) <br>Сведения о событиях в различных облачных приложениях и службах, охваченных Microsoft Cloud App Security. В эту таблицу также включены сведения, ранее доступные в `AppFileEvents` .
## <a name="february-2021"></a>Февраль 2021 г.
- (Предварительный просмотр) Расширенный центр [Microsoft 365 безопасности ( https://security.microsoft.com) ](https://security.microsoft.com) теперь доступен в общедоступных предварительных просмотрах. Этот новый опыт приводит Защитник для конечной точки и защитника для Office 365 в центр. [Дополнительные сведения об изменениях](./overview-security-center.md).

## <a name="september-2020"></a>Сентябрь 2020 г.
- [Таблица IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) <br> Поиск событий с участием локального контроллера домена под управлением Active Directory (AD). Эта [продвинутая таблица](advanced-hunting-overview.md) схемы охоты охватывает ряд событий, связанных с удостоверением, и системных событий на контроллере домена.
- [Функция AssignedIPAddresses()](advanced-hunting-assignedipaddresses-function.md) <br> Используйте эту функцию в расширенных запросах на охоту, чтобы быстро получить последние IP-адреса, назначенные устройству или последним IP-адресам за определенное время.

## <a name="july-2020"></a>Июль 2020 г.
- [Функция FileProfile()](advanced-hunting-fileprofile-function.md) <br> Используйте эту функцию в расширенных запросах на охоту, чтобы обогатить результаты комплексной информацией о файлах.
- [Таблицы удостоверений и приложений](advanced-hunting-schema-tables.md)<br> Просмотр событий проверки подлинности, запросов Active Directory и действий, связанных с приложениями, с [таблицами IdentityLogonEvents,](advanced-hunting-identitylogonevents-table.md) [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)и [AppFileEvents](advanced-hunting-appfileevents-table.md) в продвинутой схеме охоты.
- [Запуск слежения](advanced-hunting-go-hunt.md)<br> Быстро от расследования инцидента до проверки определенного события, пользователя, устройства или других типов сущности в ходе предварительной охоты.

## <a name="june-2020"></a>Июнь 2020 г.
- Канал Twitter <br> Получите последние исследования безопасности, сведения об угрозах, новости о продуктах и другие сведения — прямо на панели мониторинга.
- [Таблица схем EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) <br> Включите сведения о действиях после доставки, принятых в сообщениях электронной почты, в расширенные запросы на охоту.
- [Проверка записей в продвинутой охоте](advanced-hunting-query-results.md#drill-down-from-query-results) <br> Быстро проверьте записи в результатах запроса с помощью новой панели сведений.

## <a name="may-2020"></a>Май 2020 г.
- [Настраиваемые обнаружения](custom-detections-overview.md) <br> Используйте расширенные запросы для охоты, чтобы создать настраиваемые правила обнаружения, которые автоматически отслеживают события и состояния системы безопасности и реагируют на них.

## <a name="february-2020"></a>Февраль 2020 г.
- [Инциденты](incidents-overview.md) <br> Точное сведения о том, где началась атака, и другие сведения, которые помогут вам увидеть масштабы атаки.
- [Автоматизированный анализ угроз и реагирование на них](m365d-autoir.md) <br> Благодаря AIR служба обеспечения безопасности может значительно повысить потенциал вашей организации по работе с оповещениями безопасности и инцидентами.
- [Расширенные улучшения охоты](advanced-hunting-overview.md) <br> Активная охота за угрозами в современном рабочем пространстве с помощью языка запросов Kusto и оптимизированной для безопасности схемы.

## <a name="march-2019"></a>Март 2019 г.
- Расширенная охота на угрозы <br> Страница для разных возможностей охоты, которая позволит вам активно находить угрозы, влияющие на электронную почту, данные, устройства и удостоверения.
- [Оценка безопасности (Майкрософт)](microsoft-secure-score.md) <br> Измерение позы безопасности организации с более высоким числом, указывающее на дополнительные действия по улучшению. Следуя рекомендациям по оценке безопасности, вы сможете защитить организацию от угроз. 
- [Отчеты](overview-security-center.md) <br>  Содержит множество карт, охватывающих различные области, которые аналитики и администраторы безопасности отслеживают в рамках своей ежедневной работы.
