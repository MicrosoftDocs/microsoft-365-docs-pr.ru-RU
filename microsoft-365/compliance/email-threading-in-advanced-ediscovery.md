---
title: Потоки электронной почты в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: При проведении анализа Advanced eDiscovery потоки электронной почты анализирует беседу по электронной почте и разделяет каждое сообщение на разные категории.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285565"
---
# <a name="email-threading-in-advanced-ediscovery"></a><span data-ttu-id="d46f4-103">Потоки электронной почты в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d46f4-103">Email threading in Advanced eDiscovery</span></span>

<span data-ttu-id="d46f4-104">Рассмотрим беседу по электронной почте, которая идет уже некоторое время.</span><span class="sxs-lookup"><span data-stu-id="d46f4-104">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="d46f4-105">В большинстве случаев последнее сообщение электронной почты в потоке будет включать содержимое всех предыдущих сообщений; просмотр последнего сообщения электронной почты даст полный контекст беседы, которая произошла в потоке.</span><span class="sxs-lookup"><span data-stu-id="d46f4-105">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="d46f4-106">Потоки электронной почты определяют такие сообщения электронной почты, чтобы проверяющие могли просмотреть часть собранных документов без потери контекста.</span><span class="sxs-lookup"><span data-stu-id="d46f4-106">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="d46f4-107">Что делает потоки электронной почты?</span><span class="sxs-lookup"><span data-stu-id="d46f4-107">What does email threading do?</span></span>

<span data-ttu-id="d46f4-108">Потоки электронной почты разбирают каждое сообщение и декодирует его для отдельных сообщений; каждое сообщение электронной почты является цепочкой отдельных сообщений.</span><span class="sxs-lookup"><span data-stu-id="d46f4-108">Email threading parses each email and deconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="d46f4-109">Затем он анализирует все сообщения электронной почты в наборе для проверки, чтобы определить, содержит ли сообщение уникальное содержимое или находится ли цепочка полностью в другом сообщении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d46f4-109">Then, it analyzes all emails in the review set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="d46f4-110">В конце сообщения электронной почты делятся на четыре категории:</span><span class="sxs-lookup"><span data-stu-id="d46f4-110">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="d46f4-111">Включительно: последнее сообщение электронной почты содержит уникальное содержимое, а все вложения были включены в другие сообщения электронной почты, содержимое которых полностью содержится в этом сообщении.</span><span class="sxs-lookup"><span data-stu-id="d46f4-111">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="d46f4-112">Инклюзивный минус : последнее сообщение в сообщении электронной почты содержит уникальное содержимое, но оно не содержит некоторые вложения, которые были включены в другие сообщения электронной почты, содержимое которых полностью содержится в этом сообщении.</span><span class="sxs-lookup"><span data-stu-id="d46f4-112">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="d46f4-113">**Инклюзивная** копия: точную копию инклюзивного/включительно за вычетом электронной почты</span><span class="sxs-lookup"><span data-stu-id="d46f4-113">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="d46f4-114">**Нет.** Содержимое этого сообщения электронной почты полностью содержится по крайней мере в одном сообщении электронной почты, которое помечено как инклюзивное/инклюзивное минус.</span><span class="sxs-lookup"><span data-stu-id="d46f4-114">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="d46f4-115">Чем он отличается от бесед в Outlook?</span><span class="sxs-lookup"><span data-stu-id="d46f4-115">How is it different from conversations in Outlook?</span></span>

<span data-ttu-id="d46f4-116">С первого взгляда это похоже на группировку бесед в Outlook.</span><span class="sxs-lookup"><span data-stu-id="d46f4-116">At a glance, this sounds similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="d46f4-117">Однако существуют некоторые важные различия.</span><span class="sxs-lookup"><span data-stu-id="d46f4-117">However, there are some important distinctions.</span></span> <span data-ttu-id="d46f4-118">Рассмотрим беседу по электронной почте, которая была разорвна в две беседы; Например, кто-то ответил на сообщение электронной почты, которое не является последним в беседе, поэтому два последних сообщения в беседе имеют уникальное содержимое.</span><span class="sxs-lookup"><span data-stu-id="d46f4-118">Consider an email conversation that got forked into two conversations; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="d46f4-119">Outlook по-прежнему сгруппал бы сообщения электронной почты в одну беседу; чтение только последнего сообщения электронной почты означает отсутствие контекста последнего сообщения, которое также содержит уникальное содержимое.</span><span class="sxs-lookup"><span data-stu-id="d46f4-119">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="d46f4-120">Так как потоки электронной почты разностят каждое сообщение на отдельные компоненты и сравнивают их, потоки электронной почты помечают оба последних сообщения как включительно, гарантируя, что вы не пропустите контекст, пока читаете все сообщения, помеченные как включительно.</span><span class="sxs-lookup"><span data-stu-id="d46f4-120">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusive, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>
