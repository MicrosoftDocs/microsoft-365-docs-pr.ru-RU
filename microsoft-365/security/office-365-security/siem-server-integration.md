---
title: Интеграция сервера SIEM со службами и приложениями Microsoft 365
f1.keywords:
- NOCSH
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
- seo-marvel-apr2020
description: Обзор сведений о безопасности и службах управления событиями (SIEM) для интеграции с облачными службами и приложениями Microsoft 365
ms.openlocfilehash: 6d657990417cab2a8cbb1b03b8b79a65c095d1a5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202213"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="ad39a-103">Интеграция серверов и управления событиями (SIEM) с помощью служб и приложений Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad39a-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="summary"></a><span data-ttu-id="ad39a-104">Аннотация</span><span class="sxs-lookup"><span data-stu-id="ad39a-104">Summary</span></span>

<span data-ttu-id="ad39a-105">Используется ли в организации или планируется получение сведений о безопасности и управления событиями (SIEM)?</span><span class="sxs-lookup"><span data-stu-id="ad39a-105">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="ad39a-106">Возможно, вы захотите узнать, как она интегрируется с Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="ad39a-106">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="ad39a-107">В этой статье представлен список ресурсов, которые можно использовать для интеграции сервера SIEM со службами и приложениями Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ad39a-107">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="ad39a-108">Если у вас еще нет сервера SIEM и вы изучите свои параметры, рассмотрите **[метку Microsoft Azure](https://docs.microsoft.com/azure/sentinel/overview)**.</span><span class="sxs-lookup"><span data-stu-id="ad39a-108">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="ad39a-109">Нужен ли сервер SIEM?</span><span class="sxs-lookup"><span data-stu-id="ad39a-109">Do I need a SIEM server?</span></span>

<span data-ttu-id="ad39a-110">Необходимость использования сервера SIEM зависит от многих факторов, таких как требования к безопасности Организации и место хранения данных.</span><span class="sxs-lookup"><span data-stu-id="ad39a-110">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="ad39a-111">Microsoft 365 включает разнообразные функции безопасности, которые отвечают многим потребностям Организации, без дополнительных серверов, таких как сервер SIEM.</span><span class="sxs-lookup"><span data-stu-id="ad39a-111">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="ad39a-112">В некоторых организациях существуют особые обстоятельства, требующие использования сервера SIEM.</span><span class="sxs-lookup"><span data-stu-id="ad39a-112">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="ad39a-113">Ниже приводятся примеры:</span><span class="sxs-lookup"><span data-stu-id="ad39a-113">Here are some examples:</span></span>

- <span data-ttu-id="ad39a-114">У *Fabrikam* есть локальное содержимое и приложения, а также некоторые в облаке (у них есть гибридное развертывание в облаке).</span><span class="sxs-lookup"><span data-stu-id="ad39a-114">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="ad39a-115">Для получения отчетов о безопасности на всем их контенте и приложениях компания Fabrikam реализовала сервер SIEM.</span><span class="sxs-lookup"><span data-stu-id="ad39a-115">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="ad39a-116">*Contoso* — это организация финансовых служб, которая обладает особенно строгими требованиями к безопасности.</span><span class="sxs-lookup"><span data-stu-id="ad39a-116">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="ad39a-117">Они добавили сервер SIEM в свою среду, чтобы воспользоваться преимуществами дополнительной защиты, которые им необходимы.</span><span class="sxs-lookup"><span data-stu-id="ad39a-117">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="ad39a-118">Интеграция сервера SIEM с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad39a-118">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="ad39a-119">Сервер SIEM может получать данные из разнообразных служб и приложений Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ad39a-119">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="ad39a-120">В приведенной ниже таблице перечислены некоторые приложения и службы Microsoft 365, а также входные данные и ресурсы сервера SIEM для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="ad39a-120">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="ad39a-121">Служба или приложение Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad39a-121">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="ad39a-122">Входные данные и методы сервера SIEM</span><span class="sxs-lookup"><span data-stu-id="ad39a-122">SIEM server inputs/methods</span></span>|<span data-ttu-id="ad39a-123">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ad39a-123">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="ad39a-124">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ad39a-124">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)|<span data-ttu-id="ad39a-125">Журналы аудита</span><span class="sxs-lookup"><span data-stu-id="ad39a-125">Audit logs</span></span>|[<span data-ttu-id="ad39a-126">Интеграция SIEM с Office 365 Advanced Threat protection</span><span class="sxs-lookup"><span data-stu-id="ad39a-126">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="ad39a-127">Advanced Threat Protection в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ad39a-127">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="ad39a-128">Конечная точка HTTPS, размещенная в Azure</span><span class="sxs-lookup"><span data-stu-id="ad39a-128">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="ad39a-129">REST API</span><span class="sxs-lookup"><span data-stu-id="ad39a-129">REST API</span></span>|[<span data-ttu-id="ad39a-130">Получение оповещений о средствах SIEM</span><span class="sxs-lookup"><span data-stu-id="ad39a-130">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="ad39a-131">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ad39a-131">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="ad39a-132">Интеграция журналов</span><span class="sxs-lookup"><span data-stu-id="ad39a-132">Log integration</span></span>|[<span data-ttu-id="ad39a-133">Интеграция SIEM с Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ad39a-133">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="ad39a-134">Рассмотрим [метку Azure](https://docs.microsoft.com/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="ad39a-134">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="ad39a-135">В составе Azure Sentinel имеются соединители для решений Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ad39a-135">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="ad39a-136">Эти соединители доступны "из поля" и обеспечивают интеграцию в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="ad39a-136">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="ad39a-137">Вы можете использовать метку Azure с решениями для защиты от угроз Майкрософт и службами Microsoft 365, в том числе Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security и т. д.</span><span class="sxs-lookup"><span data-stu-id="ad39a-137">You can use Azure Sentinel with your Microsoft Threat Protection solutions and Microsoft 365 services, including Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="ad39a-138">Необходимо включить ведение журнала аудита</span><span class="sxs-lookup"><span data-stu-id="ad39a-138">Audit logging must be turned on</span></span>

<span data-ttu-id="ad39a-139">Перед настройкой интеграции сервера SIEM убедитесь, что ведение журнала аудита включено.</span><span class="sxs-lookup"><span data-stu-id="ad39a-139">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="ad39a-140">Для SharePoint Online, OneDrive для бизнеса и Azure Active Directory [ведение журнала аудита включено в центре безопасности & соответствия требованиям](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="ad39a-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="ad39a-141">В разделе [Управление аудитом почтовых ящиков](../../compliance/enable-mailbox-auditing.md)в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ad39a-141">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="ad39a-142">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ad39a-142">More resources</span></span>

[<span data-ttu-id="ad39a-143">Интеграция решений безопасности в центре безопасности Azure</span><span class="sxs-lookup"><span data-stu-id="ad39a-143">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="ad39a-144">Интеграция оповещений API безопасности Microsoft Graph с SIEM</span><span class="sxs-lookup"><span data-stu-id="ad39a-144">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
