---
title: Проверка и утверждение ожидающих действий по исправлению в автоматическом расследовании и отклике
keywords: ВОЗДУШный, Аутоир, ATP, автоматизированный, исследование, ответ, исправление, угрозы, усовершенствованный, угроза, защита
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Сведения о действиях по исправлению в автоматическом расследовании и возможностях реагирования в Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 2f1d6a1dccfaece6a52ec33fd86ea244fbb6c4fe
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202451"
---
# <a name="view-pending-or-completed-remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="5fdd0-104">Просмотр ожидающих или завершенных действий по исправлению, следующих за автоматическим исследованием в Office 365</span><span class="sxs-lookup"><span data-stu-id="5fdd0-104">View pending or completed remediation actions following an automated investigation in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]



![Страница "действия по расследованию воздуха"](../../media/air-investigationactionspage.png)

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="5fdd0-106">Утверждение (или отклонение) ожидающих действий</span><span class="sxs-lookup"><span data-stu-id="5fdd0-106">Approve (or reject) pending actions</span></span>

<span data-ttu-id="5fdd0-107">При просмотре [сведений об исследовании](air-view-investigation-results.md)вы можете утвердить или отклонить все ожидающие действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="5fdd0-107">While viewing the [details of an investigation](air-view-investigation-results.md), you can approve or reject any pending remediation actions.</span></span> <span data-ttu-id="5fdd0-108">Мы рекомендуем сделать это как можно скорее, чтобы завершить автоматическое расследование.</span><span class="sxs-lookup"><span data-stu-id="5fdd0-108">We recommend doing this as soon as possible so that your automated investigations complete.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5fdd0-109">Для утверждения или отклонения действий по исправлению необходимы соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="5fdd0-109">Appropriate permissions are required to approve or reject remediation actions.</span></span> <span data-ttu-id="5fdd0-110">Ознакомьтесь [с разрешениями, необходимыми для использования возможностей Air](office-365-air.md#required-permissions-to-use-air-capabilities).</span><span class="sxs-lookup"><span data-stu-id="5fdd0-110">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

1. <span data-ttu-id="5fdd0-111">Перейдите на страницу [https://protection.office.com](https://protection.office.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="5fdd0-111">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="5fdd0-112">Откроется Центр безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="5fdd0-112">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="5fdd0-113">Перейдите на страницу расследования по **управлению угрозами**  >  **Investigations**.</span><span class="sxs-lookup"><span data-stu-id="5fdd0-113">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="5fdd0-114">В списке исследований выберите элемент в столбце **идентификатор** .</span><span class="sxs-lookup"><span data-stu-id="5fdd0-114">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="5fdd0-115">Перейдите на вкладку **действия** .</span><span class="sxs-lookup"><span data-stu-id="5fdd0-115">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="5fdd0-116">Выберите элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="5fdd0-116">Select an item in the list.</span></span> <span data-ttu-id="5fdd0-117">(При этом становятся активными кнопки утвердить и отклонить.)</span><span class="sxs-lookup"><span data-stu-id="5fdd0-117">(This activates the Approve and Reject buttons.)</span></span>

6. <span data-ttu-id="5fdd0-118">Просмотрите доступные сведения о выбранных элементах, а затем либо утвердите, либо отклоните действия.</span><span class="sxs-lookup"><span data-stu-id="5fdd0-118">Review available information for the item(s) you selected, and then either approve or reject the action(s).</span></span> 
   - <span data-ttu-id="5fdd0-119">**Одобрить** разрешает запуск исправления.</span><span class="sxs-lookup"><span data-stu-id="5fdd0-119">**Approve** allows remediation to begin.</span></span>
   - <span data-ttu-id="5fdd0-120">**Отклонить** не предпринимать дальнейших действий</span><span class="sxs-lookup"><span data-stu-id="5fdd0-120">**Reject** takes no further action</span></span>

## <a name="next-steps"></a><span data-ttu-id="5fdd0-121">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="5fdd0-121">Next steps</span></span>

- [<span data-ttu-id="5fdd0-122">Сведения и результаты автоматического исследования в Office 365</span><span class="sxs-lookup"><span data-stu-id="5fdd0-122">Details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)

- [<span data-ttu-id="5fdd0-123">Использование обозревателя угроз</span><span class="sxs-lookup"><span data-stu-id="5fdd0-123">Use Threat Explorer</span></span>](threat-explorer.md)
