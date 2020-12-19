---
title: Лицензия и условия использования API Microsoft 365 Defender
description: Описание лицензии и условий использования API в Microsoft 365 Defender
keywords: API, API, лицензия, условия, API, юридические, уведомления, кодекс поведения
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: d9b3c48e4b9e89ef7648086b05c9fdd9f078f51e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719302"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Лицензия и условия использования API Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительно выпущенным продуктам, которые могут быть существенно изменены до его коммерческого выпуска. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="official-terms"></a>Официальные термины

API Microsoft 365 Defender управляются лицензией на API Microsoft и [условиями использования.](https://docs.microsoft.com/legal/microsoft-apis/terms-of-use)

## <a name="legal-notices"></a>Юридические уведомления

Корпорация Майкрософт и все участники выдают вам лицензию на документацию Майкрософт и другой контент в этом репозитории в рамках международной открытой лицензии Creative Commons Attribution 4.0. [](https://github.com/MicrosoftDocs/microsoft-365-docs) Дополнительные сведения см. в [файле LICENSE.](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE)

Microsoft, Windows, Microsoft Azure и/или другие продукты и службы Майкрософт, на которые ссылается документация, могут быть товарными знаками или зарегистрированными товарными знаками Корпорации Майкрософт в США и/или других странах.

Лицензии для этого проекта не предоставляет вам права на использование имен, логотипов или товарных знаков Майкрософт. Общие рекомендации по товарным знакам корпорации Майкрософт можно найти на сайте [Microsoft Trademarks.](https://go.microsoft.com/fwlink/?LinkID=254653)

Сведения о конфиденциальности можно найти на [веб-сайте "Конфиденциальность" в Корпорации Майкрософт.](https://privacy.microsoft.com)

Корпорация Майкрософт и любые участники резервировать все остальные права, в соответствии с соответствующими авторскими правами, патентами или товарными знаками, как по последствию, так и по-другому.

## <a name="other-restrictions"></a>Другие ограничения

API расширенных поисков [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations) имеет некоторые ограничения на количество возвращаемого результата и данных, которые можно запрошагов.

1. Вы можете запрашивать данные только за последние 30 дней.
1. Результаты включают не более 100 000 строк.

### <a name="quotas-and-resource-allocation"></a>Квоты и выделение ресурсов

API Microsoft 365 Defender имеют пороговые значения регулирования.

- **API инцидентов:** до 50 вызовов в минуту или 1500 вызовов в час.
- **API advanced Hunting**: до 15 вызовов в минуту, 10 минут времени работы в час и 4 часа работы в день.

Код состояния http-ответа, указывающий на то, что регулирование имеет состояние `429` .

Если ваш запрос был регулирование, в теле ответа будет указано время, когда вы можете снова начать делать запросы.

## <a name="related-articles"></a>Статьи по теме

- [Обзор API Microsoft 365 Defender](api-overview.md)
- [Поддерживаемые API Microsoft 365 Defender](api-supported.md)
- [Доступ к API Microsoft 365 Defender](api-access.md)
