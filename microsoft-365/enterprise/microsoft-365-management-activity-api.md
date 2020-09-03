---
title: API действий управления Office 365
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
- M365-analytics
f1.keywords:
- NOCSH
description: В этой статье представлены краткие сведения о API действий управления Office 365 и сведения, которые он предоставляет из журналов действий.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8d51f27f28b0adb84ef43004664ef310567263b9
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332308"
---
# <a name="office-365-management-activity-api"></a><span data-ttu-id="a9882-103">API действий управления Office 365</span><span class="sxs-lookup"><span data-stu-id="a9882-103">Office 365 Management Activity API</span></span>

<span data-ttu-id="a9882-104">Корпорация Майкрософт предоставляет службы отчетов, которые можно использовать для получения собранных сведений о транзакциях, отличных от клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="a9882-104">Microsoft provides reporting services you can use to obtain aggregated transactional information about your Office 365 tenant.</span></span> <span data-ttu-id="a9882-105">[API действий управления Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview#office-365-management-activity-api) использует стандартную схему RESTful и OAuth v2 для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="a9882-105">The [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview#office-365-management-activity-api) uses an industry-standard RESTful design and OAuth v2 for authentication.</span></span> <span data-ttu-id="a9882-106">Это позволяет легко начать эксперименты с извлечением данных и их использованием в средствах и приложениях для визуализации.</span><span class="sxs-lookup"><span data-stu-id="a9882-106">This makes it easy to start experimenting with retrieving data and ingesting it into visualization tools and applications.</span></span> <span data-ttu-id="a9882-107">API предоставляет канал данных, содержащий сведения о пользователях, администраторах, операциях и действиях по обеспечению безопасности в Office 365.</span><span class="sxs-lookup"><span data-stu-id="a9882-107">The API provides a data feed with information about user, administrator, operations, and security activity in Office 365.</span></span> <span data-ttu-id="a9882-108">Данные можно хранить в соответствии с нормативными требованиями или в сочетании с данными журналов, полученными из локальной инфраструктуры или других источников.</span><span class="sxs-lookup"><span data-stu-id="a9882-108">The data can be kept for regulatory purposes, or combined with log data procured from an on-premises infrastructure or other sources.</span></span> <span data-ttu-id="a9882-109">Это помогает создать решение мониторинга для операций, безопасности и соответствия требованиям в Организации.</span><span class="sxs-lookup"><span data-stu-id="a9882-109">This helps build a monitoring solution for operations, security, and compliance across the enterprise.</span></span>

<span data-ttu-id="a9882-110">API действий управления Office 365 обеспечивает получение информации о различных действиях и событиях, касающихся пользователей, администраторов, систем и политик, из отчетов о действиях касательно Office 365 и Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a9882-110">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="a9882-111">API предоставляет единообразную схему аудита с более чем 10 полями, которые являются общими для всех служб.</span><span class="sxs-lookup"><span data-stu-id="a9882-111">The API provides a consistent audit schema with over 10 fields common across all the services.</span></span> <span data-ttu-id="a9882-112">API позволяет организациям легко подключаться между событиями и обеспечивает новые способы определения причин для данных.</span><span class="sxs-lookup"><span data-stu-id="a9882-112">The API allows organizations to make easy connections between events, and enables new ways to reason over the data.</span></span>

<span data-ttu-id="a9882-113">Десятки независимых поставщиков программного обеспечения (ISV), которые сопоставлены с корпорацией Майкрософт и имеют готовые решения на основе API.</span><span class="sxs-lookup"><span data-stu-id="a9882-113">Dozens of Independent Software Vendors (ISVs) partnered with Microsoft and have built solutions based on the API.</span></span> <span data-ttu-id="a9882-114">Некоторые решения касаются только данных Office 365 и других исходных данных из нескольких облачных поставщиков и локальных систем, чтобы создать единое представление действий, безопасности и действий, связанных с соответствием соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a9882-114">Some solutions focus solely on Office 365 data and others source data from multiple cloud providers and on-premises systems to create a unified view of operations, security, and compliance-related activity.</span></span> 

<span data-ttu-id="a9882-115">Дополнительные сведения см. в [справочнике по API действий управления Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="a9882-115">For more information, see the [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>
