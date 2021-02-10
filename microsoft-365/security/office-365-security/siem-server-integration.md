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
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Обзор интеграции сервера SIEM с облачными службами и приложениями Microsoft 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f29da87aa6eab1852330092d93187a27b2d36eb2
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167147"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="ad425-103">Интеграция сервера SIEM со службами и приложениями Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad425-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

<span data-ttu-id="ad425-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="ad425-104">**Applies to**</span></span>
- [<span data-ttu-id="ad425-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ad425-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="ad425-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="ad425-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="ad425-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad425-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a><span data-ttu-id="ad425-108">Аннотация</span><span class="sxs-lookup"><span data-stu-id="ad425-108">Summary</span></span>

<span data-ttu-id="ad425-109">Использует ли ваша организация или планирует получить сервер SIEM?</span><span class="sxs-lookup"><span data-stu-id="ad425-109">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="ad425-110">Вам может быть интересно, как она интегрируется с Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="ad425-110">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="ad425-111">В этой статье приводится список ресурсов, которые можно использовать для интеграции сервера SIEM со службами и приложениями Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ad425-111">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="ad425-112">Если у вас еще нет сервера SIEM и вы изучаете варианты, рассмотрите **[возможность Microsoft Azure Sentinel.](https://docs.microsoft.com/azure/sentinel/overview)**</span><span class="sxs-lookup"><span data-stu-id="ad425-112">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="ad425-113">Нужен ли мне сервер SIEM?</span><span class="sxs-lookup"><span data-stu-id="ad425-113">Do I need a SIEM server?</span></span>

<span data-ttu-id="ad425-114">Необходимость сервера SIEM зависит от многих факторов, таких как требования организации к безопасности и место хранения данных.</span><span class="sxs-lookup"><span data-stu-id="ad425-114">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="ad425-115">Microsoft 365 включает широкий спектр функций безопасности, которые отвечают требованиям безопасности многих организаций без дополнительных серверов, таких как сервер SIEM.</span><span class="sxs-lookup"><span data-stu-id="ad425-115">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="ad425-116">В некоторых организациях имеются особые условия, которые требуют использования сервера SIEM.</span><span class="sxs-lookup"><span data-stu-id="ad425-116">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="ad425-117">Ниже приводятся примеры:</span><span class="sxs-lookup"><span data-stu-id="ad425-117">Here are some examples:</span></span>

- <span data-ttu-id="ad425-118">*У Fabrikam* есть некоторое содержимое и приложения локально, а некоторые — в облаке (они имеют гибридное облачное развертывание).</span><span class="sxs-lookup"><span data-stu-id="ad425-118">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="ad425-119">Чтобы получить отчеты о безопасности для всего контента и приложений, fabrikam реализовал сервер SIEM.</span><span class="sxs-lookup"><span data-stu-id="ad425-119">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="ad425-120">*Contoso* — это организация с финансовыми услугами, которая предъявляет особо строгие требования к безопасности.</span><span class="sxs-lookup"><span data-stu-id="ad425-120">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="ad425-121">Они добавили сервер SIEM в свою среду, чтобы воспользоваться дополнительной защитой безопасности.</span><span class="sxs-lookup"><span data-stu-id="ad425-121">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="ad425-122">Интеграция сервера SIEM с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad425-122">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="ad425-123">Сервер SIEM может получать данные из множества служб и приложений Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ad425-123">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="ad425-124">В следующей таблице перечислены несколько служб и приложений Microsoft 365, а также входные данные сервера SIEM и ресурсы для получения дополнительных данных.</span><span class="sxs-lookup"><span data-stu-id="ad425-124">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="ad425-125">Служба или приложение Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad425-125">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="ad425-126">Входные данные и методы сервера SIEM</span><span class="sxs-lookup"><span data-stu-id="ad425-126">SIEM server inputs/methods</span></span>|<span data-ttu-id="ad425-127">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ad425-127">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="ad425-128">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="ad425-128">Microsoft Defender for Office 365</span></span>](office-365-atp.md)|<span data-ttu-id="ad425-129">Журналы аудита</span><span class="sxs-lookup"><span data-stu-id="ad425-129">Audit logs</span></span>|[<span data-ttu-id="ad425-130">Интеграция SIEM с Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="ad425-130">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="ad425-131">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ad425-131">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="ad425-132">Конечная точка HTTPS, которая была в Azure</span><span class="sxs-lookup"><span data-stu-id="ad425-132">HTTPS endpoint hosted in Azure</span></span> <p> <span data-ttu-id="ad425-133">REST API</span><span class="sxs-lookup"><span data-stu-id="ad425-133">REST API</span></span>|[<span data-ttu-id="ad425-134">Вытягивать оповещения в средства SIEM</span><span class="sxs-lookup"><span data-stu-id="ad425-134">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="ad425-135">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ad425-135">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="ad425-136">Интеграция журналов</span><span class="sxs-lookup"><span data-stu-id="ad425-136">Log integration</span></span>|[<span data-ttu-id="ad425-137">Интеграция SIEM с Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ad425-137">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="ad425-138">Посмотрите на [Azure Sentinel.](https://docs.microsoft.com/azure/sentinel/overview)</span><span class="sxs-lookup"><span data-stu-id="ad425-138">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="ad425-139">Azure Sentinel поставляется с соединителями для решений Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ad425-139">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="ad425-140">Эти соединители доступны "из коробки" и обеспечивают интеграцию в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="ad425-140">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="ad425-141">Azure Sentinel можно использовать с решениями Microsoft 365 Defender и службами Microsoft 365, включая Office 365, Azure AD, Microsoft Defender для удостоверений, Microsoft Cloud App Security и т. д.</span><span class="sxs-lookup"><span data-stu-id="ad425-141">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="ad425-142">Ведение журнала аудита должно быть включено</span><span class="sxs-lookup"><span data-stu-id="ad425-142">Audit logging must be turned on</span></span>

<span data-ttu-id="ad425-143">Перед настройкой интеграции сервера SIEM убедитесь, что ведение журнала аудита включено.</span><span class="sxs-lookup"><span data-stu-id="ad425-143">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="ad425-144">Для SharePoint Online, OneDrive для бизнеса и Azure Active Directory ведение журнала аудита включено в Центре безопасности [& соответствия требованиям.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="ad425-144">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="ad425-145">Для Exchange Online см. ["Управление аудитом почтовых ящиков".](../../compliance/enable-mailbox-auditing.md)</span><span class="sxs-lookup"><span data-stu-id="ad425-145">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="ad425-146">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="ad425-146">More resources</span></span>

[<span data-ttu-id="ad425-147">Интеграция решений безопасности в Защитнике Azure</span><span class="sxs-lookup"><span data-stu-id="ad425-147">Integrate security solutions in Azure Defender</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="ad425-148">Интеграция оповещений API безопасности Microsoft Graph с SIEM</span><span class="sxs-lookup"><span data-stu-id="ad425-148">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
