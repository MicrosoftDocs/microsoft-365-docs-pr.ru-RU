---
title: " Интеграция серверов и управления событиями (SIEM) с помощью служб и приложений Microsoft 365"
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: Обзор сведений о безопасности и службах управления событиями (SIEM) для интеграции с облачными службами и приложениями Microsoft 365
ms.openlocfilehash: b91d45235b61ff6a3c57ec70f3e6a8fee0fd39d2
ms.sourcegitcommit: 237589a0c8a24510e5c8f3b8b4747d944ad0afbf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "38699599"
---
#  <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="402fe-103">Интеграция серверов и управления событиями (SIEM) с помощью служб и приложений Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="402fe-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

## <a name="summary"></a><span data-ttu-id="402fe-104">Сводка</span><span class="sxs-lookup"><span data-stu-id="402fe-104">Summary</span></span>

<span data-ttu-id="402fe-105">Используется ли в организации или планируется получение сведений о безопасности и управления событиями (SIEM)?</span><span class="sxs-lookup"><span data-stu-id="402fe-105">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="402fe-106">Возможно, вы захотите узнать, как она интегрируется с Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="402fe-106">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="402fe-107">В этой статье представлен список ресурсов, которые можно использовать для интеграции сервера SIEM со службами и приложениями Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="402fe-107">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="402fe-108">Если у вас еще нет сервера SIEM и вы изучите свои параметры, рассмотрите **[метку Microsoft Azure](https://docs.microsoft.com/azure/sentinel/overview)**.</span><span class="sxs-lookup"><span data-stu-id="402fe-108">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="402fe-109">Нужен ли сервер SIEM?</span><span class="sxs-lookup"><span data-stu-id="402fe-109">Do I need a SIEM server?</span></span>

<span data-ttu-id="402fe-110">Необходимость использования сервера SIEM зависит от многих факторов, таких как требования к безопасности Организации и место хранения данных.</span><span class="sxs-lookup"><span data-stu-id="402fe-110">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="402fe-111">Microsoft 365 включает разнообразные функции безопасности, которые отвечают многим потребностям Организации, без дополнительных серверов, таких как сервер SIEM.</span><span class="sxs-lookup"><span data-stu-id="402fe-111">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="402fe-112">В некоторых организациях существуют особые обстоятельства, требующие использования сервера SIEM.</span><span class="sxs-lookup"><span data-stu-id="402fe-112">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="402fe-113">Ниже приводятся примеры:</span><span class="sxs-lookup"><span data-stu-id="402fe-113">Here are some examples:</span></span>

- <span data-ttu-id="402fe-114">У *Fabrikam* есть локальное содержимое и приложения, а также некоторые в облаке (у них есть гибридное развертывание в облаке).</span><span class="sxs-lookup"><span data-stu-id="402fe-114">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="402fe-115">Для получения отчетов о безопасности на всем их контенте и приложениях компания Fabrikam реализовала сервер SIEM.</span><span class="sxs-lookup"><span data-stu-id="402fe-115">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span> 

- <span data-ttu-id="402fe-116">*Contoso* — это организация финансовых служб, которая обладает особенно строгими требованиями к безопасности.</span><span class="sxs-lookup"><span data-stu-id="402fe-116">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="402fe-117">Они добавили сервер SIEM в свою среду, чтобы воспользоваться преимуществами дополнительной защиты, которые им необходимы.</span><span class="sxs-lookup"><span data-stu-id="402fe-117">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="402fe-118">Интеграция сервера SIEM с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="402fe-118">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="402fe-119">Сервер SIEM может получать данные из разнообразных служб и приложений Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="402fe-119">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="402fe-120">В приведенной ниже таблице перечислены некоторые приложения и службы Microsoft 365, а также входные данные и ресурсы сервера SIEM для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="402fe-120">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span> 

| <span data-ttu-id="402fe-121">Служба или приложение Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="402fe-121">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="402fe-122">Входные данные и методы сервера SIEM</span><span class="sxs-lookup"><span data-stu-id="402fe-122">SIEM server inputs/methods</span></span> | <span data-ttu-id="402fe-123">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="402fe-123">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="402fe-124">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="402fe-124">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)  | <span data-ttu-id="402fe-125">Журналы аудита</span><span class="sxs-lookup"><span data-stu-id="402fe-125">Audit logs</span></span> | [<span data-ttu-id="402fe-126">Интеграция SIEM с Office 365 Advanced Threat protection</span><span class="sxs-lookup"><span data-stu-id="402fe-126">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="402fe-127">Advanced Threat Protection в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="402fe-127">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="402fe-128">Конечная точка HTTPS, размещенная в Azure</span><span class="sxs-lookup"><span data-stu-id="402fe-128">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="402fe-129">REST API</span><span class="sxs-lookup"><span data-stu-id="402fe-129">REST API</span></span>| [<span data-ttu-id="402fe-130">Получение оповещений о средствах SIEM</span><span class="sxs-lookup"><span data-stu-id="402fe-130">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [<span data-ttu-id="402fe-131">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="402fe-131">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="402fe-132">Интеграция журналов</span><span class="sxs-lookup"><span data-stu-id="402fe-132">Log integration</span></span> | [<span data-ttu-id="402fe-133">Интеграция SIEM с Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="402fe-133">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> <span data-ttu-id="402fe-134">Рассмотрим [метку Azure](https://docs.microsoft.com/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="402fe-134">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="402fe-135">В составе Azure Sentinel имеются соединители для решений Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="402fe-135">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="402fe-136">Эти соединители доступны "из поля" и обеспечивают интеграцию в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="402fe-136">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="402fe-137">Вы можете использовать метку Azure с решениями для защиты от угроз Майкрософт и службами Microsoft 365, в том числе Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security и т. д.</span><span class="sxs-lookup"><span data-stu-id="402fe-137">You can use Azure Sentinel with your Microsoft Threat Protection solutions and Microsoft 365 services, including Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="402fe-138">Необходимо включить ведение журнала аудита</span><span class="sxs-lookup"><span data-stu-id="402fe-138">Audit logging must be turned on</span></span>

<span data-ttu-id="402fe-139">Перед настройкой интеграции сервера SIEM убедитесь, что ведение журнала аудита включено.</span><span class="sxs-lookup"><span data-stu-id="402fe-139">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="402fe-140">Для SharePoint Online, OneDrive для бизнеса и Azure Active Directory [ведение журнала аудита включено в центре безопасности & соответствия требованиям](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="402fe-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="402fe-141">Для Exchange Online [ведение журнала аудита включено с помощью Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span><span class="sxs-lookup"><span data-stu-id="402fe-141">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="more-resources"></a><span data-ttu-id="402fe-142">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="402fe-142">More resources</span></span>

[<span data-ttu-id="402fe-143">Интеграция решений безопасности в центре безопасности Azure</span><span class="sxs-lookup"><span data-stu-id="402fe-143">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="402fe-144">Интеграция оповещений API безопасности Microsoft Graph с SIEM</span><span class="sxs-lookup"><span data-stu-id="402fe-144">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)