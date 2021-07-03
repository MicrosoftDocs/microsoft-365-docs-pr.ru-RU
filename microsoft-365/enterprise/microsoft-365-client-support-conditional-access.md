---
title: 'Microsoft 365 Поддержка клиентских приложений: условный доступ'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- NOCSH
description: В этой статье узнайте, какие платформы, клиенты и модули PowerShell поддерживают условные Access для Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 763380429b8643c5dd01971117fccb040a9a0210
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286565"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a><span data-ttu-id="dd983-103">Microsoft 365 Поддержка клиентских приложений: условный доступ</span><span class="sxs-lookup"><span data-stu-id="dd983-103">Microsoft 365 Client App Support: Conditional Access</span></span>

<span data-ttu-id="dd983-104">На современном рабочем месте пользователи могут получать доступ к ресурсам организации с помощью различных устройств и приложений из любой точки мира.</span><span class="sxs-lookup"><span data-stu-id="dd983-104">In the modern workplace, users can access your organization's resources using various devices and apps from anywhere.</span></span> <span data-ttu-id="dd983-105">В результате этого недостаточно просто сосредоточиться на том, кто может получить доступ к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="dd983-105">As a result, just focusing on who can access a resource is not sufficient anymore.</span></span> <span data-ttu-id="dd983-106">Организация также должна поддерживать доступ к ресурсу в инфраструктуре управления доступом.</span><span class="sxs-lookup"><span data-stu-id="dd983-106">Your organization must also support how and where a resource is accessed in your access control infrastructure.</span></span>

<span data-ttu-id="dd983-107">Благодаря Azure Active Directory устройству, расположению и многофакторной проверке подлинности условным доступом можно выполнить это новое требование.</span><span class="sxs-lookup"><span data-stu-id="dd983-107">With Azure Active Directory device, location, and multi-factor authentication-based Conditional Access, you can meet this new requirement.</span></span> <span data-ttu-id="dd983-108">Условный доступ — это возможность Azure Active Directory, которая позволяет применять элементы управления доступом к приложениям в вашей среде, все зависит от определенных условий и управляется из центра.</span><span class="sxs-lookup"><span data-stu-id="dd983-108">Conditional Access is a capability of Azure Active Directory that enables you to enforce controls on the access to apps in your environment, all based on specific conditions and managed from a central location.</span></span>

<span data-ttu-id="dd983-109">Дополнительные дополнительные [Azure Active Directory условного доступа](/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="dd983-109">Learn more about [Azure Active Directory Conditional Access](/azure/active-directory/conditional-access/).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="dd983-110">Поддерживаемые & платформы</span><span class="sxs-lookup"><span data-stu-id="dd983-110">Supported clients & platforms</span></span>

<span data-ttu-id="dd983-111">Последние версии следующих клиентов и платформ поддерживают условный доступ.</span><span class="sxs-lookup"><span data-stu-id="dd983-111">The latest versions of the following clients and platforms support conditional access.</span></span> <span data-ttu-id="dd983-112">Дополнительные сведения о поддержке платформы в Microsoft 365 см. в [Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)</span><span class="sxs-lookup"><span data-stu-id="dd983-112">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Conditional access services support table](../includes/microsoft-365-client-support-conditional-access-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="dd983-113">Поддерживаемые модули PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd983-113">Supported PowerShell modules</span></span>

- [<span data-ttu-id="dd983-114">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd983-114">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview)
- [<span data-ttu-id="dd983-115">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd983-115">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="dd983-116">PowerShell в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="dd983-116">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
