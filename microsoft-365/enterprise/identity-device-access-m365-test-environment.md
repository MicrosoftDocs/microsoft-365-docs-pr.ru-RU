---
title: Удостоверения и доступ к устройствам для тестовой среды Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Создание среды Microsoft 365 для тестирования удостоверений и доступа к устройствам.
ms.openlocfilehash: b8e91a58bb6e1c00013b963c77151080a419b836
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398811"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Удостоверения и доступ к устройствам для тестовой среды Microsoft 365

*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для тестовых сред предприятия.*

[Конфигурации доступа для удостоверений и устройств](../security/office-365-security/microsoft-365-policies-configurations.md) — это набор функций и политик условного доступа для защиты доступа ко всем службам, интегрированным с Azure Active Directory (Azure AD).

Чтобы создать тестовую среду с общими конфигурациями идентификации и доступа к устройствам, выполните следующие действия:

1. Настройте тестовую среду с использованием предварительных требований к функциям удостоверений и безопасности с учетом выбора модели удостоверений и метода проверки подлинности:

  - [Только облако](cloud-only-prereqs-m365-test-environment.md)
  - [Синхронизация хэша паролей (PHS)](phs-prereqs-m365-test-environment.md)
  - [Сквозная проверка подлинности (PTA)](pta-prereqs-m365-test-environment.md)

2. Используйте [Общие политики удостоверений и доступа к устройствам](identity-access-policies.md) , чтобы настроить политики, которые создают необходимые компоненты для тестовой среды, и проанализируйте и проверьте защиту для удостоверений и устройств.

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для дополнительного удостоверения](m365-enterprise-test-lab-guides.md#identity)

[Схема удостоверений](identity-roadmap-microsoft-365.md)

[Руководства по лаборатории тестирования для Microsoft 365 для предприятий](m365-enterprise-test-lab-guides.md)

[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)

[Microsoft 365 для корпоративных документов](https://docs.microsoft.com/microsoft-365-enterprise/)
