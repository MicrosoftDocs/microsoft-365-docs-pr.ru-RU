---
title: Реагирование на инциденты безопасности
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/27/2018
audience: ITPro
ms.topic: overview
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Это решение сообщает вам, как могут выглядеть наиболее распространенные атаки на кибербезопасность в Microsoft 365 и как на них реагировать
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d37fb232b717485c40218fd8a3c3117ba9b8322b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287645"
---
# <a name="security-incident-response"></a><span data-ttu-id="74ac7-103">Реагирование на инциденты безопасности</span><span class="sxs-lookup"><span data-stu-id="74ac7-103">Security Incident Response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="74ac7-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="74ac7-104">**Applies to**</span></span>
- [<span data-ttu-id="74ac7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="74ac7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="74ac7-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="74ac7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="74ac7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74ac7-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

 <span data-ttu-id="74ac7-108">**Сводка:** Это решение сообщает, какие показатели являются индикаторами наиболее распространенных кибератак в Office 365, как положительно подтвердить любую заданную атаку и как реагировать на нее.</span><span class="sxs-lookup"><span data-stu-id="74ac7-108">**Summary:** This solution tells you what the indicators are for the most common cybersecurity attacks in Office 365, how to positively confirm any given attack, and how to respond to it.</span></span>

## <a name="learn-how-to-respond-to-cyberattacks"></a><span data-ttu-id="74ac7-109">Узнайте, как реагировать на кибератаки</span><span class="sxs-lookup"><span data-stu-id="74ac7-109">Learn how to respond to cyberattacks</span></span>

<span data-ttu-id="74ac7-110">Не все кибератаки можно предотвратить.</span><span class="sxs-lookup"><span data-stu-id="74ac7-110">Not all cyberattacks can be thwarted.</span></span> <span data-ttu-id="74ac7-111">Злоумышленники постоянно ищут новые слабые места в стратегии защиты или используют старые.</span><span class="sxs-lookup"><span data-stu-id="74ac7-111">Attackers are constantly looking for new weaknesses in your defensive strategy or they are exploiting old ones.</span></span> <span data-ttu-id="74ac7-112">Знание того, как распознать атаку, позволяет быстрее реагировать на нее, что сокращает продолжительность инцидента безопасности.</span><span class="sxs-lookup"><span data-stu-id="74ac7-112">Knowing how to recognize an attack allows you to respond to it faster, which shortens the duration of the security incident.</span></span>

<span data-ttu-id="74ac7-113">Эта серия статей поможет вам понять, как может выглядеть определенный тип атаки в Microsoft 365, и поможет вам предпринять определенные действия для реагирования.</span><span class="sxs-lookup"><span data-stu-id="74ac7-113">This series of article helps you understand what a particular type of attack might look like in Microsoft 365 and gives you steps you can take to respond.</span></span> <span data-ttu-id="74ac7-114">Они являются краткими точками входа для понимания:</span><span class="sxs-lookup"><span data-stu-id="74ac7-114">They are quick entry points to understanding:</span></span>

- <span data-ttu-id="74ac7-115">Что такое атака и как она работает.</span><span class="sxs-lookup"><span data-stu-id="74ac7-115">What the attack is and how it works.</span></span>

- <span data-ttu-id="74ac7-116">Какие знаки, называемые индикаторами компрометации (IOC), искать и как их искать.</span><span class="sxs-lookup"><span data-stu-id="74ac7-116">What signs, called indicators of compromise (IOC), to look for and how to look for them.</span></span>

- <span data-ttu-id="74ac7-117">Как положительно подтвердить атаку.</span><span class="sxs-lookup"><span data-stu-id="74ac7-117">How to positively confirm the attack.</span></span>

- <span data-ttu-id="74ac7-118">Действия, которые необходимо предпринять, чтобы отсечь атаки и улучшить защиту вашей организации в будущем.</span><span class="sxs-lookup"><span data-stu-id="74ac7-118">Steps to take to cut off the attack and better protect your organization in the future.</span></span>

- <span data-ttu-id="74ac7-119">Ссылки на подробную информацию по каждому типу атаки.</span><span class="sxs-lookup"><span data-stu-id="74ac7-119">Links to in-depth information on each attack type.</span></span>

<span data-ttu-id="74ac7-120">По мере того, как со временем будут добавляться дополнительные статьи, ознакомьтесь с этой статьей ежемесячно.</span><span class="sxs-lookup"><span data-stu-id="74ac7-120">Check back here monthly as more articles will be added over time.</span></span>

## <a name="detect-and-remediate-articles"></a><span data-ttu-id="74ac7-121">Обнаружение и исправление статей</span><span class="sxs-lookup"><span data-stu-id="74ac7-121">Detect and remediate articles</span></span>

- [<span data-ttu-id="74ac7-122">Обнаружение случаев незаконного предоставления разрешений и устранение их последствий в Office 365</span><span class="sxs-lookup"><span data-stu-id="74ac7-122">Detect and Remediate Illicit Consent Grants in Office 365</span></span>](detect-and-remediate-illicit-consent-grants.md)

- [<span data-ttu-id="74ac7-123">Обнаружение атак с внедрением правил и пользовательских форм Outlook и устранение их последствий в Office 365</span><span class="sxs-lookup"><span data-stu-id="74ac7-123">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

## <a name="incident-response-articles"></a><span data-ttu-id="74ac7-124">Статьи об реагировании на инциденты</span><span class="sxs-lookup"><span data-stu-id="74ac7-124">Incident response articles</span></span>

- [<span data-ttu-id="74ac7-125">Реагирование на компрометацию учетной записи электронной почты в Office 365</span><span class="sxs-lookup"><span data-stu-id="74ac7-125">Responding to a Compromised Email Account in Office 365</span></span>](responding-to-a-compromised-email-account.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="74ac7-126">Защитите Microsoft 365 на профессиональном уровне</span><span class="sxs-lookup"><span data-stu-id="74ac7-126">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="74ac7-127">Для вашей подписки Microsoft 365 предусмотрен целый ряд полезных функций безопасности, которые можно использовать для защиты ваших данных и пользователей.</span><span class="sxs-lookup"><span data-stu-id="74ac7-127">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="74ac7-128">Воспользуйтесь стратегией безопасности Microsoft 365 : первые приоритеты на [первые 30, 90](security-roadmap.md) и более дней, чтобы реализовать рекомендуемые корпорацией Майкрософт рекомендации по обеспечению безопасности вашей организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74ac7-128">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 organization.</span></span>

- <span data-ttu-id="74ac7-129">Задачи для выполнения в первые 30 дней.</span><span class="sxs-lookup"><span data-stu-id="74ac7-129">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="74ac7-130">Они дают немедленный эффект и не создают помех вашим пользователям.</span><span class="sxs-lookup"><span data-stu-id="74ac7-130">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="74ac7-131">Задачи для выполнения в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="74ac7-131">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="74ac7-132">На их планирование и реализацию уйма времени, но значительно повышается уровень безопасности.</span><span class="sxs-lookup"><span data-stu-id="74ac7-132">These take a bit more time to plan and implement but greatly improve your security posture</span></span>

- <span data-ttu-id="74ac7-133">Более 90 дней.</span><span class="sxs-lookup"><span data-stu-id="74ac7-133">Beyond 90 days.</span></span> <span data-ttu-id="74ac7-134">Эти меры дополняют ваши действия в течение первых 90 дней.</span><span class="sxs-lookup"><span data-stu-id="74ac7-134">These enhancements build in your first 90 days work.</span></span>
