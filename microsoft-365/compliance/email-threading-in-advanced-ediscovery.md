---
title: Потоки почты
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
ms.assetid: ''
description: ''
ms.openlocfilehash: ea40acc3c83d5083a68473223f849a9bebbe98ce
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074746"
---
# <a name="email-threading"></a><span data-ttu-id="38cce-102">Потоки почты</span><span class="sxs-lookup"><span data-stu-id="38cce-102">Email threading</span></span>

<span data-ttu-id="38cce-103">Рассмотрим беседу по электронной почте в течение определенного сеанса.</span><span class="sxs-lookup"><span data-stu-id="38cce-103">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="38cce-104">В большинстве случаев последняя электронная почта в потоке будет включать содержимое всех предшествующих сообщений. Просмотр последней электронной почты дает полный контекст беседы, возникшей в цепочке.</span><span class="sxs-lookup"><span data-stu-id="38cce-104">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="38cce-105">Поток электронной почты определяет такие сообщения электронной почты, чтобы проверяющие могли просматривать долю собранных документов без потери контекста.</span><span class="sxs-lookup"><span data-stu-id="38cce-105">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="38cce-106">Что делает почтовые потоки?</span><span class="sxs-lookup"><span data-stu-id="38cce-106">What does email threading do?</span></span>

<span data-ttu-id="38cce-107">Почтовые потоки анализируют каждое сообщение электронной почты и десконструктс их к отдельным сообщениям; Каждое сообщение электронной почты представляет собой цепочку отдельных сообщений.</span><span class="sxs-lookup"><span data-stu-id="38cce-107">Email threading parses each email and desconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="38cce-108">Затем он анализирует все сообщения электронной почты в наборе проверки, чтобы определить, имеет ли электронная почта уникальный контент или находится ли цепочка полностью в другом сообщении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="38cce-108">Then, it analyzes all emails in the review set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="38cce-109">В конечной почте разделяются четыре категории:</span><span class="sxs-lookup"><span data-stu-id="38cce-109">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="38cce-110">**Включительно**: Последнее сообщение в сообщении содержит уникальный контент, а в электронной почте есть все вложения, включенные в другие сообщения электронной почты, содержимое которых полностью содержалось в этом сообщении.</span><span class="sxs-lookup"><span data-stu-id="38cce-110">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>


- <span data-ttu-id="38cce-111">**Включительно**: Последнее сообщение в сообщении содержит уникальный контент, но в электронной почте нет некоторых вложений, включенных в другие сообщения электронной почты, содержимое которых полностью содержалось в этом сообщении.</span><span class="sxs-lookup"><span data-stu-id="38cce-111">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="38cce-112">**Инклюзивная копия**: Точная копия инклюзивного/инклюзивного минуса электронной почты</span><span class="sxs-lookup"><span data-stu-id="38cce-112">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="38cce-113">**None**: содержимое этого сообщения полностью содержаться по крайней мере в одном сообщении, помеченном как инклюзивное/инклюзивное минус.</span><span class="sxs-lookup"><span data-stu-id="38cce-113">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="38cce-114">Чем она отличается от бесед в Outlook?</span><span class="sxs-lookup"><span data-stu-id="38cce-114">How is it different from conversations in Outlook?</span></span>
<span data-ttu-id="38cce-115">С первого взгляда это звучит очень похоже на группы сообщений в Outlook.</span><span class="sxs-lookup"><span data-stu-id="38cce-115">At a glance, this sounds very similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="38cce-116">Однако существует несколько важных отличительных моментов.</span><span class="sxs-lookup"><span data-stu-id="38cce-116">However, there are some important distinctions.</span></span> <span data-ttu-id="38cce-117">Рассмотрим электронную беседу, разветвление на две беседы; Например, кто-то ответил на сообщение электронной почты, которое не является последним в беседе, поэтому последние два сообщения в беседе имеют уникальный контент.</span><span class="sxs-lookup"><span data-stu-id="38cce-117">Consider an email conversation that got forked into two conversation; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="38cce-118">Outlook по-прежнему будет группировать сообщения в один сеанс; при чтении только последней электронной почты отсутствует контекст второй и последней электронной почты, который также содержит уникальный контент.</span><span class="sxs-lookup"><span data-stu-id="38cce-118">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="38cce-119">Так как поток электронной почты анализирует каждую электронную почту в отдельные компоненты и сравнивает их, поток электронной почты помечает обе последние два сообщения электронной почты как инклюзивные, что гарантирует, что вы не пропустите контекст, пока не прочитаете все сообщения, помеченные как Инклюзивные.</span><span class="sxs-lookup"><span data-stu-id="38cce-119">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusives, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>
