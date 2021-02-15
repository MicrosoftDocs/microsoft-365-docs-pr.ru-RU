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
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="6d708-103">Удостоверения и доступ к устройствам для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d708-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="6d708-104">*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для корпоративных тестовых сред.*</span><span class="sxs-lookup"><span data-stu-id="6d708-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="6d708-105">[Конфигурации доступа к](../security/office-365-security/microsoft-365-policies-configurations.md) удостоверениям и устройствам — это набор рекомендуемых конфигураций и политик условного доступа для защиты доступа ко всем службам, интегрированным с Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="6d708-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="6d708-106">Чтобы создать тестовую среду с общими конфигурациями доступа к удостоверениям и устройствам:</span><span class="sxs-lookup"><span data-stu-id="6d708-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="6d708-107">Настройте тестовую среду с использованием предварительных требований к функциям удостоверений и безопасности с учетом выбора модели удостоверений и метода проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="6d708-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="6d708-108">Только облако</span><span class="sxs-lookup"><span data-stu-id="6d708-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="6d708-109">Синхронизация хэша паролей (PHS)</span><span class="sxs-lookup"><span data-stu-id="6d708-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="6d708-110">Сквозная проверка подлинности (PTA)</span><span class="sxs-lookup"><span data-stu-id="6d708-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="6d708-111">Используйте [общие политики доступа](identity-access-policies.md) к удостоверениям и устройствам для настройки политик, которые используют необходимые условия, настроенные для тестовой среды, а также изучения и проверки защиты удостоверений и устройств.</span><span class="sxs-lookup"><span data-stu-id="6d708-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d708-112">См. также</span><span class="sxs-lookup"><span data-stu-id="6d708-112">See also</span></span>

[<span data-ttu-id="6d708-113">Руководства по лаборатории тестирования для дополнительного удостоверения</span><span class="sxs-lookup"><span data-stu-id="6d708-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="6d708-114">План удостоверений</span><span class="sxs-lookup"><span data-stu-id="6d708-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="6d708-115">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="6d708-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6d708-116">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="6d708-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="6d708-117">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="6d708-117">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
