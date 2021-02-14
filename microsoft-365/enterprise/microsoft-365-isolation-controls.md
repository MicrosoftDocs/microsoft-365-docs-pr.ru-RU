---
title: Элементы управления изоляцией Microsoft 365
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
description: Узнайте, как средства управления изоляцией работают в Microsoft 365, позволяя службам работать или оставаться автономными по мере необходимости.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bb0989f19002267ab92bf184a12a4076f753580e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332380"
---
# <a name="microsoft-365-isolation-controls"></a><span data-ttu-id="e6bcd-103">Элементы управления изоляцией Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e6bcd-103">Microsoft 365 isolation controls</span></span> 

<span data-ttu-id="e6bcd-104">Корпорация Майкрософт постоянно работает над тем, чтобы многоэтапная архитектура Microsoft 365 обеспечивала поддержку корпоративных стандартов безопасности, конфиденциальности, конфиденциальности, целостности, локальных, международных и [доступности.](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)</span><span class="sxs-lookup"><span data-stu-id="e6bcd-104">Microsoft continuously works to ensure that the multi-tenant architecture of Microsoft 365 supports enterprise-level security, confidentiality, privacy, integrity, local, international, and availability [standards](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons).</span></span> <span data-ttu-id="e6bcd-105">Масштаб и область служб, предоставляемых корпорацией Майкрософт, затрудняет и неэкономичен управление Microsoft 365 с значительным взаимодействием с людьми.</span><span class="sxs-lookup"><span data-stu-id="e6bcd-105">The scale and the scope of services provided by Microsoft make it difficult and non-economical to manage Microsoft 365 with significant human interaction.</span></span> <span data-ttu-id="e6bcd-106">Службы Microsoft 365 предоставляются через несколько глобально распределенных центров обработки данных, каждый из которых сильно автоматизирован с помощью нескольких операций, требующих сенсорного управления или доступа к контенту клиента.</span><span class="sxs-lookup"><span data-stu-id="e6bcd-106">Microsoft 365 services are provided through multiple globally distributed data centers, each highly automated with few operations requiring a human touch or any access to customer content.</span></span> <span data-ttu-id="e6bcd-107">Наши сотрудники поддерживают эти службы и центры обработки данных с помощью автоматизированных средств и удаленного доступа с высокой безопасностью.</span><span class="sxs-lookup"><span data-stu-id="e6bcd-107">Our staff supports these services and data centers using automated tools and highly secure remote access.</span></span> 

<span data-ttu-id="e6bcd-108">Microsoft 365 состоит из нескольких служб, которые предоставляют важные бизнес-функции и вносят вклад в весь процесс работы с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6bcd-108">Microsoft 365 is composed of multiple services that provide important business functionality and contribute to the entire Microsoft 365 experience.</span></span> <span data-ttu-id="e6bcd-109">Каждая из этих служб является автономным и предназначена для интеграции друг с другом.</span><span class="sxs-lookup"><span data-stu-id="e6bcd-109">Each of these services is self-contained and designed to integrate with one another.</span></span>

<span data-ttu-id="e6bcd-110">Microsoft 365 разработан на основе следующих принципов:</span><span class="sxs-lookup"><span data-stu-id="e6bcd-110">Microsoft 365 is designed with the following principles:</span></span>

 - <span data-ttu-id="e6bcd-111">**[Service-Oriented Architecture](https://docs.microsoft.com/previous-versions/aa480021(v=msdn.10)):** designing and developing software in the form of interoperable services providing well-defined business functionality.</span><span class="sxs-lookup"><span data-stu-id="e6bcd-111">**[Service-Oriented Architecture](https://docs.microsoft.com/previous-versions/aa480021(v=msdn.10)):** designing and developing software in the form of interoperable services providing well-defined business functionality.</span></span>
 - <span data-ttu-id="e6bcd-112">**Operational [Security Assurance](https://www.microsoft.com/download/details.aspx?id=40872)—** это структура, которая включает знания, полученные с помощью различных уникальных для [](https://technet.microsoft.com/library/dn440717.aspx)Корпорации Майкрософт возможностей, включая жизненный цикл разработки для системы безопасности [(Майкрософт),](https://www.microsoft.com/sdl/default.aspx)Центр реагирования на угрозы безопасности (Майкрософт) и глубокую осведомленность об угрозе кибербезопасности.</span><span class="sxs-lookup"><span data-stu-id="e6bcd-112">**[Operational Security Assurance](https://www.microsoft.com/download/details.aspx?id=40872):** a framework that incorporates the knowledge gained through various capabilities that are unique to Microsoft, including the Microsoft [Security Development Lifecycle](https://www.microsoft.com/sdl/default.aspx), the [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx), and deep awareness of the cybersecurity threat landscape.</span></span>

<span data-ttu-id="e6bcd-113">Службы Microsoft 365 работают друг с другом, но разработаны и реализованы таким образом, чтобы их можно было развертывать и использовать как автономные службы независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="e6bcd-113">Microsoft 365 services inter-operate with each other, but are designed and implemented so they can be deployed and operated as autonomous services, independent of each other.</span></span> <span data-ttu-id="e6bcd-114">Корпорация Майкрософт разделяет обязанности и области ответственности для Microsoft 365, чтобы уменьшить возможности несанкционированного или непреднамерения изменения или неправильного использования активов организации.</span><span class="sxs-lookup"><span data-stu-id="e6bcd-114">Microsoft segregates duties and areas of responsibility for Microsoft 365 to reduce opportunities for unauthorized or unintentional modification or misuse of the organization's assets.</span></span> <span data-ttu-id="e6bcd-115">Группы Microsoft 365 определили роли в рамках комплексного механизма управления доступом на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="e6bcd-115">Microsoft 365 teams have defined roles as part of a comprehensive role-based access control mechanism.</span></span>

## <a name="customer-content-isolation"></a><span data-ttu-id="e6bcd-116">Изоляция контента клиента</span><span class="sxs-lookup"><span data-stu-id="e6bcd-116">Customer content isolation</span></span>

<span data-ttu-id="e6bcd-117">Весь контент клиента в клиенте изолирован от других клиентов, а также от операций и системных данных, используемых при управлении Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6bcd-117">All customer content in a tenant is isolated from other tenants and from operations and systems data used in the management of Microsoft 365.</span></span> <span data-ttu-id="e6bcd-118">В Microsoft 365 реализовано несколько форм защиты, чтобы свести к минимуму риск компрометации любой службы или приложения Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6bcd-118">Multiple forms of protection are implemented throughout Microsoft 365 to minimize the risk of compromise of any Microsoft 365 service or application.</span></span> <span data-ttu-id="e6bcd-119">Несколько форм защиты также предотвращают несанкционированный доступ к информации клиентов или самой системы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6bcd-119">Multiple forms of protection also prevent unauthorized access to the information of tenants or the Microsoft 365 system itself.</span></span>

<span data-ttu-id="e6bcd-120">Сведения о том, как Корпорация Майкрософт реализует логическую изоляцию данных клиента в Microsoft 365, см. в этой [теме.](microsoft-365-tenant-isolation-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e6bcd-120">For information about how Microsoft implements logical isolation of tenant data within Microsoft 365, see [Tenant Isolation in Microsoft 365](microsoft-365-tenant-isolation-overview.md).</span></span>
