---
title: 'Microsoft 365 Поддержка клиентских приложений: многофакторная проверка подлинности'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: В этой статье узнайте, какие платформы, клиенты и модули PowerShell поддерживают многофакторную проверку подлинности для Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 80ee370526d17d472cd048cd4d89b862e158b631
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927569"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a><span data-ttu-id="f3e0b-103">Microsoft 365 Поддержка клиентских приложений: многофакторная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="f3e0b-103">Microsoft 365 Client App Support: Multi-factor authentication</span></span>

<span data-ttu-id="f3e0b-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="f3e0b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f3e0b-105">Чтобы обеспечить дополнительный уровень безопасности для входных входов, клиенты могут быть настроены на использование многофакторной проверки подлинности (MFA), которая использует как пароль пользователя, так и другой метод проверки пользователей на основе:</span><span class="sxs-lookup"><span data-stu-id="f3e0b-105">To provide an additional level of security for sign-ins, clients may be configured to use multi-factor authentication (MFA), which uses both a user password and another user verification method based on:</span></span>

- <span data-ttu-id="f3e0b-106">Что-то в их распоряжении, которое не легко дублировать, например, смартфон.</span><span class="sxs-lookup"><span data-stu-id="f3e0b-106">Something  in their possession that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="f3e0b-107">Что-то уникальное и биологическое, например отпечатки пальцев, лицо или другой биометрический атрибут.</span><span class="sxs-lookup"><span data-stu-id="f3e0b-107">Something the user has uniquely and biologically, such as their fingerprints, face, or other biometric attribute</span></span>

<span data-ttu-id="f3e0b-108">Узнайте больше о [многофакторной проверке подлинности.](/azure/active-directory/authentication/multi-factor-authentication)</span><span class="sxs-lookup"><span data-stu-id="f3e0b-108">Learn more about [multi-factor authentication](/azure/active-directory/authentication/multi-factor-authentication).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="f3e0b-109">Поддерживаемые & платформы</span><span class="sxs-lookup"><span data-stu-id="f3e0b-109">Supported clients & platforms</span></span>

<span data-ttu-id="f3e0b-110">Последние версии следующих клиентов и платформ поддерживают многофакторную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="f3e0b-110">The latest versions of the following clients and platforms support multi-factor authentication.</span></span> <span data-ttu-id="f3e0b-111">Дополнительные сведения о поддержке платформы в Microsoft 365 см. в [Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)</span><span class="sxs-lookup"><span data-stu-id="f3e0b-111">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Multi-factor authentication services support table](../includes/microsoft-365-client-support-modern-authentication-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="f3e0b-112">Поддерживаемые модули PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3e0b-112">Supported PowerShell modules</span></span>

- [<span data-ttu-id="f3e0b-113">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3e0b-113">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [<span data-ttu-id="f3e0b-114">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3e0b-114">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="f3e0b-115">PowerShell в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f3e0b-115">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)