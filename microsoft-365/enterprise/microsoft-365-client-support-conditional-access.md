---
title: 'Поддержка клиентских приложений Microsoft 365: условный доступ'
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
description: В этой статье узнайте, какие платформы, клиенты и модули PowerShell поддерживают условный доступ для Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7b0b65ea25091aad01fd8741f9925f2b545e9c4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904970"
---
# <a name="microsoft-365-client-app-support-conditional-access"></a><span data-ttu-id="cd60e-103">Поддержка клиентских приложений Microsoft 365: условный доступ</span><span class="sxs-lookup"><span data-stu-id="cd60e-103">Microsoft 365 Client App Support: Conditional Access</span></span>

<span data-ttu-id="cd60e-104">На современном рабочем месте пользователи могут получать доступ к ресурсам организации с помощью различных устройств и приложений из любой точки мира.</span><span class="sxs-lookup"><span data-stu-id="cd60e-104">In the modern workplace, users can access your organization's resources using various devices and apps from anywhere.</span></span> <span data-ttu-id="cd60e-105">В результате этого недостаточно просто сосредоточиться на том, кто может получить доступ к ресурсу.</span><span class="sxs-lookup"><span data-stu-id="cd60e-105">As a result, just focusing on who can access a resource is not sufficient anymore.</span></span> <span data-ttu-id="cd60e-106">Организация также должна поддерживать доступ к ресурсу в инфраструктуре управления доступом.</span><span class="sxs-lookup"><span data-stu-id="cd60e-106">Your organization must also support how and where a resource is accessed in your access control infrastructure.</span></span>

<span data-ttu-id="cd60e-107">Благодаря устройству Azure Active Directory, расположению и многофакторной проверке подлинности условным доступом можно выполнить это новое требование.</span><span class="sxs-lookup"><span data-stu-id="cd60e-107">With Azure Active Directory device, location, and multi-factor authentication-based Conditional Access, you can meet this new requirement.</span></span> <span data-ttu-id="cd60e-108">Условный доступ — это возможность Azure Active Directory, которая позволяет применять элементы управления доступом к приложениям в вашей среде, все зависит от определенных условий и управляется из центра.</span><span class="sxs-lookup"><span data-stu-id="cd60e-108">Conditional Access is a capability of Azure Active Directory that enables you to enforce controls on the access to apps in your environment, all based on specific conditions and managed from a central location.</span></span>

<span data-ttu-id="cd60e-109">Дополнительные возможности условного [доступа к Azure Active Directory](/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="cd60e-109">Learn more about [Azure Active Directory Conditional Access](/azure/active-directory/conditional-access/).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="cd60e-110">Поддерживаемые & платформы</span><span class="sxs-lookup"><span data-stu-id="cd60e-110">Supported clients & platforms</span></span>

<span data-ttu-id="cd60e-111">Последние версии следующих клиентов и платформ поддерживают условный доступ.</span><span class="sxs-lookup"><span data-stu-id="cd60e-111">The latest versions of the following clients and platforms support conditional access.</span></span> <span data-ttu-id="cd60e-112">Дополнительные сведения о поддержке платформы в Microsoft 365 см. в дополнительных сведениях о требованиях [системы к Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)</span><span class="sxs-lookup"><span data-stu-id="cd60e-112">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Conditional access services support table](../includes/microsoft-365-client-support-conditional-access-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="cd60e-113">Поддерживаемые модули PowerShell</span><span class="sxs-lookup"><span data-stu-id="cd60e-113">Supported PowerShell modules</span></span>

- [<span data-ttu-id="cd60e-114">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="cd60e-114">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [<span data-ttu-id="cd60e-115">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="cd60e-115">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="cd60e-116">PowerShell в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cd60e-116">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
