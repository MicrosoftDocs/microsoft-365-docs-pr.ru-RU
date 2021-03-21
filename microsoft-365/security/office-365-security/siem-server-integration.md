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
ms.openlocfilehash: 21aaad71f40a01a3bea2f9535d1c3256ae667bae
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916590"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="def1c-103">Интеграция серверов системы безопасности и управления событиями (SIEM) с службами и приложениями Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="def1c-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

<span data-ttu-id="def1c-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="def1c-104">**Applies to**</span></span>
- [<span data-ttu-id="def1c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="def1c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="def1c-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="def1c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="def1c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="def1c-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a><span data-ttu-id="def1c-108">Аннотация</span><span class="sxs-lookup"><span data-stu-id="def1c-108">Summary</span></span>

<span data-ttu-id="def1c-109">Использует ли ваша организация или планирует получить сервер управления сведениями о безопасности и событиями (SIEM)?</span><span class="sxs-lookup"><span data-stu-id="def1c-109">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="def1c-110">Возможно, вам будет интересно, как она интегрируется с Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="def1c-110">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="def1c-111">В этой статье приводится список ресурсов, которые можно использовать для интеграции сервера SIEM с службами и приложениями Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="def1c-111">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="def1c-112">Если у вас еще нет сервера SIEM и вы изучаете варианты, рассмотрите **[Microsoft Azure Sentinel.](/azure/sentinel/overview)**</span><span class="sxs-lookup"><span data-stu-id="def1c-112">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="def1c-113">Нужен ли мне siEM-сервер?</span><span class="sxs-lookup"><span data-stu-id="def1c-113">Do I need a SIEM server?</span></span>

<span data-ttu-id="def1c-114">Потребность в siEM-сервере зависит от многих факторов, таких как требования к безопасности организации и место хранения данных.</span><span class="sxs-lookup"><span data-stu-id="def1c-114">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="def1c-115">Microsoft 365 включает широкий спектр функций безопасности, которые отвечают требованиям безопасности многих организаций без дополнительных серверов, таких как сервер SIEM.</span><span class="sxs-lookup"><span data-stu-id="def1c-115">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="def1c-116">В некоторых организациях имеются особые условия, которые требуют использования сервера SIEM.</span><span class="sxs-lookup"><span data-stu-id="def1c-116">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="def1c-117">Ниже приводятся примеры:</span><span class="sxs-lookup"><span data-stu-id="def1c-117">Here are some examples:</span></span>

- <span data-ttu-id="def1c-118">*Fabrikam* имеет некоторое содержимое и приложения на месте, а некоторые в облаке (они имеют гибридное развертывание облака).</span><span class="sxs-lookup"><span data-stu-id="def1c-118">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="def1c-119">Чтобы получить отчеты о безопасности во всем их контенте и приложениях, Fabrikam реализовал сервер SIEM.</span><span class="sxs-lookup"><span data-stu-id="def1c-119">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="def1c-120">*Contoso* — это организация финансовых служб, которая предъявляет особо строгие требования к безопасности.</span><span class="sxs-lookup"><span data-stu-id="def1c-120">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="def1c-121">Они добавили сервер SIEM в свою среду, чтобы воспользоваться необходимой дополнительной защитой безопасности.</span><span class="sxs-lookup"><span data-stu-id="def1c-121">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="def1c-122">Интеграция серверов SIEM с Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="def1c-122">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="def1c-123">Сервер SIEM может получать данные из широкого спектра служб и приложений Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="def1c-123">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="def1c-124">В следующей таблице перечислены несколько служб и приложений Microsoft 365, а также входные данные и ресурсы сервера SIEM, чтобы узнать больше.</span><span class="sxs-lookup"><span data-stu-id="def1c-124">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="def1c-125">Служба Или приложение Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="def1c-125">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="def1c-126">Входные данные и методы сервера SIEM</span><span class="sxs-lookup"><span data-stu-id="def1c-126">SIEM server inputs/methods</span></span>|<span data-ttu-id="def1c-127">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="def1c-127">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="def1c-128">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="def1c-128">Microsoft Defender for Office 365</span></span>](office-365-atp.md)|<span data-ttu-id="def1c-129">Журналы аудита</span><span class="sxs-lookup"><span data-stu-id="def1c-129">Audit logs</span></span>|[<span data-ttu-id="def1c-130">Интеграция SIEM с Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="def1c-130">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="def1c-131">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="def1c-131">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)|<span data-ttu-id="def1c-132">Конечная точка HTTPS, организованная в Azure</span><span class="sxs-lookup"><span data-stu-id="def1c-132">HTTPS endpoint hosted in Azure</span></span> <p> <span data-ttu-id="def1c-133">REST API</span><span class="sxs-lookup"><span data-stu-id="def1c-133">REST API</span></span>|[<span data-ttu-id="def1c-134">Вытащать оповещения в инструменты SIEM</span><span class="sxs-lookup"><span data-stu-id="def1c-134">Pull alerts to your SIEM tools</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="def1c-135">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="def1c-135">Microsoft Cloud App Security</span></span>](/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="def1c-136">Интеграция журнала</span><span class="sxs-lookup"><span data-stu-id="def1c-136">Log integration</span></span>|[<span data-ttu-id="def1c-137">Интеграция SIEM с безопасностью облачных приложений Майкрософт</span><span class="sxs-lookup"><span data-stu-id="def1c-137">SIEM integration with Microsoft Cloud App Security</span></span>](/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="def1c-138">Взгляните на [Azure Sentinel](/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="def1c-138">Take a look at [Azure Sentinel](/azure/sentinel/overview).</span></span> <span data-ttu-id="def1c-139">Azure Sentinel поставляется с соединителями для решений Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="def1c-139">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="def1c-140">Эти соединители доступны "из окна" и обеспечивают интеграцию в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="def1c-140">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="def1c-141">Вы можете использовать Azure Sentinel с решениями Microsoft 365 Defender и службами Microsoft 365, включая Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security и другие.</span><span class="sxs-lookup"><span data-stu-id="def1c-141">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="def1c-142">Необходимо включить журнал аудита</span><span class="sxs-lookup"><span data-stu-id="def1c-142">Audit logging must be turned on</span></span>

<span data-ttu-id="def1c-143">Убедитесь, что журнал аудита включен перед настройкой интеграции серверов SIEM.</span><span class="sxs-lookup"><span data-stu-id="def1c-143">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="def1c-144">Для SharePoint Online, OneDrive для бизнеса и Azure Active Directory журнал аудита включен в Центре & [безопасности.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="def1c-144">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="def1c-145">Для Exchange Online см. [в рублях Управление аудитом почтовых ящиков.](../../compliance/enable-mailbox-auditing.md)</span><span class="sxs-lookup"><span data-stu-id="def1c-145">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="def1c-146">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="def1c-146">More resources</span></span>

[<span data-ttu-id="def1c-147">Интеграция решений безопасности в Azure Defender</span><span class="sxs-lookup"><span data-stu-id="def1c-147">Integrate security solutions in Azure Defender</span></span>](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="def1c-148">Интеграция оповещений API безопасности Microsoft Graph с SIEM</span><span class="sxs-lookup"><span data-stu-id="def1c-148">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](/graph/security-integration)