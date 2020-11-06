---
title: Вспомогательные ресурсы для соблюдения нормативных требований к управлению данными и записями
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Вспомогательные ресурсы для соблюдения нормативных требований к управлению данными и записями.
ms.openlocfilehash: 47fa49f1253ee5e5b5ee4546a7243a529b6105a1
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920714"
---
# <a name="regulatory-requirements-for-information-governance-and-records-management"></a><span data-ttu-id="0d2ba-103">Нормативные требования к управлению данными и записями</span><span class="sxs-lookup"><span data-stu-id="0d2ba-103">Regulatory requirements for information governance and records management</span></span>

><span data-ttu-id="0d2ba-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="0d2ba-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="0d2ba-105">Использование ресурсов, находящихся на этой странице, помогает соблюдать конкретные нормативные требования к управлению данными и записями в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0d2ba-105">Use the resources on this page to help you meet specific regulatory requirements for information governance and records management in Microsoft 365.</span></span> <span data-ttu-id="0d2ba-106">В каждом разделе этого документа рассматривается одно или несколько нормативных требований и приводятся инструкции или сторонние оценки по настройке Microsoft 365, которые помогут при выполнении описанных требований.</span><span class="sxs-lookup"><span data-stu-id="0d2ba-106">Each section of this document focuses on one or more related regulations and includes any existing guidance or third-party assessment of how to configure Microsoft 365 to help with the requirements outlined.</span></span>

<span data-ttu-id="0d2ba-107">Эти ресурсы можно скачать на странице [Часто задаваемые вопросы и техническая документация по ресурсам, связанным с защитой данных](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers) сайта Service Trust Portal.</span><span class="sxs-lookup"><span data-stu-id="0d2ba-107">These resources are available to download from the [Data Protection Resources, FAQ and White Papers](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers) page of the Service Trust Portal.</span></span>

## <a name="sec-17a-4f-finra-4511c-and-cftc-131c-d"></a><span data-ttu-id="0d2ba-108">SEC 17a-4(f), FINRA 4511(c) и CFTC 1.31(c)-(d)</span><span class="sxs-lookup"><span data-stu-id="0d2ba-108">SEC 17a-4(f), FINRA 4511(c), and CFTC 1.31(c)-(d)</span></span>

<span data-ttu-id="0d2ba-109">**Оценка Cohasset - Microsoft 365 - SEC Rule 17a-4(f) - Неизменяемое хранилище для SharePoint, OneDrive, Teams, Exchange и Skype**</span><span class="sxs-lookup"><span data-stu-id="0d2ba-109">**Cohasset Assessment - Microsoft 365 - SEC Rule 17a-4(f) - Immutable Storage for SharePoint, OneDrive, Teams, Exchange, and Skype**</span></span>

<span data-ttu-id="0d2ba-110">Применимые рабочие нагрузки: SharePoint, OneDrive, Teams, Exchange и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0d2ba-110">Applicable workloads: SharePoint, OneDrive, Teams, Exchange, and Skype for Business</span></span>

<span data-ttu-id="0d2ba-111">Этот отчет, опубликованный в ноябре 2020 г., был подготовлен совместно с компанией Cohasset Associates, Inc. (Cohasset) для оценки возможностей служб Microsoft 365 в отношении создания и хранения электронных записей, а также управления ими в соответствии с требованиями, указанными:</span><span class="sxs-lookup"><span data-stu-id="0d2ba-111">Released November 2020, this report has been produced in partnership with Cohasset Associates, Inc. (Cohasset) to assess the capabilities of Microsoft 365 services for recording, storing, and managing requirements for electronic records, as specified by:</span></span>  

- <span data-ttu-id="0d2ba-112">Комиссией по ценным бумагам и биржам США (SEC) в 17 CFR § 240.17a-4(f), где содержатся требования для участников биржи, брокеров и дилеров.</span><span class="sxs-lookup"><span data-stu-id="0d2ba-112">Securities and Exchange Commission (SEC) in 17 CFR § 240.17a-4(f), which regulates exchange members, brokers or dealers.</span></span>  

- <span data-ttu-id="0d2ba-113">Агентством по регулированию деятельности финансовых институтов (FINRA) в правиле 4511(c), опирающемся на требования к формату и носителям, определенные правилом 17a-4(f) SEC.</span><span class="sxs-lookup"><span data-stu-id="0d2ba-113">Financial Industry Regulatory Authority (FINRA) Rule 4511(c), which defers to the format and media requirements of SEC Rule 17a-4(f).</span></span>  

- <span data-ttu-id="0d2ba-114">Комиссией по торговле товарными фьючерсами (CFTC) в положении 17 CFR § 1.31(c)-(d), где изложены принципиальные требования.</span><span class="sxs-lookup"><span data-stu-id="0d2ba-114">The principles-based electronic records requirements of the Commodity Futures Trading Commission (CFTC) in 17 CFR § 1.31(c)-(d).</span></span>

<span data-ttu-id="0d2ba-115">Мнение компании Cohasset заключается в том, что при правильной настройке функций соответствия требованиям, их внимательном применении и тщательном управлении ими в порядке, изложенном в отчете, рассмотренные службы Microsoft 365 удовлетворяют пяти требованиям к созданию электронных записей и их хранению без возможности перезаписи и удаления.</span><span class="sxs-lookup"><span data-stu-id="0d2ba-115">The opinion from Cohasset is that when compliance features are properly configured and carefully applied and managed as described in their report, the assessed Microsoft 365 services meet the five requirements related to the recording and non-rewriteable, non-erasable storage of electronic records.</span></span>
