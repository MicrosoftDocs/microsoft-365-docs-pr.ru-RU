---
title: Цепочки электронных сообщений — расследования данных
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
description: При управлении исследованием данных почтовые потоки анализируют электронную беседу и разделяют каждое сообщение на разные категории.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6cc466bf89187f292acd454fd8ca6efb05958d2b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035661"
---
# <a name="email-threading"></a><span data-ttu-id="4c8c9-103">Потоки почты</span><span class="sxs-lookup"><span data-stu-id="4c8c9-103">Email threading</span></span>

<span data-ttu-id="4c8c9-104">Рассмотрим беседу по электронной почте в течение определенного сеанса.</span><span class="sxs-lookup"><span data-stu-id="4c8c9-104">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="4c8c9-105">В большинстве случаев последняя электронная почта в потоке будет включать содержимое всех предшествующих сообщений. Просмотр последней электронной почты дает полный контекст беседы, возникшей в цепочке.</span><span class="sxs-lookup"><span data-stu-id="4c8c9-105">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="4c8c9-106">Поток электронной почты определяет такие сообщения электронной почты, чтобы проверяющие могли просматривать долю собранных документов без потери контекста.</span><span class="sxs-lookup"><span data-stu-id="4c8c9-106">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="4c8c9-107">Что делает почтовые потоки?</span><span class="sxs-lookup"><span data-stu-id="4c8c9-107">What does email threading do?</span></span>

<span data-ttu-id="4c8c9-108">Почтовые потоки анализируют каждое сообщение электронной почты и десконструктс их к отдельным сообщениям; Каждое сообщение электронной почты представляет собой цепочку отдельных сообщений.</span><span class="sxs-lookup"><span data-stu-id="4c8c9-108">Email threading parses each email and desconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="4c8c9-109">Затем он анализирует все сообщения электронной почты в рабочем наборе, чтобы определить, имеет ли электронная почта уникальный контент или находится ли цепочка полностью в другом сообщении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4c8c9-109">Then, it analyzes all emails in the working set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="4c8c9-110">В конечной почте разделяются четыре категории:</span><span class="sxs-lookup"><span data-stu-id="4c8c9-110">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="4c8c9-111">**Включительно**: Последнее сообщение в сообщении содержит уникальный контент, а в электронной почте есть все вложения, включенные в другие сообщения электронной почты, содержимое которых полностью содержалось в этом сообщении.</span><span class="sxs-lookup"><span data-stu-id="4c8c9-111">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>


- <span data-ttu-id="4c8c9-112">**Включительно**: Последнее сообщение в сообщении содержит уникальный контент, но в электронной почте нет некоторых вложений, включенных в другие сообщения электронной почты, содержимое которых полностью содержалось в этом сообщении.</span><span class="sxs-lookup"><span data-stu-id="4c8c9-112">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="4c8c9-113">**Инклюзивная копия**: Точная копия инклюзивного/инклюзивного минуса электронной почты</span><span class="sxs-lookup"><span data-stu-id="4c8c9-113">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="4c8c9-114">**None**: содержимое этого сообщения полностью содержаться по крайней мере в одном сообщении, помеченном как инклюзивное/инклюзивное минус.</span><span class="sxs-lookup"><span data-stu-id="4c8c9-114">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="4c8c9-115">Чем она отличается от бесед в Outlook?</span><span class="sxs-lookup"><span data-stu-id="4c8c9-115">How is it different from conversations in Outlook?</span></span>
<span data-ttu-id="4c8c9-116">С первого взгляда это звучит очень похоже на группы сообщений в Outlook.</span><span class="sxs-lookup"><span data-stu-id="4c8c9-116">At a glance, this sounds very similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="4c8c9-117">Однако существует несколько важных отличительных моментов.</span><span class="sxs-lookup"><span data-stu-id="4c8c9-117">However, there are some important distinctions.</span></span> <span data-ttu-id="4c8c9-118">Рассмотрим электронную беседу, разветвление на две беседы; Например, кто-то ответил на сообщение электронной почты, которое не является последним в беседе, поэтому последние два сообщения в беседе имеют уникальный контент.</span><span class="sxs-lookup"><span data-stu-id="4c8c9-118">Consider an email conversation that got forked into two conversation; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="4c8c9-119">Outlook по-прежнему будет группировать сообщения в один сеанс; при чтении только последней электронной почты отсутствует контекст второй и последней электронной почты, который также содержит уникальный контент.</span><span class="sxs-lookup"><span data-stu-id="4c8c9-119">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="4c8c9-120">Так как поток электронной почты анализирует каждую электронную почту в отдельные компоненты и сравнивает их, поток электронной почты помечает обе последние два сообщения электронной почты как инклюзивные, что гарантирует, что вы не пропустите контекст, пока не прочитаете все сообщения, помеченные как Инклюзивные.</span><span class="sxs-lookup"><span data-stu-id="4c8c9-120">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusives, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>
