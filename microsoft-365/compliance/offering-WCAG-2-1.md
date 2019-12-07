---
title: Руководство по обеспечению доступности веб-контента 2.1
description: Майкрософт публикует отчеты WCAG 2.1 AA, целиком описывающие продукт, службу или части продукта, которые можно установить отдельно.
keywords: Microsoft 365, соответствие требованиям, предложения
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: a1887bd2b6c04836ebb11d224fcc59debcd88e55
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "39859449"
---
# <a name="web-content-accessibility-guidelines-21"></a><span data-ttu-id="dca49-104">Руководство по обеспечению доступности веб-контента 2.1</span><span class="sxs-lookup"><span data-stu-id="dca49-104">Web Content Accessibility Guidelines 2.1</span></span>

## <a name="about-wcag-21"></a><span data-ttu-id="dca49-105">Сведения о WCAG 2.1</span><span class="sxs-lookup"><span data-stu-id="dca49-105">About WCAG 2.1</span></span>

<span data-ttu-id="dca49-106">Руководство WCAG 2.1 предоставляет структуру для разработки веб-контента с улучшенной доступностью для людей с ограниченными возможностями в дополнение к пользователям устройств с ограниченными графическими возможностями.</span><span class="sxs-lookup"><span data-stu-id="dca49-106">WCAG 2.1 provides a framework for developing web content that improves accessibility for people with disabilities, in addition to users of devices with limited graphical abilities.</span></span> <span data-ttu-id="dca49-107">Руководство WCAG 2.0 было опубликовано в 2008 г. консорциумом W3C, международной организацией, занимающейся созданием веб-стандартов. Оно было обновлено до версии WCAG 2.1 в июне 2018 г.</span><span class="sxs-lookup"><span data-stu-id="dca49-107">WCAG 2.0 was published in 2008 by the World Wide Web Consortium (W3C), an international organization dedicated to creating web standards, and updated to WCAG 2.1 in June 2018.</span></span> <span data-ttu-id="dca49-108">В 2012 г. руководство WCAG 2.0 также было опубликовано Международной организацией по стандартизации (ISO) в виде стандарта ISO/IEC 40500:2012.</span><span class="sxs-lookup"><span data-stu-id="dca49-108">In 2012, WCAG 2.0 was also published by the International Organization for Standardization (ISO) as ISO/IEC 40500:2012.</span></span>  
  
<span data-ttu-id="dca49-109">Контент, соответствующий WCAG 2.1, также соответствует WCAG 2.0.</span><span class="sxs-lookup"><span data-stu-id="dca49-109">Content that conforms to WCAG 2.1 also conforms to WCAG 2.0.</span></span> <span data-ttu-id="dca49-110">Для политик, которые должны соответствовать WCAG 2.0, в руководстве WCAG 2.1 могут содержаться альтернативные способы обеспечения соответствия.</span><span class="sxs-lookup"><span data-stu-id="dca49-110">For policies requiring conformance to WCAG 2.0, WCAG 2.1 can provide an alternate means of conformance.</span></span>  
  
<span data-ttu-id="dca49-111">Требования соответствия для каждого руководства оцениваются по трем уровням: A, AA и AAA.</span><span class="sxs-lookup"><span data-stu-id="dca49-111">Conformance requirements for each guideline are measured in three levels: A, AA, and AAA.</span></span> <span data-ttu-id="dca49-112">Так как корпорация Майкрософт является основным поставщиком программного обеспечения и облачных служб для стран и правительств по всему миру, она обязуется соответствовать всем важным [международным стандартам и средствам контроля соответствия требованиям](https://go.microsoft.com/fwlink/p/?linkid=2052226).</span><span class="sxs-lookup"><span data-stu-id="dca49-112">Because Microsoft is a major software and cloud-services provider to states and governments around the world, it is committed to complying with all relevant [international standards and compliance controls](https://go.microsoft.com/fwlink/p/?linkid=2052226).</span></span> <span data-ttu-id="dca49-113">Соблюдая эти комплексные стандарты по обеспечению доступности, корпорация Майкрософт гарантирует, что все клиенты (из государственных и иных учреждений) могут использовать службы и продукты Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="dca49-113">By adhering to these wide-ranging accessibility standards, Microsoft ensures that all customers — both inside and outside of government — can use Microsoft services and products.</span></span>  

## <a name="microsoft-and-wcag-21"></a><span data-ttu-id="dca49-114">Майкрософт и WCAG 2.1</span><span class="sxs-lookup"><span data-stu-id="dca49-114">Microsoft and WCAG 2.1</span></span>

<span data-ttu-id="dca49-115">Выполнение корпорацией Майкрософт стандарта WCAG 2.1 (ISO/IEC 40500) определяет ее обязательства по обеспечению доступности технологий и данных для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="dca49-115">Microsoft’s adherence to the WCAG 2.1 (ISO/IEC 40500) standard points to its commitment to making technology and data accessible for all customers.</span></span> <span data-ttu-id="dca49-116">WCAG 2.1 (ISO/IEC 40500) — это международные требования по обеспечению доступности, дополняющие стандарт EN 301 549 (Европа) и Раздел 508 (США).</span><span class="sxs-lookup"><span data-stu-id="dca49-116">WCAG 2.1 (ISO/IEC 40500) is the international accessibility requirement that complements EN 301 549 (Europe) and Section 508 (U.S.).</span></span>  
  
<span data-ttu-id="dca49-117">Майкрософт публикует отчеты WCAG 2.1, целиком описывающие продукт или службу.</span><span class="sxs-lookup"><span data-stu-id="dca49-117">Microsoft publishes WCAG 2.1 reports that reflect the complete product or service.</span></span> <span data-ttu-id="dca49-118">Как правило, отчеты для отдельных функций или компонентов не создаются.</span><span class="sxs-lookup"><span data-stu-id="dca49-118">It generally does not create reports for individual features or components.</span></span> <span data-ttu-id="dca49-119">Иногда корпорация Майкрософт может выпустить новый компонент для существующего продукта или новую версию существующего компонента, который пользователи могут устанавливать отдельно. Майкрософт может опубликовать отчет WCAG 2.1 для такого компонента.</span><span class="sxs-lookup"><span data-stu-id="dca49-119">Sometimes, Microsoft might release a new component for an existing product, or a new version of an existing component, which users can choose to install separately, and Microsoft might also publish a WCAG 2.1 report for that component.</span></span>  
  
[<span data-ttu-id="dca49-120">Скачать стандарты обеспечения доступности WCAG 2.1 (ISO/IEC 40500)</span><span class="sxs-lookup"><span data-stu-id="dca49-120">Download the WCAG 2.1 (ISO/IEC 40500) accessibility standards</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2052226)

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="dca49-121">Поддерживаемые облачные службы Майкрософт</span><span class="sxs-lookup"><span data-stu-id="dca49-121">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="dca49-122">Azure и Azure для государственных организаций</span><span class="sxs-lookup"><span data-stu-id="dca49-122">Azure and Azure Government</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2051569)
- <span data-ttu-id="dca49-123">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="dca49-123">Azure DevOps Services</span></span>
- <span data-ttu-id="dca49-124">Dynamics 365 и Dynamics 365 для государственных организаций США</span><span class="sxs-lookup"><span data-stu-id="dca49-124">Dynamics 365 and Dynamics 365 U.S. Government</span></span>
- <span data-ttu-id="dca49-125">Intune</span><span class="sxs-lookup"><span data-stu-id="dca49-125">Intune</span></span>
- <span data-ttu-id="dca49-126">Office 365 и Office 365 для государственных организаций США</span><span class="sxs-lookup"><span data-stu-id="dca49-126">Office 365 and Office 365 U.S. Government</span></span>
- <span data-ttu-id="dca49-127">Office 365 для министерства обороны США</span><span class="sxs-lookup"><span data-stu-id="dca49-127">Office 365 U.S. Government Defense</span></span>
- <span data-ttu-id="dca49-128">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="dca49-128">Windows Server 2016</span></span>

## <a name="microsoft-accessibility-conformance-reports"></a><span data-ttu-id="dca49-129">Отчеты о соответствии специальных возможностей Майкрософт</span><span class="sxs-lookup"><span data-stu-id="dca49-129">Microsoft accessibility conformance reports</span></span>

<span data-ttu-id="dca49-130">Ознакомьтесь с отчетами WCAG для всех наших продуктов и служб.</span><span class="sxs-lookup"><span data-stu-id="dca49-130">Find WCAG reports for all our products and services.</span></span>

[<span data-ttu-id="dca49-131">**Подробнее**</span><span class="sxs-lookup"><span data-stu-id="dca49-131">**Learn more**</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2050974)

## <a name="resources"></a><span data-ttu-id="dca49-132">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="dca49-132">Resources</span></span>

<span data-ttu-id="dca49-133">[Сайт по специальным возможностям Майкрософт — ознакомьтесь с использованием функций обеспечения доступности и изучите новые способы, применяемые корпорацией Майкрософт для достижения целей любыми пользователями.</span><span class="sxs-lookup"><span data-stu-id="dca49-133">[Microsoft accessibility site — Get information on using accessibility features and explore the ways Microsoft innovates to help everyone achieve more.</span></span>

<span data-ttu-id="dca49-134">[Центр специальных возможностей Office 365](https://go.microsoft.com/fwlink/p/?linkid=2051801).</span><span class="sxs-lookup"><span data-stu-id="dca49-134">[Office 365 Accessibility Center](https://go.microsoft.com/fwlink/p/?linkid=2051801)</span></span>
    - <span data-ttu-id="dca49-135">Ресурсы Office 365 для людей с ограниченными возможностями.</span><span class="sxs-lookup"><span data-stu-id="dca49-135">Office 365 resources for people with disabilities.</span></span>

<span data-ttu-id="dca49-136">[Enterprise Disability Answer Desk](https://go.microsoft.com/fwlink/p/?linkid=2050890).</span><span class="sxs-lookup"><span data-stu-id="dca49-136">[Enterprise Disability Answer Desk](https://go.microsoft.com/fwlink/p/?linkid=2050890)</span></span>
    - <span data-ttu-id="dca49-137">Поддержка для корпоративных клиентов с вопросами о специальных возможностях наших продуктов и служб.</span><span class="sxs-lookup"><span data-stu-id="dca49-137">Dedicated support for enterprise customers with accessibility questions about our products and services or compliance.</span></span>

[<span data-ttu-id="dca49-138">Соответствие требованиям в центре управления безопасностью Майкрософт</span><span class="sxs-lookup"><span data-stu-id="dca49-138">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="dca49-139">Загрузить информационный документ предложения</span><span class="sxs-lookup"><span data-stu-id="dca49-139">Download the offering backgrounder</span></span>

<span data-ttu-id="dca49-140">Нужен информационный документ для этого предложения?</span><span class="sxs-lookup"><span data-stu-id="dca49-140">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="dca49-141">Скачайте [PDF-файл](https://download.microsoft.com/download/3/E/1/3E10CC43-036D-4DB5-ACBA-8665A752C8F7/Accessibility-Compliance.pdf).</span><span class="sxs-lookup"><span data-stu-id="dca49-141">Download the [PDF](https://download.microsoft.com/download/3/E/1/3E10CC43-036D-4DB5-ACBA-8665A752C8F7/Accessibility-Compliance.pdf).</span></span>
