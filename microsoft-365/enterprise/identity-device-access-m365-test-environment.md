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
ms.openlocfilehash: 84af7747fc1d0e80e933397f4f0f96018ed246c3
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327811"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="e9949-103">Удостоверения и доступ к устройствам для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e9949-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="e9949-104">*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для тестовых сред предприятия.*</span><span class="sxs-lookup"><span data-stu-id="e9949-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="e9949-105">[Конфигурации доступа для удостоверений и устройств](microsoft-365-policies-configurations.md) — это набор функций и политик условного доступа для защиты доступа ко всем службам, интегрированным с Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="e9949-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="e9949-106">Чтобы создать тестовую среду с общими конфигурациями идентификации и доступа к устройствам, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e9949-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="e9949-107">Настройте тестовую среду с использованием предварительных требований к функциям удостоверений и безопасности с учетом выбора модели удостоверений и метода проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="e9949-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="e9949-108">Только облако</span><span class="sxs-lookup"><span data-stu-id="e9949-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="e9949-109">Синхронизация хэша паролей (PHS)</span><span class="sxs-lookup"><span data-stu-id="e9949-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="e9949-110">Сквозная проверка подлинности (PTA)</span><span class="sxs-lookup"><span data-stu-id="e9949-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="e9949-111">Используйте [Общие политики удостоверений и доступа к устройствам](identity-access-policies.md) , чтобы настроить политики, которые создают необходимые компоненты для тестовой среды, и проанализируйте и проверьте защиту для удостоверений и устройств.</span><span class="sxs-lookup"><span data-stu-id="e9949-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9949-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e9949-112">See also</span></span>

[<span data-ttu-id="e9949-113">Руководства по лаборатории тестирования для дополнительного удостоверения</span><span class="sxs-lookup"><span data-stu-id="e9949-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="e9949-114">Схема удостоверений</span><span class="sxs-lookup"><span data-stu-id="e9949-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="e9949-115">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="e9949-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e9949-116">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="e9949-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e9949-117">Microsoft 365 для корпоративных документов</span><span class="sxs-lookup"><span data-stu-id="e9949-117">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
