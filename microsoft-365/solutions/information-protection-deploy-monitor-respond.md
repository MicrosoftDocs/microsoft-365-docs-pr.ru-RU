---
title: Отслеживание инцидентов конфиденциальности данных в Организации и реагирование на них
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Использование политик аудита и оповещений и запросов субъектов данных для отслеживания инцидентов персональных данных и реагирования на них.
ms.openlocfilehash: 296220ac8b34d9ce10c783194b78ca344e746b84
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377203"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="965f5-103">Отслеживание инцидентов конфиденциальности данных в Организации и реагирование на них</span><span class="sxs-lookup"><span data-stu-id="965f5-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="965f5-104">Функции Microsoft 365 помогут вам отслеживать, изучать и отвечать на инциденты конфиденциальности данных в вашей организации, как вы оператионализее связанные возможности.</span><span class="sxs-lookup"><span data-stu-id="965f5-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="965f5-105">Процесс, процедуры и другая документация для каждого из них также могут быть важны для демонстрации соответствия нормативным требованиям.</span><span class="sxs-lookup"><span data-stu-id="965f5-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="965f5-106">Такие законодательные акты перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="965f5-106">These include:</span></span> 

- <span data-ttu-id="965f5-107">Политики аудита и оповещений</span><span class="sxs-lookup"><span data-stu-id="965f5-107">Auditing and alert policies</span></span>
- <span data-ttu-id="965f5-108">Запросы субъектов данных (в том числе поиск контента и обнаружение электронных данных)</span><span class="sxs-lookup"><span data-stu-id="965f5-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="965f5-109">Дополнительные изученные средства и отчеты</span><span class="sxs-lookup"><span data-stu-id="965f5-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="965f5-110">Требования к конфиденциальности данных влияют на использование средств мониторинга и реагирования</span><span class="sxs-lookup"><span data-stu-id="965f5-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="965f5-111">Ниже приведен пример списка нормативных актов о конфиденциальности данных, которые могут относиться к элементам управления для управления сведениями:</span><span class="sxs-lookup"><span data-stu-id="965f5-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="965f5-112">ЛГПД статья 46</span><span class="sxs-lookup"><span data-stu-id="965f5-112">LGPD Article 46</span></span>
- <span data-ttu-id="965f5-113">ЛГПД статья 48</span><span class="sxs-lookup"><span data-stu-id="965f5-113">LGPD Article 48</span></span>
- <span data-ttu-id="965f5-114">Статья GDPR (5) (1) (f)</span><span class="sxs-lookup"><span data-stu-id="965f5-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="965f5-115">Статья GDPR (15) (1) (e)</span><span class="sxs-lookup"><span data-stu-id="965f5-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="965f5-116">HIPAA-HITECH (45 К.Ф.Р.</span><span class="sxs-lookup"><span data-stu-id="965f5-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="965f5-117">164.308 (a) (1) (II) (D))</span><span class="sxs-lookup"><span data-stu-id="965f5-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="965f5-118">HIPAA-HITECH (45 К.Ф.Р.</span><span class="sxs-lookup"><span data-stu-id="965f5-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="965f5-119">164.308(a)(6)(ii)</span><span class="sxs-lookup"><span data-stu-id="965f5-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="965f5-120">HIPAA-HITECH (45 К.Ф.Р.</span><span class="sxs-lookup"><span data-stu-id="965f5-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="965f5-121">164.312 (b))</span><span class="sxs-lookup"><span data-stu-id="965f5-121">164.312(b))</span></span>
- <span data-ttu-id="965f5-122">ККПА (1798.105 (c))</span><span class="sxs-lookup"><span data-stu-id="965f5-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="965f5-123">Дополнительную информацию можно узнать в статье [Оценка рисков конфиденциальности данных и определение конфиденциальной информации](information-protection-deploy-assess.md).</span><span class="sxs-lookup"><span data-stu-id="965f5-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="965f5-124">В соответствии с правилами конфиденциальности данных в целом для мониторинга и ответа, как правило, вызывается следующее:</span><span class="sxs-lookup"><span data-stu-id="965f5-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="965f5-125">Аудит, оповещения и отчеты о действиях, связанных с хранилищем, совместном использовании и обработкой персональных данных</span><span class="sxs-lookup"><span data-stu-id="965f5-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="965f5-126">Возможность реагирования на запрос субъекта данных (DSR) и, в некоторых случаях, на выполнение таких запросов обеспечивается с помощью изученной и другой административной меры.</span><span class="sxs-lookup"><span data-stu-id="965f5-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="965f5-127">В организации также может потребоваться выполнить мониторинг и отреагировать на действия для других целей, например для других требований соответствия требованиям или для бизнес-целей.</span><span class="sxs-lookup"><span data-stu-id="965f5-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="965f5-128">Создание схемы мониторинга и ответа для обеспечения конфиденциальности данных должно выполняться в рамках общего мониторинга и планирования, внедрения и управления откликами.</span><span class="sxs-lookup"><span data-stu-id="965f5-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="965f5-129">В этой статье перечислены полезные возможности Microsoft 365, которые помогут вам начать работу с схемой мониторинга и ответа в Microsoft 365 для обеспечения конфиденциальности данных, чтобы ответить на следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="965f5-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="965f5-130">Какие приемы ежедневного мониторинга и создания отчетов доступны для различных типов и источников данных?</span><span class="sxs-lookup"><span data-stu-id="965f5-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="965f5-131">Какие механизмы необходимы для обработки запросов субъектов данных (DSR) и любых действий, таких как анонимность, исправление и удаление.</span><span class="sxs-lookup"><span data-stu-id="965f5-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="965f5-132">Политики аудита и оповещений в центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="965f5-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="965f5-133">В следующих статьях приводятся сведения о настройке аудита, расширенном аудите и политиках оповещений.</span><span class="sxs-lookup"><span data-stu-id="965f5-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="965f5-134">Единый аудит</span><span class="sxs-lookup"><span data-stu-id="965f5-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="965f5-135">Аудит почтового ящика</span><span class="sxs-lookup"><span data-stu-id="965f5-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="965f5-136">Расширенный аудит</span><span class="sxs-lookup"><span data-stu-id="965f5-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="965f5-137">Политики оповещений</span><span class="sxs-lookup"><span data-stu-id="965f5-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="965f5-138">Запросы субъектов данных для GDPR и ККПА</span><span class="sxs-lookup"><span data-stu-id="965f5-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="965f5-139">В разделе [запросы субъектов данных GDPR и ККПА](../compliance/gdpr-dsr-office365.md) для получения сведений о том, как отвечать на коммутаторы DSR в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="965f5-139">See [Data Subject Requests for the GDPR and CCPA](../compliance/gdpr-dsr-office365.md) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="965f5-140">Управление удаленными пользователями в Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="965f5-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="965f5-141">Для Microsoft Stream, когда пользователь удаляется из Azure Active Directory (Azure AD), если его имя было связано с видеороликом до этой точки, их адрес электронной почты остается связанным с видеороликом.</span><span class="sxs-lookup"><span data-stu-id="965f5-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="965f5-142">Чтобы удалить из Microsoft Stream, обратитесь к разделу [Управление удаленными пользователями](https://docs.microsoft.com/stream/managing-deleted-users) .</span><span class="sxs-lookup"><span data-stu-id="965f5-142">See [Manage deleted users from Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) to remove it.</span></span>

## <a name="additional-investigative-tools"></a><span data-ttu-id="965f5-143">Дополнительные средства исследования</span><span class="sxs-lookup"><span data-stu-id="965f5-143">Additional investigative tools</span></span>

<span data-ttu-id="965f5-144">Ниже приведены два дополнительных средства, которые могут пригодиться для мониторинга, исследования и устранение в организации инцидентов, связанных с конфиденциальностью данных.</span><span class="sxs-lookup"><span data-stu-id="965f5-144">Here are two additional tools that might be useful for monitoring, investigating, and remediating data privacy-related incidents in your organization:</span></span>

- <span data-ttu-id="965f5-145">Функция "исследование [рисков" в microsoft 365](../compliance/insider-risk-management.md), которая позволяет свести к минимуму внутренний риск, позволяя обнаруживать, анализировать и принимать меры по рискованным действиям в Организации.</span><span class="sxs-lookup"><span data-stu-id="965f5-145">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md), a feature of the Microsoft Compliance admin center to help minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>
- <span data-ttu-id="965f5-146">Исследование [данных в microsoft 365](../compliance/overview-data-investigations.md), компонент центра администрирования соответствия требованиям Майкрософт для поиска конфиденциальных, нежелательных или некорректных данных в Microsoft 365, а затем проанализируйте, что произошло для выполнения соответствующих действий для исправления инцидента.</span><span class="sxs-lookup"><span data-stu-id="965f5-146">[Data investigations in Microsoft 365](../compliance/overview-data-investigations.md), a feature of the Microsoft Compliance admin center to search for sensitive, malicious, or misplaced data across Microsoft 365, and then investigate what happened to take the appropriate actions to remediate the incident.</span></span>
