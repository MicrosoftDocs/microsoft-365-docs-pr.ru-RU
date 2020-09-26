---
title: Почтовые потоки в Advanced eDiscovery
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
description: При проведении расширенного анализа обнаружения электронных данных почтовые потоки анализируют электронную беседу и разделяют каждое сообщение на разные категории.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285565"
---
# <a name="email-threading-in-advanced-ediscovery"></a><span data-ttu-id="249a2-103">Почтовые потоки в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="249a2-103">Email threading in Advanced eDiscovery</span></span>

<span data-ttu-id="249a2-104">Рассмотрим беседу по электронной почте в течение определенного сеанса.</span><span class="sxs-lookup"><span data-stu-id="249a2-104">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="249a2-105">В большинстве случаев последняя электронная почта в потоке будет включать содержимое всех предшествующих сообщений. Просмотр последней электронной почты дает полный контекст беседы, возникшей в цепочке.</span><span class="sxs-lookup"><span data-stu-id="249a2-105">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="249a2-106">Поток электронной почты определяет такие сообщения электронной почты, чтобы проверяющие могли просматривать долю собранных документов без потери контекста.</span><span class="sxs-lookup"><span data-stu-id="249a2-106">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="249a2-107">Что делает почтовые потоки?</span><span class="sxs-lookup"><span data-stu-id="249a2-107">What does email threading do?</span></span>

<span data-ttu-id="249a2-108">Цепочка электронной почты анализирует каждое сообщение электронной почты и создает их для отдельных сообщений; Каждое сообщение электронной почты представляет собой цепочку отдельных сообщений.</span><span class="sxs-lookup"><span data-stu-id="249a2-108">Email threading parses each email and deconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="249a2-109">Затем он анализирует все сообщения электронной почты в наборе проверки, чтобы определить, имеет ли электронная почта уникальный контент или находится ли цепочка полностью в другом сообщении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="249a2-109">Then, it analyzes all emails in the review set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="249a2-110">В конечной почте разделяются четыре категории:</span><span class="sxs-lookup"><span data-stu-id="249a2-110">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="249a2-111">**Включительно**: Последнее сообщение в сообщении содержит уникальный контент, а в электронной почте есть все вложения, включенные в другие сообщения электронной почты, содержимое которых полностью содержалось в этом сообщении.</span><span class="sxs-lookup"><span data-stu-id="249a2-111">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="249a2-112">**Включительно**: Последнее сообщение в сообщении содержит уникальный контент, но в электронной почте нет некоторых вложений, включенных в другие сообщения электронной почты, содержимое которых полностью содержалось в этом сообщении.</span><span class="sxs-lookup"><span data-stu-id="249a2-112">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="249a2-113">**Инклюзивная копия**: Точная копия инклюзивного/инклюзивного минуса электронной почты</span><span class="sxs-lookup"><span data-stu-id="249a2-113">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="249a2-114">**None**: содержимое этого сообщения полностью содержаться по крайней мере в одном сообщении, помеченном как инклюзивное/инклюзивное минус.</span><span class="sxs-lookup"><span data-stu-id="249a2-114">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="249a2-115">Чем она отличается от бесед в Outlook?</span><span class="sxs-lookup"><span data-stu-id="249a2-115">How is it different from conversations in Outlook?</span></span>

<span data-ttu-id="249a2-116">Это звучит аналогично группам бесед в Outlook.</span><span class="sxs-lookup"><span data-stu-id="249a2-116">At a glance, this sounds similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="249a2-117">Однако существует несколько важных отличительных моментов.</span><span class="sxs-lookup"><span data-stu-id="249a2-117">However, there are some important distinctions.</span></span> <span data-ttu-id="249a2-118">Рассмотрим беседу по электронной почте, которая разбивается на две беседы; Например, кто-то ответил на сообщение электронной почты, которое не является последним в беседе, поэтому последние два сообщения в беседе имеют уникальный контент.</span><span class="sxs-lookup"><span data-stu-id="249a2-118">Consider an email conversation that got forked into two conversations; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="249a2-119">Outlook по-прежнему будет группировать сообщения в один сеанс; при чтении только последней электронной почты отсутствует контекст второй и последней электронной почты, который также содержит уникальный контент.</span><span class="sxs-lookup"><span data-stu-id="249a2-119">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="249a2-120">Так как поток электронной почты анализирует каждую электронную почту в отдельные компоненты и сравнивает их, поток электронной почты помечает обе последние два сообщения электронной почты как включительно, что гарантирует, что вы не пропустите контекст, пока не прочитаете все сообщения, помеченные как Инклюзивные.</span><span class="sxs-lookup"><span data-stu-id="249a2-120">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusive, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>
