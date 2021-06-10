---
title: В &apos; чем разница между нежелательной электронной почтой и массовой электронной почтой?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать о различиях между нежелательной почтой (нежелательной почтой) и массовой электронной почтой (серая почта) в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fc9c94946c3da2f9a14f45070a86c557a5c7dc85
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206977"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="8c30a-103">В чем разница между нежелательной электронной почтой и массовой электронной почтой в EOP?</span><span class="sxs-lookup"><span data-stu-id="8c30a-103">What's the difference between junk email and bulk email in EOP?</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8c30a-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="8c30a-104">**Applies to**</span></span>
- [<span data-ttu-id="8c30a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8c30a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8c30a-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="8c30a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8c30a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8c30a-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="8c30a-108">В Microsoft 365 организациях с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без Exchange Online почтовых ящиков клиенты иногда спрашивают: "В чем разница между нежелательной электронной почтой и массовой электронной почтой?"</span><span class="sxs-lookup"><span data-stu-id="8c30a-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="8c30a-109">В этом разделе объясняется разница и описываются элементы управления, доступные в EOP.</span><span class="sxs-lookup"><span data-stu-id="8c30a-109">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="8c30a-110">**Нежелательной** почты является нежелательной почты, которые являются нежелательными и нежелательными от нежелательной почты (при правильном обнаружении).</span><span class="sxs-lookup"><span data-stu-id="8c30a-110">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="8c30a-111">По умолчанию EOP отклоняет спам в зависимости от репутации сервера электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8c30a-111">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="8c30a-112">Если сообщение проходит проверку IP-адреса источника, оно отправляется на фильтрацию нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="8c30a-112">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="8c30a-113">Если сообщение классифицируется как спам с помощью фильтрации нежелательной почты, сообщение (по умолчанию) доставляется предполагаемым получателям и перемещается в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="8c30a-113">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="8c30a-114">Вы можете настроить действия для несения вердиктов по фильтрации нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="8c30a-114">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="8c30a-115">Инструкции см. в [сообщении Configure anti-spam policies in EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="8c30a-115">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="8c30a-116">Если вы не согласны с вердиктом по фильтрации нежелательной почты, вы можете сообщать о сообщениях, которые считаются нежелательной почтой или не спамом, в Microsoft несколькими способами, как описано в сообщениях и файлах Отчета в [Корпорацию Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="8c30a-116">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="8c30a-117">**Массовая** электронная почта (также известная как _серая почта),_ более трудна для классификации.</span><span class="sxs-lookup"><span data-stu-id="8c30a-117">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="8c30a-118">В то время как спам — это постоянная угроза, массовая электронная почта часто представляет собой разовую рекламу или маркетинговые сообщения.</span><span class="sxs-lookup"><span data-stu-id="8c30a-118">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="8c30a-119">Некоторые пользователи хотят массовых сообщений электронной почты (и на самом деле они сознательно подписались на их получение), в то время как другие пользователи считают массовые сообщения электронной почты нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="8c30a-119">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="8c30a-120">Например, некоторые пользователи хотят получать рекламные сообщения от корпорации Contoso или приглашения на предстоящие конференции по кибербезопасности, в то время как другие пользователи считают эти сообщения спамом.</span><span class="sxs-lookup"><span data-stu-id="8c30a-120">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="8c30a-121">Дополнительные сведения о том, как массовое сообщение электронной почты идентифицировано, см. в сообщении [Навалом уровня жалоб (BCL) в EOP.](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="8c30a-121">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="8c30a-122">Управление массовыми сообщениями электронной почты</span><span class="sxs-lookup"><span data-stu-id="8c30a-122">How to manage bulk email</span></span>

<span data-ttu-id="8c30a-123">Из-за неоднозначной реакции на массовую электронную почту универсальные рекомендации, применимые к каждой организации, не применяются.</span><span class="sxs-lookup"><span data-stu-id="8c30a-123">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="8c30a-124">Для анти-спам-полиции установлен порог BCL по умолчанию, используемый для определения массовой электронной почты как нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="8c30a-124">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="8c30a-125">Администраторы могут увеличивать или уменьшать пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="8c30a-125">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="8c30a-126">Дополнительную информацию см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="8c30a-126">For more information, see the following topics:</span></span>

- <span data-ttu-id="8c30a-127">[Настройка политик по борьбе со спамом в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8c30a-127">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="8c30a-128">Параметры политики борьбы со нежелательной почтой EOP</span><span class="sxs-lookup"><span data-stu-id="8c30a-128">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

<span data-ttu-id="8c30a-129">Другой вариант, который легко игнорировать: если пользователь жалуется на получение массовой электронной почты, но сообщения от надежных отправителей, которые проходят фильтрацию нежелательной почты в EOP, у пользователя проверьте возможность отписаться в массовом сообщении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8c30a-129">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
