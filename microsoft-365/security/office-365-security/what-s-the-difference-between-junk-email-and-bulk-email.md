---
title: '&apos;В чем разница между нежелательной почтой и групповой почтой?'
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать о различиях между нежелательной почтой и нежелательной почтой (серой почтой) в Exchange Online Protection (EOP).
ms.openlocfilehash: 1e11f897a145f7b34acc81e1d132d6babac08979
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195483"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="94fc0-103">В чем разница между нежелательной почтой и пакетами электронной почты в EOP?</span><span class="sxs-lookup"><span data-stu-id="94fc0-103">What's the difference between junk email and bulk email in EOP?</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="94fc0-104">В организациях Microsoft 365 с почтовыми ящиками в организациях Exchange Online или автономной службе Exchange Online Protection (EOP) без почтовых ящиков Exchange Online клиенты иногда запрашивают: "что такое разница между нежелательной почтой и групповой почтой?"</span><span class="sxs-lookup"><span data-stu-id="94fc0-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="94fc0-105">В этом разделе объясняются различия и описываются элементы управления, доступные в EOP.</span><span class="sxs-lookup"><span data-stu-id="94fc0-105">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="94fc0-106">**Нежелательная почта** — это нежелательная почта, которые являются нежелательными нежелательными сообщениями (при их правильном обнаружении).</span><span class="sxs-lookup"><span data-stu-id="94fc0-106">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="94fc0-107">По умолчанию EOP отклоняет нежелательную почту в зависимости от репутации исходного почтового сервера.</span><span class="sxs-lookup"><span data-stu-id="94fc0-107">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="94fc0-108">Если сообщение проходит проверку IP-адреса источника, оно отправляется в фильтрацию нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="94fc0-108">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="94fc0-109">Если при фильтрации нежелательной почты сообщение классифицируется как нежелательная почта, сообщение будет (по умолчанию) доставлено предполагаемым получателям и перемещено в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="94fc0-109">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="94fc0-110">Вы можете настроить действия, выполняемые при фильтрации нежелательной почты вердиктс.</span><span class="sxs-lookup"><span data-stu-id="94fc0-110">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="94fc0-111">Инструкции см в разделе [Настройка политик защиты от нежелательной почты в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="94fc0-111">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="94fc0-112">Если вы не согласны с фильтром нежелательной почты вредоносности, вы можете отправлять сообщения о нежелательной почте и нежелательной почте в корпорацию Майкрософт несколькими способами, как описано в [статье Reporting messages and Files to Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="94fc0-112">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="94fc0-113">**Массовая рассылка сообщений электронной почты** (также называемая _серой почтой_) более сложная.</span><span class="sxs-lookup"><span data-stu-id="94fc0-113">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="94fc0-114">Несмотря на то, что нежелательная почта является постоянной угрозой, Массовая Электронная почта часто представляет собой одноразовые рекламные сообщения или маркетинговые сообщения.</span><span class="sxs-lookup"><span data-stu-id="94fc0-114">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="94fc0-115">Некоторые пользователи хотят создавать массовые сообщения электронной почты (и на самом деле имеют намеренную подпись, чтобы получить их), а другие пользователи рассчитают сообщение нежелательной почтой.</span><span class="sxs-lookup"><span data-stu-id="94fc0-115">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="94fc0-116">Например, некоторые пользователи хотят получать рекламные сообщения от корпорации Contoso или приглашений на предстоящую конференцию по безопасности кибератак, а другие пользователи рассчитают эти же сообщения нежелательной почтой.</span><span class="sxs-lookup"><span data-stu-id="94fc0-116">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="94fc0-117">Для получения дополнительных сведений о том, как обозначается Массовая Электронная почта, ознакомьтесь со статьей [уровень жалоб (BCL) в EOP](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="94fc0-117">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="94fc0-118">Управление массовыми сообщениями электронной почты</span><span class="sxs-lookup"><span data-stu-id="94fc0-118">How to manage bulk email</span></span>

<span data-ttu-id="94fc0-119">Из-за смешанной реакции на массовую почту не существует универсальных рекомендаций, которые применяются ко всем организациям.</span><span class="sxs-lookup"><span data-stu-id="94fc0-119">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="94fc0-120">Политики защиты от нежелательной почты имеют пороговое значение BCL по умолчанию, которое используется для идентификации массовых сообщений электронной почты как спама.</span><span class="sxs-lookup"><span data-stu-id="94fc0-120">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="94fc0-121">Администраторы могут увеличить или уменьшить пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="94fc0-121">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="94fc0-122">Дополнительную информацию см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="94fc0-122">For more information, see the following topics:</span></span>

- <span data-ttu-id="94fc0-123">[Настройка политик защиты от нежелательной почты в EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="94fc0-123">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="94fc0-124">Параметры политики защиты от нежелательной почты EOP</span><span class="sxs-lookup"><span data-stu-id="94fc0-124">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="94fc0-125">Еще один вариант, который легко не заметить: Если пользователь выдает сообщение о получении массовых сообщений электронной почты, но сообщения от надежных отправителей, которые проверяют фильтрацию нежелательной почты в EOP, пользователь должен проверить возможность отмены подписки в сообщении массовой рассылки.</span><span class="sxs-lookup"><span data-stu-id="94fc0-125">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
