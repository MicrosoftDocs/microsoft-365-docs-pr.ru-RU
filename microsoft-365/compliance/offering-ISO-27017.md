---
title: ISO/IEC 27017:2015 "Свод правил по управлению информационной безопасностью"
description: В облачных службах Майкрософт реализованы этот свод правил по управлению информационной безопасностью.
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
ms.openlocfilehash: 6bd989a5600252ee60ada4eb4e3d1414ef3853d5
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602246"
---
# <a name="isoiec-270172015-code-of-practice-for-information-security-controls"></a><span data-ttu-id="5ce9a-104">ISO/IEC 27017:2015 "Свод правил по управлению информационной безопасностью"</span><span class="sxs-lookup"><span data-stu-id="5ce9a-104">ISO/IEC 27017:2015 Code of Practice for Information Security Controls</span></span>

## <a name="iso-iec-27017-overview"></a><span data-ttu-id="5ce9a-105">Общие сведения о ISO-IEC 27017</span><span class="sxs-lookup"><span data-stu-id="5ce9a-105">ISO-IEC 27017 Overview</span></span>

<span data-ttu-id="5ce9a-106">Свод правил ISO/IEC 27017:2015 предназначен для организаций для использования в качестве справочника при выборе средств контроля информационной безопасностью облачных служб при реализации системы управления информационной безопасностью облачных вычислений на основе стандарта ISO/IEC 27002:2013.</span><span class="sxs-lookup"><span data-stu-id="5ce9a-106">The ISO/IEC 27017:2015 code of practice is designed for organizations to use as a reference for selecting cloud services information security controls when implementing a cloud computing information security management system based on ISO/IEC 27002:2013.</span></span> <span data-ttu-id="5ce9a-107">Он также может использоваться поставщиками облачных служб в качестве руководства по реализации общепринятых средств контроля защиты.</span><span class="sxs-lookup"><span data-stu-id="5ce9a-107">It can also be used by cloud service providers as a guidance document for implementing commonly accepted protection controls.</span></span>

<span data-ttu-id="5ce9a-108">Этот международный стандарт предоставляет дополнительные инструкции по внедрению для облачной среды, основанные на стандарте ISO/IEC 27002, и содержит дополнительные средства контроля для устранения облачных рисков и угроз информационной безопасности, ссылаясь на пункты 5–18 стандарта ISO/IEC 27002:2013 со сведениями об средствах контроля, инструкциями реализации и прочей информацией.</span><span class="sxs-lookup"><span data-stu-id="5ce9a-108">This international standard provides additional cloud-specific implementation guidance based on ISO/IEC 27002, and provides additional controls to address cloud-specific information security threats and risks referring to clauses 5–18 in ISO/IEC 27002: 2013 for controls, implementation guidance, and other information.</span></span> <span data-ttu-id="5ce9a-109">В частности, этот стандарт предоставляет инструкции по 37 средствам контроля из стандарта ISO/IEC 27002, а также содержит семь новых средств контроля, отсутствующих в стандарте ISO/IEC 27002.</span><span class="sxs-lookup"><span data-stu-id="5ce9a-109">Specifically, this standard provides guidance on 37 controls in ISO/IEC 27002, and it also features seven new controls that are not duplicated in ISO/IEC 27002.</span></span> <span data-ttu-id="5ce9a-110">Эти новые средства контроля предназначены для следующих важных областей:</span><span class="sxs-lookup"><span data-stu-id="5ce9a-110">These new controls address the following important areas:</span></span>

- <span data-ttu-id="5ce9a-111">Общие роли и обязанности в облачной среде</span><span class="sxs-lookup"><span data-stu-id="5ce9a-111">Shared roles and responsibilities within a cloud computing environment</span></span>
- <span data-ttu-id="5ce9a-112">Удаление и возврат ресурсов клиента облачной службы при расторжении договора</span><span class="sxs-lookup"><span data-stu-id="5ce9a-112">Removal and return of cloud service customer assets upon contract termination</span></span>
- <span data-ttu-id="5ce9a-113">Защита и отделение виртуальной среды клиента от сред других клиентов</span><span class="sxs-lookup"><span data-stu-id="5ce9a-113">Protection and separation of a customer’s virtual environment from that of other customers</span></span>
- <span data-ttu-id="5ce9a-114">Требования к обеспечению безопасности виртуальной машины для соблюдения бизнес-потребностей</span><span class="sxs-lookup"><span data-stu-id="5ce9a-114">Virtual machine hardening requirements to meet business needs</span></span>
- <span data-ttu-id="5ce9a-115">Процедуры для административных операций с облачной средой</span><span class="sxs-lookup"><span data-stu-id="5ce9a-115">Procedures for administrative operations of a cloud computing environment</span></span>
- <span data-ttu-id="5ce9a-116">Разрешение клиентам отслеживать важные действия в облачной среде</span><span class="sxs-lookup"><span data-stu-id="5ce9a-116">Enabling customers to monitor relevant activities within a cloud computing environment</span></span>
- <span data-ttu-id="5ce9a-117">Согласование управления безопасностью для виртуальных и физических сетей</span><span class="sxs-lookup"><span data-stu-id="5ce9a-117">Alignment of security management for virtual and physical networks</span></span>

## <a name="microsoft-and-isoiec-27017"></a><span data-ttu-id="5ce9a-118">Майкрософт и ISO/IEC 27017</span><span class="sxs-lookup"><span data-stu-id="5ce9a-118">Microsoft and ISO/IEC 27017</span></span>

<span data-ttu-id="5ce9a-119">ISO/IEC 27017 является уникальным стандартом, предоставляющим руководство как поставщикам облачных служб, так и клиентам облачных служб.</span><span class="sxs-lookup"><span data-stu-id="5ce9a-119">ISO/IEC 27017 is unique in providing guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="5ce9a-120">Он также содержит практические сведения для клиентов облачных служб о том, что следует ожидать от поставщиков облачных служб.</span><span class="sxs-lookup"><span data-stu-id="5ce9a-120">It also provides cloud service customers with practical information on what they should expect from cloud service providers.</span></span> <span data-ttu-id="5ce9a-121">Клиенты могут получить прямую выгоду от использования стандарта ISO/IEC 27017, разобравшись с понятием общей ответственности в облаке.</span><span class="sxs-lookup"><span data-stu-id="5ce9a-121">Customers can benefit directly from ISO/IEC 27017 by ensuring they understand the shared responsibilities in the cloud.</span></span>

<span data-ttu-id="5ce9a-122">Узнайте о преимуществах стандарта ISO/IEC 27017 в Microsoft Cloud: [скачайте ISO/IEC 27017 "Свод правил по управлению информационной безопасностью"](https://aka.ms/iso27017-backgrounder)</span><span class="sxs-lookup"><span data-stu-id="5ce9a-122">Learn about the benefits of ISO/IEC 27017 on the Microsoft Cloud: [Download the ISO/IEC 27017: Code of Practice for Information Security Controls](https://aka.ms/iso27017-backgrounder)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="5ce9a-123">Поддерживаемые облачные службы Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5ce9a-123">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="5ce9a-124">Azure, Azure для государственных организаций и Azure для Германии</span><span class="sxs-lookup"><span data-stu-id="5ce9a-124">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="5ce9a-125">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5ce9a-125">Cloud App Security</span></span>
- [<span data-ttu-id="5ce9a-126">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="5ce9a-126">Dynamics 365</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="5ce9a-127">Genomics</span><span class="sxs-lookup"><span data-stu-id="5ce9a-127">Genomics</span></span>
- <span data-ttu-id="5ce9a-128">Graph</span><span class="sxs-lookup"><span data-stu-id="5ce9a-128">Graph</span></span>
- <span data-ttu-id="5ce9a-129">Intune</span><span class="sxs-lookup"><span data-stu-id="5ce9a-129">Intune</span></span>
- <span data-ttu-id="5ce9a-130">Компьютеры, управляемые Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5ce9a-130">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="5ce9a-131">Облачная служба Microsoft Flow в виде автономной службы или в составе плана либо набора Office 365 или Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="5ce9a-131">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="5ce9a-132">Office 365, Office 365 для государственных организаций США, Office 365 U.S. Government Defense и Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="5ce9a-132">Office 365, Office 365 U.S. Government, Office 365 U.S. Government Defense, and Office 365 Germany</span></span>
- <span data-ttu-id="5ce9a-133">Облачная служба PowerApps в виде автономной службы или в составе плана либо набора Office 365 или Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="5ce9a-133">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="5ce9a-134">Облачная служба Power BI в виде автономной службы или в составе плана либо набора Office 365</span><span class="sxs-lookup"><span data-stu-id="5ce9a-134">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="5ce9a-135">Ознакомьтесь с [подробным списком](https://go.microsoft.com/fwlink/p/?linkid=2077751) поддерживаемых служб в Office 365</span><span class="sxs-lookup"><span data-stu-id="5ce9a-135">See a [detailed list](https://go.microsoft.com/fwlink/p/?linkid=2077751) of covered services in Office 365</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="5ce9a-136">Аудит, отчеты и сертификаты</span><span class="sxs-lookup"><span data-stu-id="5ce9a-136">Audits, reports, and certificates</span></span>

<span data-ttu-id="5ce9a-137">Аудит облачных служб Майкрософт выполняется раз в год на соответствие своду правил ISO/IEC 27017:2015 в рамках процесса сертификации для ISO/IEC 27001:2013.</span><span class="sxs-lookup"><span data-stu-id="5ce9a-137">Microsoft cloud services are audited once a year for the ISO/IEC 27017:2015 code of practice as part of the certification process for ISO/IEC 27001:2013.</span></span>

- [<span data-ttu-id="5ce9a-138">Сертификат Azure ISO 27017</span><span class="sxs-lookup"><span data-stu-id="5ce9a-138">Azure ISO 27017 Certificate</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2078005)
- [<span data-ttu-id="5ce9a-139">Отчет по оценке Azure ISO 27017</span><span class="sxs-lookup"><span data-stu-id="5ce9a-139">Azure ISO 27017 Assessment report</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2078010)
- [<span data-ttu-id="5ce9a-140">Заявление о применимости Azure ISO 27017</span><span class="sxs-lookup"><span data-stu-id="5ce9a-140">Azure ISO 27017 Statement of Applicability</span></span>](https://aka.ms/AzureISO27017StatementofApplicability)
- [<span data-ttu-id="5ce9a-141">Отчет аудиторской оценки по ISO 27001, 27018 и 27017 в Office 365</span><span class="sxs-lookup"><span data-stu-id="5ce9a-141">Office 365 ISO 27001, 27018, and 27017 Audit Assessment Report</span></span>](https://aka.ms/o365isoreport)

## <a name="frequently-asked-questions"></a><span data-ttu-id="5ce9a-142">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="5ce9a-142">Frequently asked questions</span></span>

<span data-ttu-id="5ce9a-143">К кому применим стандарт?</span><span class="sxs-lookup"><span data-stu-id="5ce9a-143">To whom does the standard apply?</span></span>

<span data-ttu-id="5ce9a-144">Этот свод правил содержит средства контроля и инструкции по реализации для поставщиков облачных служб и клиентов облачных служб.</span><span class="sxs-lookup"><span data-stu-id="5ce9a-144">This code of practice provides controls and implementation guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="5ce9a-145">Его структура аналогична стандарту ISO/IEC 27002:2013.</span><span class="sxs-lookup"><span data-stu-id="5ce9a-145">It is structured in a format similar to ISO/IEC 27002:2013.</span></span>

<span data-ttu-id="5ce9a-146">**Где можно посмотреть сведения о соответствии Майкрософт требованиям ISO/IEC 27017:2015?**</span><span class="sxs-lookup"><span data-stu-id="5ce9a-146">**Where can I view Microsoft’s compliance information for ISO/IEC 27017:2015?**</span></span>

<span data-ttu-id="5ce9a-147">Вы можете скачать [сертификат ISO/IEC 27017:2015](https://aka.ms/azureiso27017) для Azure, Intune и Power BI.</span><span class="sxs-lookup"><span data-stu-id="5ce9a-147">You can download the [ISO/IEC 27017:2015 certificate](https://aka.ms/azureiso27017) for Azure, Intune, and Power BI.</span></span>

<span data-ttu-id="5ce9a-148">**Можно ли использовать соответствие стандарту ISO/IEC 27017 для служб Майкрософт в процессе сертификации моей организации?**</span><span class="sxs-lookup"><span data-stu-id="5ce9a-148">**Can I use the ISO/IEC 27017 compliance of Microsoft services in my organization’s certification process?**</span></span>

<span data-ttu-id="5ce9a-149">Да.</span><span class="sxs-lookup"><span data-stu-id="5ce9a-149">Yes.</span></span> <span data-ttu-id="5ce9a-150">Если ваша организации стремится пройти сертификацию для реализаций, развернутых в любых поддерживаемых корпоративных облачных службах Майкрософт, вы можете использовать соответствующие сертификаты Майкрософт при оценке соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="5ce9a-150">If your business is seeking certification for implementations deployed on any Microsoft in-scope enterprise cloud services, you can use Microsoft’s relevant certifications in your compliance assessment.</span></span> <span data-ttu-id="5ce9a-151">Однако вы несете ответственность за привлечение аудитора для оценки реализации на соответствие требованиям, а также оценки средств управления и процессов в рамках вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5ce9a-151">However, you are responsible for engaging an assessor to evaluate your implementation for compliance, and for the controls and processes within your own organization.</span></span>

<span data-ttu-id="5ce9a-152">**Как получить копии соответствующих отчетов об аудите?**</span><span class="sxs-lookup"><span data-stu-id="5ce9a-152">**How can I get copies of the applicable audit reports?**</span></span>

<span data-ttu-id="5ce9a-153">На портале [Service Trust Portal](https://aka.ms/stphelp) доступны отчеты о независимом аудите и другие сопутствующие документы.</span><span class="sxs-lookup"><span data-stu-id="5ce9a-153">The [Service Trust Portal](https://aka.ms/stphelp) provides independent, third-party audit reports and other related documentation.</span></span> <span data-ttu-id="5ce9a-154">Вы можете использовать этот портал для скачивания и просмотра этих документов, помогающих выполнять нормативные требования.</span><span class="sxs-lookup"><span data-stu-id="5ce9a-154">You can use the portal to download and review this documentation for assistance with your own regulatory requirements.</span></span>

## <a name="resources"></a><span data-ttu-id="5ce9a-155">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="5ce9a-155">Resources</span></span>

- [<span data-ttu-id="5ce9a-156">Свод правил ISO/IEC 27017:2015</span><span class="sxs-lookup"><span data-stu-id="5ce9a-156">ISO/IEC 27017:2015 code of practice</span></span>](https://www.iso.org/iso/iso_catalogue/catalogue_tc/catalogue_detail.htm?csnumber=43757)
- [<span data-ttu-id="5ce9a-157">Условия использования веб-служб Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5ce9a-157">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="5ce9a-158">Соответствие требованиям в центре управления безопасностью Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5ce9a-158">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="5ce9a-159">Загрузить информационный документ предложения</span><span class="sxs-lookup"><span data-stu-id="5ce9a-159">Download the offering backgrounder</span></span>

<span data-ttu-id="5ce9a-160">Нужен информационный документ для этого предложения?</span><span class="sxs-lookup"><span data-stu-id="5ce9a-160">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="5ce9a-161">Скачайте [PDF-файл](https://download.microsoft.com/download/7/7/9/7799D02B-A97A-48E0-A057-C19DD543BB24/ISO-IEC-27017_backgrounder.pdf).</span><span class="sxs-lookup"><span data-stu-id="5ce9a-161">Download the [PDF](https://download.microsoft.com/download/7/7/9/7799D02B-A97A-48E0-A057-C19DD543BB24/ISO-IEC-27017_backgrounder.pdf).</span></span>
