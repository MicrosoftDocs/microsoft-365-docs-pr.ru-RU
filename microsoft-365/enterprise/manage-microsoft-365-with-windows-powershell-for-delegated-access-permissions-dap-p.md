---
title: Управление Microsoft 365 с помощью Windows PowerShell для партнеров в системе доступа к данным
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: be497751-596f-431d-b256-0a89d36a47ce
description: Сводка. партнеры по синдикации и поставщикам облачных решений (CSP) могут использовать Windows PowerShell для управления клиентскими клиентами Microsoft 365.
ms.openlocfilehash: d4109c09a14fb5644d34daf24383053536440871
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693418"
---
# <a name="manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="bdab3-103">Управление Microsoft 365 с помощью Windows PowerShell для партнеров с правами доступа к данным делегированного доступа</span><span class="sxs-lookup"><span data-stu-id="bdab3-103">Manage Microsoft 365 with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="bdab3-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="bdab3-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="bdab3-105">Партнеры по делегированным правам доступа (DAP)  партнеры по синдикации и поставщики облачных решений (CSP).</span><span class="sxs-lookup"><span data-stu-id="bdab3-105">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="bdab3-106">Они часто бывают поставщиками сети или телекоммуникационных услуг в других компаниях.</span><span class="sxs-lookup"><span data-stu-id="bdab3-106">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="bdab3-107">Они объединяют подписки на Microsoft 365 на свои услуги своим клиентам.</span><span class="sxs-lookup"><span data-stu-id="bdab3-107">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="bdab3-108">Когда вы продаете подписку на Microsoft 365, им автоматически предоставляются разрешения на администрирование от имени пользователя (АОБО), чтобы они могли администрировать и предоставлять отчеты для клиентов клиенты.</span><span class="sxs-lookup"><span data-stu-id="bdab3-108">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span> <span data-ttu-id="bdab3-109">В центре администрирования Майкрософт 365 это сложно и много времени.</span><span class="sxs-lookup"><span data-stu-id="bdab3-109">At best, this is difficult and time consuming to do in the Microsoft 365 admin center.</span></span> <span data-ttu-id="bdab3-110">Значительно упрощается выполнение административных задач, таких как список всех клиентов **тенантидс** и их доменов, а также определение всех пользователей в клиентской лицензии и лицензий, назначенных им с помощью PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bdab3-110">It is much easier to do administrative tasks like listing all the customer **TenantIds** and their domains or identifying all users in a customer tenancy and what licenses they are assigned by using PowerShell for Microsoft 365.</span></span> <span data-ttu-id="bdab3-111">В некоторых случаях эти административные задачи можно выполнить только в PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bdab3-111">In some cases, it is possible to do these administrative tasks only in PowerShell for Microsoft 365.</span></span> <span data-ttu-id="bdab3-112">Ниже приведены примеры сценариев, которые партнеры служб синдикации и CSP чаще всего используют для администрирования своих клиентов:</span><span class="sxs-lookup"><span data-stu-id="bdab3-112">Here are samples of scenarios that Syndication and CSP partners most frequently use to administer their customer tenancies:</span></span>
  
## 

- [<span data-ttu-id="bdab3-113">Управление клиентами Microsoft 365 с помощью Windows PowerShell для партнеров с правами доступа к данным делегированного доступа</span><span class="sxs-lookup"><span data-stu-id="bdab3-113">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [<span data-ttu-id="bdab3-114">Добавление домена к аренде клиента с помощью Windows PowerShell для партнеров службы разрешений делегированного доступа (DAP)</span><span class="sxs-lookup"><span data-stu-id="bdab3-114">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [<span data-ttu-id="bdab3-115">Подключение к клиентам Exchange Online с помощью удаленного сеанса Windows PowerShell для партнеров службы разрешений делегированного доступа (DAP)</span><span class="sxs-lookup"><span data-stu-id="bdab3-115">Connect to Exchange Online tenants with remote Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md)
    
- [<span data-ttu-id="bdab3-116">Получение отчетных данных пользовательских клиентов с помощью Windows PowerShell для партнеров службы разрешений делегированного доступа (DAP)</span><span class="sxs-lookup"><span data-stu-id="bdab3-116">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
    

    

