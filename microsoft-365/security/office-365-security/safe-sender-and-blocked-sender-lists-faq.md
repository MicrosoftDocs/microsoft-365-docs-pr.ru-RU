---
title: Списки надежных и заблокированных отправителей в Exchange Online
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 959af558c32e71e5a4cede2aff7bbcd1dbb092e2
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598516"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a><span data-ttu-id="9dbe0-104">Списки надежных и заблокированных отправителей в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9dbe0-104">Safe sender and blocked sender lists in Exchange Online</span></span>

<span data-ttu-id="9dbe0-p102">Чтобы пересылаемые через службу сообщения не помечались как спам, администратор Exchange Online или Exchange Online Protection (EOP) может создать списки надежных и заблокированных отправителей для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-p102">As an Exchange Online or Exchange Online Protection (EOP) administrator, you can help ensure that an email message traveling through the service isn't marked as spam. One way to do this is to create safe sender and blocked sender lists for the people in your organization.</span></span>

<span data-ttu-id="9dbe0-107">*Ознакомьтесь с обновленной версией советов и процедур для работы с этими списками в качестве администратора* , [чтобы предотвратить пометку сообщений электронной почты как спама в Office 365](prevent-email-from-being-marked-as-spam.md).</span><span class="sxs-lookup"><span data-stu-id="9dbe0-107">*See the updated version of the tips and procedures for how to work with these lists as an admin in* [How to prevent good email from being marked as spam in Office 365](prevent-email-from-being-marked-as-spam.md).</span></span>

<span data-ttu-id="9dbe0-108">Если вы не являетесь администратором и хотите управлять собственной нежелательной почтой в Outlook с помощью списка надежных отправителей, ознакомьтесь с инструкциями в статье[Обзор фильтра нежелательной почты](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span><span class="sxs-lookup"><span data-stu-id="9dbe0-108">If you're not an admin, and you just want to manage your own junk email in Outlook by using a safe sender list, check out the steps in the[Overview of the Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span>

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a><span data-ttu-id="9dbe0-109">Сколько надежных и заблокированных отправителей можно добавить в Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="9dbe0-109">What is the safe and blocked sender limits in Exchange Online?</span></span>

<span data-ttu-id="9dbe0-p103">Ограничения на количество надежных и заблокированных отправителей в Exchange Online, Active Directory и Outlook отличаются. Они представлены ниже.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-p103">The safe and blocked sender limits in Exchange Online differ from the Active Directory and Outlook limits. They are:</span></span>

- <span data-ttu-id="9dbe0-112">Лимит надежного отправителя: 1 024</span><span class="sxs-lookup"><span data-stu-id="9dbe0-112">Safe sender limit: 1,024</span></span>

- <span data-ttu-id="9dbe0-113">Предельное количество заблокированных отправителей: 500</span><span class="sxs-lookup"><span data-stu-id="9dbe0-113">Blocked sender limit: 500</span></span>

<span data-ttu-id="9dbe0-114">Примечание.</span><span class="sxs-lookup"><span data-stu-id="9dbe0-114">Note:</span></span>

<span data-ttu-id="9dbe0-115">Вы можете столкнуться с ошибкой, описанной в статье [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span><span class="sxs-lookup"><span data-stu-id="9dbe0-115">You may experience the error that is described in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span></span> <span data-ttu-id="9dbe0-116">Чтобы устранить эту проблему, снимите флажок "доверять сообщениям от контактов".</span><span class="sxs-lookup"><span data-stu-id="9dbe0-116">To resolve this issue, clear the "Trust emails from my contacts" check box.</span></span> <span data-ttu-id="9dbe0-117">Кроме того, уменьшите количество адресов электронной почты в папке "Контакты" по умолчанию, чтобы оно прибыло в пределах максимально допустимого значения 1024 в Exchange Online, для которого задан атрибут "Макссафесендерс".</span><span class="sxs-lookup"><span data-stu-id="9dbe0-117">Alternatively, decrease the amount of email addresses that are in your default Contacts folder to bring it within the maximum allowed limit of 1024 in Exchange Online that is set for "MaxSafeSenders" attribute.</span></span> <span data-ttu-id="9dbe0-118">Для получения дополнительных сведений об этом атрибуте и командлете Set – Mailbox Сисе следующий раздел:</span><span class="sxs-lookup"><span data-stu-id="9dbe0-118">For more information about this attribute and the Set-Mailbox cmdlet, seethe following topic:</span></span>

[<span data-ttu-id="9dbe0-119">Set-Mailbox</span><span class="sxs-lookup"><span data-stu-id="9dbe0-119">Set-Mailbox</span></span>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a><span data-ttu-id="9dbe0-120">См. также</span><span class="sxs-lookup"><span data-stu-id="9dbe0-120">See also</span></span>

[<span data-ttu-id="9dbe0-121">Фильтрация отправителей в Exchange Server</span><span class="sxs-lookup"><span data-stu-id="9dbe0-121">Sender filtering in Exchange Server</span></span>](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
