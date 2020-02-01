---
title: Настройка гарантированной отправки нежелательной почты в соответствующую папку каждого пользователя
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 7/16/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Администраторы могут научиться маршрутизировать нежелательную почту в папки нежелательной почты пользователя в Exchange Online Protection.
ms.openlocfilehash: 6d1fd625669e8b638a408b2db1993f45fa653ffb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599366"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="ca597-103">Настройка гарантированной отправки нежелательной почты в соответствующую папку каждого пользователя</span><span class="sxs-lookup"><span data-stu-id="ca597-103">Ensure that spam is routed to each user's Junk Email folder</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ca597-p101">Сведения, представленные в этом разделе, касаются только пользователей Exchange Online Protection (EOP), чьи почтовые ящики размещаются локально в гибридном развертывании. Пользователям Exchange Online, чьи почтовые ящики размещаются в Office 365, не нужно выполнять эти команды.</span><span class="sxs-lookup"><span data-stu-id="ca597-p101">This topic only applies to Exchange Online Protection (EOP) customers who host mailboxes on-premises in a hybrid deployment. Exchange Online customers whose mailboxes are fully-hosted in Office 365 do not need to run these commands.</span></span>

<span data-ttu-id="ca597-106">Для пользователей EOP нежелательная почта по умолчанию перемещается в соответствующую папку получателя.</span><span class="sxs-lookup"><span data-stu-id="ca597-106">The default anti-spam action for EOP customers is to move spam messages to the recipients' Junk Email folder.</span></span> <span data-ttu-id="ca597-107">Чтобы это действие работало с локальными почтовыми ящиками, необходимо настроить правила для почтовых ящиков Exchange (также называемые правилами транспорта) на локальных пограничных серверах или серверах-концентраторах, чтобы обнаружить заголовки нежелательной почты, добавленные EOP.</span><span class="sxs-lookup"><span data-stu-id="ca597-107">In order for this action to work with on-premises mailboxes, you must configure Exchange mail flow rules (also known as transport rules) on your on-premises Edge or Hub servers to detect spam headers added by EOP.</span></span> <span data-ttu-id="ca597-108">Эти правила для этих почтовых ящиков устанавливают степень вероятности нежелательной почты (SCL), используемую свойством SclJunkThreshold командлета Set-OrganizationConfig, для перемещения спама в папку нежелательной почты каждого почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="ca597-108">These mail flow rules set the spam confidence level (SCL) used by the SclJunkThreshold property of the Set-OrganizationConfig cmdlet to move spam into the Junk Email folder of each mailbox.</span></span>

### <a name="to-add-mail-flow-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a><span data-ttu-id="ca597-109">Добавление правил для почтового процесса для перемещения спама в папку нежелательной почты с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca597-109">To add mail flow rules to ensure spam is moved to the Junk Email folder by using Windows PowerShell</span></span>

1. <span data-ttu-id="ca597-p103">Откройте командную консоль Exchange для локального сервера Exchange Server. Сведения о том, как открыть командную консоль Exchange в локальной организации Exchange, см. в статье **Open the Shell**.</span><span class="sxs-lookup"><span data-stu-id="ca597-p103">Access the Exchange Management Shell for your on-premises Exchange server. To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**.</span></span>

2. <span data-ttu-id="ca597-112">Выполните следующую команду, чтобы перенаправлять отфильтрованную по содержимому нежелательную почту в папку "Нежелательная почта":</span><span class="sxs-lookup"><span data-stu-id="ca597-112">Run the following command to route content-filtered spam messages to the Junk Email folder:</span></span>

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
   ```

   <span data-ttu-id="ca597-113">Где _NameForRule_ это имя нового правила (например, JunkContentFilteredMail).</span><span class="sxs-lookup"><span data-stu-id="ca597-113">Where _NameForRule_ is the name for the new rule, for example, JunkContentFilteredMail.</span></span>

3. <span data-ttu-id="ca597-114">Выполните следующую команду, чтобы перенаправлять сообщения, отмеченные как нежелательные, перед их попаданием в фильтр содержимого и папку нежелательной почты:</span><span class="sxs-lookup"><span data-stu-id="ca597-114">Run the following command to route messages marked as spam prior to reaching the content filter to the Junk Email folder:</span></span>

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
   ```

   <span data-ttu-id="ca597-115">Где _NameForRule_ это имя нового правила (например, JunkMailBeforeReachingContentFilter).</span><span class="sxs-lookup"><span data-stu-id="ca597-115">Where _NameForRule_ is the name for the new rule, for example, JunkMailBeforeReachingContentFilter.</span></span>

4. <span data-ttu-id="ca597-116">Выполните следующую команду, чтобы направлять сообщения от заблокированных отправителей, например в списке **блокировок отправителя**, в папку нежелательной почты:</span><span class="sxs-lookup"><span data-stu-id="ca597-116">Run the following command to ensure that messages from senders in a block list in the spam filter policy, such as the **Sender block** list, are routed to the Junk Email folder:</span></span>

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
   ```

   <span data-ttu-id="ca597-117">Где _NameForRule_ это имя нового правила (например, JunkMailInSenderBlockList).</span><span class="sxs-lookup"><span data-stu-id="ca597-117">Where _NameForRule_ is the name for the new rule, for example, JunkMailInSenderBlockList.</span></span>

<span data-ttu-id="ca597-p104">Если вы не хотите использовать действие **Переместить сообщение в папку нежелательной почты**, можно выбрать другое действие с помощью политик фильтрации содержимого в Центре администрирования Exchange. Дополнительные сведения см. в статье [Настройте политики защиты от спама](configure-your-spam-filter-policies.md). Дополнительные сведения об этих полях в заголовке сообщения см. в статье [Заголовки сообщений по защите от нежелательной почты](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="ca597-p104">If you do not want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

> [!TIP]
> <span data-ttu-id="ca597-121">Если вы не хотите использовать действие **переместить сообщение в папку нежелательной почты** , вы можете выбрать другое действие в политиках фильтрации содержимого в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="ca597-121">If you don't want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="ca597-122">Дополнительные сведения см. в статье [Настройка политик фильтрации спама](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ca597-122">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="ca597-123">Для получения дополнительных сведений об этих полях в заголовке сообщения просмотрите [заголовки сообщений по защите от нежелательной почты](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="ca597-123">For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ca597-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ca597-124">See also</span></span>

[<span data-ttu-id="ca597-125">New — TransportRule</span><span class="sxs-lookup"><span data-stu-id="ca597-125">New-TransportRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)
