---
title: Шаг 3. Настройка усиленной защиты для Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как настроить усиленную защиту для Office 365, включая Office 365 Advanced Threat Protection.
ms.openlocfilehash: 0344778b8d8f9940dc6267a39eac2f4cfb261f9a
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870965"
---
# <a name="step-3-configure-increased-security-for-office-365"></a><span data-ttu-id="2056a-103">Шаг 3. Настройка усиленной защиты для Office 365</span><span class="sxs-lookup"><span data-stu-id="2056a-103">Step 3: Configure increased security for Office 365</span></span>

<span data-ttu-id="2056a-104">*Этот шаг — обязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="2056a-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="2056a-105">Чтобы защитить вашу подписку на Office 365 и ее данные от вредоносных угроз, выполните инструкции в статье [Настройка клиента Office 365 для повышения безопасности](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355). Кроме того, настройте указанные ниже дополнительные средства обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="2056a-105">To ensure that your Office 365 subscription and its data start off and remain secure from malicious threats, see [Configure your Office 365 tenant for increased security](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355) and configure the following additional security:</span></span>

- <span data-ttu-id="2056a-106">Политики управления угрозами в Центре безопасности и соответствия требованиям Office 365</span><span class="sxs-lookup"><span data-stu-id="2056a-106">Threat management policies in the Office 365 Security & Compliance Center</span></span>
- <span data-ttu-id="2056a-107">Дополнительные параметры, используемые во всем клиенте Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2056a-107">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="2056a-108">Политики общего доступа, используемые во всем клиенте, в Центре администрирования SharePoint</span><span class="sxs-lookup"><span data-stu-id="2056a-108">Tenant-wide sharing policies in the SharePoint admin center</span></span>
- <span data-ttu-id="2056a-109">Параметры в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2056a-109">Settings in Azure Active Directory</span></span>

<span data-ttu-id="2056a-110">После настройки вы сможете получать сведения о состоянии системы обеспечения безопасности из указанных ниже источников.</span><span class="sxs-lookup"><span data-stu-id="2056a-110">Once configured, you can obtain information about your security status from:</span></span>

- <span data-ttu-id="2056a-111">Панель мониторинга и отчеты в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="2056a-111">Dashboards and reports in the Security & Compliance Center</span></span>
- [<span data-ttu-id="2056a-112">Оценка безопасности Office 365</span><span class="sxs-lookup"><span data-stu-id="2056a-112">Office 365 Secure Score</span></span>](https://securescore.office.com/)
 
  <span data-ttu-id="2056a-113">Для доступа к этой странице необходимо войти в систему в качестве администратора клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="2056a-113">To access this page, you must be signed in as an Office 365 tenant admin.</span></span>

<span data-ttu-id="2056a-114">Кроме того, с помощью Cloud App Security или Office 365 Cloud App Security вы можете отслеживать события безопасности и выполнять необходимые действия. Дополнительные сведения см. в статье [Общие сведения о безопасности облачных приложений Office 365](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475).</span><span class="sxs-lookup"><span data-stu-id="2056a-114">You can also use Cloud App Security or Office 365 Cloud App Security to monitor for security events and act. For more information, see [Overview of Office 365 Cloud App Security](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475).</span></span>

<span data-ttu-id="2056a-115">Office 365 Advanced Threat Protection — это дополнительная функция защиты. Благодаря ей совместная работа в вашей организации станет более безопасной благодаря указанным ниже средствам.</span><span class="sxs-lookup"><span data-stu-id="2056a-115">An additional security feature is Office 365 Advanced Threat Protection (ATP), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="2056a-116">Защита ссылок и вложений в электронных письмах.</span><span class="sxs-lookup"><span data-stu-id="2056a-116">Protecting links and attachments in email.</span></span> 
- <span data-ttu-id="2056a-117">Функции анализа подделок и антифишинга для почты в Exchange Online и файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2056a-117">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> 

>[!Note]
><span data-ttu-id="2056a-p101">Функция Office 365 Advanced Threat Protection включена в план E5 в Microsoft 365 корпоративный. Если вы используете план E3 в Microsoft 365 корпоративный, вы можете приобрести отдельные лицензии на Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="2056a-p101">Office 365 ATP is included with Microsoft 365 Enterprise E5. If you have Microsoft 365 Enterprise E3, you can purchase individual licenses for ATP.</span></span>
>

<span data-ttu-id="2056a-120">Сведения о том, как включить Office 365 Advanced Threat Protection, см. в разделе [Включение Office 365 Advanced Threat Protection для SharePoint Online, OneDrive для бизнеса и Microsoft Teams](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span><span class="sxs-lookup"><span data-stu-id="2056a-120">To enable Office 365 ATP, see [Turn it on](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span></span>

<span data-ttu-id="2056a-121">Дополнительные сведения см. в статье [Office 365 ATP для SharePoint, OneDrive и Microsoft Teams](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607).</span><span class="sxs-lookup"><span data-stu-id="2056a-121">For more information, see [Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607).</span></span>


|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="2056a-123">Руководство по лаборатории тестирования: настройка усиленной защиты Office 365</span><span class="sxs-lookup"><span data-stu-id="2056a-123">Test Lab Guide: Configure increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="2056a-124">Прежде чем перейти к следующему шагу, проверьте [условия](infoprotect-exit-criteria.md#crit-infoprotect-step4), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="2056a-124">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="2056a-125">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="2056a-125">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="2056a-126">Настройка управления привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="2056a-126">Configure privileged access management</span></span>](infoprotect-configure-privileged-access-management.md)|


