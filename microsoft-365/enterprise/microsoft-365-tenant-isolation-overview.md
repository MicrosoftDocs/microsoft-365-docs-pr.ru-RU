---
title: Изоляция клиента в Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: В этой статье содержится сводка о том, как Корпорация Майкрософт обеспечивает изоляцию клиента в облачных службах, таких как Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b52d936bb00ac0adef0baf428cbc5f9a8f8aba49
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194653"
---
# <a name="tenant-isolation-in-microsoft-365"></a><span data-ttu-id="45824-103">Изоляция клиента в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="45824-103">Tenant Isolation in Microsoft 365</span></span>

<span data-ttu-id="45824-104">Одним из основных преимуществ облачных вычислений является концепция общей общей инфраструктуры для многочисленных клиентов одновременно, что приводит к экономии масштаба.</span><span class="sxs-lookup"><span data-stu-id="45824-104">One of the primary benefits of cloud computing is concept of a shared, common infrastructure across numerous customers simultaneously, leading to economies of scale.</span></span> <span data-ttu-id="45824-105">Эта концепция называется *multi-tenancy*.</span><span class="sxs-lookup"><span data-stu-id="45824-105">This concept is called *multi-tenancy*.</span></span> <span data-ttu-id="45824-106">Корпорация Майкрософт непрерывно работает над тем, чтобы многозанимавные архитектуры наших облачных служб обеспечивали поддержку стандартов безопасности, конфиденциальности, конфиденциальности, целостности и доступности.</span><span class="sxs-lookup"><span data-stu-id="45824-106">Microsoft works continuously to ensure that the multi-tenant architectures of our cloud services support enterprise-level security, confidentiality, privacy, integrity, and availability standards.</span></span>

<span data-ttu-id="45824-107">На основе значительных инвестиций и [](https://www.microsoft.com/trust-center) опыта, собранных из надежных вычислений и жизненного цикла разработки [безопасности,](https://www.microsoft.com/securityengineering/sdl/)облачные службы Майкрософт были разработаны с учетом того, что все клиенты потенциально враждебно настроены ко всем другим клиентам, и мы реализовали меры безопасности, чтобы предотвратить действия одного клиента, чтобы повлиять на безопасность или службу другого клиента или получить доступ к содержимому другого клиента.</span><span class="sxs-lookup"><span data-stu-id="45824-107">Based upon the significant investments and experience gathered from [Trustworthy Computing](https://www.microsoft.com/trust-center) and the [Security Development Lifecycle](https://www.microsoft.com/securityengineering/sdl/), Microsoft cloud services were designed with the assumption that all tenants are potentially hostile to all other tenants, and we have implemented security measures to prevent the actions of one tenant from affecting the security or service of another tenant, or accessing the content of another tenant.</span></span>

<span data-ttu-id="45824-108">Две основные цели сохранения изоляции клиента в среде с несколькими клиентами:</span><span class="sxs-lookup"><span data-stu-id="45824-108">The two primary goals of maintaining tenant isolation in a multi-tenant environment are:</span></span>

1.    <span data-ttu-id="45824-109">Предотвращение утечек или несанкционированного доступа к контенту клиентов между клиентами; и</span><span class="sxs-lookup"><span data-stu-id="45824-109">Preventing leakage of, or unauthorized access to, customer content across tenants; and</span></span>
2.    <span data-ttu-id="45824-110">Предотвращение негативного влияния действий одного клиента на службу для другого клиента</span><span class="sxs-lookup"><span data-stu-id="45824-110">Preventing the actions of one tenant from adversely affecting the service for another tenant</span></span>

<span data-ttu-id="45824-111">В течение всего Microsoft 365 внедрены различные формы защиты, чтобы не допустить компрометации Microsoft 365 служб или приложений или получения несанкционированного доступа к сведениям других клиентов или самой Microsoft 365 системы, включая:</span><span class="sxs-lookup"><span data-stu-id="45824-111">Multiple forms of protection have been implemented throughout Microsoft 365 to prevent customers from compromising Microsoft 365 services or applications or gaining unauthorized access to the information of other tenants or the Microsoft 365 system itself, including:</span></span>

- <span data-ttu-id="45824-112">Логическая изоляция контента клиента в каждом клиенте для Microsoft 365 служб достигается Azure Active Directory авторизации и управления доступом на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="45824-112">Logical isolation of customer content within each tenant for Microsoft 365 services is achieved through Azure Active Directory authorization and role-based access control.</span></span>
- <span data-ttu-id="45824-113">SharePoint Online предоставляет механизмы изоляции данных на уровне хранилища.</span><span class="sxs-lookup"><span data-stu-id="45824-113">SharePoint Online provides data isolation mechanisms at the storage level.</span></span>
- <span data-ttu-id="45824-114">Корпорация Майкрософт использует строгую физическую безопасность, фоновое тестирование и многоуровневую стратегию шифрования для защиты конфиденциальности и целостности контента клиента.</span><span class="sxs-lookup"><span data-stu-id="45824-114">Microsoft uses rigorous physical security, background screening, and a multi-layered encryption strategy to protect the confidentiality and integrity of customer content.</span></span> <span data-ttu-id="45824-115">Все Microsoft 365 центрах обработки данных имеют элементы управления биометрическим доступом, при этом для получения физического доступа требуется большинство отпечатков ладоней.</span><span class="sxs-lookup"><span data-stu-id="45824-115">All Microsoft 365 datacenters have biometric access controls, with most requiring palm prints to gain physical access.</span></span> <span data-ttu-id="45824-116">Кроме того, все сотрудники Корпорации Майкрософт из США должны успешно пройти стандартную проверку фона в рамках процесса найма.</span><span class="sxs-lookup"><span data-stu-id="45824-116">In addition, all U.S.-based Microsoft employees are required to successfully complete a standard background check as part of the hiring process.</span></span> <span data-ttu-id="45824-117">Дополнительные сведения о средствах управления, используемых для административного доступа в Microsoft 365, см. в Microsoft 365 [Управления административным доступом.](/compliance/assurance/assurance-administrative-access-controls-overview)</span><span class="sxs-lookup"><span data-stu-id="45824-117">For more information on the controls used for administrative access in Microsoft 365, see [Microsoft 365 Administrative Access Controls](/compliance/assurance/assurance-administrative-access-controls-overview).</span></span>
- <span data-ttu-id="45824-118">Microsoft 365 использует технологии, которые шифруют содержимое клиента в покое и в пути, в том числе BitLocker, шифрование каждого файла, безопасность транспортного слоя (TLS) и безопасность протокола Интернета (IPsec).</span><span class="sxs-lookup"><span data-stu-id="45824-118">Microsoft 365 uses service-side technologies that encrypt customer content at rest and in transit, including BitLocker, per-file encryption, Transport Layer Security (TLS) and Internet Protocol Security (IPsec).</span></span> <span data-ttu-id="45824-119">Подробные сведения о шифровании в Microsoft 365 [см.](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md)в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="45824-119">For specific details about encryption in Microsoft 365, see [Data Encryption Technologies in Microsoft 365](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md).</span></span>

<span data-ttu-id="45824-120">В совокупности указанные выше средства защиты обеспечивают надежные элементы управления логической изоляцией, которые обеспечивают защиту от угроз и смягчение последствий, эквивалентные средствам физической изоляции.</span><span class="sxs-lookup"><span data-stu-id="45824-120">Together, the above-listed protections provide robust logical isolation controls that provide threat protection and mitigation equivalent to that provided by physical isolation alone.</span></span>

## <a name="related-links"></a><span data-ttu-id="45824-121">Дополнительные ссылки</span><span class="sxs-lookup"><span data-stu-id="45824-121">Related Links</span></span>

- [<span data-ttu-id="45824-122">Изоляция и управление доступом в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="45824-122">Isolation and Access Control in Azure Active Directory</span></span>](microsoft-365-isolation-in-azure-active-directory.md)
- [<span data-ttu-id="45824-123">Изоляция клиента в Office Graph и Delve</span><span class="sxs-lookup"><span data-stu-id="45824-123">Tenant Isolation in the Office Graph and Delve</span></span>](microsoft-365-isolation-in-graph-and-delve.md)
- [<span data-ttu-id="45824-124">Изоляция клиента в поиске Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="45824-124">Tenant Isolation in Microsoft 365 Search</span></span>](microsoft-365-isolation-in-microsoft-365-search.md)
- [<span data-ttu-id="45824-125">Ограничения ресурсов</span><span class="sxs-lookup"><span data-stu-id="45824-125">Resource Limits</span></span>](/compliance/assurance/assurance-resource-limits)
- [<span data-ttu-id="45824-126">Мониторинг и тестирование границ клиента</span><span class="sxs-lookup"><span data-stu-id="45824-126">Monitoring and Testing Tenant Boundaries</span></span>](/compliance/assurance/assurance-monitoring-and-testing)
- [<span data-ttu-id="45824-127">Изоляция и управление доступом в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="45824-127">Isolation and Access Control in Microsoft 365</span></span>](microsoft-365-isolation-in-microsoft-365.md)