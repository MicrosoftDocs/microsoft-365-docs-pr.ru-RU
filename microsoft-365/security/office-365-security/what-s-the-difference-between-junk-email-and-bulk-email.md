---
title: В чем &apos; разница между нежелательной почтой и массовыми сообщениями электронной почты?
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
description: Администраторы могут узнать о различиях между нежелательной почтой и массовой рассылкой (серый список рассылки) в Exchange Online Protection (EOP).
ms.openlocfilehash: 17e6223175013678f389c0d7624cc4e4f4476f98
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826733"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="d4c9c-103">В чем разница между нежелательной почтой и массовой рассылкой электронной почты в EOP?</span><span class="sxs-lookup"><span data-stu-id="d4c9c-103">What's the difference between junk email and bulk email in EOP?</span></span>

<span data-ttu-id="d4c9c-104">Иногда в организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online иногда свидетельствуют: "В чем разница между нежелательной почтой и массовой рассылкой?"</span><span class="sxs-lookup"><span data-stu-id="d4c9c-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="d4c9c-105">В этой статье описаны различия и описаны элементы управления, доступные в EOP.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-105">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="d4c9c-106">**Нежелательная почта** это нежелательная почта, которые являются нежелательными и универсальными (если они установлены правильно).</span><span class="sxs-lookup"><span data-stu-id="d4c9c-106">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="d4c9c-107">По умолчанию EOP отклоняет нежелательную почту на основании репутации исходного почтового сервера.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-107">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="d4c9c-108">Если сообщение прошло проверку IP-адреса, оно отправляется в фильтр нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-108">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="d4c9c-109">Если сообщение классифицировано как нежелательное с помощью фильтрации нежелательной почты, сообщение доставляется указанным получателям и перемещается в папку "Нежелательная почта".</span><span class="sxs-lookup"><span data-stu-id="d4c9c-109">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="d4c9c-110">Вы можете настроить действия, применяемые к выполнению условных фильтров нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-110">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="d4c9c-111">Инструкции см. в статье ["Настройка политик защиты от нежелательной почты" в EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d4c9c-111">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="d4c9c-112">Если вы не согласны с решением фильтра нежелательной почты, вы можете сообщить корпорации Майкрософт различные способы отправки отчетов о нежелательных сообщениях или обычных сообщениях, как описано в [отчете о сообщениях и файлах корпорации Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="d4c9c-112">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="d4c9c-113">**Массовая** рассылка (также _называемая "серой почтой")_ более трудно классифицировать.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-113">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="d4c9c-114">Несмотря на спам — это стоп-угроза, массовые сообщения часто составляют одноразовые рекламные сообщения или маркетинговые сообщения.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-114">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="d4c9c-115">Некоторым пользователям нужны массовые рассылки электронной почты (на самом деле они намеренно подписались на них), а другие же пользователи могут посылать массовые рассылки как нежелательные.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-115">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="d4c9c-116">Например, некоторые пользователи хотят получать рекламные сообщения от Contoso Corporation или приглашения на предстоящую конференцию по кибербезопасности, а другие же рассматривают эти же сообщения как нежелательную.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-116">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="d4c9c-117">Дополнительные сведения о том, как определяется массовые рассылки электронной почты, см. в статье об уровне жалоб [на массовую рассылку (BCL) в СЛУЖБЕ EOP.](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="d4c9c-117">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="d4c9c-118">Управление массовыми сообщениями электронной почты</span><span class="sxs-lookup"><span data-stu-id="d4c9c-118">How to manage bulk email</span></span>

<span data-ttu-id="d4c9c-119">Из-за смешанного реакции на массовую рассылку электронной почты не существует никакого универсального руководства, применимых к каждой организации.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-119">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="d4c9c-120">Политики защиты от нежелательной почты имеют пороговое значение BCL по умолчанию, использовавшееся для идентификации массовых рассылок как спама.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-120">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="d4c9c-121">Администраторы могут увеличить или уменьшать пороговое значение.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-121">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="d4c9c-122">Дополнительную информацию см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="d4c9c-122">For more information, see the following topics:</span></span>

- <span data-ttu-id="d4c9c-123">[Настройка политик защиты от нежелательной почты в EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d4c9c-123">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="d4c9c-124">Параметры политики защиты от нежелательной почты EOP</span><span class="sxs-lookup"><span data-stu-id="d4c9c-124">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="d4c9c-125">Рассмотрим еще один вариант: если пользователь жался на массовую рассылку, но сообщения отправляются от надежных отправителей, которые проходят фильтрацию нежелательной почты в EOP, проверяют наличие уних одинакового значения в массовых сообщениях электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-125">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
