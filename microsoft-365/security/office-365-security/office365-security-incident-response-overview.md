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
description: В этом решении рассказывается, как могут выглядеть наиболее распространенные атаки кибербезопасности в Microsoft 365 и как на них реагировать
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65ff75253f45ae2d0f051dafe73c6e665f89827a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205873"
---
# <a name="security-incident-response"></a><span data-ttu-id="12769-103">Реагирование на инциденты безопасности</span><span class="sxs-lookup"><span data-stu-id="12769-103">Security Incident Response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="12769-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="12769-104">**Applies to**</span></span>
- [<span data-ttu-id="12769-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="12769-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="12769-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="12769-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="12769-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="12769-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

 <span data-ttu-id="12769-108">**Сводка:** В этом решении рассказывается, какие показатели являются для наиболее распространенных атак кибербезопасности в Office 365, как положительно подтвердить любую заданную атаку и как реагировать на нее.</span><span class="sxs-lookup"><span data-stu-id="12769-108">**Summary:** This solution tells you what the indicators are for the most common cybersecurity attacks in Office 365, how to positively confirm any given attack, and how to respond to it.</span></span>

## <a name="learn-how-to-respond-to-cyberattacks"></a><span data-ttu-id="12769-109">Узнайте, как реагировать на кибератаки</span><span class="sxs-lookup"><span data-stu-id="12769-109">Learn how to respond to cyberattacks</span></span>

<span data-ttu-id="12769-110">Не все кибератаки можно предотвратить.</span><span class="sxs-lookup"><span data-stu-id="12769-110">Not all cyberattacks can be thwarted.</span></span> <span data-ttu-id="12769-111">Злоумышленники постоянно ищут новые слабые места в вашей оборонительной стратегии или используют старые.</span><span class="sxs-lookup"><span data-stu-id="12769-111">Attackers are constantly looking for new weaknesses in your defensive strategy or they are exploiting old ones.</span></span> <span data-ttu-id="12769-112">Знание того, как распознать атаку, позволяет быстрее реагировать на нее, что сокращает продолжительность инцидента с безопасностью.</span><span class="sxs-lookup"><span data-stu-id="12769-112">Knowing how to recognize an attack allows you to respond to it faster, which shortens the duration of the security incident.</span></span>

<span data-ttu-id="12769-113">В этой серии статей вы сможете понять, как может выглядеть атака определенного типа в Microsoft 365, и вы сможете предпринять шаги для ответа.</span><span class="sxs-lookup"><span data-stu-id="12769-113">This series of article helps you understand what a particular type of attack might look like in Microsoft 365 and gives you steps you can take to respond.</span></span> <span data-ttu-id="12769-114">Они являются быстрыми точками входа к пониманию:</span><span class="sxs-lookup"><span data-stu-id="12769-114">They are quick entry points to understanding:</span></span>

- <span data-ttu-id="12769-115">Что такое атака и как она работает.</span><span class="sxs-lookup"><span data-stu-id="12769-115">What the attack is and how it works.</span></span>

- <span data-ttu-id="12769-116">Какие знаки, называемые индикаторами компромисса (МОК), искать и как их искать.</span><span class="sxs-lookup"><span data-stu-id="12769-116">What signs, called indicators of compromise (IOC), to look for and how to look for them.</span></span>

- <span data-ttu-id="12769-117">Как положительно подтвердить атаку.</span><span class="sxs-lookup"><span data-stu-id="12769-117">How to positively confirm the attack.</span></span>

- <span data-ttu-id="12769-118">Меры, которые необходимо предпринять, чтобы отрезать атаку и лучше защитить организацию в будущем.</span><span class="sxs-lookup"><span data-stu-id="12769-118">Steps to take to cut off the attack and better protect your organization in the future.</span></span>

- <span data-ttu-id="12769-119">Ссылки на углубленные сведения по каждому типу атаки.</span><span class="sxs-lookup"><span data-stu-id="12769-119">Links to in-depth information on each attack type.</span></span>

<span data-ttu-id="12769-120">Проверьте здесь ежемесячно, как больше статей будут добавлены с течением времени.</span><span class="sxs-lookup"><span data-stu-id="12769-120">Check back here monthly as more articles will be added over time.</span></span>

## <a name="detect-and-remediate-articles"></a><span data-ttu-id="12769-121">Обнаружение и исправление статей</span><span class="sxs-lookup"><span data-stu-id="12769-121">Detect and remediate articles</span></span>

- [<span data-ttu-id="12769-122">Обнаружение случаев незаконного предоставления разрешений и устранение их последствий в Office 365</span><span class="sxs-lookup"><span data-stu-id="12769-122">Detect and Remediate Illicit Consent Grants in Office 365</span></span>](detect-and-remediate-illicit-consent-grants.md)

- [<span data-ttu-id="12769-123">Обнаружение атак с внедрением правил и пользовательских форм Outlook и устранение их последствий в Office 365</span><span class="sxs-lookup"><span data-stu-id="12769-123">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

## <a name="incident-response-articles"></a><span data-ttu-id="12769-124">Статьи реагирования на инциденты</span><span class="sxs-lookup"><span data-stu-id="12769-124">Incident response articles</span></span>

- [<span data-ttu-id="12769-125">Реагирование на компрометацию учетной записи электронной почты в Office 365</span><span class="sxs-lookup"><span data-stu-id="12769-125">Responding to a Compromised Email Account in Office 365</span></span>](responding-to-a-compromised-email-account.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="12769-126">Защитите Microsoft 365 на профессиональном уровне</span><span class="sxs-lookup"><span data-stu-id="12769-126">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="12769-127">Для вашей подписки Microsoft 365 предусмотрен целый ряд полезных функций безопасности, которые можно использовать для защиты ваших данных и пользователей.</span><span class="sxs-lookup"><span data-stu-id="12769-127">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="12769-128">Используйте дорожную карту безопасности Microsoft 365 — главные приоритеты в течение первых [30 дней, 90](security-roadmap.md) дней и далее, чтобы реализовать рекомендации Корпорации Майкрософт по обеспечению безопасности организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="12769-128">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 organization.</span></span>

- <span data-ttu-id="12769-129">Задачи для выполнения в первые 30 дней.</span><span class="sxs-lookup"><span data-stu-id="12769-129">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="12769-130">Они дают немедленный эффект и не создают помех вашим пользователям.</span><span class="sxs-lookup"><span data-stu-id="12769-130">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="12769-131">Задачи для выполнения в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="12769-131">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="12769-132">На планирование и реализацию этих действий уйма времени, но значительно улучшится ваша осанка безопасности.</span><span class="sxs-lookup"><span data-stu-id="12769-132">These take a bit more time to plan and implement but greatly improve your security posture</span></span>

- <span data-ttu-id="12769-133">Более 90 дней.</span><span class="sxs-lookup"><span data-stu-id="12769-133">Beyond 90 days.</span></span> <span data-ttu-id="12769-134">Эти меры дополняют ваши действия в течение первых 90 дней.</span><span class="sxs-lookup"><span data-stu-id="12769-134">These enhancements build in your first 90 days work.</span></span>
