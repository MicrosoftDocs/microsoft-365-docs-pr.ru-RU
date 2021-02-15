---
title: Отслеживание инцидентов конфиденциальности данных в организации и реагирование на них
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
description: Используйте политики аудита и оповещений, а также запросы субъектов данных для отслеживания инцидентов персональных данных и реагирования на них.
ms.openlocfilehash: 3ae0f2a6528f6188500c7cee7732c6447013eaa6
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749591"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a><span data-ttu-id="a5314-103">Отслеживание инцидентов конфиденциальности данных в организации и реагирование на них</span><span class="sxs-lookup"><span data-stu-id="a5314-103">Monitor and respond to data privacy incidents in your organization</span></span>

<span data-ttu-id="a5314-104">Функции Microsoft 365 помогают отслеживать, исследовать инциденты конфиденциальности данных в вашей организации и реагировать на них при эксплуатации связанных возможностей.</span><span class="sxs-lookup"><span data-stu-id="a5314-104">Microsoft 365 features are available to help you monitor, investigate, and respond to data privacy incidents in your organization as you operationalize related capabilities.</span></span> <span data-ttu-id="a5314-105">Процессы, процедуры и другая документация для каждого из них также могут быть важны для демонстрации соответствия нормативным органам.</span><span class="sxs-lookup"><span data-stu-id="a5314-105">Having processes, procedures, and other documentation for each of these may also be important to demonstrate compliance to regulatory bodies.</span></span>

<span data-ttu-id="a5314-106">Такие законодательные акты перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="a5314-106">These include:</span></span> 

- <span data-ttu-id="a5314-107">Политики аудита и оповещений</span><span class="sxs-lookup"><span data-stu-id="a5314-107">Auditing and alert policies</span></span>
- <span data-ttu-id="a5314-108">Запросы субъектов данных (включая поиск контента и eDiscovery)</span><span class="sxs-lookup"><span data-stu-id="a5314-108">Data subject requests (including content search and eDiscovery)</span></span>
- <span data-ttu-id="a5314-109">Дополнительные средства анализа и отчетность</span><span class="sxs-lookup"><span data-stu-id="a5314-109">Additional investigative tools and reporting</span></span>

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a><span data-ttu-id="a5314-110">Правила конфиденциальности данных, которые влияют на использование средств мониторинга и реагирования</span><span class="sxs-lookup"><span data-stu-id="a5314-110">Data privacy regulations impacting the use of monitoring and response tools</span></span>

<span data-ttu-id="a5314-111">Вот пример правил конфиденциальности данных, которые могут относиться к средствам управления информацией:</span><span class="sxs-lookup"><span data-stu-id="a5314-111">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="a5314-112">Статья 46, посвященная LGPD</span><span class="sxs-lookup"><span data-stu-id="a5314-112">LGPD Article 46</span></span>
- <span data-ttu-id="a5314-113">Статья 48, посвященная LGPD</span><span class="sxs-lookup"><span data-stu-id="a5314-113">LGPD Article 48</span></span>
- <span data-ttu-id="a5314-114">Статья GDPR (5)(1)(f)</span><span class="sxs-lookup"><span data-stu-id="a5314-114">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="a5314-115">Статья GDPR (15)(1)(e)</span><span class="sxs-lookup"><span data-stu-id="a5314-115">GDPR Article (15)(1)(e)</span></span>
- <span data-ttu-id="a5314-116">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="a5314-116">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="a5314-117">164.308(a)(1)(ii)(D))</span><span class="sxs-lookup"><span data-stu-id="a5314-117">164.308(a)(1)(ii)(D))</span></span>
- <span data-ttu-id="a5314-118">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="a5314-118">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="a5314-119">164.308(a)(6)(ii)</span><span class="sxs-lookup"><span data-stu-id="a5314-119">164.308(a)(6)(ii)</span></span>
- <span data-ttu-id="a5314-120">HIPAA-HITECH (45 C.F.R.</span><span class="sxs-lookup"><span data-stu-id="a5314-120">HIPAA-HITECH (45 C.F.R.</span></span> <span data-ttu-id="a5314-121">164.312(b))</span><span class="sxs-lookup"><span data-stu-id="a5314-121">164.312(b))</span></span>
- <span data-ttu-id="a5314-122">CCPA (1798.105(c))</span><span class="sxs-lookup"><span data-stu-id="a5314-122">CCPA (1798.105(c))</span></span>

<span data-ttu-id="a5314-123">Дополнительные сведения см. в теме "Оценка рисков [конфиденциальности данных и идентификация конфиденциальной информации".](information-protection-deploy-assess.md)</span><span class="sxs-lookup"><span data-stu-id="a5314-123">For more information, see [Assess data privacy risks and identify sensitive information](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="a5314-124">Нормативы конфиденциальности данных обычно вызовите следующие требования для мониторинга и реагирования:</span><span class="sxs-lookup"><span data-stu-id="a5314-124">The data privacy regulations generally call for the following for monitoring and response:</span></span>

- <span data-ttu-id="a5314-125">Аудит, оповещение и отчетность по действиям, связанным с хранением, совместным использованием и обработкой персональных данных</span><span class="sxs-lookup"><span data-stu-id="a5314-125">Auditing, alerting, and reporting for activities related to the storage, sharing and processing of personal data</span></span>
- <span data-ttu-id="a5314-126">Возможность отвечать на запрос субъекта данных (DSR), а в некоторых случаях выполнять расследования и другие административные меры в соответствии с такими запросами.</span><span class="sxs-lookup"><span data-stu-id="a5314-126">The ability to respond to a data subject request (DSR) and in some cases, perform investigative and other administrative measures to comply with such requests.</span></span>

<span data-ttu-id="a5314-127">Вашей организации также может потребоваться выполнять действия по мониторингу и реагированию на них для других целей, таких как другие потребности в соответствии с соответствием требованиям или бизнес-причины.</span><span class="sxs-lookup"><span data-stu-id="a5314-127">Your organization may also wish to perform monitoring and response activities for other purposes, such as other compliance needs or for business reasons.</span></span> <span data-ttu-id="a5314-128">Создание схемы мониторинга и реагирования на конфиденциальность данных должно быть сделано в рамках общего планирования мониторинга и реагирования, внедрения и управления.</span><span class="sxs-lookup"><span data-stu-id="a5314-128">Establishing your monitoring and response scheme for data privacy should be done as part of overall monitoring and response planning, implementation, and management.</span></span>

<span data-ttu-id="a5314-129">Чтобы помочь вам начать работу со схемой мониторинга и реагирования в Microsoft 365 для нормативов конфиденциальности данных, в этой статье перечислены полезные возможности Microsoft 365 для ответа на такие вопросы, как:</span><span class="sxs-lookup"><span data-stu-id="a5314-129">To help you get started with a monitoring and response scheme in Microsoft 365 for data privacy regulations, this article lists useful capabilities in Microsoft 365 to answer questions such as:</span></span> 

- <span data-ttu-id="a5314-130">Какие методы ежедневного мониторинга, анализа и отчетности доступны для различных типов данных и источников?</span><span class="sxs-lookup"><span data-stu-id="a5314-130">What sort of day-to-day monitoring, investigative and reporting techniques are available for the different data types and sources?</span></span>
- <span data-ttu-id="a5314-131">Какие механизмы будут необходимы для обработки запросов субъектов данных (DSRS) и любых исправлений, таких как анонимизация, исправление и удаление.</span><span class="sxs-lookup"><span data-stu-id="a5314-131">What mechanisms will be needed to handle data subject requests (DSRs) and any remedial actions, such as anonymization, redaction, and deletion.</span></span>

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a><span data-ttu-id="a5314-132">Политики аудита и оповещений в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="a5314-132">Auditing and Alert Policies in the Security and Compliance Center</span></span>

<span data-ttu-id="a5314-133">В этих статьях вы можете узнать, как настраивать аудит, расширенный аудит и политики оповещений:</span><span class="sxs-lookup"><span data-stu-id="a5314-133">See these articles for setting up auditing, advanced auditing, and alert policies:</span></span>

- [<span data-ttu-id="a5314-134">Единый аудит</span><span class="sxs-lookup"><span data-stu-id="a5314-134">Unified auditing</span></span>](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [<span data-ttu-id="a5314-135">Аудит почтового ящика</span><span class="sxs-lookup"><span data-stu-id="a5314-135">Mailbox auditing</span></span>](../compliance/enable-mailbox-auditing.md)
- [<span data-ttu-id="a5314-136">Расширенный аудит</span><span class="sxs-lookup"><span data-stu-id="a5314-136">Advanced audit</span></span>](../compliance/advanced-audit.md)
- [<span data-ttu-id="a5314-137">Политики оповещений</span><span class="sxs-lookup"><span data-stu-id="a5314-137">Alert policies</span></span>](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="a5314-138">Запросы субъектов данных в GDPR и CCPA</span><span class="sxs-lookup"><span data-stu-id="a5314-138">Data subject requests for the GDPR and CCPA</span></span>

<span data-ttu-id="a5314-139">Сведения о реагировании на DSR в Microsoft 365 см. в запросах субъектов данных в GDPR и [CCPA.](../compliance/gdpr-dsr-office365.md)</span><span class="sxs-lookup"><span data-stu-id="a5314-139">See [Data Subject Requests for the GDPR and CCPA](../compliance/gdpr-dsr-office365.md) for information on responding to a DSR in Microsoft 365.</span></span>

## <a name="manage-deleted-users-in-microsoft-stream"></a><span data-ttu-id="a5314-140">Управление удаленными пользователями в Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="a5314-140">Manage deleted users in Microsoft Stream</span></span>

<span data-ttu-id="a5314-141">Для Microsoft Stream, когда пользователь удаляется из Azure Active Directory (Azure AD), если его имя было связано с опубликованным видео Stream до этого момента, его адрес электронной почты остается связанным с видео.</span><span class="sxs-lookup"><span data-stu-id="a5314-141">For Microsoft Stream, when a user is deleted from Azure Active Directory (Azure AD), if their name was associated with a posted Stream video prior to that point, their email address remains associated with the video.</span></span> <span data-ttu-id="a5314-142">См. ["Управление удаленными пользователями из Microsoft Stream",](https://docs.microsoft.com/stream/managing-deleted-users) чтобы удалить его.</span><span class="sxs-lookup"><span data-stu-id="a5314-142">See [Manage deleted users from Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) to remove it.</span></span>

## <a name="insider-risk-management-as-an-investigative-tool"></a><span data-ttu-id="a5314-143">Управление рисками внутри организации в качестве средства анализа</span><span class="sxs-lookup"><span data-stu-id="a5314-143">Insider risk management as an investigative tool</span></span>

<span data-ttu-id="a5314-144">Управление внутренними рисками в [Microsoft 365](../compliance/insider-risk-management.md) — это функция Центра администрирования соответствия требованиям Майкрософт, помогающая свести к минимуму внутренний риск, позволяя обнаруживать, исследовать и принимать меры в отношении рискованных действий в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a5314-144">[Insider risk management in Microsoft 365](../compliance/insider-risk-management.md) is a feature of the Microsoft Compliance admin center to help you minimize internal risk by enabling you to detect, investigate, and take action on risky activities in your organization.</span></span>
