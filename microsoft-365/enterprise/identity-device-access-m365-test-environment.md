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
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Создание среды Microsoft 365 для тестирования удостоверений и доступа к устройствам.
ms.openlocfilehash: e43483afc9e17de9582b2998867b53cfff7d8492
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601006"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>Удостоверения и доступ к устройствам для тестовой среды Microsoft 365

*Это руководство по лаборатории тестирования можно использовать только для тестовых сред Microsoft 365 корпоративный.*

[Конфигурации удостоверений и доступа к устройствам](microsoft-365-policies-configurations.md) — это набор функций и политик условного доступа для защиты доступа ко всем службам, интегрированным с Azure Active Directory (Azure AD), включая Office 365 и Microsoft Intune в Microsoft 365 корпоративный.

Чтобы создать тестовую среду с применением этих политик:

1. Настройте тестовую среду с использованием предварительных требований к функциям удостоверений и безопасности с учетом выбора модели удостоверений и метода проверки подлинности:

  - [Только облако](cloud-only-prereqs-m365-test-environment.md)
  - [Синхронизация хэша паролей (PHS)](phs-prereqs-m365-test-environment.md)
  - [Сквозная проверка подлинности (PTA)](pta-prereqs-m365-test-environment.md)

2. Используйте статью [Основные политики доступа для удостоверений и устройств](identity-access-policies.md), чтобы настроить политики, созданные на основе предварительных требований, и проверить защиту для удостоверений и устройств.

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для дополнительного удостоверения](m365-enterprise-test-lab-guides.md#identity)

[Шаг 2. Идентификация](identity-infrastructure.md)

[Руководства по лаборатории тестирования для Microsoft 365 корпоративный](m365-enterprise-test-lab-guides.md)

[Развертывание Microsoft 365 корпоративный](deploy-microsoft-365-enterprise.md)

[Документация по Microsoft 365 корпоративный](https://docs.microsoft.com/microsoft-365-enterprise/)
