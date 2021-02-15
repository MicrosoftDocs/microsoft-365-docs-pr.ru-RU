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
description: В этой статье содержится сводка по принудительной изоляции клиентов в облачных службах, таких как Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c9af522c71f3b089c8f2f198f861bcac8a0011a2
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384937"
---
# <a name="tenant-isolation-in-microsoft-365"></a><span data-ttu-id="20f0d-103">Изоляция клиента в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="20f0d-103">Tenant Isolation in Microsoft 365</span></span>

<span data-ttu-id="20f0d-104">Одно из основных преимуществ облачных вычислений — концепция общей общей инфраструктуры для множества клиентов одновременно, что приводит к масштабным преимуществам.</span><span class="sxs-lookup"><span data-stu-id="20f0d-104">One of the primary benefits of cloud computing is concept of a shared, common infrastructure across numerous customers simultaneously, leading to economies of scale.</span></span> <span data-ttu-id="20f0d-105">Это понятие называется *мультитенантность.*</span><span class="sxs-lookup"><span data-stu-id="20f0d-105">This concept is called *multi-tenancy*.</span></span> <span data-ttu-id="20f0d-106">Корпорация Майкрософт постоянно работает над тем, чтобы архитектуры наших облачных служб с несколькими клиентами обеспечивали поддержку корпоративных стандартов безопасности, конфиденциальности, конфиденциальности, целостности и доступности.</span><span class="sxs-lookup"><span data-stu-id="20f0d-106">Microsoft works continuously to ensure that the multi-tenant architectures of our cloud services support enterprise-level security, confidentiality, privacy, integrity, and availability standards.</span></span>

<span data-ttu-id="20f0d-107">На основе значительных инвестиций и [](https://www.microsoft.com/trust-center) опыта, собранных в сфере заслуживающих доверия вычислений и жизненного цикла разработки системы [безопасности,](https://www.microsoft.com/securityengineering/sdl/)облачные службы Майкрософт были разработаны с учетом предположения, что все клиенты потенциально не согласованы со всеми другими клиентами, и мы реализовали меры безопасности, чтобы предотвратить влияние действий одного клиента на безопасность или службу другого клиента или доступ к содержимому другого клиента.</span><span class="sxs-lookup"><span data-stu-id="20f0d-107">Based upon the significant investments and experience gathered from [Trustworthy Computing](https://www.microsoft.com/trust-center) and the [Security Development Lifecycle](https://www.microsoft.com/securityengineering/sdl/), Microsoft cloud services were designed with the assumption that all tenants are potentially hostile to all other tenants, and we have implemented security measures to prevent the actions of one tenant from affecting the security or service of another tenant, or accessing the content of another tenant.</span></span>

<span data-ttu-id="20f0d-108">Две основные задачи по поддержанию изоляции клиентов в среде с несколькими арендаторами:</span><span class="sxs-lookup"><span data-stu-id="20f0d-108">The two primary goals of maintaining tenant isolation in a multi-tenant environment are:</span></span>

1.    <span data-ttu-id="20f0d-109">предотвращение утечки или несанкционированного доступа к контенту клиентов в клиентах; и</span><span class="sxs-lookup"><span data-stu-id="20f0d-109">Preventing leakage of, or unauthorized access to, customer content across tenants; and</span></span>
2.    <span data-ttu-id="20f0d-110">Предотвращение негативного влияния действий одного клиента на службу для другого клиента</span><span class="sxs-lookup"><span data-stu-id="20f0d-110">Preventing the actions of one tenant from adversely affecting the service for another tenant</span></span>

<span data-ttu-id="20f0d-111">В Microsoft 365 реализовано несколько форм защиты, предотвращающих компрометации служб или приложений Microsoft 365 или получения несанкционированного доступа к информации других клиентов или самой системы Microsoft 365, в том числе:</span><span class="sxs-lookup"><span data-stu-id="20f0d-111">Multiple forms of protection have been implemented throughout Microsoft 365 to prevent customers from compromising Microsoft 365 services or applications or gaining unauthorized access to the information of other tenants or the Microsoft 365 system itself, including:</span></span>

- <span data-ttu-id="20f0d-112">Логическая изоляция контента клиента в каждом клиенте для служб Microsoft 365 достигается посредством авторизации Azure Active Directory и управления доступом на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="20f0d-112">Logical isolation of customer content within each tenant for Microsoft 365 services is achieved through Azure Active Directory authorization and role-based access control.</span></span>
- <span data-ttu-id="20f0d-113">SharePoint Online предоставляет механизмы изоляции данных на уровне хранилища.</span><span class="sxs-lookup"><span data-stu-id="20f0d-113">SharePoint Online provides data isolation mechanisms at the storage level.</span></span>
- <span data-ttu-id="20f0d-114">Корпорация Майкрософт использует строгую физическую безопасность, проверку биографии и многоуровневую стратегию шифрования для защиты конфиденциальности и целостности контента клиента.</span><span class="sxs-lookup"><span data-stu-id="20f0d-114">Microsoft uses rigorous physical security, background screening, and a multi-layered encryption strategy to protect the confidentiality and integrity of customer content.</span></span> <span data-ttu-id="20f0d-115">Все центр обработки данных Microsoft 365 имеют биометрические элементы управления доступом, большинство из которых требуют напечатать ладони для получения физического доступа.</span><span class="sxs-lookup"><span data-stu-id="20f0d-115">All Microsoft 365 datacenters have biometric access controls, with most requiring palm prints to gain physical access.</span></span> <span data-ttu-id="20f0d-116">Кроме того, все сотрудники майкрософт из США должны успешно пройти стандартную проверку в фоновом режиме в процессе найма.</span><span class="sxs-lookup"><span data-stu-id="20f0d-116">In addition, all U.S.-based Microsoft employees are required to successfully complete a standard background check as part of the hiring process.</span></span> <span data-ttu-id="20f0d-117">Дополнительные сведения об средствах контроля, используемых для административного доступа в Microsoft 365, см. в подуправлении административного [доступа Microsoft 365.](microsoft-365-administrative-access-controls-overview.md)</span><span class="sxs-lookup"><span data-stu-id="20f0d-117">For more information on the controls used for administrative access in Microsoft 365, see [Microsoft 365 Administrative Access Controls](microsoft-365-administrative-access-controls-overview.md).</span></span>
- <span data-ttu-id="20f0d-118">Microsoft 365 использует технологии на стороне службы, которые шифруют содержимое клиентов неавтомантно и в пути, включая BitLocker, шифрование для каждого файла, TLS и IPsec.</span><span class="sxs-lookup"><span data-stu-id="20f0d-118">Microsoft 365 uses service-side technologies that encrypt customer content at rest and in transit, including BitLocker, per-file encryption, Transport Layer Security (TLS) and Internet Protocol Security (IPsec).</span></span> <span data-ttu-id="20f0d-119">Подробные сведения о шифровании в Microsoft 365 см. в сведениях о технологиях шифрования [данных в Microsoft 365.](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md)</span><span class="sxs-lookup"><span data-stu-id="20f0d-119">For specific details about encryption in Microsoft 365, see [Data Encryption Technologies in Microsoft 365](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md).</span></span>

<span data-ttu-id="20f0d-120">В совокупности перечисленные выше средства защиты обеспечивают надежные элементы управления логической изоляцией, которые обеспечивают защиту от угроз и меры, эквивалентные средствам физической изоляции.</span><span class="sxs-lookup"><span data-stu-id="20f0d-120">Together, the above-listed protections provide robust logical isolation controls that provide threat protection and mitigation equivalent to that provided by physical isolation alone.</span></span>

## <a name="related-links"></a><span data-ttu-id="20f0d-121">Дополнительные ссылки</span><span class="sxs-lookup"><span data-stu-id="20f0d-121">Related Links</span></span>

- [<span data-ttu-id="20f0d-122">Изоляция и управление доступом в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="20f0d-122">Isolation and Access Control in Azure Active Directory</span></span>](microsoft-365-isolation-in-azure-active-directory.md)
- [<span data-ttu-id="20f0d-123">Изоляция клиента в Office Graph и Delve</span><span class="sxs-lookup"><span data-stu-id="20f0d-123">Tenant Isolation in the Office Graph and Delve</span></span>](microsoft-365-isolation-in-graph-and-delve.md)
- [<span data-ttu-id="20f0d-124">Изоляция клиента в поиске Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="20f0d-124">Tenant Isolation in Microsoft 365 Search</span></span>](microsoft-365-isolation-in-microsoft-365-search.md)
- [<span data-ttu-id="20f0d-125">Изоляция клиента в Office 365 Видео</span><span class="sxs-lookup"><span data-stu-id="20f0d-125">Tenant Isolation in Office 365 Video</span></span>](microsoft-365-isolation-in-microsoft-365-video.md)
- [<span data-ttu-id="20f0d-126">Ограничения ресурсов</span><span class="sxs-lookup"><span data-stu-id="20f0d-126">Resource Limits</span></span>](microsoft-365-resource-limits.md)
- [<span data-ttu-id="20f0d-127">Мониторинг и тестирование границ клиента</span><span class="sxs-lookup"><span data-stu-id="20f0d-127">Monitoring and Testing Tenant Boundaries</span></span>](microsoft-365-monitoring-and-testing.md)
- [<span data-ttu-id="20f0d-128">Изоляция и управление доступом в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="20f0d-128">Isolation and Access Control in Microsoft 365</span></span>](microsoft-365-isolation-in-microsoft-365.md)
