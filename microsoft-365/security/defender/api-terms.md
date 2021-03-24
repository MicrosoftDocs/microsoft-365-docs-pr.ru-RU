---
title: Лицензия и условия использования API Защитника Microsoft 365
description: Описание лицензии и условий использования API в Microsoft 365 Defender
keywords: api, apis, license, terms, apis, legal, notices, code of conduct
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 9b70311726b6c1c5bedf34a18ee1763255c93ba3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070070"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Лицензия и условия использования API Защитника Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Некоторые сведения относятся к предварительным выпускам продуктов, которые могут быть существенно изменены до коммерческого выпуска. Корпорация Майкрософт не дает никаких гарантий, явных или подразумеваемых, относительно предоставленных здесь сведений.

## <a name="official-terms"></a>Официальные термины

API Защитника Microsoft 365 регулируются лицензией [API Microsoft и условиями использования.](/legal/microsoft-apis/terms-of-use)

## <a name="legal-notices"></a>Юридические уведомления

Корпорация Майкрософт и все участники выдают вам лицензию на документацию Майкрософт и другой контент в этом репозитории [в](https://github.com/MicrosoftDocs/microsoft-365-docs)соответствии с международной публичной лицензией Creative Commons Attribution 4.0. Дополнительные сведения см. в [файле LICENSE.](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE)

Microsoft, Windows, Microsoft Azure и/или другие продукты и службы Майкрософт, на которые ссылается документация, могут быть товарными знаками или зарегистрированными товарными знаками Корпорации Майкрософт в США и/или других странах.

Лицензии для этого проекта не дарют вам права на использование имен, логотипов или товарных знаков Майкрософт. Общие рекомендации по товарным знакам Корпорации Майкрософт можно найти на [сайте Microsoft Trademarks.](https://go.microsoft.com/fwlink/?LinkID=254653)

Сведения о конфиденциальности можно найти на [сайте Privacy в Microsoft.](https://privacy.microsoft.com)

Корпорация Майкрософт и все участники резервировать все другие права, будь то в соответствии со своими соответствующими авторскими правами, патентами или товарными знаками, будь то под влиянием, эстоппелем или иным образом.

## <a name="other-restrictions"></a>Другие ограничения

Расширенный API охоты [](/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations) имеет некоторые ограничения на количество возвращенных результатов и данных, которые можно задать запрос.

1. Вы можете запрашивать данные только за последние 30 дней.
1. Результаты будут включать не более 100 000 строк.

### <a name="quotas-and-resource-allocation"></a>Квоты и распределение ресурсов

API Защитника Microsoft 365 имеют пороговые значения регулирования.

- **API инцидентов:** до 50 вызовов в минуту или 1500 вызовов в час.
- **Расширенный API** охоты: до 15 вызовов в минуту, 10 минут времени работы в час и 4 часа времени работы в день.

Код состояния отклика HTTP, указывающий на `429` регулирование.

Если ваш запрос был отлажин, в органе ответа будет указано время, когда можно снова начать делать запросы.

## <a name="related-articles"></a>Связанные статьи

- [Обзор API защитника Microsoft 365](api-overview.md)
- [Поддерживаемые API Microsoft 365 Defender](api-supported.md)
- [Доступ к API защитника Microsoft 365](api-access.md)