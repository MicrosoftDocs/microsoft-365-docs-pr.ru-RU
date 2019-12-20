---
title: Шаг 3. Настройка усиленной защиты для Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как настроить усиленную защиту для Microsoft 365.
ms.openlocfilehash: 15a4121315a81e1169e7cf1fa1c7ed079201b67b
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801684"
---
# <a name="step-3-configure-increased-security-for-microsoft-365"></a><span data-ttu-id="c9a1d-103">Шаг 3. Настройка усиленной защиты для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c9a1d-103">Step 3: Configure increased security for Microsoft 365</span></span>

<span data-ttu-id="c9a1d-104">*Этот шаг — обязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="c9a1d-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Этап 6. Защита данных](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="c9a1d-106">Чтобы защитить вашу подписку на Microsoft 365 и ее данные от вредоносных угроз, настройте следующее:</span><span class="sxs-lookup"><span data-stu-id="c9a1d-106">To ensure that your Microsoft 365 subscription and its data start off and remain secure from malicious threats, configure the following:</span></span>

- [<span data-ttu-id="c9a1d-107">Политики управления угрозами</span><span class="sxs-lookup"><span data-stu-id="c9a1d-107">Tune threat management policies</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#tune-threat-management-policies-in-the-microsoft-365-security-center)
- [<span data-ttu-id="c9a1d-108">Дополнительные параметры, используемые во всем клиенте Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c9a1d-108">Additional Exchange Online tenant-wide settings</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-additional-exchange-online-tenant-wide-settings)
- [<span data-ttu-id="c9a1d-109">Политики общего доступа для всего клиента в Центре администрирования SharePoint</span><span class="sxs-lookup"><span data-stu-id="c9a1d-109">Tenant-wide sharing policies in the SharePoint admin center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-tenant-wide-sharing-policies-in-sharepoint-admin-center)
- [<span data-ttu-id="c9a1d-110">Параметры в Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="c9a1d-110">Settings in Azure Active Directory (Azure AD)</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-settings-in-azure-active-directory)

<span data-ttu-id="c9a1d-111">После настройки вы сможете получать сведения о состоянии системы обеспечения безопасности из указанных ниже источников.</span><span class="sxs-lookup"><span data-stu-id="c9a1d-111">Once configured, you can obtain information about your security status from:</span></span>

- [<span data-ttu-id="c9a1d-112">Панели мониторинга и отчеты в Центре безопасности Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c9a1d-112">Dashboards and reports in the Microsoft security Center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#view-dashboards-and-reports-in-the-security-and-compliance-centers)
- [<span data-ttu-id="c9a1d-113">Оценка безопасности (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="c9a1d-113">Microsoft Secure Score</span></span>](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)

<span data-ttu-id="c9a1d-114">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) — это дополнительная функция защиты, обеспечивающая более безопасную совместную работу в вашей организации благодаря указанным ниже средствам.</span><span class="sxs-lookup"><span data-stu-id="c9a1d-114">An additional security feature is [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="c9a1d-115">Защита [ссылок](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) и [вложений](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) в электронных письмах.</span><span class="sxs-lookup"><span data-stu-id="c9a1d-115">Protecting [links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) and [attachments](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) in email.</span></span> 
- <span data-ttu-id="c9a1d-116">Функции анализа подделок и антифишинга для почты в Exchange Online и [файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="c9a1d-116">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and [files in SharePoint Online, OneDrive for Business, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span></span> 

<span data-ttu-id="c9a1d-117">Функция Office 365 ATP доступна только в плане Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c9a1d-117">Office 365 ATP is only available with Microsoft 365 Enterprise E5.</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="c9a1d-119">Руководство по лаборатории тестирования: настройка усиленной защиты Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c9a1d-119">Test Lab Guide: Configure increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="c9a1d-120">Прежде чем перейти к следующему шагу, проверьте [условия](infoprotect-exit-criteria.md#crit-infoprotect-step3), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="c9a1d-120">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="c9a1d-121">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="c9a1d-121">Next step</span></span>


|||
|:-------|:-----|
|![Шаг 4](./media/stepnumbers/Step4.png)|[<span data-ttu-id="c9a1d-123">Настройка Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="c9a1d-123">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|


