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
ms.openlocfilehash: 5a9e9ef9ea6b8f6dc80aa7fea225f3573b8fcadc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197879"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="c4fbb-103">Удостоверения и доступ к устройствам для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c4fbb-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="c4fbb-104">*Это руководство по тестовой лаборатории можно использовать только для Microsoft 365 для корпоративных тестовых сред.*</span><span class="sxs-lookup"><span data-stu-id="c4fbb-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="c4fbb-105">[Конфигурации удостоверений](../security/office-365-security/microsoft-365-policies-configurations.md) и доступа к устройствам — это набор рекомендуемых конфигураций и политик условного доступа для защиты доступа ко всем службам, интегрированным с Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c4fbb-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="c4fbb-106">Создание тестовой среды, в которой имеются общие конфигурации доступа к удостоверениям и устройствам:</span><span class="sxs-lookup"><span data-stu-id="c4fbb-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="c4fbb-107">Настройте тестовую среду с использованием предварительных требований к функциям удостоверений и безопасности с учетом выбора модели удостоверений и метода проверки подлинности:</span><span class="sxs-lookup"><span data-stu-id="c4fbb-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="c4fbb-108">Только облако</span><span class="sxs-lookup"><span data-stu-id="c4fbb-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="c4fbb-109">Синхронизация хэша паролей (PHS)</span><span class="sxs-lookup"><span data-stu-id="c4fbb-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="c4fbb-110">Сквозная проверка подлинности (PTA)</span><span class="sxs-lookup"><span data-stu-id="c4fbb-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="c4fbb-111">Используйте [общие политики](../security/office-365-security/identity-access-policies.md) доступа к удостоверениям и устройствам для настройки политик, которые строятся на предпосылках, настроенных для тестовой среды, а также для изучения и проверки защиты удостоверений и устройств.</span><span class="sxs-lookup"><span data-stu-id="c4fbb-111">Use [Common identity and device access policies](../security/office-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4fbb-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c4fbb-112">See also</span></span>

[<span data-ttu-id="c4fbb-113">Руководства по лаборатории тестирования для дополнительного удостоверения</span><span class="sxs-lookup"><span data-stu-id="c4fbb-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="c4fbb-114">Дорожная карта удостоверений</span><span class="sxs-lookup"><span data-stu-id="c4fbb-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="c4fbb-115">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="c4fbb-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="c4fbb-116">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="c4fbb-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="c4fbb-117">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="c4fbb-117">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
