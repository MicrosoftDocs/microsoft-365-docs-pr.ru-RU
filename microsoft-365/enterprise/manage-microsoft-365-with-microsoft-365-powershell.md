---
title: Управление Microsoft 365 с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- O365ITProTrain
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 932d57c0-1520-4f0f-8ec9-9966d646480f
description: Сведения о том, как управлять пользователями, лицензиями и 365 для приложений Microsoft 365 с помощью PowerShell.
ms.openlocfilehash: b1e8353eac1fb2917330ef5b5c2c7752fe5b1824
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655855"
---
# <a name="manage-microsoft-365-with-powershell"></a><span data-ttu-id="9d3f7-103">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d3f7-103">Manage Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="9d3f7-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="9d3f7-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9d3f7-105">PowerShell для Microsoft 365 — это мощное средство управления, которое дополняет центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9d3f7-105">PowerShell for Microsoft 365 is a powerful management tool that complements the Microsoft 365 admin center.</span></span> <span data-ttu-id="9d3f7-106">Например, вы можете использовать автоматизацию PowerShell для упрощения управления несколькими учетными записями и лицензиями пользователей, а также для создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="9d3f7-106">For example, you can use PowerShell automation to easily manage multiple user accounts and licenses and to create reports.</span></span>

<span data-ttu-id="9d3f7-107">Чтобы узнать, как использовать PowerShell для управления Microsoft 365, выберите из следующих разделов:</span><span class="sxs-lookup"><span data-stu-id="9d3f7-107">Select from the following topics to learn how to use PowerShell to manage Microsoft 365:</span></span>
  
- [<span data-ttu-id="9d3f7-108">**Начало работы**</span><span class="sxs-lookup"><span data-stu-id="9d3f7-108">**Get started**</span></span>](getting-started-with-microsoft-365-powershell.md)

    <span data-ttu-id="9d3f7-109">Начните отсюда, если вы не знакомы с PowerShell для Microsoft 365 и хотите установить модули Microsoft 365 и подключиться к вашей подписке.</span><span class="sxs-lookup"><span data-stu-id="9d3f7-109">Start here if you're not familiar with PowerShell for Microsoft 365, and you want to install the Microsoft 365 modules and connect to your subscription.</span></span>

- [<span data-ttu-id="9d3f7-110">**Учетные записи пользователей, лицензии и группы**</span><span class="sxs-lookup"><span data-stu-id="9d3f7-110">**User accounts, licenses, and groups**</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

    <span data-ttu-id="9d3f7-111">Начните отсюда, если хотите узнать об использовании команд автоматизации для управления учетными записями пользователей, лицензиями и группами.</span><span class="sxs-lookup"><span data-stu-id="9d3f7-111">Start here if want to learn about using automation commands to manage user accounts, licenses, and groups.</span></span>

- [<span data-ttu-id="9d3f7-112">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="9d3f7-112">**SharePoint**</span></span>](manage-sharepoint-online-with-microsoft-365-powershell.md)

    <span data-ttu-id="9d3f7-113">Начните отсюда, если вы хотите использовать команды автоматизации для управления SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9d3f7-113">Start here if you want to use automation commands to manage SharePoint.</span></span>

- [<span data-ttu-id="9d3f7-114">**Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="9d3f7-114">**Exchange Online**</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)

    <span data-ttu-id="9d3f7-115">Начните отсюда, если вы хотите управлять Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9d3f7-115">Start here if you want to manage Exchange Online.</span></span>

- [<span data-ttu-id="9d3f7-116">**миграции электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="9d3f7-116">**Email migration**</span></span>](use-powershell-for-email-migration-to-microsoft-365.md)

    <span data-ttu-id="9d3f7-117">Начните отсюда, если вы хотите перенести электронную почту из уже имеющихся систем.</span><span class="sxs-lookup"><span data-stu-id="9d3f7-117">Start here if you want to migrate your email from pre-existing systems.</span></span>

- [<span data-ttu-id="9d3f7-118">**Центр безопасности и соответствия требованиям**</span><span class="sxs-lookup"><span data-stu-id="9d3f7-118">**Security & Compliance Center**</span></span>](https://docs.microsoft.com/powershell/exchange/scc-powershell)

    <span data-ttu-id="9d3f7-119">Начните отсюда, если вы хотите управлять функциями безопасности & центра соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="9d3f7-119">Start here if you want to manage Security & Compliance Center features.</span></span>

- [<span data-ttu-id="9d3f7-120">**Партнеры по Делегированному доступу**</span><span class="sxs-lookup"><span data-stu-id="9d3f7-120">**Delegated Access Permissions (DAP) partners**</span></span>](manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-dap-p.md)

    <span data-ttu-id="9d3f7-121">Начните отсюда, если вы хотите использовать партнеров для синдикации и поставщиков облачных решений (CSP) для управления вашими клиентами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9d3f7-121">Start here if you want to use Syndication and Cloud Solution Provider (CSP) partners to manage your Microsoft 365 customer tenants.</span></span>

- [<span data-ttu-id="9d3f7-122">**Skype для Бизнеса Онлайн**</span><span class="sxs-lookup"><span data-stu-id="9d3f7-122">**Skype for Business Online**</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)

    <span data-ttu-id="9d3f7-123">Начните с этой статьи, чтобы управлять Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="9d3f7-123">Start here to manage Skype for Business Online.</span></span>
