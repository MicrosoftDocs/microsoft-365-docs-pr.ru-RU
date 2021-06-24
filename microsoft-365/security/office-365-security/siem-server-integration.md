---
title: Интеграция сервера SIEM с Microsoft 365 службами и приложениями
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
description: Получение обзора интеграции серверов служб безопасности и управления событиями (SIEM) с Microsoft 365 облачными службами и приложениями
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ea4d844595aaab8d8148666430187edef463b92e
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105600"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="eef98-103">Интеграция серверов с данными о безопасности и управление событиями (SIEM) с Microsoft 365 службами и приложениями</span><span class="sxs-lookup"><span data-stu-id="eef98-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

<span data-ttu-id="eef98-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="eef98-104">**Applies to**</span></span>
- [<span data-ttu-id="eef98-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="eef98-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="eef98-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="eef98-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="eef98-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eef98-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a><span data-ttu-id="eef98-108">Сводка</span><span class="sxs-lookup"><span data-stu-id="eef98-108">Summary</span></span>

<span data-ttu-id="eef98-109">Использует ли ваша организация или планирует получить сервер управления сведениями о безопасности и событиями (SIEM)?</span><span class="sxs-lookup"><span data-stu-id="eef98-109">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="eef98-110">Возможно, вам будет интересно, как она интегрируется с Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="eef98-110">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="eef98-111">В этой статье приводится список ресурсов, которые можно использовать для интеграции сервера SIEM с Microsoft 365 службами и приложениями.</span><span class="sxs-lookup"><span data-stu-id="eef98-111">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="eef98-112">Если у вас еще нет сервера SIEM и вы изучаете параметры, Microsoft Azure **[Sentinel](/azure/sentinel/overview)**.</span><span class="sxs-lookup"><span data-stu-id="eef98-112">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="eef98-113">Нужен ли мне siEM-сервер?</span><span class="sxs-lookup"><span data-stu-id="eef98-113">Do I need a SIEM server?</span></span>

<span data-ttu-id="eef98-114">Потребность в siEM-сервере зависит от многих факторов, таких как требования к безопасности организации и место хранения данных.</span><span class="sxs-lookup"><span data-stu-id="eef98-114">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="eef98-115">Microsoft 365 включает широкий спектр функций безопасности, которые отвечают требованиям безопасности многих организаций без дополнительных серверов, таких как сервер SIEM.</span><span class="sxs-lookup"><span data-stu-id="eef98-115">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="eef98-116">В некоторых организациях имеются особые условия, которые требуют использования сервера SIEM.</span><span class="sxs-lookup"><span data-stu-id="eef98-116">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="eef98-117">Ниже приводятся примеры:</span><span class="sxs-lookup"><span data-stu-id="eef98-117">Here are some examples:</span></span>

- <span data-ttu-id="eef98-118">*Fabrikam* имеет некоторое содержимое и приложения на месте, а некоторые в облаке (они имеют гибридное развертывание облака).</span><span class="sxs-lookup"><span data-stu-id="eef98-118">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="eef98-119">Чтобы получить отчеты о безопасности во всем их контенте и приложениях, Fabrikam реализовал сервер SIEM.</span><span class="sxs-lookup"><span data-stu-id="eef98-119">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>
- <span data-ttu-id="eef98-120">*Contoso* — это организация финансовых служб, которая предъявляет особо строгие требования к безопасности.</span><span class="sxs-lookup"><span data-stu-id="eef98-120">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="eef98-121">Они добавили сервер SIEM в свою среду, чтобы воспользоваться необходимой дополнительной защитой безопасности.</span><span class="sxs-lookup"><span data-stu-id="eef98-121">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="eef98-122">Интеграция сервера SIEM с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eef98-122">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="eef98-123">Сервер SIEM может получать данные из различных Microsoft 365 и приложений.</span><span class="sxs-lookup"><span data-stu-id="eef98-123">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="eef98-124">В следующей таблице перечислены несколько Microsoft 365 и приложений, а также входные данные и ресурсы сервера SIEM, чтобы узнать больше.</span><span class="sxs-lookup"><span data-stu-id="eef98-124">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

<br>

****

|<span data-ttu-id="eef98-125">Microsoft 365 Служба или приложение</span><span class="sxs-lookup"><span data-stu-id="eef98-125">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="eef98-126">Входные данные и методы сервера SIEM</span><span class="sxs-lookup"><span data-stu-id="eef98-126">SIEM server inputs/methods</span></span>|<span data-ttu-id="eef98-127">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="eef98-127">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="eef98-128">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="eef98-128">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)|<span data-ttu-id="eef98-129">Журналы аудита</span><span class="sxs-lookup"><span data-stu-id="eef98-129">Audit logs</span></span>|[<span data-ttu-id="eef98-130">Интеграция SIEM с Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="eef98-130">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="eef98-131">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="eef98-131">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)|<span data-ttu-id="eef98-132">Конечная точка HTTPS, организованная в Azure</span><span class="sxs-lookup"><span data-stu-id="eef98-132">HTTPS endpoint hosted in Azure</span></span> <p> <span data-ttu-id="eef98-133">REST API</span><span class="sxs-lookup"><span data-stu-id="eef98-133">REST API</span></span>|[<span data-ttu-id="eef98-134">Вытащать оповещения в инструменты SIEM</span><span class="sxs-lookup"><span data-stu-id="eef98-134">Pull alerts to your SIEM tools</span></span>](../defender-endpoint/configure-siem.md)|
|[<span data-ttu-id="eef98-135">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="eef98-135">Microsoft Cloud App Security</span></span>](/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="eef98-136">Интеграция журнала</span><span class="sxs-lookup"><span data-stu-id="eef98-136">Log integration</span></span>|[<span data-ttu-id="eef98-137">Интеграция SIEM с Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="eef98-137">SIEM integration with Microsoft Cloud App Security</span></span>](/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="eef98-138">Взгляните на [Azure Sentinel](/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="eef98-138">Take a look at [Azure Sentinel](/azure/sentinel/overview).</span></span> <span data-ttu-id="eef98-139">Azure Sentinel поставляется с соединителями для решений Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="eef98-139">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="eef98-140">Эти соединители доступны "из окна" и обеспечивают интеграцию в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="eef98-140">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="eef98-141">Вы можете использовать Azure Sentinel с Microsoft 365 Defender решениями и Microsoft 365 службами, включая Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security и другие.</span><span class="sxs-lookup"><span data-stu-id="eef98-141">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="eef98-142">Необходимо включить журнал аудита</span><span class="sxs-lookup"><span data-stu-id="eef98-142">Audit logging must be turned on</span></span>

<span data-ttu-id="eef98-143">Убедитесь, что журнал аудита включен перед настройкой интеграции серверов SIEM.</span><span class="sxs-lookup"><span data-stu-id="eef98-143">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="eef98-144">Для SharePoint Online, OneDrive для бизнеса и Azure Active Directory см. в включите аудит или [отключение.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="eef98-144">For SharePoint Online, OneDrive for Business, and Azure Active Directory, see [Turn auditing on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>
- <span data-ttu-id="eef98-145">Для Exchange Online см. в этой Exchange Online [Управление аудитом почтовых ящиков.](../../compliance/enable-mailbox-auditing.md)</span><span class="sxs-lookup"><span data-stu-id="eef98-145">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="eef98-146">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="eef98-146">More resources</span></span>

[<span data-ttu-id="eef98-147">Интеграция решений безопасности в Azure Defender</span><span class="sxs-lookup"><span data-stu-id="eef98-147">Integrate security solutions in Azure Defender</span></span>](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="eef98-148">Интеграция оповещений API безопасности Microsoft Graph с SIEM</span><span class="sxs-lookup"><span data-stu-id="eef98-148">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](/graph/security-integration)
