---
title: Обозреватель угроз и обнаружение в режиме реального времени в Microsoft Defender для Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Используйте обнаружения Explorer или в режиме реального времени для эффективного расследования и реагирования на угрозы.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4d0a9ba7ee40c8ad97df745a20d6b5b3314bb3d8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083192"
---
# <a name="explorer-and-real-time-detections-basics"></a><span data-ttu-id="6c4e4-103">Основы обнаружения explorer и обнаружения в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="6c4e4-103">Explorer and Real-time detections basics</span></span>

<span data-ttu-id="6c4e4-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="6c4e4-104">**Applies to**</span></span>
- [<span data-ttu-id="6c4e4-105">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="6c4e4-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6c4e4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c4e4-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="6c4e4-107">В этой статье</span><span class="sxs-lookup"><span data-stu-id="6c4e4-107">In this article:</span></span>

- [<span data-ttu-id="6c4e4-108">Различия между обнаружениями Explorer и в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="6c4e4-108">Differences between Explorer and Real-time detections</span></span>](#differences-between-explorer-and-real-time-detections)
- [<span data-ttu-id="6c4e4-109">Обязательные лицензии и разрешения</span><span class="sxs-lookup"><span data-stu-id="6c4e4-109">Required licenses and permissions</span></span>](#required-licenses-and-permissions)

> [!NOTE]
> <span data-ttu-id="6c4e4-110">Это часть трехсерийной серии в Обозревателе (также известном как **Обозреватель угроз),** безопасности электронной почты, а также базовых обнаружениях explorer и в режиме реального времени **(таких** как различия между инструментами и разрешениями, необходимыми для их работы).  </span><span class="sxs-lookup"><span data-stu-id="6c4e4-110">This is part of a **3-article series** on **Explorer (also known as Threat Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="6c4e4-111">Другие две статьи в этой серии : [охота](threat-hunting-in-threat-explorer.md) на угрозы в Explorer и [безопасность электронной почты с помощью Explorer.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="6c4e4-111">The other two articles in this series are [Threat hunting in Explorer](threat-hunting-in-threat-explorer.md) and [Email security with Explorer](email-security-in-microsoft-defender.md).</span></span>

<span data-ttu-id="6c4e4-112">В этой статье объясняется разница между отчетами об обнаружениях Explorer и обнаружениями в режиме реального времени, а также требуемой лицензией и разрешениями.</span><span class="sxs-lookup"><span data-stu-id="6c4e4-112">This article explains the difference between Explorer and real-time detections reporting, and the licenses and permissions that are required.</span></span>

<span data-ttu-id="6c4e4-113">Если в вашей организации есть microsoft Defender [для](defender-for-office-365.md)Office 365, и у вас есть [разрешения,](#required-licenses-and-permissions)для  обнаружения и устранения угроз можно использовать **explorer** (также известный как **Explorer** угроз) или обнаружения в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="6c4e4-113">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** (also known as **Threat Explorer**) or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="6c4e4-114">На портале Microsoft 365 Defender () перейдите к совместной работе & электронной почты, а затем выберите обнаружение Explorer или в <https://security.microsoft.com>   **режиме реального времени.** </span><span class="sxs-lookup"><span data-stu-id="6c4e4-114">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<span data-ttu-id="6c4e4-115">С помощью этих средств можно выполнять перечисленные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="6c4e4-115">With these tools, you can:</span></span>

- <span data-ttu-id="6c4e4-116">См. вредоносные программы, обнаруженные Microsoft 365 функциями безопасности.</span><span class="sxs-lookup"><span data-stu-id="6c4e4-116">See malware detected by Microsoft 365 security features.</span></span>
- <span data-ttu-id="6c4e4-117">Просмотр фишинговых URL-адресов и щелкните данные вердикта.</span><span class="sxs-lookup"><span data-stu-id="6c4e4-117">View phishing URL and click verdict data.</span></span>
- <span data-ttu-id="6c4e4-118">Запустите автоматизированный процесс расследования и ответа из представления в Explorer.</span><span class="sxs-lookup"><span data-stu-id="6c4e4-118">Start an automated investigation and response process from a view in Explorer.</span></span>
- <span data-ttu-id="6c4e4-119">Изучение вредоносных сообщений электронной почты и другие.</span><span class="sxs-lookup"><span data-stu-id="6c4e4-119">Investigate malicious email, and more.</span></span>

<span data-ttu-id="6c4e4-120">Дополнительные сведения см. в [сообщении email security with Explorer.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="6c4e4-120">For more information, see [Email security with Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="differences-between-explorer-and-real-time-detections"></a><span data-ttu-id="6c4e4-121">Различия между обнаружениями Explorer и в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="6c4e4-121">Differences between Explorer and Real-time detections</span></span>

- <span data-ttu-id="6c4e4-122">*Обнаружение в режиме реального* времени — это средство отчетности, доступное в Defender для Office 365 Plan 1.</span><span class="sxs-lookup"><span data-stu-id="6c4e4-122">*Real-time detections* is a reporting tool available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="6c4e4-123">*Обозреватель угроз* — это средство поиска и устранения угроз, доступное в Defender для Office 365 Plan 2.</span><span class="sxs-lookup"><span data-stu-id="6c4e4-123">*Threat Explorer* is a threat hunting and remediation tool available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="6c4e4-124">Отчет о обнаружениях в режиме реального времени позволяет просматривать обнаружения в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="6c4e4-124">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="6c4e4-125">Это также делает обозреватель угроз, но он предоставляет дополнительные сведения для данной атаки, например выделение кампаний атак, и предоставляет [](automated-investigation-response-office.md)командам операций безопасности возможность устранять угрозы (включая запуск автоматического расследования и расследования ответов).</span><span class="sxs-lookup"><span data-stu-id="6c4e4-125">Threat Explorer does this as well, but it provides additional details for a given attack, such as highlighting attack campaigns, and gives security operations teams the ability to remediate threats (including triggering an [Automated Investigation and Response investigation](automated-investigation-response-office.md)).</span></span>
- <span data-ttu-id="6c4e4-126">Все *представления электронной* почты доступны в Обозревателе угроз, но не включены в отчет о обнаружениях в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="6c4e4-126">An *All email* view is available in Threat Explorer, but not included in the Real-time detections report.</span></span>
- <span data-ttu-id="6c4e4-127">Богатые возможности фильтрации и действия по исправлению включены в Обозреватель угроз.</span><span class="sxs-lookup"><span data-stu-id="6c4e4-127">Rich filtering capabilities and remediation actions are included in Threat Explorer.</span></span> <span data-ttu-id="6c4e4-128">Дополнительные сведения см. в [описании Microsoft Defender для службы Office 365:](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)доступность функций в Defender для Office 365 планов.</span><span class="sxs-lookup"><span data-stu-id="6c4e4-128">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="6c4e4-129">Обязательные лицензии и разрешения</span><span class="sxs-lookup"><span data-stu-id="6c4e4-129">Required licenses and permissions</span></span>

<span data-ttu-id="6c4e4-130">Вы должны иметь [Microsoft Defender, Office 365](defender-for-office-365.md) использовать обнаружения Explorer или в режиме реального времени:</span><span class="sxs-lookup"><span data-stu-id="6c4e4-130">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use either of Explorer or Real-time detections:</span></span>

- <span data-ttu-id="6c4e4-131">Explorer включен только в Defender для Office 365 Plan 2.</span><span class="sxs-lookup"><span data-stu-id="6c4e4-131">Explorer is only included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="6c4e4-132">Отчет о обнаружениях в режиме реального времени включен в Defender для Office 365 плана 1.</span><span class="sxs-lookup"><span data-stu-id="6c4e4-132">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>

<span data-ttu-id="6c4e4-133">Группы операций безопасности должны назначать лицензии всем пользователям, которые должны быть защищены defender для Office 365 и знать, что в обнаружениях Explorer и в режиме реального времени имеются данные обнаружения для лицензированных пользователей.</span><span class="sxs-lookup"><span data-stu-id="6c4e4-133">Security Operations teams need to assign licenses for all users who should be protected by Defender for Office 365 and be aware that Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="6c4e4-134">Для просмотра и использования обнаружения Explorer *или* в режиме реального времени необходимы следующие разрешения:</span><span class="sxs-lookup"><span data-stu-id="6c4e4-134">To view and use Explorer *or* Real-time detections, you need the following permissions:</span></span>

- <span data-ttu-id="6c4e4-135">В Defender для Office 365:</span><span class="sxs-lookup"><span data-stu-id="6c4e4-135">In Defender for Office 365:</span></span>
  - <span data-ttu-id="6c4e4-136">Управление организацией</span><span class="sxs-lookup"><span data-stu-id="6c4e4-136">Organization Management</span></span>
  - <span data-ttu-id="6c4e4-137">Администратор безопасности (это может быть назначено в центре администрирования Azure Active Directory ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="6c4e4-137">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="6c4e4-138">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="6c4e4-138">Security Reader</span></span>
- <span data-ttu-id="6c4e4-139">В Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="6c4e4-139">In Exchange Online:</span></span>
  - <span data-ttu-id="6c4e4-140">Управление организацией</span><span class="sxs-lookup"><span data-stu-id="6c4e4-140">Organization Management</span></span>
  - <span data-ttu-id="6c4e4-141">Управление организацией только с правом на просмотр</span><span class="sxs-lookup"><span data-stu-id="6c4e4-141">View-Only Organization Management</span></span>
  - <span data-ttu-id="6c4e4-142">Получатели только для чтения</span><span class="sxs-lookup"><span data-stu-id="6c4e4-142">View-Only Recipients</span></span>
  - <span data-ttu-id="6c4e4-143">Управление соответствием требованиям</span><span class="sxs-lookup"><span data-stu-id="6c4e4-143">Compliance Management</span></span>

<span data-ttu-id="6c4e4-144">Дополнительные информацию о ролях и разрешениях см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="6c4e4-144">To learn more about roles and permissions, see the following articles:</span></span>

- [<span data-ttu-id="6c4e4-145">Разрешения на портале Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c4e4-145">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-microsoft-365-security-center.md)
- [<span data-ttu-id="6c4e4-146">Разрешения в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6c4e4-146">Permissions in Exchange Online</span></span>](/e/exchange/permissions-exo/permissions-exo)

## <a name="more-information"></a><span data-ttu-id="6c4e4-147">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="6c4e4-147">More information</span></span>

- [<span data-ttu-id="6c4e4-148">Обозреватель угроз собирает сведения электронной почты на странице сущности электронной почты</span><span class="sxs-lookup"><span data-stu-id="6c4e4-148">Threat Explorer collect email details on the email entity page</span></span>](mdo-email-entity-page.md)
- [<span data-ttu-id="6c4e4-149">Поиск и изучение доставленной нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="6c4e4-149">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="6c4e4-150">Просмотр вредоносных файлов, обнаруженных в SharePoint Online, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6c4e4-150">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- <span data-ttu-id="6c4e4-151">[отчет о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report);</span><span class="sxs-lookup"><span data-stu-id="6c4e4-151">[Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="6c4e4-152">Автоматизированный анализ угроз и реакция на угрозы в службе защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="6c4e4-152">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)
