---
title: Что такое EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: dansimp
ms.date: 02/25/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom:
- TN2DMC
- seo-marvel-apr2020
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 393b0050-7c7e-49e6-a03d-b1e09fe4de9e
description: В этой статье рассказывается о службе Exchange Online Protection (EOP), службе фильтрации электронной почты на основе облака.
ms.openlocfilehash: 7a9c122edf229d70f0ea5a1dbea8be56b5a2a3a9
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034942"
---
# <a name="what-is-exchange-online-protection-eop"></a><span data-ttu-id="315b0-103">Что такое Exchange Online Protection (EOP)</span><span class="sxs-lookup"><span data-stu-id="315b0-103">What is Exchange Online Protection (EOP)</span></span>

<span data-ttu-id="315b0-104">Exchange Online Protection (EOP) — это облачная служба фильтрации электронной почты, которая помогает защитить организацию от нежелательной почты и вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="315b0-104">Exchange Online Protection (EOP) is a cloud-based email filtering service that helps protect your organization against spam and malware.</span></span> <span data-ttu-id="315b0-105">Если у вас есть почтовые ящики в Microsoft 365, они автоматически защищаются службой EOP, так как она является частью службы.</span><span class="sxs-lookup"><span data-stu-id="315b0-105">If you have mailboxes in Microsoft 365, they are automatically protected by EOP since it is part of the service.</span></span> <span data-ttu-id="315b0-106">Сюда входят организации с почтовыми ящиками в Microsoft 365 и локальной среде, которая обычно называется гибридным сценарием.</span><span class="sxs-lookup"><span data-stu-id="315b0-106">This includes organizations that have mailboxes in both Microsoft 365 and on-premise, which is commonly known as a hybrid scenario.</span></span> <span data-ttu-id="315b0-107">EOP standalone также доступен для пользователей, у которых нет почтовых ящиков в облаке, но необходимо защищать их локальные почтовые ящики.</span><span class="sxs-lookup"><span data-stu-id="315b0-107">EOP standalone is also available for customers who do not have mailboxes in the cloud but want to protect their on-premises mailboxes.</span></span>

<span data-ttu-id="315b0-108">EOP пытается отфильтровывать нежелательные сообщения, не позволяя пользователям видеть их.</span><span class="sxs-lookup"><span data-stu-id="315b0-108">EOP attempts to filter out junk, keeping your Inbox clear of content that users don't want to see.</span></span> <span data-ttu-id="315b0-109">Обычно Нежелательная почта доставляется в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="315b0-109">Normally, junk mail is delivered to the Junk Email folder.</span></span> <span data-ttu-id="315b0-110">Некоторые пользователи намерены проверить, нужно ли выполнять фильтрацию, чтобы сделать папку нежелательной почты простой, чтобы пользователи могли самостоятельно проверять их.</span><span class="sxs-lookup"><span data-stu-id="315b0-110">Some users like to check to make sure the filtering is doing what they want so the Junk Email folder is an easy way for users to check on their own.</span></span>  

> [!TIP]
> <span data-ttu-id="315b0-111">Это хорошо, когда нежелательные сообщения электронной почты автоматически перемещаются в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="315b0-111">It is a good thing when junk or otherwise bad email goes into the Junk Email folder automatically.</span></span> <span data-ttu-id="315b0-112">Служба выполняет необходимые действия в зависимости от состояния параметров по умолчанию или настраиваемого администратора.</span><span class="sxs-lookup"><span data-stu-id="315b0-112">The service will do what is necessary based on what the default or the custom admin settings state.</span></span> <span data-ttu-id="315b0-113">Другими словами, пользователи не должны беспокоиться о большом объеме нежелательной почты в папке нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="315b0-113">In other words, users should not worry about seeing a lot of spam mail in the Junk Email folder.</span></span> <span data-ttu-id="315b0-114">Если администраторы предпочитают перемещать все нежелательные сведения, необходимо настроить карантин.</span><span class="sxs-lookup"><span data-stu-id="315b0-114">If admins prefer to move all junk out of sight, then the Quarantine should be configured.</span></span> <span data-ttu-id="315b0-115">Дополнительные сведения см. в статье [карантинные сообщения электронной почты](quarantine-email-messages.md) .</span><span class="sxs-lookup"><span data-stu-id="315b0-115">For more details, see the [Quarantine email messages](quarantine-email-messages.md) article.</span></span>

## <a name="important-terms"></a><span data-ttu-id="315b0-116">Важные термины</span><span class="sxs-lookup"><span data-stu-id="315b0-116">Important terms</span></span>

<span data-ttu-id="315b0-117">**Входящие**: сообщения, поступающие в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="315b0-117">**Inbound**: Messages that are coming into Microsoft 365.</span></span>

<span data-ttu-id="315b0-118">**Исходящие**: сообщения, которые выходят из Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="315b0-118">**Outbound**: Messages that are going out of Microsoft 365.</span></span>

<span data-ttu-id="315b0-119">**Internal**: сообщения от кого-либо из Организации кому-то внутри Организации.</span><span class="sxs-lookup"><span data-stu-id="315b0-119">**Internal**: Messages that are from someone inside the organization to someone inside the organization.</span></span> <span data-ttu-id="315b0-120">Сюда входят клиенты, которые находятся в гибридных сценариях, и один почтовый ящик может быть локальным, а другой — находиться в облаке.</span><span class="sxs-lookup"><span data-stu-id="315b0-120">This includes customers who are in hybrid scenarios and one mailbox could be on-premises and the other mailbox is in the cloud.</span></span>

<span data-ttu-id="315b0-121">**False (FN)**: спам и другие нежелательные сообщения, которые ошибочно отправляются в папку "Входящие".</span><span class="sxs-lookup"><span data-stu-id="315b0-121">**False Negative (FN)**: Spam and other junk that incorrectly gets sent into the inbox.</span></span>

<span data-ttu-id="315b0-122">**Ложное срабатывание (FP)**: легальные сообщения, которые ошибочно помечаются как спам и помещаются в папку нежелательной почты или в карантин.</span><span class="sxs-lookup"><span data-stu-id="315b0-122">**False Positive (FP)**: Legitimate messages that incorrectly get marked as spam and put into the Junk Email folder or Quarantine.</span></span>

<span data-ttu-id="315b0-123">**Нежелательная почта, также называемая нежелательной почтой**: это полагается на коммерческую рекламу, цепочку писем, сообщения электронной почты и т. д. Это электронная почта, с которой пользователи не подключаются к отправителям, которые пытаются закомментировать продукцию, или попытаются зафиксировать мошенничество.</span><span class="sxs-lookup"><span data-stu-id="315b0-123">**Spam, also known as unsolicited e-mail**: This comes in the form of commercial advertising, chain letters, political mailings, etc. This is email that users do not sign up for and from spammers who are trying to solicit products or attempting to commit fraud.</span></span>

<span data-ttu-id="315b0-124">**Фишинг**: Фишинг — это особый тип спама, который предназначен для получения персональных данных в целях фиксации хищения личных данных или мошенничества.</span><span class="sxs-lookup"><span data-stu-id="315b0-124">**Phish**: Phishing is a special type of spam that is intended to trick you into giving up personal information for the purpose of committing identity theft or fraud.</span></span> <span data-ttu-id="315b0-125">Сообщение этого типа обычно содержит вредоносную ссылку или вложенный объект, но не всегда.</span><span class="sxs-lookup"><span data-stu-id="315b0-125">This type of message usually contains a malicious link or attachment, but not always.</span></span>

<span data-ttu-id="315b0-126">**Подделка**: подмена — когда нежелательные сообщения подменяют заголовок "от", чтобы сообщения были отправлены от кого-либо, отличного от действительного источника.</span><span class="sxs-lookup"><span data-stu-id="315b0-126">**Spoof**: Spoofing is when spammers forge the FROM header so that messages appear to have originated from someone or somewhere other than the actual source.</span></span> <span data-ttu-id="315b0-127">Это может быть Нежелательная почта, но наиболее часто используется для фишинговых пользователей.</span><span class="sxs-lookup"><span data-stu-id="315b0-127">This can be spam but most commonly used to phish users.</span></span>

<span data-ttu-id="315b0-128">**Олицетворение**: этот тип нежелательной почты также позволяет подделывать адрес отправителя, но это делается путем изменения части имени или домена таким образом, чтобы она выглядела как действительный источник.</span><span class="sxs-lookup"><span data-stu-id="315b0-128">**Impersonation**: This type of spam is also a way to forge the sender address, but it is done by modifying part of the name or domain so that it looks like the real source.</span></span> <span data-ttu-id="315b0-129">Например, Bi11@micr0s0ft.com, где "l" в счете, — это число одиннадцати, а "o" в Microsoft заменен на число, равное нулю.</span><span class="sxs-lookup"><span data-stu-id="315b0-129">For example, Bi11@micr0s0ft.com, where the "l" in Bill was actually the number eleven and the "o" in Microsoft was replaced with the number zero.</span></span>

<span data-ttu-id="315b0-130">**BULK**: Массовая почта обычно запрашивается пользователями, хотя иногда косвенно, когда компании пропродают информацию другим компаниям.</span><span class="sxs-lookup"><span data-stu-id="315b0-130">**Bulk**: Bulk mail is usually solicited by users, although sometimes indirectly when companies sell information to other companies.</span></span> <span data-ttu-id="315b0-131">Обычно пользователи намеренно подписываются на массовую почту (например, невлеттерс), но забывают позже и думают, что это нежелательная почта.</span><span class="sxs-lookup"><span data-stu-id="315b0-131">It is common that users intentionally sign up for bulk mail (i.e. newletters) but forget later on and think it is spam.</span></span> <span data-ttu-id="315b0-132">Массовая рассылка сообщений становится нежелательной, когда массовые почтовые ящики отправляют больше, чем у пользователей, и слишком высокие уровни жалоб.</span><span class="sxs-lookup"><span data-stu-id="315b0-132">Bulk mail becomes spam when bulk mailers send more than users sign up and complaint levels get too high.</span></span>
