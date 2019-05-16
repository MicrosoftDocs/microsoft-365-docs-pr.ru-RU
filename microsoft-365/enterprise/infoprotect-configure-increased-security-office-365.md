---
title: Шаг 3. Настройка усиленной защиты для Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как настроить усиленную защиту для Microsoft 365.
ms.openlocfilehash: 81c39eb6a51e7596a72721c72084f1f255f7f451
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073639"
---
# <a name="step-3-configure-increased-security-for-microsoft-365"></a><span data-ttu-id="896f9-103">Шаг 3. Настройка усиленной защиты для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="896f9-103">Step 3: Configure increased security for Microsoft 365</span></span>

<span data-ttu-id="896f9-104">*Этот шаг — обязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="896f9-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="896f9-105">Чтобы защитить вашу подписку на Microsoft 365 и ее данные от вредоносных угроз, настройте следующее:</span><span class="sxs-lookup"><span data-stu-id="896f9-105">To ensure that your Microsoft 365 subscription and its data start off and remain secure from malicious threats, configure the following:</span></span>

- [<span data-ttu-id="896f9-106">Политики управления угрозами</span><span class="sxs-lookup"><span data-stu-id="896f9-106">Tune threat management policies</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#tune-threat-management-policies-in-the-office-365-security--compliance-center)
- [<span data-ttu-id="896f9-107">Дополнительные параметры, используемые во всем клиенте Exchange Online</span><span class="sxs-lookup"><span data-stu-id="896f9-107">Additional Exchange Online tenant-wide settings</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-additional-exchange-online-tenant-wide-settings)
- [<span data-ttu-id="896f9-108">Политики общего доступа для всего клиента в Центре администрирования SharePoint</span><span class="sxs-lookup"><span data-stu-id="896f9-108">Tenant-wide sharing policies in the SharePoint admin center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-tenant-wide-sharing-policies-in-sharepoint-admin-center)
- [<span data-ttu-id="896f9-109">Параметры в Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="896f9-109">Settings in Azure Active Directory (Azure AD)</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-settings-in-azure-active-directory)

<span data-ttu-id="896f9-110">После настройки вы сможете получать сведения о состоянии системы обеспечения безопасности из указанных ниже источников.</span><span class="sxs-lookup"><span data-stu-id="896f9-110">Once configured, you can obtain information about your security status from:</span></span>

- [<span data-ttu-id="896f9-111">Панели мониторинга и отчеты в Центре безопасности Майкрософт</span><span class="sxs-lookup"><span data-stu-id="896f9-111">Dashboards and reports in the Microsoft security Center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#view-dashboards-and-reports-in-the-security--compliance-center)
- [<span data-ttu-id="896f9-112">Оценка безопасности (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="896f9-112">Microsoft Secure Score</span></span>](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)

<span data-ttu-id="896f9-113">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) — это дополнительная функция защиты, обеспечивающая более безопасную совместную работу в вашей организации благодаря указанным ниже средствам.</span><span class="sxs-lookup"><span data-stu-id="896f9-113">An additional security feature is [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="896f9-114">Защита [ссылок](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) и [вложений](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) в электронных письмах.</span><span class="sxs-lookup"><span data-stu-id="896f9-114">Protecting [links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) and [attachments](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) in email.</span></span> 
- <span data-ttu-id="896f9-115">Функции анализа подделок и антифишинга для почты в Exchange Online и [файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="896f9-115">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and [files in SharePoint Online, OneDrive for Business, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span></span> 

<span data-ttu-id="896f9-116">Функция Office 365 ATP доступна только в плане Microsoft 365 корпоративный E5.</span><span class="sxs-lookup"><span data-stu-id="896f9-116">Office 365 ATP is only available with Microsoft 365 Enterprise E5.</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="896f9-118">Руководство по лаборатории тестирования: настройка усиленной защиты Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="896f9-118">Test Lab Guide: Configure increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="896f9-119">Прежде чем перейти к следующему шагу, проверьте [условия](infoprotect-exit-criteria.md#crit-infoprotect-step3), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="896f9-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="896f9-120">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="896f9-120">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="896f9-121">Настройка Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="896f9-121">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|


