---
title: Интеграция сервера SIEM со службами и приложениями Microsoft 365
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/15/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: В этой статье приводятся общие сведения о интеграции сервера SIEM с Microsoft 365.
ms.openlocfilehash: bea6141022fef1275a7e291217f698f52613f170
ms.sourcegitcommit: d8d001c03c28c10bea005d1c9b5f4a8f393af706
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "38677512"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="7f06a-103">Интеграция сервера SIEM со службами и приложениями Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7f06a-103">SIEM server integration with Microsoft 365 services and applications</span></span>

## <a name="summary"></a><span data-ttu-id="7f06a-104">Описание</span><span class="sxs-lookup"><span data-stu-id="7f06a-104">Summary</span></span>

<span data-ttu-id="7f06a-105">Если в Организации используются сведения о безопасности и сервер управления событиями (SIEM) или если вы планируете немедленно получить сервер SIEM, вам может быть интересно узнать, как интегрироваться с Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="7f06a-105">If your organization is using a Security Information and Event Management (SIEM) server, or if you are planning to get a SIEM server soon, you might be wondering how that'll integrate with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="7f06a-106">В этой статье представлен список ресурсов, которые можно использовать для настройки интеграции сервера SIEM с службами и приложениями Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7f06a-106">This article provides a list of resources you can use to set up SIEM server integration with your Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="7f06a-107">Если у вас еще нет сервера SIEM и вы изучите свои параметры, рассмотрите **[метку Microsoft Azure](https://docs.microsoft.com/azure/sentinel/overview)**.</span><span class="sxs-lookup"><span data-stu-id="7f06a-107">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="7f06a-108">Нужен ли сервер SIEM?</span><span class="sxs-lookup"><span data-stu-id="7f06a-108">Do I need a SIEM server?</span></span>

<span data-ttu-id="7f06a-109">Необходимость использования сервера SIEM зависит от многих факторов, таких как требования к безопасности Организации и место хранения данных.</span><span class="sxs-lookup"><span data-stu-id="7f06a-109">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="7f06a-110">Microsoft 365 включает разнообразные функции безопасности, которые отвечают многим потребностям Организации, без дополнительных серверов, таких как сервер SIEM.</span><span class="sxs-lookup"><span data-stu-id="7f06a-110">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="7f06a-111">В некоторых организациях существуют особые обстоятельства, требующие использования сервера SIEM.</span><span class="sxs-lookup"><span data-stu-id="7f06a-111">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="7f06a-112">Ниже приводятся примеры:</span><span class="sxs-lookup"><span data-stu-id="7f06a-112">Here are some examples:</span></span>

- <span data-ttu-id="7f06a-113">У *Fabrikam* есть локальное содержимое и приложения, а также некоторые в облаке (у них есть гибридное развертывание в облаке).</span><span class="sxs-lookup"><span data-stu-id="7f06a-113">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="7f06a-114">Для получения отчетов о безопасности на всем их контенте и приложениях компания Fabrikam реализовала сервер SIEM.</span><span class="sxs-lookup"><span data-stu-id="7f06a-114">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span> 

- <span data-ttu-id="7f06a-115">*Contoso* — это организация финансовых служб, которая обладает особенно строгими требованиями к безопасности.</span><span class="sxs-lookup"><span data-stu-id="7f06a-115">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="7f06a-116">Они добавили сервер SIEM в свою среду, чтобы воспользоваться преимуществами дополнительной защиты, которые им необходимы.</span><span class="sxs-lookup"><span data-stu-id="7f06a-116">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="7f06a-117">Интеграция сервера SIEM с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7f06a-117">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="7f06a-118">Сервер SIEM может получать данные из разнообразных служб и приложений Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7f06a-118">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="7f06a-119">В следующей таблице приведены некоторые приложения и службы Microsoft 365, а также входные данные сервера SIEM, а также ресурсы для получения дополнительных сведений о интеграции сервера SIEM.</span><span class="sxs-lookup"><span data-stu-id="7f06a-119">The following table lists several Microsoft 365 services and applications along with SIEM server inputs, and resources to learn more about SIEM server integration.</span></span> 

| <span data-ttu-id="7f06a-120">Служба или приложение Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7f06a-120">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="7f06a-121">Входные данные сервера SIEM</span><span class="sxs-lookup"><span data-stu-id="7f06a-121">SIEM server inputs</span></span> | <span data-ttu-id="7f06a-122">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="7f06a-122">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="7f06a-123">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7f06a-123">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)  | <span data-ttu-id="7f06a-124">Журналы аудита</span><span class="sxs-lookup"><span data-stu-id="7f06a-124">Audit logs</span></span> | [<span data-ttu-id="7f06a-125">Интеграция SIEM с Office 365 Advanced Threat protection</span><span class="sxs-lookup"><span data-stu-id="7f06a-125">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="7f06a-126">Advanced Threat Protection в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7f06a-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="7f06a-127">Конечная точка HTTPS, размещенная в Azure</span><span class="sxs-lookup"><span data-stu-id="7f06a-127">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="7f06a-128">REST API</span><span class="sxs-lookup"><span data-stu-id="7f06a-128">REST API</span></span>| [<span data-ttu-id="7f06a-129">Получение оповещений о средствах SIEM</span><span class="sxs-lookup"><span data-stu-id="7f06a-129">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [<span data-ttu-id="7f06a-130">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7f06a-130">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="7f06a-131">Интеграция журналов</span><span class="sxs-lookup"><span data-stu-id="7f06a-131">Log integration</span></span> | [<span data-ttu-id="7f06a-132">Интеграция SIEM с Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7f06a-132">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> <span data-ttu-id="7f06a-133">Взгляните на [метку Azure](https://docs.microsoft.com/azure/sentinel/overview), которая поставляется с несколькими соединителями для решений Майкрософт, которые доступны в режиме реального времени и предоставляют интеграцию в режиме реального времени, в том числе решения Майкрософт для защиты от угроз и источники Microsoft 365, в том числе Office 365, Azure AD, Azure ATP и Microsoft Cloud App Security и многое другое.</span><span class="sxs-lookup"><span data-stu-id="7f06a-133">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview), which comes with a number of connectors for Microsoft solutions, available out of the box and providing real-time integration, including Microsoft Threat Protection solutions, and Microsoft 365 sources, including Office 365, Azure AD, Azure ATP, and Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="7f06a-134">Необходимо включить ведение журнала аудита</span><span class="sxs-lookup"><span data-stu-id="7f06a-134">Audit logging must be turned on</span></span>

<span data-ttu-id="7f06a-135">Перед настройкой интеграции сервера SIEM убедитесь, что ведение журнала аудита включено.</span><span class="sxs-lookup"><span data-stu-id="7f06a-135">Make sure audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="7f06a-136">Для SharePoint Online, OneDrive для бизнеса и Azure Active Directory [ведение журнала аудита включено в центре безопасности & соответствия требованиям](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="7f06a-136">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="7f06a-137">Для Exchange Online [ведение журнала аудита включено с помощью Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span><span class="sxs-lookup"><span data-stu-id="7f06a-137">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="additional-resources"></a><span data-ttu-id="7f06a-138">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="7f06a-138">Additional resources</span></span>

[<span data-ttu-id="7f06a-139">Интеграция решений безопасности в центре безопасности Azure</span><span class="sxs-lookup"><span data-stu-id="7f06a-139">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="7f06a-140">Интеграция оповещений API безопасности Microsoft Graph с SIEM</span><span class="sxs-lookup"><span data-stu-id="7f06a-140">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)