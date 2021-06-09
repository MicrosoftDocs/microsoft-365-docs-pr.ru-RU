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
description: При Advanced eDiscovery анализе потоки электронной почты анализирует беседу по электронной почте и разделяет каждое сообщение на разные категории.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285565"
---
# <a name="email-threading-in-advanced-ediscovery"></a><span data-ttu-id="4a7cd-103">Потоки электронной почты в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="4a7cd-103">Email threading in Advanced eDiscovery</span></span>

<span data-ttu-id="4a7cd-104">Рассмотрим беседу по электронной почте, которая уже некоторое время идет.</span><span class="sxs-lookup"><span data-stu-id="4a7cd-104">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="4a7cd-105">В большинстве случаев последняя электронная почта в потоке будет включать содержимое всех предыдущих сообщений; Просмотр последнего сообщения электронной почты даст полный контекст беседы, которая произошла в потоке.</span><span class="sxs-lookup"><span data-stu-id="4a7cd-105">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="4a7cd-106">Потоки электронной почты определяют такие сообщения, чтобы рецензенты могли просмотреть часть собранных документов без потери контекста.</span><span class="sxs-lookup"><span data-stu-id="4a7cd-106">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="4a7cd-107">Что делает поток электронной почты?</span><span class="sxs-lookup"><span data-stu-id="4a7cd-107">What does email threading do?</span></span>

<span data-ttu-id="4a7cd-108">Потоковая отправка электронной почты разборка каждой электронной почты и ее деконструктивация для отдельных сообщений; каждое сообщение — это цепочка отдельных сообщений.</span><span class="sxs-lookup"><span data-stu-id="4a7cd-108">Email threading parses each email and deconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="4a7cd-109">Затем он анализирует все сообщения электронной почты в наборе отзывов, чтобы определить, имеет ли электронная почта уникальное содержимое или цепочка полностью содержится в другом сообщении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4a7cd-109">Then, it analyzes all emails in the review set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="4a7cd-110">В итоге сообщения электронной почты делятся на четыре категории:</span><span class="sxs-lookup"><span data-stu-id="4a7cd-110">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="4a7cd-111">**Инклюзивное**: последнее сообщение электронной почты содержит уникальное содержимое, а также все вложения, которые были включены в другие сообщения электронной почты, содержимое которых полностью содержится в этом сообщении.</span><span class="sxs-lookup"><span data-stu-id="4a7cd-111">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="4a7cd-112">**Полное сообщение без вложения**: последнее сообщение электронной почты содержит уникальное содержимое, но не содержит некоторых вложений, которые были включены в другие сообщения электронной почты, содержимое которых полностью содержится в этом сообщении.</span><span class="sxs-lookup"><span data-stu-id="4a7cd-112">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="4a7cd-113">**Инклюзивная копия**: точная копия инклюзивного сообщения или полного сообщения без вложения.</span><span class="sxs-lookup"><span data-stu-id="4a7cd-113">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="4a7cd-114">**Отсутствует**: содержимое этого сообщения электронной почты полностью содержится по крайней мере в одном сообщении электронной почты, помеченном как инклюзивное сообщение или полное сообщение без вложения.</span><span class="sxs-lookup"><span data-stu-id="4a7cd-114">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="4a7cd-115">Чем он отличается от бесед в Outlook?</span><span class="sxs-lookup"><span data-stu-id="4a7cd-115">How is it different from conversations in Outlook?</span></span>

<span data-ttu-id="4a7cd-116">На первый взгляд это похоже на группы бесед в Outlook.</span><span class="sxs-lookup"><span data-stu-id="4a7cd-116">At a glance, this sounds similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="4a7cd-117">Однако существуют некоторые важные различия.</span><span class="sxs-lookup"><span data-stu-id="4a7cd-117">However, there are some important distinctions.</span></span> <span data-ttu-id="4a7cd-118">Рассмотрим беседу по электронной почте, которая была развяна в два разговора; например, кто-то ответил на сообщение электронной почты, которое не является последним в беседе, поэтому два последних сообщения в беседе имеют уникальный контент.</span><span class="sxs-lookup"><span data-stu-id="4a7cd-118">Consider an email conversation that got forked into two conversations; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="4a7cd-119">Outlook все равно сгруппив электронные письма в один разговор; чтение только последнего сообщения будет означать отсутствие контекста последней электронной почты, которая также содержит уникальный контент.</span><span class="sxs-lookup"><span data-stu-id="4a7cd-119">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="4a7cd-120">Так как потоки электронной почты сравнивают каждую электронную почту в отдельные компоненты и сравнивают их, потоки электронной почты будут отмечать оба последних сообщения как инклюзивные, гарантируя, что вы не пропустите контекст до тех пор, пока вы читаете все электронные письма, отмеченные как инклюзивные.</span><span class="sxs-lookup"><span data-stu-id="4a7cd-120">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusive, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>
