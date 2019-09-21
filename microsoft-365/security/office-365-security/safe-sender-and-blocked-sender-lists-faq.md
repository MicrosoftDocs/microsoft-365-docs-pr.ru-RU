---
title: Списки надежных и заблокированных отправителей в Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: Чтобы пересылаемые через службу сообщения не помечались как спам, администратор Exchange Online или Exchange Online Protection (EOP) может создать списки надежных и заблокированных отправителей для пользователей в вашей организации.
ms.openlocfilehash: 5b1082e0a8f492da1ebc559b0958a6ef76f9a70c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091371"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a><span data-ttu-id="3faaf-104">Списки надежных и заблокированных отправителей в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3faaf-104">Safe sender and blocked sender lists in Exchange Online</span></span>

<span data-ttu-id="3faaf-p102">Чтобы пересылаемые через службу сообщения не помечались как спам, администратор Exchange Online или Exchange Online Protection (EOP) может создать списки надежных и заблокированных отправителей для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3faaf-p102">As an Exchange Online or Exchange Online Protection (EOP) administrator, you can help ensure that an email message traveling through the service isn't marked as spam. One way to do this is to create safe sender and blocked sender lists for the people in your organization.</span></span> 
  
 <span data-ttu-id="3faaf-107">*Обновленные подсказки и процедуры по работе с этими списками от имени администратора приведены в статье* [Предотвращение попадания электронной почты в спам в EOP и Office 365](https://go.microsoft.com/fwlink/p/?LinkID=534224).</span><span class="sxs-lookup"><span data-stu-id="3faaf-107">*See the updated version of the tips and procedures for how to work with these lists as an admin in* [Prevent false positive email marked as spam with a safelist or other techniques](https://go.microsoft.com/fwlink/p/?LinkID=534224).</span></span> 
  
<span data-ttu-id="3faaf-108">Если вы не администратор и просто хотите управлять нежелательной почтой в Outlook с помощью списка надежных отправителей, просмотрите общие сведения о [фильтре нежелательной почты](https://go.microsoft.com/fwlink/?LinkId=817222).</span><span class="sxs-lookup"><span data-stu-id="3faaf-108">If you're not an admin, and you just want to manage your own junk email in Outlook by using a safe sender list, check out the steps in this overview of [the Junk Email Filter](https://go.microsoft.com/fwlink/?LinkId=817222).</span></span> 
  
## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a><span data-ttu-id="3faaf-109">Сколько надежных и заблокированных отправителей можно добавить в Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="3faaf-109">What is the safe and blocked sender limits in Exchange Online?</span></span>

<span data-ttu-id="3faaf-p103">Ограничения на количество надежных и заблокированных отправителей в Exchange Online, Active Directory и Outlook отличаются. Они представлены ниже.</span><span class="sxs-lookup"><span data-stu-id="3faaf-p103">The safe and blocked sender limits in Exchange Online differ from the Active Directory and Outlook limits. They are:</span></span>
  
- <span data-ttu-id="3faaf-112">Лимит надежного отправителя: 1 024</span><span class="sxs-lookup"><span data-stu-id="3faaf-112">Safe sender limit: 1,024</span></span>
    
- <span data-ttu-id="3faaf-113">Предельное количество заблокированных отправителей: 500</span><span class="sxs-lookup"><span data-stu-id="3faaf-113">Blocked sender limit: 500</span></span>
    
<span data-ttu-id="3faaf-114">Примечание.</span><span class="sxs-lookup"><span data-stu-id="3faaf-114">Note:</span></span>
  
<span data-ttu-id="3faaf-115">Вы можете столкнуться с ошибкой, описанной в статье [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span><span class="sxs-lookup"><span data-stu-id="3faaf-115">You may experience the error that is described in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span></span> <span data-ttu-id="3faaf-116">Чтобы устранить эту проблему, снимите флажок "доверять сообщениям от контактов".</span><span class="sxs-lookup"><span data-stu-id="3faaf-116">To resolve this issue, clear the "Trust emails from my contacts" check box.</span></span> <span data-ttu-id="3faaf-117">Кроме того, уменьшите количество адресов электронной почты в папке "Контакты" по умолчанию, чтобы оно прибыло в пределах максимально допустимого значения 1024 в Exchange Online, для которого задан атрибут "Макссафесендерс".</span><span class="sxs-lookup"><span data-stu-id="3faaf-117">Alternatively, decrease the amount of email addresses that are in your default Contacts folder to bring it within the maximum allowed limit of 1024 in Exchange Online that is set for "MaxSafeSenders" attribute.</span></span> <span data-ttu-id="3faaf-118">Для получения дополнительных сведений об этом атрибуте и командлете Set – Mailbox Сисе следующий раздел:</span><span class="sxs-lookup"><span data-stu-id="3faaf-118">For more information about this attribute and the Set-Mailbox cmdlet, seethe following topic:</span></span>
  
[<span data-ttu-id="3faaf-119">Set-Mailbox</span><span class="sxs-lookup"><span data-stu-id="3faaf-119">Set-Mailbox</span></span>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)
  
## <a name="see-also"></a><span data-ttu-id="3faaf-120">См. также</span><span class="sxs-lookup"><span data-stu-id="3faaf-120">See also</span></span>

[<span data-ttu-id="3faaf-121">Sender filtering in Exchange 2016</span><span class="sxs-lookup"><span data-stu-id="3faaf-121">Sender filtering in Exchange 2016</span></span>](http://technet.microsoft.com/library/b833f864-ff10-46a0-a653-28fb9ba30896.aspx)

