---
title: Удостоверения и доступ к устройствам для тестовой среды Microsoft 365
author: JoeDavies-MSFT
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
ms.openlocfilehash: 9195f532222511fc9dce474617ed52916d8e382a
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073599"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="13f2d-103">Удостоверения и доступ к устройствам для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="13f2d-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="13f2d-104">[Конфигурации удостоверений и доступа к устройствам](microsoft-365-policies-configurations.md) — это набор функций и политик условного доступа для защиты доступа ко всем службам, интегрированным с Azure Active Directory (Azure AD), включая Office 365 и Enterprise Mobility + Security (EMS) в Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="13f2d-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="13f2d-105">Чтобы создать тестовую среду с применением этих политик:</span><span class="sxs-lookup"><span data-stu-id="13f2d-105">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="13f2d-106">Настройте тестовую среду с использованием предварительных требований к функциям удостоверений и безопасности с учетом выбора модели удостоверений и метода проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="13f2d-106">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="13f2d-107">Только облако</span><span class="sxs-lookup"><span data-stu-id="13f2d-107">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="13f2d-108">Синхронизация хэша паролей (PHS)</span><span class="sxs-lookup"><span data-stu-id="13f2d-108">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="13f2d-109">Сквозная проверка подлинности (PTA)</span><span class="sxs-lookup"><span data-stu-id="13f2d-109">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="13f2d-110">Используйте статью [Основные политики доступа для удостоверений и устройств](identity-access-policies.md), чтобы настроить политики, созданные на основе предварительных требований, и проверить защиту для удостоверений и устройств.</span><span class="sxs-lookup"><span data-stu-id="13f2d-110">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="13f2d-111">См. также</span><span class="sxs-lookup"><span data-stu-id="13f2d-111">See also</span></span>

[<span data-ttu-id="13f2d-112">Руководства по лаборатории тестирования для дополнительного удостоверения</span><span class="sxs-lookup"><span data-stu-id="13f2d-112">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="13f2d-113">Шаг 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="13f2d-113">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="13f2d-114">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="13f2d-114">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="13f2d-115">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="13f2d-115">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="13f2d-116">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="13f2d-116">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
