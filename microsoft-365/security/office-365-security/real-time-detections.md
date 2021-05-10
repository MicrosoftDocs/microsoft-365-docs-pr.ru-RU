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
ms.openlocfilehash: 7ab7b5731d121106d930868b03330d4ac7befd77
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300219"
---
# <a name="threat-explorer-and-real-time-detections-basics"></a><span data-ttu-id="0116d-103">Основы обнаружения обнаружения в режиме реального времени и обозреватель угроз</span><span class="sxs-lookup"><span data-stu-id="0116d-103">Threat Explorer and Real-time detections basics</span></span>

<span data-ttu-id="0116d-104">В этой статье</span><span class="sxs-lookup"><span data-stu-id="0116d-104">In this article:</span></span>

- [<span data-ttu-id="0116d-105">Различия между обнаружением обозревателя угроз и обнаружения в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="0116d-105">Differences between Threat Explorer and Real-time detections</span></span>](#differences-between-threat-explorer-and-real-time-detections)<br/>
- [<span data-ttu-id="0116d-106">Обязательные лицензии и разрешения</span><span class="sxs-lookup"><span data-stu-id="0116d-106">Required licenses and permissions</span></span>](#required-licenses-and-permissions)

> [!NOTE]
> <span data-ttu-id="0116d-107">Это часть трехсерийной серии по обозревателю угроз **(Explorer),** безопасности электронной почты **и** основам обнаружения explorer и в режиме реального времени **(например,** различия между инструментами и разрешениями, необходимыми для их работы). </span><span class="sxs-lookup"><span data-stu-id="0116d-107">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="0116d-108">Другие две статьи в этой серии : "Охота на угрозы в [обозревателе угроз"](threat-hunting-in-threat-explorer.md) и "Безопасность электронной почты [с помощью обозревателя угроз".](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="0116d-108">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

<span data-ttu-id="0116d-109">В этой статье объясняется разница между отчетами об обнаружении угроз и обнаружениями в режиме реального времени, а также требуемой лицензией и разрешениями.</span><span class="sxs-lookup"><span data-stu-id="0116d-109">This article explains the difference between threat exploration and real-time detections reporting, and the licenses and permissions that are required.</span></span>

<span data-ttu-id="0116d-110">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="0116d-110">**Applies to**</span></span>
- [<span data-ttu-id="0116d-111">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="0116d-111">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0116d-112">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0116d-112">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0116d-113">Если в вашей организации есть microsoft  [Defender](defender-for-office-365.md)для Office 365, и у вас есть разрешения, для обнаружения и устранения угроз можно использовать обнаружение обозревателя угроз (под названием **Explorer)** или обнаружения в режиме реального времени. [](#required-licenses-and-permissions) </span><span class="sxs-lookup"><span data-stu-id="0116d-113">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Threat Explorer** (called **Explorer**) or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="0116d-114">В  Центре **&** безопасности перейдите к управлению угрозами, а затем выберите обнаружение **Explorer** или в **режиме реального времени.** </span><span class="sxs-lookup"><span data-stu-id="0116d-114">In the **Security & Compliance Center**, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<br>

****

|<span data-ttu-id="0116d-115">В Microsoft Defender для Office 365 Plan 2 см.:</span><span class="sxs-lookup"><span data-stu-id="0116d-115">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="0116d-116">В Microsoft Defender для Office 365 1 см.:</span><span class="sxs-lookup"><span data-stu-id="0116d-116">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![Обозреватель угроз](../../media/threatmgmt-explorer.png)|![Обнаружение в режиме реального времени](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="0116d-119">С помощью этих средств можно:</span><span class="sxs-lookup"><span data-stu-id="0116d-119">With these tools, you can:</span></span>

- <span data-ttu-id="0116d-120">См. вредоносные программы, обнаруженные Microsoft 365 функциями безопасности.</span><span class="sxs-lookup"><span data-stu-id="0116d-120">See malware detected by Microsoft 365 security features.</span></span>
- <span data-ttu-id="0116d-121">Просмотр фишинговых URL-адресов и щелкните данные вердикта.</span><span class="sxs-lookup"><span data-stu-id="0116d-121">View phishing URL and click verdict data.</span></span>
- <span data-ttu-id="0116d-122">Запустите автоматизированный процесс расследования и ответа из представления в Explorer.</span><span class="sxs-lookup"><span data-stu-id="0116d-122">Start an automated investigation and response process from a view in Explorer.</span></span>
- <span data-ttu-id="0116d-123">Изучение вредоносных сообщений электронной почты и другие.</span><span class="sxs-lookup"><span data-stu-id="0116d-123">Investigate malicious email, and more.</span></span>

<span data-ttu-id="0116d-124">Дополнительные сведения см. в [сообщении email security with Threat Explorer.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="0116d-124">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="0116d-125">Различия между обнаружением обозревателя угроз и обнаружения в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="0116d-125">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="0116d-126">*Обнаружение в режиме реального* времени — это средство отчетности, доступное в Defender для Office 365 Plan 1.</span><span class="sxs-lookup"><span data-stu-id="0116d-126">*Real-time detections* is a reporting tool available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="0116d-127">*Обозреватель угроз* — это средство поиска и устранения угроз, доступное в Defender для Office 365 Plan 2.</span><span class="sxs-lookup"><span data-stu-id="0116d-127">*Threat Explorer* is a threat hunting and remediation tool available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="0116d-128">Отчет о обнаружениях в режиме реального времени позволяет просматривать обнаружения в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="0116d-128">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="0116d-129">Это также делает обозреватель угроз, но он предоставляет дополнительные сведения для данной атаки, например выделение кампаний атак, и предоставляет [](automated-investigation-response-office.md)командам операций безопасности возможность устранять угрозы (включая запуск автоматического расследования и расследования ответов).</span><span class="sxs-lookup"><span data-stu-id="0116d-129">Threat Explorer does this as well, but it provides additional details for a given attack, such as highlighting attack campaigns, and gives security operations teams the ability to remediate threats (including triggering an [Automated Investigation and Response investigation](automated-investigation-response-office.md)).</span></span>
- <span data-ttu-id="0116d-130">Все *представления электронной* почты доступны в Обозревателе угроз, но не включены в отчет о обнаружениях в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="0116d-130">An *All email* view is available in Threat Explorer, but not included in the Real-time detections report.</span></span>
- <span data-ttu-id="0116d-131">Богатые возможности фильтрации и действия по исправлению включены в Обозреватель угроз.</span><span class="sxs-lookup"><span data-stu-id="0116d-131">Rich filtering capabilities and remediation actions are included in Threat Explorer.</span></span> <span data-ttu-id="0116d-132">Дополнительные сведения см. в [описании Microsoft Defender для службы Office 365:](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)доступность функций в Defender для Office 365 планов.</span><span class="sxs-lookup"><span data-stu-id="0116d-132">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="0116d-133">Обязательные лицензии и разрешения</span><span class="sxs-lookup"><span data-stu-id="0116d-133">Required licenses and permissions</span></span>

<span data-ttu-id="0116d-134">Вы должны иметь [Microsoft Defender, Office 365](defender-for-office-365.md) использовать обнаружения Explorer или в режиме реального времени:</span><span class="sxs-lookup"><span data-stu-id="0116d-134">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use either of Explorer or Real-time detections:</span></span>

- <span data-ttu-id="0116d-135">Но Explorer включен только в Defender для Office 365 Plan 2.</span><span class="sxs-lookup"><span data-stu-id="0116d-135">But Explorer is only included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="0116d-136">Отчет о обнаружениях в режиме реального времени включен в Defender для Office 365 плана 1.</span><span class="sxs-lookup"><span data-stu-id="0116d-136">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>

<span data-ttu-id="0116d-137">Группы операций безопасности должны назначать лицензии всем пользователям, которые должны быть защищены defender для Office 365 и знать, что в обнаружениях Explorer и в режиме реального времени имеются данные обнаружения для лицензированных пользователей.</span><span class="sxs-lookup"><span data-stu-id="0116d-137">Security Operations teams need to assign licenses for all users who should be protected by Defender for Office 365 and be aware that Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="0116d-138">Чтобы просмотреть и использовать обнаружения Explorer *или* в режиме реального времени, необходимо иметь следующее:</span><span class="sxs-lookup"><span data-stu-id="0116d-138">To view and use Explorer *or* Real-time detections, you must have the following:</span></span>

- <span data-ttu-id="0116d-139">Центр обеспечения & безопасности:</span><span class="sxs-lookup"><span data-stu-id="0116d-139">For the Security & Compliance Center:</span></span>

  - <span data-ttu-id="0116d-140">Управление организацией</span><span class="sxs-lookup"><span data-stu-id="0116d-140">Organization Management</span></span>
  - <span data-ttu-id="0116d-141">Администратор безопасности (это может быть назначено в центре администрирования Azure Active Directory ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="0116d-141">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="0116d-142">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="0116d-142">Security Reader</span></span>

- <span data-ttu-id="0116d-143">Для Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="0116d-143">For Exchange Online:</span></span>

  - <span data-ttu-id="0116d-144">Управление организацией</span><span class="sxs-lookup"><span data-stu-id="0116d-144">Organization Management</span></span>
  - <span data-ttu-id="0116d-145">Управление организацией только с правом на просмотр</span><span class="sxs-lookup"><span data-stu-id="0116d-145">View-Only Organization Management</span></span>
  - <span data-ttu-id="0116d-146">Получатели только для чтения</span><span class="sxs-lookup"><span data-stu-id="0116d-146">View-Only Recipients</span></span>
  - <span data-ttu-id="0116d-147">Управление соответствием требованиям</span><span class="sxs-lookup"><span data-stu-id="0116d-147">Compliance Management</span></span>

<span data-ttu-id="0116d-148">Дополнительные информацию о ролях и разрешениях см. в следующих ресурсах:</span><span class="sxs-lookup"><span data-stu-id="0116d-148">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="0116d-149">Разрешения в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="0116d-149">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="0116d-150">Разрешения компонентов в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0116d-150">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="0116d-151">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="0116d-151">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="0116d-152">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="0116d-152">More information</span></span>
- [<span data-ttu-id="0116d-153">Обозреватель угроз собирает сведения электронной почты на странице сущности электронной почты</span><span class="sxs-lookup"><span data-stu-id="0116d-153">Threat Explorer collect email details on the email entity page</span></span>](mdo-email-entity-page.md)
- [<span data-ttu-id="0116d-154">Поиск и изучение доставленной нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="0116d-154">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="0116d-155">Просмотр вредоносных файлов, обнаруженных в SharePoint Online, OneDrive и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0116d-155">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- <span data-ttu-id="0116d-156">[отчет о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report);</span><span class="sxs-lookup"><span data-stu-id="0116d-156">[Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="0116d-157">Автоматизированный анализ угроз и реакция на угрозы в службе защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="0116d-157">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)