---
title: Изоляция клиентов в Microsoft 365
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
description: В этой статье представлен обзор того, как корпорация Майкрософт обеспечивает изоляцию клиентов в облачных службах, таких как Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7aca35fc61d03e94225375fcf67970e13dd691c9
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332692"
---
# <a name="tenant-isolation-in-microsoft-365"></a><span data-ttu-id="85838-103">Изоляция клиентов в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="85838-103">Tenant Isolation in Microsoft 365</span></span>

<span data-ttu-id="85838-104">Одним из основных преимуществ облачных вычислений является концепция общей общей инфраструктуры для многочисленных клиентов одновременно, что приводит к экономии масштаба.</span><span class="sxs-lookup"><span data-stu-id="85838-104">One of the primary benefits of cloud computing is concept of a shared, common infrastructure across numerous customers simultaneously, leading to economies of scale.</span></span> <span data-ttu-id="85838-105">Эта концепция называется *Multi-аренды*.</span><span class="sxs-lookup"><span data-stu-id="85838-105">This concept is called *multi-tenancy*.</span></span> <span data-ttu-id="85838-106">Корпорация Майкрософт непрерывно работает над тем, чтобы обеспечить поддержку архитектуры с несколькими клиентами в облачных службах, а также для обеспечения безопасности, конфиденциальности, конфиденциальности, целостности и доступности на уровне предприятия.</span><span class="sxs-lookup"><span data-stu-id="85838-106">Microsoft works continuously to ensure that the multi-tenant architectures of our cloud services support enterprise-level security, confidentiality, privacy, integrity, and availability standards.</span></span>

<span data-ttu-id="85838-107">С учетом значительных инвестиций и опыта, собранных из [надежных вычислений](https://www.microsoft.com/trust-center) и [жизненного цикла разработки системы безопасности](https://www.microsoft.com/securityengineering/sdl/), облачные службы Майкрософт создавались с предположением о том, что все клиенты потенциально могут злонамеренно работать со всеми другими клиентами, а также были реализованы меры безопасности, чтобы предотвратить влияние действий одного клиента на безопасность или обслуживание другого клиента или доступ к содержимому другого клиента.</span><span class="sxs-lookup"><span data-stu-id="85838-107">Based upon the significant investments and experience gathered from [Trustworthy Computing](https://www.microsoft.com/trust-center) and the [Security Development Lifecycle](https://www.microsoft.com/securityengineering/sdl/), Microsoft cloud services were designed with the assumption that all tenants are potentially hostile to all other tenants, and we have implemented security measures to prevent the actions of one tenant from affecting the security or service of another tenant, or accessing the content of another tenant.</span></span>

<span data-ttu-id="85838-108">Две основные цели обслуживания клиентов в среде с несколькими клиентами:</span><span class="sxs-lookup"><span data-stu-id="85838-108">The two primary goals of maintaining tenant isolation in a multi-tenant environment are:</span></span>

1.    <span data-ttu-id="85838-109">Предотвращение утечки или несанкционированного доступа к контенту клиентов в разных клиентах; с</span><span class="sxs-lookup"><span data-stu-id="85838-109">Preventing leakage of, or unauthorized access to, customer content across tenants; and</span></span>
2.    <span data-ttu-id="85838-110">Предотвращение неблагоприятного влияния действий одного клиента на службу для другого клиента</span><span class="sxs-lookup"><span data-stu-id="85838-110">Preventing the actions of one tenant from adversely affecting the service for another tenant</span></span>

<span data-ttu-id="85838-111">В Microsoft 365 реализовано несколько форм защиты, чтобы предотвратить появление пользователями служб или приложений Microsoft 365, а также получение несанкционированного доступа к сведениям о других клиентах или самой системе Microsoft 365, в том числе:</span><span class="sxs-lookup"><span data-stu-id="85838-111">Multiple forms of protection have been implemented throughout Microsoft 365 to prevent customers from compromising Microsoft 365 services or applications or gaining unauthorized access to the information of other tenants or the Microsoft 365 system itself, including:</span></span>

- <span data-ttu-id="85838-112">Логическая изоляция контента клиента в каждом клиенте для служб Microsoft 365 обеспечивается через авторизацию Azure Active Directory и управление доступом на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="85838-112">Logical isolation of customer content within each tenant for Microsoft 365 services is achieved through Azure Active Directory authorization and role-based access control.</span></span>
- <span data-ttu-id="85838-113">SharePoint Online предоставляет механизмы изоляции данных на уровне хранилища.</span><span class="sxs-lookup"><span data-stu-id="85838-113">SharePoint Online provides data isolation mechanisms at the storage level.</span></span>
- <span data-ttu-id="85838-114">Корпорация Майкрософт использует строгую физическую защиту, фоновый отбор и многоуровневую стратегию шифрования для защиты конфиденциальности и целостности контента клиента.</span><span class="sxs-lookup"><span data-stu-id="85838-114">Microsoft uses rigorous physical security, background screening, and a multi-layered encryption strategy to protect the confidentiality and integrity of customer content.</span></span> <span data-ttu-id="85838-115">Все центры обработки данных Microsoft 365 имеют элементы управления биометрического доступа, большинство из которых требуют от карманного компьютера получить физический доступ.</span><span class="sxs-lookup"><span data-stu-id="85838-115">All Microsoft 365 datacenters have biometric access controls, with most requiring palm prints to gain physical access.</span></span> <span data-ttu-id="85838-116">Кроме того, все сотрудники Майкрософт на основе США должны успешно выполнить стандартную фоновую проверку в рамках процесса найма.</span><span class="sxs-lookup"><span data-stu-id="85838-116">In addition, all U.S.-based Microsoft employees are required to successfully complete a standard background check as part of the hiring process.</span></span> <span data-ttu-id="85838-117">Для получения дополнительных сведений об элементах управления, используемых для административного доступа в Microsoft 365, обратитесь к разделу [Управление административным доступом microsoft 365](microsoft-365-administrative-access-controls-overview.md).</span><span class="sxs-lookup"><span data-stu-id="85838-117">For more information on the controls used for administrative access in Microsoft 365, see [Microsoft 365 Administrative Access Controls](microsoft-365-administrative-access-controls-overview.md).</span></span>
- <span data-ttu-id="85838-118">Microsoft 365 использует технологии на стороне службы, которые шифруют контент клиентов на месте и в транзитном месте, в том числе BitLocker, шифрование на уровне файлов, TLS и безопасность протокола IP (IPsec).</span><span class="sxs-lookup"><span data-stu-id="85838-118">Microsoft 365 uses service-side technologies that encrypt customer content at rest and in transit, including BitLocker, per-file encryption, Transport Layer Security (TLS) and Internet Protocol Security (IPsec).</span></span> <span data-ttu-id="85838-119">Для получения подробных сведений о шифровании в Microsoft 365, ознакомьтесь со статьей [технология шифрования данных в microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview).</span><span class="sxs-lookup"><span data-stu-id="85838-119">For specific details about encryption in Microsoft 365, see [Data Encryption Technologies in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview).</span></span>

<span data-ttu-id="85838-120">В совокупности перечисленные выше меры безопасности предоставляют надежные логические элементы управления, которые обеспечивают защиту от угроз и эквиваленты смягчения, предоставляемые физической изоляцией.</span><span class="sxs-lookup"><span data-stu-id="85838-120">Together, the above-listed protections provide robust logical isolation controls that provide threat protection and mitigation equivalent to that provided by physical isolation alone.</span></span>

## <a name="related-links"></a><span data-ttu-id="85838-121">Дополнительные ссылки</span><span class="sxs-lookup"><span data-stu-id="85838-121">Related Links</span></span>

- [<span data-ttu-id="85838-122">Изоляция и управление доступом в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="85838-122">Isolation and Access Control in Azure Active Directory</span></span>](microsoft-365-isolation-in-azure-active-directory.md)
- [<span data-ttu-id="85838-123">Изоляция клиента в Office Graph и Delve</span><span class="sxs-lookup"><span data-stu-id="85838-123">Tenant Isolation in the Office Graph and Delve</span></span>](microsoft-365-isolation-in-graph-and-delve.md)
- [<span data-ttu-id="85838-124">Изоляция клиента в поиске Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="85838-124">Tenant Isolation in Microsoft 365 Search</span></span>](microsoft-365-isolation-in-microsoft-365-search.md)
- [<span data-ttu-id="85838-125">Изоляция клиента в Office 365 Видео</span><span class="sxs-lookup"><span data-stu-id="85838-125">Tenant Isolation in Office 365 Video</span></span>](microsoft-365-isolation-in-microsoft-365-video.md)
- [<span data-ttu-id="85838-126">Ограничения ресурсов</span><span class="sxs-lookup"><span data-stu-id="85838-126">Resource Limits</span></span>](microsoft-365-resource-limits.md)
- [<span data-ttu-id="85838-127">Мониторинг и тестирование границ клиента</span><span class="sxs-lookup"><span data-stu-id="85838-127">Monitoring and Testing Tenant Boundaries</span></span>](microsoft-365-monitoring-and-testing.md)
- [<span data-ttu-id="85838-128">Изоляция и управление доступом в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="85838-128">Isolation and Access Control in Microsoft 365</span></span>](microsoft-365-isolation-in-microsoft-365.md)
