---
title: Мониторинг и реагирование на инциденты конфиденциальности данных в организации
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 01/04/2021
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
description: Используйте политики аудита и оповещения и запросы субъектов данных для мониторинга инцидентов с личными данными и реагирования на них.
ms.openlocfilehash: 4070cd772d243bcfba33bfb164fd05e1f0911b3b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928428"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="8bbbf-103">Мониторинг и реагирование на инциденты конфиденциальности данных в организации</span><span class="sxs-lookup"><span data-stu-id="8bbbf-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="8bbbf-104">Функции Microsoft 365 доступны для мониторинга, расследования и реагирования на инциденты конфиденциальности данных в организации при работе с связанными возможностями.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="8bbbf-105">Наличие процессов, процедур и другой документации для каждого из них также может иметь важное значение для демонстрации соответствия нормативным органам.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="8bbbf-106">Такие законодательные акты перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-106">These include:</span></span> 

- <span data-ttu-id="8bbbf-107">Политики аудита и оповещения</span><span class="sxs-lookup"><span data-stu-id="8bbbf-107">Auditing and alert policies</span></span>
- <span data-ttu-id="8bbbf-108">Запросы субъекта данных (включая поиск контента и поиск электронных данных)</span><span class="sxs-lookup"><span data-stu-id="8bbbf-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="8bbbf-109">Дополнительные средства расследования и отчеты</span><span class="sxs-lookup"><span data-stu-id="8bbbf-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="8bbbf-110">Правила конфиденциальности данных, которые влияют на использование средств мониторинга и реагирования</span><span class="sxs-lookup"><span data-stu-id="8bbbf-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="8bbbf-111">Вот пример списка правил конфиденциальности данных, которые могут относиться к средствам управления информацией:</span><span class="sxs-lookup"><span data-stu-id="8bbbf-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="8bbbf-112">Статья 46 LGPD</span><span class="sxs-lookup"><span data-stu-id="8bbbf-112">LGPD Article 46</span></span>
- <span data-ttu-id="8bbbf-113">Статья 48 LGPD</span><span class="sxs-lookup"><span data-stu-id="8bbbf-113">LGPD Article 48</span></span>
- <span data-ttu-id="8bbbf-114">Статья GDPR (5)(1)(f)</span><span class="sxs-lookup"><span data-stu-id="8bbbf-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="8bbbf-115">Статья GDPR (15)(1)(e)</span><span class="sxs-lookup"><span data-stu-id="8bbbf-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="8bbbf-116">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="8bbbf-117">164.308(a)(1)(II)(D))</span><span class="sxs-lookup"><span data-stu-id="8bbbf-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="8bbbf-118">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="8bbbf-119">164.308(a)(6)(ii)</span><span class="sxs-lookup"><span data-stu-id="8bbbf-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="8bbbf-120">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="8bbbf-121">164.312 (b))</span><span class="sxs-lookup"><span data-stu-id="8bbbf-121">164.312(b))</span></span>
- <span data-ttu-id="8bbbf-122">CCPA (1798.105 (c))</span><span class="sxs-lookup"><span data-stu-id="8bbbf-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="8bbbf-123">Дополнительные сведения см. в [дополнительных сведениях: Оценка](information-protection-deploy-assess.md)рисков конфиденциальности данных и определение конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="8bbbf-124">Правила конфиденциальности данных, как правило, призывают к следующему мониторингу и реагированию:</span><span class="sxs-lookup"><span data-stu-id="8bbbf-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="8bbbf-125">Аудит, оповещение и отчеты о действиях, связанных с хранением, обменом и обработкой персональных данных.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="8bbbf-126">Возможность отвечать на запрос субъекта данных (DSR), а в некоторых случаях выполнять следственные и другие административные меры для выполнения таких запросов.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="8bbbf-127">Ваша организация может также выполнять действия по мониторингу и реагированию для других целей, например для других потребностей в соответствии с требованиям или по бизнес-причинам.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="8bbbf-128">Создание схемы мониторинга и реагирования на конфиденциальность данных должно быть сделано в рамках общего планирования мониторинга и реагирования, реализации и управления.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="8bbbf-129">Чтобы помочь вам начать работу с схемой мониторинга и реагирования в Microsoft 365 для правил конфиденциальности данных, в этой статье перечислены полезные возможности в Microsoft 365 для ответа на такие вопросы, как:</span><span class="sxs-lookup"><span data-stu-id="8bbbf-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="8bbbf-130">Какие методы мониторинга, расследования и отчетности доступны для различных типов и источников данных?</span><span class="sxs-lookup"><span data-stu-id="8bbbf-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="8bbbf-131">Какие механизмы будут необходимы для обработки запросов субъекта данных (DSRs) и любых исправлений, таких как анонимизация, исправление и удаление.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="8bbbf-132">Политики аудита и оповещения в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="8bbbf-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="8bbbf-133">Дополнительные политики аудита и оповещения см. в статьях:</span><span class="sxs-lookup"><span data-stu-id="8bbbf-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="8bbbf-134">Единый аудит</span><span class="sxs-lookup"><span data-stu-id="8bbbf-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="8bbbf-135">Аудит почтового ящика</span><span class="sxs-lookup"><span data-stu-id="8bbbf-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="8bbbf-136">Расширенный аудит</span><span class="sxs-lookup"><span data-stu-id="8bbbf-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="8bbbf-137">Политики оповещений</span><span class="sxs-lookup"><span data-stu-id="8bbbf-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="8bbbf-138">Запросы субъекта данных для GDPR и CCPA</span><span class="sxs-lookup"><span data-stu-id="8bbbf-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="8bbbf-139">Сведения об ответе на запросы субъекта данных для GDPR и [CCPA](/compliance/regulatory/gdpr-dsr-Office365) в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-139">See [Data Subject Requests for the GDPR and CCPA](/compliance/regulatory/gdpr-dsr-Office365) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="8bbbf-140">Управление удаленными пользователями в Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="8bbbf-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="8bbbf-141">Для Microsoft Stream, когда пользователь удаляется из Azure Active Directory (Azure AD), если его имя было связано с опубликованным видео Stream до этого момента, его адрес электронной почты остается связанным с видео.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="8bbbf-142">См. в этой записи Управление [удаленными пользователями из Microsoft Stream,](/stream/managing-deleted-users) чтобы удалить его.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-142">See [Manage deleted users from Microsoft Stream](/stream/managing-deleted-users) to remove it.</span></span>

## <a name="insider-risk-management-as-an-investigative-tool"></a><span data-ttu-id="8bbbf-143">Управление рисками в инсайдерской области в качестве средства расследования</span><span class="sxs-lookup"><span data-stu-id="8bbbf-143">Insider risk management as an investigative tool</span></span>

<span data-ttu-id="8bbbf-144">Управление рисками в [Microsoft 365](../compliance/insider-risk-management.md) — это функция центра администрирования соответствия требованиям Майкрософт, помогающая минимизировать внутренние риски, позволяя обнаруживать, исследовать и принимать меры по рискованным действиям в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8bbbf-144">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md) is a feature of the Microsoft Compliance admin center to help you minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>