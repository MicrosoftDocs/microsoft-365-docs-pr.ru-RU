---
title: Дополнительные сведения для поставщиков облачных решений
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: Сводка. Дополнительные сведения для поставщиков облачных решений, которые имеют отношение к миграции из Microsoft Cloud Deutschland.
ms.openlocfilehash: 843552c55acba57c5c2da4a1a885d65cb4e59d84
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984920"
---
# <a name="additional-information-for-cloud-solution-providers"></a>Дополнительные сведения для поставщиков облачных решений

Поставщики облачных решений (CSPs), поддерживающие клиентов, должны предпринять дополнительные действия во время миграции из Microsoft Cloud Deutschland в новый немецкий центр обработки данных.

## <a name="partner-tenant-migration"></a>Миграция клиента-партнера

Клиенты партнеров Microsoft Cloud Deutschland не будут перенесены. Вместо этого для каждого Office 365 Microsoft Partner в новом немецком регионе центра обработки данных будет создан новый клиент Office 365 служб.

Клиенты CSP будут перенесены в новый немецкий центр обработки данных и связаны с новым клиентом Office 365 услуг того же партнера. После перехода клиента партнер может управлять клиентом с помощью нового клиента Office 365 служб в немецком регионе центра обработки данных.

## <a name="missing-subscriptions-in-azure"></a>Отсутствующие подписки в Azure

После завершения перехода на подписку и лицензирование [(этап 3)](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) поставщики облачных решений больше не будут иметь доступ к подписке Azure.

Чтобы восстановить доступ, выполните следующие действия, чтобы повысить доступ к управлению всеми подписками [и группами управления Azure.](/azure/role-based-access-control/elevate-access-global-admin)
