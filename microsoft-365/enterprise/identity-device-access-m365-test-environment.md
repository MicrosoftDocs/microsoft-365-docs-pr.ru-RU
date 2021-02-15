---
title: Удостоверения и доступ к устройствам для тестовой среды Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Создание среды Microsoft 365 для тестирования удостоверений и доступа к устройствам.
ms.openlocfilehash: ed143341079a55d6bdd1d4a68feea68acb86ef85
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233732"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Удостоверения и доступ к устройствам для тестовой среды Microsoft 365

*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для корпоративных тестовых сред.*

[Конфигурации доступа к](../security/office-365-security/microsoft-365-policies-configurations.md) удостоверениям и устройствам — это набор рекомендуемых конфигураций и политик условного доступа для защиты доступа ко всем службам, интегрированным с Azure Active Directory (Azure AD).

Чтобы создать тестовую среду с общими конфигурациями доступа к удостоверениям и устройствам:

1. Настройте тестовую среду с использованием предварительных требований к функциям удостоверений и безопасности с учетом выбора модели удостоверений и метода проверки подлинности:

  - [Только облако](cloud-only-prereqs-m365-test-environment.md)
  - [Синхронизация хэша паролей (PHS)](phs-prereqs-m365-test-environment.md)
  - [Сквозная проверка подлинности (PTA)](pta-prereqs-m365-test-environment.md)

2. Используйте [общие политики доступа](identity-access-policies.md) к удостоверениям и устройствам для настройки политик, которые используют необходимые условия, настроенные для тестовой среды, а также изучения и проверки защиты удостоверений и устройств.

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для дополнительного удостоверения](m365-enterprise-test-lab-guides.md#identity)

[План удостоверений](identity-roadmap-microsoft-365.md)

[Руководства по лаборатории тестирования для Microsoft 365 для предприятий](m365-enterprise-test-lab-guides.md)

[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)

[Документация по Microsoft 365 для предприятий](https://docs.microsoft.com/microsoft-365-enterprise/)
