---
title: Средства контроля обслуживающей организации (SOC)
description: Облачные службы Майкрософт соответствуют стандартам средств контроля обслуживающей организации для операционной безопасности.
keywords: Microsoft 365, соответствие требованиям, предложения
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 57d4093712efbee7bcb4f27280b0ba64a50dbe41
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2020
ms.locfileid: "41662025"
---
# <a name="service-organization-controls-soc"></a><span data-ttu-id="3251b-104">Средства контроля обслуживающей организации (SOC)</span><span class="sxs-lookup"><span data-stu-id="3251b-104">Service Organization Controls (SOC)</span></span>

## <a name="soc-1-2-and-3-reports-overview"></a><span data-ttu-id="3251b-105">Сведения об отчетах SOC 1, 2 и 3</span><span class="sxs-lookup"><span data-stu-id="3251b-105">SOC 1, 2, and 3 Reports overview</span></span>

<span data-ttu-id="3251b-106">Компании все чаще передают основные функции, например хранение данных и доступ к приложениям, на аутсорсинг поставщикам облачных служб (CSP) и другим обслуживающим организациям.</span><span class="sxs-lookup"><span data-stu-id="3251b-106">Increasingly, businesses outsource basic functions such as data storage and access to applications to cloud service providers (CSPs) and other service organizations.</span></span> <span data-ttu-id="3251b-107">Для таких случаев Американский институт дипломированных присяжных бухгалтеров (AICPA) разработал платформу средств контроля обслуживающей организации (SOC) — стандарт для средств контроля, защищающий конфиденциальность информации, хранящейся и обрабатываемой в облаке.</span><span class="sxs-lookup"><span data-stu-id="3251b-107">In response, the American Institute of Certified Public Accountants (AICPA) has developed the Service Organization Controls (SOC) framework, a standard for controls that safeguard the confidentiality and privacy of information stored and processed in the cloud.</span></span> <span data-ttu-id="3251b-108">Он соответствует международному стандарту заданий по подтверждению достоверности информации (ISAE) — стандарту отчетов для международных обслуживающих организаций.</span><span class="sxs-lookup"><span data-stu-id="3251b-108">This aligns with the International Standard on Assurance Engagements (ISAE), the reporting standard for international service organizations.</span></span>

<span data-ttu-id="3251b-109">Аудиты служб на основе платформы SOC делятся на две категории — SOC 1 и SOC 2, применяющиеся к соответствующим облачным службам Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3251b-109">Service audits based on the SOC framework fall into two categories — SOC 1 and SOC 2 — that apply to in-scope Microsoft cloud services.</span></span>

<span data-ttu-id="3251b-110">Аудит SOC 1, предназначенный для организаций CPA, проводящих аудит финансовых отчетов, оценивает эффективность внутренних средств контроля CSP, влияющих на финансовые отчеты клиентов, которые используют облачные службы поставщика.</span><span class="sxs-lookup"><span data-stu-id="3251b-110">A SOC 1 audit, intended for CPA firms that audit financial statements, evaluates the effectiveness of a CSP’s internal controls that affect the financial reports of a customer using the provider’s cloud services.</span></span> <span data-ttu-id="3251b-111">Положение о стандартах аттестационных проверок (SSAE 18) и международный стандарт заданий по подтверждению достоверности информации №</span><span class="sxs-lookup"><span data-stu-id="3251b-111">The Statement on Standards for Attestation Engagements (SSAE 18) and the International Standards for Assurance Engagements No.</span></span> <span data-ttu-id="3251b-112">3402 (ISAE 3402) — это стандарты, распространяющиеся на выполняемый аудит и являющиеся основой отчета SOC 1.</span><span class="sxs-lookup"><span data-stu-id="3251b-112">3402 (ISAE 3402) are the standards under which the audit is performed, and is the basis of the SOC 1 report.</span></span>

<span data-ttu-id="3251b-113">Аудит SOC 2 оценивает эффективность системы поставщика облачных служб (CSP) на основе принципов и критериев услуг в области доверия для удостоверяющих центров AICPA.</span><span class="sxs-lookup"><span data-stu-id="3251b-113">A SOC 2 audit gauges the effectiveness of a CSP’s system based on the AICPA Trust Service Principles and Criteria.</span></span> <span data-ttu-id="3251b-114">Раздел 101 "Задания по аттестации в соответствии со стандартами аттестации (AT)" — это основа отчетов SOC 2 и SOC 3.</span><span class="sxs-lookup"><span data-stu-id="3251b-114">An Attest Engagement under Attestation Standards (AT) Section 101 is the basis of SOC 2 and SOC 3 reports.</span></span>

<span data-ttu-id="3251b-115">В завершении аудита SOC 1 или SOC 2 аудитор службы формирует заключение в отчете SOC 1 (тип 2) или SOC 2 (тип 2), в котором описывается система CSP и оценивается объективность CSP в описании своих средств контроля.</span><span class="sxs-lookup"><span data-stu-id="3251b-115">At the conclusion of a SOC 1 or SOC 2 audit, the service auditor renders an opinion in a SOC 1 Type 2 or SOC 2 Type 2 report, which describes the CSP’s system and assesses the fairness of the CSP’s description of its controls.</span></span> <span data-ttu-id="3251b-116">В нем также оценивается соответствие назначения средств контроля CSP; работали ли они в указанную дату и были ли эффективны в определенный период времени.</span><span class="sxs-lookup"><span data-stu-id="3251b-116">It also evaluates whether the CSP’s controls are designed appropriately, were in operation on a specified date, and were operating effectively over a specified time period.</span></span>

<span data-ttu-id="3251b-117">Аудиторы также могут создать отчет SOC 3 (сокращенная версия отчета аудитора SOC 2 (тип 2)) для пользователей, которым требуется гарантия в отношении средств контроля CSP, но не требуется полный отчет SOC 2.</span><span class="sxs-lookup"><span data-stu-id="3251b-117">Auditors can also create a SOC 3 report — an abbreviated version of the SOC 2 Type 2 audit report — for users who want assurance about the CSP’s controls but don’t need a full SOC 2 report.</span></span> <span data-ttu-id="3251b-118">Отчет SOC 3 может быть предоставлен только в том случае, если CSP получил аудиторское заключение без оговорок для SOC 2.</span><span class="sxs-lookup"><span data-stu-id="3251b-118">A SOC 3 report can be conferred only if the CSP has an unqualified audit opinion for SOC 2.</span></span>

## <a name="microsoft-and-soc-1-2-and-3-reports"></a><span data-ttu-id="3251b-119">Майкрософт и отчеты SOC 1, 2 и 3</span><span class="sxs-lookup"><span data-stu-id="3251b-119">Microsoft and SOC 1, 2, and 3 Reports</span></span>

<span data-ttu-id="3251b-120">Поддерживаемые облачные службы Майкрософт минимум раз в год подвергаются аудиту с использованием платформы отчетности SOC, который проводится независимыми аудиторами.</span><span class="sxs-lookup"><span data-stu-id="3251b-120">Microsoft covered cloud services are audited at least annually against the SOC reporting framework by independent third-party auditors.</span></span> <span data-ttu-id="3251b-121">Аудит облачных служб Майкрософт охватывает средства контроля для обеспечения безопасности данных, доступности, целостности обработки и конфиденциальности согласно соответствующим принципам доверия для каждой службы.</span><span class="sxs-lookup"><span data-stu-id="3251b-121">The audit for Microsoft cloud services covers controls for data security, availability, processing integrity, and confidentiality as applicable to in-scope trust principles for each service.</span></span>

<span data-ttu-id="3251b-122">Корпорация Майкрософт получили отчеты SOC 1 (тип 2), SOC 2 (тип 2) и SOC 3.</span><span class="sxs-lookup"><span data-stu-id="3251b-122">Microsoft has achieved SOC 1 Type 2, SOC 2 Type 2, and SOC 3 reports.</span></span> <span data-ttu-id="3251b-123">Обычно доступ к отчетам SOC 1 и SOC 2 предоставляется только клиентам, подписавшим соглашение о неразглашении с Майкрософт, а отчет SOC 3 общедоступен.</span><span class="sxs-lookup"><span data-stu-id="3251b-123">In general, the availability of SOC 1 and SOC 2 reports is restricted to customers who have signed nondisclosure agreements with Microsoft; the SOC 3 report is publicly available.</span></span>

<span data-ttu-id="3251b-124">Узнайте о преимуществах SOC 1, 2, 3 в Microsoft Cloud: [скачайте информационный документ для отчетов SOC 1 и SOC 2 (тип 2)](https://aka.ms/soc_backgrounder)</span><span class="sxs-lookup"><span data-stu-id="3251b-124">Learn about the benefits of SOC 1, 2, 3 on the Microsoft Cloud: [Download the SOC 1 and SOC 2 type 2 reports backgrounder](https://aka.ms/soc_backgrounder)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="3251b-125">Поддерживаемые облачные службы Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3251b-125">Microsoft in-scope cloud services</span></span>

### <a name="covered-services-for-soc-1-and-soc-2"></a><span data-ttu-id="3251b-126">Поддерживаемые службы для SOC 1 и SOC 2</span><span class="sxs-lookup"><span data-stu-id="3251b-126">Covered services for SOC 1 and SOC 2</span></span>

- [<span data-ttu-id="3251b-127">Azure, Azure для государственных организаций и Azure для Германии</span><span class="sxs-lookup"><span data-stu-id="3251b-127">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="3251b-128">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3251b-128">Cloud App Security</span></span>
- [<span data-ttu-id="3251b-129">Dynamics 365 и Dynamics 365 для государственных организаций США</span><span class="sxs-lookup"><span data-stu-id="3251b-129">Dynamics 365 and Dynamics 365 U.S. Government</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="3251b-130">Graph</span><span class="sxs-lookup"><span data-stu-id="3251b-130">Graph</span></span>
- <span data-ttu-id="3251b-131">Intune</span><span class="sxs-lookup"><span data-stu-id="3251b-131">Intune</span></span>
- <span data-ttu-id="3251b-132">Компьютеры, управляемые Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3251b-132">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="3251b-133">Облачная служба Microsoft Flow в виде автономной службы или в составе плана либо набора Office 365 или Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3251b-133">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- [<span data-ttu-id="3251b-134">Office 365, Office 365 для государственных организаций США и Office 365 U.S. Government Defense</span><span class="sxs-lookup"><span data-stu-id="3251b-134">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="3251b-135">Облачная служба PowerApps в виде автономной службы или в составе плана либо набора Office 365 или Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3251b-135">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="3251b-136">Облачная служба Power BI в виде автономной службы или в составе плана либо набора Office 365</span><span class="sxs-lookup"><span data-stu-id="3251b-136">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="3251b-137">Stream</span><span class="sxs-lookup"><span data-stu-id="3251b-137">Stream</span></span>
- <span data-ttu-id="3251b-138">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="3251b-138">Azure DevOps Services</span></span>

### <a name="covered-services-for-soc-3"></a><span data-ttu-id="3251b-139">Поддерживаемые службы для SOC 3</span><span class="sxs-lookup"><span data-stu-id="3251b-139">Covered services for SOC 3</span></span>

- [<span data-ttu-id="3251b-140">Azure, Azure для государственных организаций и Azure для Германии</span><span class="sxs-lookup"><span data-stu-id="3251b-140">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="3251b-141">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3251b-141">Cloud App Security</span></span>
- <span data-ttu-id="3251b-142">Graph</span><span class="sxs-lookup"><span data-stu-id="3251b-142">Graph</span></span>
- <span data-ttu-id="3251b-143">Intune</span><span class="sxs-lookup"><span data-stu-id="3251b-143">Intune</span></span>
- <span data-ttu-id="3251b-144">Компьютеры, управляемые Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3251b-144">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="3251b-145">Облачная служба Microsoft Flow в виде автономной службы или в составе плана либо набора Office 365 или Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3251b-145">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="3251b-146">Облачная служба PowerApps в виде автономной службы или в составе плана либо набора Office 365 или Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3251b-146">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- [<span data-ttu-id="3251b-147">Office 365, Office 365 для государственных организаций США и Office 365 U.S. Government Defense</span><span class="sxs-lookup"><span data-stu-id="3251b-147">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="3251b-148">Power BI</span><span class="sxs-lookup"><span data-stu-id="3251b-148">Power BI</span></span>
- <span data-ttu-id="3251b-149">Stream</span><span class="sxs-lookup"><span data-stu-id="3251b-149">Stream</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="3251b-150">Аудит, отчеты и сертификаты</span><span class="sxs-lookup"><span data-stu-id="3251b-150">Audits, reports, and certificates</span></span>

### <a name="audit-cycle"></a><span data-ttu-id="3251b-151">Цикл аудита</span><span class="sxs-lookup"><span data-stu-id="3251b-151">Audit cycle</span></span>

<span data-ttu-id="3251b-152">Облачные службы Майкрософт подлежат аудиту не менее одного раза в год по стандартам SOC 1 (SSAE18, ISAE 3402) и SOC 2 (AT Раздел 101).</span><span class="sxs-lookup"><span data-stu-id="3251b-152">Microsoft cloud services are audited at least annually against SOC 1 (SSAE18, ISAE 3402) and SOC 2 (AT Section 101) standards.</span></span>

#### <a name="azure-cloud-app-security-flow-graph-intune-power-bi-powerapps-stream-and-microsoft-datacenters"></a><span data-ttu-id="3251b-153">Azure, Cloud App Security, Flow, Graph, Intune, Power BI, PowerApps, Stream и центры обработки данных Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3251b-153">Azure, Cloud App Security, Flow, Graph, Intune, Power BI, PowerApps, Stream, and Microsoft Datacenters</span></span>

- [<span data-ttu-id="3251b-154">Отчет SOC 1 (тип 2) об Azure и Azure для государственных организаций</span><span class="sxs-lookup"><span data-stu-id="3251b-154">Azure and Azure Government SOC 1 Type 2 Report</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2099601)
- [<span data-ttu-id="3251b-155">Отчет SOC 2 (тип 2) об Azure и Azure для государственных организаций</span><span class="sxs-lookup"><span data-stu-id="3251b-155">Azure and Azure Government SOC 2 Type 2 Report</span></span>](https://aka.ms/azuresoc2auditreport)
- [<span data-ttu-id="3251b-156">Отчет SOC 3 об Azure и Azure для государственных организаций</span><span class="sxs-lookup"><span data-stu-id="3251b-156">Azure and Azure Government SOC 3 Report</span></span>](https://aka.ms/azuresoc3auditreport)

#### <a name="dynamics-365"></a><span data-ttu-id="3251b-157">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3251b-157">Dynamics 365</span></span>

- [<span data-ttu-id="3251b-158">Отчет SOC 1 (тип 2) для Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3251b-158">Dynamics 365 SOC 1 Type 2 Report</span></span>](https://aka.ms/Dynamics365SOC1AuditReport)
- [<span data-ttu-id="3251b-159">Отчет о результатах аудита SOC 2 (AT 101, тип II) для Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="3251b-159">Dynamics 365 SOC 2 AT 101 Type II Audit Report</span></span>](https://aka.ms/Dynamics365SOC2AuditReport)
- [<span data-ttu-id="3251b-160">См. связывающие письма и дополнительные отчеты аудита</span><span class="sxs-lookup"><span data-stu-id="3251b-160">See bridge letters and additional audit reports</span></span>](https://aka.ms/auditreports)

#### <a name="office-365"></a><span data-ttu-id="3251b-161">Office 365</span><span class="sxs-lookup"><span data-stu-id="3251b-161">Office 365</span></span>

- [<span data-ttu-id="3251b-162">Отчет SOC 1 (SSAE 18) для Office 365 Core</span><span class="sxs-lookup"><span data-stu-id="3251b-162">Office 365 Core - SSAE 18 SOC 1 Report</span></span>](https://aka.ms/o365SOC-1)
- [<span data-ttu-id="3251b-163">Отчет SOC 2 (SSAE 18) для Office 365 Core</span><span class="sxs-lookup"><span data-stu-id="3251b-163">Office 365 Core - SSAE 18 SOC 2 Report</span></span>](https://aka.ms/o365SOC-2)
- [<span data-ttu-id="3251b-164">Отчет SOC 3 (SSAE 18) для Office 365 Core</span><span class="sxs-lookup"><span data-stu-id="3251b-164">Office 365 Core - SSAE 18 SOC 3 Report</span></span>](https://aka.ms/o365SOC-3)
- [<span data-ttu-id="3251b-165">Отчет SOC 2 (T1 — SSAE 18, тип I) для микрослужб Office 365</span><span class="sxs-lookup"><span data-stu-id="3251b-165">Office 365 Microservices T1 – SSAE 18 SOC2 Type I Report</span></span>](https://aka.ms/o365-MS-SOC-2-type1)
- [<span data-ttu-id="3251b-166">Отчет о результатах аудита SOC 1 (SSAE 16) для защищенного хранилища Office 365</span><span class="sxs-lookup"><span data-stu-id="3251b-166">Office 365 Customer Lockbox SOC 1 SSAE 16 Audit Report</span></span>](https://aka.ms/Office365CustomerLockboxSOCAuditReport)
- [<span data-ttu-id="3251b-167">Отчет о результатах аудита SOC 2 (AT 101, тип I) для Yammer</span><span class="sxs-lookup"><span data-stu-id="3251b-167">Yammer SOC 2 AT 101 Type I Audit Report</span></span>](https://aka.ms/YammerSOC2Type1AuditReport)
- [<span data-ttu-id="3251b-168">Отчет SOC 2 (тип II) для Yammer</span><span class="sxs-lookup"><span data-stu-id="3251b-168">Yammer SOC 2 Type II Report</span></span>](https://aka.ms/yammerSOC-2)
- [<span data-ttu-id="3251b-169">См. связывающие письма и дополнительные отчеты аудита</span><span class="sxs-lookup"><span data-stu-id="3251b-169">See bridge letters and additional audit reports</span></span>](https://aka.ms/auditreports)

## <a name="frequently-asked-questions"></a><span data-ttu-id="3251b-170">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="3251b-170">Frequently asked questions</span></span>

<span data-ttu-id="3251b-171">**Как получить копии отчетов SOC?**</span><span class="sxs-lookup"><span data-stu-id="3251b-171">**How can I get copies of the SOC reports?**</span></span>

<span data-ttu-id="3251b-172">С помощью отчетов ваши аудиторы могут сравнить результаты для облачных служб Майкрософт с вашими юридическими и нормативными требованиями.</span><span class="sxs-lookup"><span data-stu-id="3251b-172">With the reports, your auditors can compare Microsoft business cloud services results with your own legal and regulatory requirements.</span></span>

- <span data-ttu-id="3251b-173">Вы можете просмотреть все отчеты SOC с помощью [платформы Service Trust](https://www.microsoft.com/trustcenter/STP/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="3251b-173">You can see all SOC reports through the [Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx).</span></span>
- <span data-ttu-id="3251b-174">Клиенты службы Azure DevOps, которым недоступна [платформа Service Trust](https://www.microsoft.com/trustcenter/STP/default.aspx) могут связаться по электронной почте со службой [Azure DevOps](mailto:AzureDevOpsSOCReport@microsoft.com) для получения отчетов SOC 1 и SOC 2.</span><span class="sxs-lookup"><span data-stu-id="3251b-174">Azure DevOps Service customers that can’t access [Service Trust Platform](https://www.microsoft.com/trustcenter/STP/default.aspx) can email [Azure DevOps](mailto:AzureDevOpsSOCReport@microsoft.com) for its SOC 1 and SOC 2 reports.</span></span> <span data-ttu-id="3251b-175">Эта электронная почта предназначена только для запроса отчетов SOC по Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="3251b-175">This email is to request Azure DevOps SOC reports only.</span></span>

<span data-ttu-id="3251b-176">**Как часто выпускаются отчеты SOC для Azure?**</span><span class="sxs-lookup"><span data-stu-id="3251b-176">**How often are Azure SOC reports issued?**</span></span>

<span data-ttu-id="3251b-177">Отчеты SOC для Azure, Cloud App Security, Flow, Graph, Intune, Power BI, PowerApps, Stream и центров обработки данных Майкрософт основаны на 12-месячном сроке работы (период аудита), а новые отчеты выпускаются раз в полгода (периоды заканчиваются 31 марта и 30 сентября).</span><span class="sxs-lookup"><span data-stu-id="3251b-177">SOC reports for Azure, Cloud App Security, Flow, Graph, Intune, Power BI, PowerApps, Stream, and Microsoft Datacenters are based on a rolling 12-month run window (audit period) with new reports issued semi-annually (period ends are March 31 and September 30).</span></span> <span data-ttu-id="3251b-178">Связывающие письма рассылаются в январе (за период от 1.10 до 31.12) и в июле (за период от 1.04 до 30.06).</span><span class="sxs-lookup"><span data-stu-id="3251b-178">Bridge letters are issued in January to cover the period of 10/1 – 12/31 and July to cover the period of 4/1 – 6/30.</span></span> <span data-ttu-id="3251b-179">Клиенты могут [скачать](https://aka.ms/stp) последние отчеты с портала Service Trust Portal.</span><span class="sxs-lookup"><span data-stu-id="3251b-179">Customers can [download](https://aka.ms/stp) the latest reports from the Service Trust Portal.</span></span>

<span data-ttu-id="3251b-180">**Нужно ли самостоятельно проводить аудит центров обработки данных Майкрософт?**</span><span class="sxs-lookup"><span data-stu-id="3251b-180">**Do I need to conduct my own audit of Microsoft datacenters?**</span></span>

<span data-ttu-id="3251b-181">Нет.</span><span class="sxs-lookup"><span data-stu-id="3251b-181">No.</span></span> <span data-ttu-id="3251b-182">Корпорация Майкрософт предоставляет отчеты независимого аудита и сертификаты клиентам, чтобы они могли проверить соответствие Майкрософт требованиям в отношении безопасности.</span><span class="sxs-lookup"><span data-stu-id="3251b-182">Microsoft shares the independent audit reports and certifications with customers so that they can verify Microsoft compliance with its security commitments.</span></span>

<span data-ttu-id="3251b-183">**Можно ли использовать соответствие требованиям Майкрософт в процессе сертификации моей организации?**</span><span class="sxs-lookup"><span data-stu-id="3251b-183">**Can I use Microsoft’s compliance in my organization’s certification process?**</span></span>

<span data-ttu-id="3251b-184">Да.</span><span class="sxs-lookup"><span data-stu-id="3251b-184">Yes.</span></span> <span data-ttu-id="3251b-185">При переносе приложений и данных в поддерживаемые облачные службы Майкрософт вы можете использовать в качестве основы аудит и сертификаты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3251b-185">When you migrate your applications and data to covered Microsoft cloud services, you can build on the audits and certifications that Microsoft holds.</span></span> <span data-ttu-id="3251b-186">Независимые отчеты подтверждают эффективность средств контроля, реализованных корпорацией Майкрософт для обеспечения безопасности и конфиденциальности данных.</span><span class="sxs-lookup"><span data-stu-id="3251b-186">The independent reports attest to the effectiveness of controls that Microsoft has implemented to help maintain the security and privacy of your data.</span></span>

<span data-ttu-id="3251b-187">**С чего начинается обеспечение соответствия требованиям в организации?**</span><span class="sxs-lookup"><span data-stu-id="3251b-187">**Where do I start with my organization’s own compliance effort?**</span></span>

<span data-ttu-id="3251b-188">[Набор средств SOC для обслуживающих организаций](https://aka.ms/soc-toolkit) — это полезный ресурс для знакомства с процессами создания отчетов SOC и расширения их использования в организации.</span><span class="sxs-lookup"><span data-stu-id="3251b-188">The [SOC Toolkit for Service Organizations](https://aka.ms/soc-toolkit) is a helpful resource for understanding SOC reporting processes and promoting your organization’s use of them.</span></span>

## <a name="resources"></a><span data-ttu-id="3251b-189">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="3251b-189">Resources</span></span>

- [<span data-ttu-id="3251b-190">Улучшенная защита данных с помощью облачных служб Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3251b-190">Better protect your data by using Microsoft cloud services</span></span>](https://www.microsoft.com/trustcenter/guidance/protect-data)
- [<span data-ttu-id="3251b-191">Отчеты по средствам контроля обслуживающей организации (SOC)</span><span class="sxs-lookup"><span data-stu-id="3251b-191">Service Organization Control (SOC) Reports</span></span>](https://aka.ms/mssocreports)
- [<span data-ttu-id="3251b-192">Обзор SSAE 16</span><span class="sxs-lookup"><span data-stu-id="3251b-192">SSAE 16 Overview</span></span>](http://ssae16.com/SSAE16_overview.html)
- [<span data-ttu-id="3251b-193">Обзор ISAE 3402</span><span class="sxs-lookup"><span data-stu-id="3251b-193">ISAE 3402 Overview</span></span>](http://isae3402.com/ISAE3402_overview.html)
- [<span data-ttu-id="3251b-194">Условия использования веб-служб Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3251b-194">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="3251b-195">Облако Майкрософт для государственных организаций</span><span class="sxs-lookup"><span data-stu-id="3251b-195">Microsoft Government Cloud</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [<span data-ttu-id="3251b-196">Соответствие требованиям в центре управления безопасностью Майкрософт</span><span class="sxs-lookup"><span data-stu-id="3251b-196">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
