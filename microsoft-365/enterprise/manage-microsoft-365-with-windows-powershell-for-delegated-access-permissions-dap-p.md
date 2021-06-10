---
title: Управление Microsoft 365 с Windows PowerShell для партнеров DAP
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
description: Как партнеры syndication и поставщик облачных решений (CSP) могут использовать Windows PowerShell для управления Microsoft 365 клиентов.
ms.openlocfilehash: 352a9a01414b94a1593de6a734151b687524fe7d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909530"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a><span data-ttu-id="bd08d-103">Управление Microsoft 365 с Windows PowerShell для партнеров по делегированным разрешениям доступа</span><span class="sxs-lookup"><span data-stu-id="bd08d-103">How to manage Microsoft 365 with Windows PowerShell for Delegated Access Permissions partners</span></span>

<span data-ttu-id="bd08d-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="bd08d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="bd08d-105">Партнеры по делегированным правам доступа (DAP)  партнеры по синдикации и поставщики облачных решений (CSP).</span><span class="sxs-lookup"><span data-stu-id="bd08d-105">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="bd08d-106">Многие из них являются сетевыми или телекоммуникационными поставщиками.</span><span class="sxs-lookup"><span data-stu-id="bd08d-106">Many are network or telecom providers.</span></span> <span data-ttu-id="bd08d-107">Они Microsoft 365 подписок в свои предложения служб.</span><span class="sxs-lookup"><span data-stu-id="bd08d-107">They bundle Microsoft 365 subscriptions into their service offerings.</span></span> <span data-ttu-id="bd08d-108">Когда они продают подписку Microsoft 365, они автоматически получают разрешения администрирования от имени (AOBO) для клиентов tenancies, чтобы они могли администрировать и сообщать об этих tenancies.</span><span class="sxs-lookup"><span data-stu-id="bd08d-108">When they sell a Microsoft 365 subscription, they're automatically granted Administer On Behalf Of (AOBO) permissions to the customer's tenancies so they can administer and report on those tenancies.</span></span> <span data-ttu-id="bd08d-109">Эти задачи трудно выполнять в центре Microsoft 365 администрирования.</span><span class="sxs-lookup"><span data-stu-id="bd08d-109">These tasks are difficult to do in the Microsoft 365 admin center.</span></span> <span data-ttu-id="bd08d-110">Гораздо проще использовать PowerShell для Microsoft 365 для выполнения административных задач, таких как:</span><span class="sxs-lookup"><span data-stu-id="bd08d-110">It's much easier to use PowerShell for Microsoft 365 to do administrative tasks such as:</span></span>
- <span data-ttu-id="bd08d-111">Список всех клиентов **TenantIds** и их доменов</span><span class="sxs-lookup"><span data-stu-id="bd08d-111">List all the customer **TenantIds** and their domains</span></span> 
- <span data-ttu-id="bd08d-112">Определение всех пользователей в клиентской аренде и их назначенных лицензий</span><span class="sxs-lookup"><span data-stu-id="bd08d-112">Identify all users in a customer tenancy and their assigned licenses</span></span>
> [!NOTE]
> <span data-ttu-id="bd08d-113">Некоторые административные задачи можно выполнять только в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd08d-113">Some administrative tasks can only be done in PowerShell.</span></span>

<span data-ttu-id="bd08d-114">В следующих статьях покажите, как партнеры По синдикации и CSP используют PowerShell для администрирования своих клиентов:</span><span class="sxs-lookup"><span data-stu-id="bd08d-114">The following articles show how Syndication and CSP partners use PowerShell to administer their customer tenancies:</span></span>
  
- [<span data-ttu-id="bd08d-115">Управление Microsoft 365 с помощью Windows PowerShell партнеров по делегированию разрешений доступа (DAP)</span><span class="sxs-lookup"><span data-stu-id="bd08d-115">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [<span data-ttu-id="bd08d-116">Добавление домена к аренде клиента с помощью Windows PowerShell для партнеров службы разрешений делегированного доступа (DAP)</span><span class="sxs-lookup"><span data-stu-id="bd08d-116">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [<span data-ttu-id="bd08d-117">Подключение к PowerShell Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bd08d-117">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
    
- [<span data-ttu-id="bd08d-118">Получение отчетных данных пользовательских клиентов с помощью Windows PowerShell для партнеров службы разрешений делегированного доступа (DAP)</span><span class="sxs-lookup"><span data-stu-id="bd08d-118">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
