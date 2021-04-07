---
title: Интеграция серверов SIEM с службами и приложениями Microsoft 365
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
description: Получение обзора интеграции серверов служб безопасности и управления событиями (SIEM) с облачными службами и приложениями Microsoft 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bea8aa3914da4b813f3928eddbb6df9c98ef6605
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599951"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="41973-103">Интеграция серверов системы безопасности и управления событиями (SIEM) с службами и приложениями Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="41973-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

<span data-ttu-id="41973-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="41973-104">**Applies to**</span></span>
- [<span data-ttu-id="41973-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="41973-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="41973-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="41973-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="41973-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41973-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a><span data-ttu-id="41973-108">Сводка</span><span class="sxs-lookup"><span data-stu-id="41973-108">Summary</span></span>

<span data-ttu-id="41973-109">Использует ли ваша организация или планирует получить сервер управления сведениями о безопасности и событиями (SIEM)?</span><span class="sxs-lookup"><span data-stu-id="41973-109">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="41973-110">Возможно, вам будет интересно, как она интегрируется с Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="41973-110">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="41973-111">В этой статье приводится список ресурсов, которые можно использовать для интеграции сервера SIEM с службами и приложениями Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41973-111">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="41973-112">Если у вас еще нет сервера SIEM и вы изучаете варианты, рассмотрите **[Microsoft Azure Sentinel.](/azure/sentinel/overview)**</span><span class="sxs-lookup"><span data-stu-id="41973-112">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="41973-113">Нужен ли мне siEM-сервер?</span><span class="sxs-lookup"><span data-stu-id="41973-113">Do I need a SIEM server?</span></span>

<span data-ttu-id="41973-114">Потребность в siEM-сервере зависит от многих факторов, таких как требования к безопасности организации и место хранения данных.</span><span class="sxs-lookup"><span data-stu-id="41973-114">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="41973-115">Microsoft 365 включает широкий спектр функций безопасности, которые отвечают требованиям безопасности многих организаций без дополнительных серверов, таких как сервер SIEM.</span><span class="sxs-lookup"><span data-stu-id="41973-115">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="41973-116">В некоторых организациях имеются особые условия, которые требуют использования сервера SIEM.</span><span class="sxs-lookup"><span data-stu-id="41973-116">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="41973-117">Ниже приводятся примеры:</span><span class="sxs-lookup"><span data-stu-id="41973-117">Here are some examples:</span></span>

- <span data-ttu-id="41973-118">*Fabrikam* имеет некоторое содержимое и приложения на месте, а некоторые в облаке (они имеют гибридное развертывание облака).</span><span class="sxs-lookup"><span data-stu-id="41973-118">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="41973-119">Чтобы получить отчеты о безопасности во всем их контенте и приложениях, Fabrikam реализовал сервер SIEM.</span><span class="sxs-lookup"><span data-stu-id="41973-119">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="41973-120">*Contoso* — это организация финансовых служб, которая предъявляет особо строгие требования к безопасности.</span><span class="sxs-lookup"><span data-stu-id="41973-120">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="41973-121">Они добавили сервер SIEM в свою среду, чтобы воспользоваться необходимой дополнительной защитой безопасности.</span><span class="sxs-lookup"><span data-stu-id="41973-121">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="41973-122">Интеграция серверов SIEM с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="41973-122">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="41973-123">Сервер SIEM может получать данные из широкого спектра служб и приложений Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41973-123">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="41973-124">В следующей таблице перечислены несколько служб и приложений Microsoft 365, а также входные данные и ресурсы сервера SIEM, чтобы узнать больше.</span><span class="sxs-lookup"><span data-stu-id="41973-124">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="41973-125">Служба Или приложение Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="41973-125">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="41973-126">Входные данные и методы сервера SIEM</span><span class="sxs-lookup"><span data-stu-id="41973-126">SIEM server inputs/methods</span></span>|<span data-ttu-id="41973-127">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="41973-127">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="41973-128">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="41973-128">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)|<span data-ttu-id="41973-129">Журналы аудита</span><span class="sxs-lookup"><span data-stu-id="41973-129">Audit logs</span></span>|[<span data-ttu-id="41973-130">Интеграция SIEM с Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="41973-130">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="41973-131">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="41973-131">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)|<span data-ttu-id="41973-132">Конечная точка HTTPS, организованная в Azure</span><span class="sxs-lookup"><span data-stu-id="41973-132">HTTPS endpoint hosted in Azure</span></span> <p> <span data-ttu-id="41973-133">REST API</span><span class="sxs-lookup"><span data-stu-id="41973-133">REST API</span></span>|[<span data-ttu-id="41973-134">Вытащать оповещения в инструменты SIEM</span><span class="sxs-lookup"><span data-stu-id="41973-134">Pull alerts to your SIEM tools</span></span>](../defender-endpoint/configure-siem.md)|
|[<span data-ttu-id="41973-135">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="41973-135">Microsoft Cloud App Security</span></span>](/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="41973-136">Интеграция журнала</span><span class="sxs-lookup"><span data-stu-id="41973-136">Log integration</span></span>|[<span data-ttu-id="41973-137">Интеграция SIEM с безопасностью облачных приложений Майкрософт</span><span class="sxs-lookup"><span data-stu-id="41973-137">SIEM integration with Microsoft Cloud App Security</span></span>](/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="41973-138">Взгляните на [Azure Sentinel](/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="41973-138">Take a look at [Azure Sentinel](/azure/sentinel/overview).</span></span> <span data-ttu-id="41973-139">Azure Sentinel поставляется с соединителями для решений Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="41973-139">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="41973-140">Эти соединители доступны "из окна" и обеспечивают интеграцию в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="41973-140">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="41973-141">Вы можете использовать Azure Sentinel с решениями Microsoft 365 Defender и службами Microsoft 365, включая Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security и другие.</span><span class="sxs-lookup"><span data-stu-id="41973-141">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="41973-142">Необходимо включить журнал аудита</span><span class="sxs-lookup"><span data-stu-id="41973-142">Audit logging must be turned on</span></span>

<span data-ttu-id="41973-143">Убедитесь, что журнал аудита включен перед настройкой интеграции серверов SIEM.</span><span class="sxs-lookup"><span data-stu-id="41973-143">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="41973-144">Для SharePoint Online, OneDrive для бизнеса и Azure Active Directory журнал аудита включен в Центре & [безопасности.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="41973-144">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="41973-145">Для Exchange Online см. [в рублях Управление аудитом почтовых ящиков.](../../compliance/enable-mailbox-auditing.md)</span><span class="sxs-lookup"><span data-stu-id="41973-145">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="41973-146">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="41973-146">More resources</span></span>

[<span data-ttu-id="41973-147">Интеграция решений безопасности в Azure Defender</span><span class="sxs-lookup"><span data-stu-id="41973-147">Integrate security solutions in Azure Defender</span></span>](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="41973-148">Интеграция оповещений API безопасности Microsoft Graph с SIEM</span><span class="sxs-lookup"><span data-stu-id="41973-148">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](/graph/security-integration)