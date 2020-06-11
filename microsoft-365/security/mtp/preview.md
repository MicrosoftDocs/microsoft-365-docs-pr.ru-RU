---
title: Предварительная версия функций защиты от угроз Майкрософт
description: Сведения о новых возможностях Microsoft 365 Security
keywords: Предварительная версия, новая, m365 безопасность, безопасность, 365, возможности
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
ms.openlocfilehash: 8a3e4b8979a346266336e2729d18465d391c28f9
ms.sourcegitcommit: efd4dd29af0ea2b71b674534de3b2dcbfd7482db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2020
ms.locfileid: "44689270"
---
# <a name="microsoft-threat-protection-preview-features"></a>Функции предварительной версии Microsoft Threat protection

**Область применения:**
- Защита от угроз (Майкрософт)


Служба Microsoft Threat Protection постоянно обновляется с добавлением новых функций и возможностей.

Узнайте о новых возможностях в выпуске ознакомительной версии Microsoft Threat Protection, а также в первую очередь для последующей работы, включив ознакомительную версию.

Дополнительные сведения о новых возможностях, которые обычно доступны, см. в статье [Новые возможности системы защиты от угроз (Майкрософт)](whats-new.md).

## <a name="turn-on-preview-features"></a>Включение предварительных функций
Вы получите доступ к будущим функциям, которые помогут вам повысить эффективность работы, прежде чем они будут доступны.

Включите параметр Предварительный просмотр, чтобы попытаться выполнить будущие функции.

1. В области навигации выберите **Параметры**.

2. Выберите **Защита от угроз Майкрософт**.


3. Нажмите кнопку **Предварительный просмотр компонентов**  >  , чтобы**включить предварительные функции**. 

3. Нажмите кнопку **Сохранить**.

Вы узнаете, что функции предварительного просмотра включены, когда вы видите флажок **включить предварительный просмотр компонентов** . 

## <a name="preview-features"></a>Предварительные функции
В настоящее время доступны следующие функции и расширения для предварительной версии:

- **[Таблицы удостоверений и приложений](advanced-hunting-schema-tables.md)** — получение представления о событиях проверки подлинности, запросах Active Directory и действиях, связанных с приложениями, с таблицами [идентитилогоневентс](advanced-hunting-identitylogonevents-table.md), [идентитикуеревентс](advanced-hunting-identityqueryevents-table.md)и [аппфиливентс](advanced-hunting-appfileevents-table.md) в схеме расширенного поискового запроса.

- **[Go Go](advanced-hunting-go-hunt.md)** — быстро изучите сведения об инциденте, чтобы проверить конкретное событие, пользователя, устройства или других типов сущностей с помощью [расширенных](advanced-hunting-overview.md) возможностей поиска на основе запросов.

- **[Таблица емаилпостделиверевентс](advanced-hunting-emailpostdeliveryevents-table.md)** — эта таблица используется для создания [расширенных](advanced-hunting-overview.md) запросов поиска, которые проверяют действия, выполненные на сообщениях после их доставки в почтовые ящики получателей.

- **[Функция филепрофиле ()](advanced-hunting-fileprofile-function.md)** — используется в [расширенных](advanced-hunting-overview.md) запросах на поиск для включения исчерпывающей информации о файле.
