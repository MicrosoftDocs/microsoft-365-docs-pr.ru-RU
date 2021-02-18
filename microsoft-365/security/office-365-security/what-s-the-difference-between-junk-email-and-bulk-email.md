---
title: В &apos; чем разница между нежелательной почтой и массовой рассылкой?
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
description: Администраторы могут узнать о различиях между нежелательной почтой (нежелательной почтой) и массовой рассылкой (серой почтой) в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c656ed1807b451ae03ecfeb0f220f5d7b902c7ac
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290649"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="f3338-103">В чем разница между нежелательной почтой и массовой рассылкой в EOP?</span><span class="sxs-lookup"><span data-stu-id="f3338-103">What's the difference between junk email and bulk email in EOP?</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f3338-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="f3338-104">**Applies to**</span></span>
- [<span data-ttu-id="f3338-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f3338-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f3338-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="f3338-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="f3338-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3338-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="f3338-108">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online клиенты иногда задают вопрос: "В чем разница между нежелательной почтой и массовой рассылкой?".</span><span class="sxs-lookup"><span data-stu-id="f3338-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="f3338-109">В этом разделе описываются различия и элементы управления, доступные в EOP.</span><span class="sxs-lookup"><span data-stu-id="f3338-109">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="f3338-110">**Нежелательная** почта — это нежелательная почта, нежелательная почта, которая является нежелательными и универсальными (если определена правильно).</span><span class="sxs-lookup"><span data-stu-id="f3338-110">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="f3338-111">По умолчанию EOP отклоняет спам в зависимости от репутации сервера электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f3338-111">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="f3338-112">Если сообщение проходит проверку IP-адреса источника, оно отправляется на фильтрацию нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="f3338-112">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="f3338-113">Если сообщение классифицируется как нежелательное с помощью фильтрации нежелательной почты, сообщение (по умолчанию) доставляется получателям и перемещается в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="f3338-113">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="f3338-114">Вы можете настроить действия, которые необходимо принять для решения фильтра нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="f3338-114">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="f3338-115">Инструкции см. в подстройке "Настройка политик [нежелательной почты" в EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f3338-115">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="f3338-116">Если вы не согласны с решением фильтра нежелательной почты, вы можете сообщить о сообщениях, которые считаются нежелательными или не спамом, корпорации Майкрософт несколькими способами, как описано в отчете о сообщениях и файлах корпорации [Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="f3338-116">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="f3338-117">**Массовую** рассылку (также известная как _серая_ почта) классифицировать сложнее.</span><span class="sxs-lookup"><span data-stu-id="f3338-117">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="f3338-118">В то время как спам является постоянной угрозой, массовая рассылка часто представляет собой разовую рекламу или маркетинговые сообщения.</span><span class="sxs-lookup"><span data-stu-id="f3338-118">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="f3338-119">Некоторым пользователям нужны массовые сообщения электронной почты (а они специально подписаны на их получение), а другие считают массовую рассылку нежелательной почтой.</span><span class="sxs-lookup"><span data-stu-id="f3338-119">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="f3338-120">Например, некоторые пользователи хотят получать рекламные сообщения от корпорации Contoso или приглашения на предстоящие конференции по кибербезопасности, а другие считают такие же сообщения спамом.</span><span class="sxs-lookup"><span data-stu-id="f3338-120">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="f3338-121">Дополнительные сведения о том, как выявляется массовая рассылка электронной почты, см. в записи О массовой жалобе [(BCL) в EOP.](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="f3338-121">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="f3338-122">Управление массовыми сообщениями электронной почты</span><span class="sxs-lookup"><span data-stu-id="f3338-122">How to manage bulk email</span></span>

<span data-ttu-id="f3338-123">Из-за смешанной реакции на массовую рассылку электронной почты универсальные рекомендации, применимые к каждой организации, не существуют.</span><span class="sxs-lookup"><span data-stu-id="f3338-123">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="f3338-124">Для них установлено пороговое значение BCL по умолчанию, которое используется для определения массовой рассылки как нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="f3338-124">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="f3338-125">Администраторы могут увеличить или уменьшить порог.</span><span class="sxs-lookup"><span data-stu-id="f3338-125">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="f3338-126">Дополнительную информацию см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="f3338-126">For more information, see the following topics:</span></span>

- <span data-ttu-id="f3338-127">[Настройка политик нежелательной почты в EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f3338-127">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="f3338-128">Параметры политики EOP для борьбы с нежелательной почтой</span><span class="sxs-lookup"><span data-stu-id="f3338-128">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="f3338-129">Другой вариант, который легко пропустить: если пользователь жалуется на получение массовой рассылки электронной почты, но сообщения отправлены от надежных отправителей, которые проходят фильтрацию нежелательной почты в EOP, пользователь должен проверить возможность отписаться в массовом сообщении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f3338-129">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
