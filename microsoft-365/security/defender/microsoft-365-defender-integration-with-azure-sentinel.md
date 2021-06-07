---
title: Microsoft 365 Интеграция защитника с Azure Sentinel
description: Используйте Azure Sentinel в качестве SIEM для Microsoft 365 и событий Defender.
keywords: инциденты, оповещения, исследование, анализ, ответ, корреляция, атака, компьютеры, устройства, пользователи, удостоверения, удостоверения, почтовый ящик, электронная почта, 365, Microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 7d9cff584f35c39544034501c607b7156a0f1bf2
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782925"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a>Microsoft 365 Интеграция защитника с Azure Sentinel

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Область применения:**
- Microsoft 365 Defender

Соединитель Microsoft 365 Defender для Azure Sentinel (предварительный просмотр) отправляет все инциденты Microsoft 365 Defender и оповещает о них в Azure Sentinel и сохраняет синхронизацию инцидентов. 

После добавления соединителя инциденты Microsoft 365 Defender, которые включают все связанные оповещения, объекты и релевантные сведения, полученные от Microsoft Defender для конечной точки, Microsoft Defender для удостоверений, Microsoft Defender для Office 365 и Microsoft Cloud App Security будут передаваться в Azure Sentinel в качестве данных по безопасности и управлению событиями (SIEM), предоставляя контекст для выполнения триажа и реагирования на инциденты с &mdash; &mdash; помощью Azure Sentinel. 

После работы в Azure Sentinel инциденты по-прежнему синхронизируются с Microsoft 365 Defender, что позволяет использовать преимущества центра безопасности Microsoft 365 и Azure Sentinel на портале Azure для расследования инцидентов и реагирования на них.

Вот как это работает.

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Поток и обмен данными об инцидентах между Microsoft 365 Defender и Azure Sentinel":::

## <a name="next-steps"></a>Дальнейшие действия

1. Получите более глубокое представление об [интеграции Microsoft 365 Defender с Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).
2. [Подключение от Microsoft 365 Defender до Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).

## <a name="see-also"></a>См. также

- [Обзор инцидентов в Microsoft 365 Defender](incidents-overview.md)
- [Расследование инцидентов с Azure Sentinel](/azure/sentinel/tutorial-investigate-cases)
