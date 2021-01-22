---
title: Решение проблем с общими почтовыми ящиками
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Попробуйте эти решения, если возникают проблемы с общими почтовыми ящиками.
ms.openlocfilehash: ba62db76edff6e4ab3d738ed0af8db2a40c18394
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926490"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="6e1ee-103">Решение проблем с общими почтовыми ящиками</span><span class="sxs-lookup"><span data-stu-id="6e1ee-103">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="6e1ee-104">Если при создании или использовании общего почтового ящика вы видите сообщения об ошибках, попробуйте использовать эти возможные решения.</span><span class="sxs-lookup"><span data-stu-id="6e1ee-104">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="6e1ee-105">Ошибка при создании общих почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="6e1ee-105">Error when creating shared mailboxes</span></span>
<span data-ttu-id="6e1ee-106"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="6e1ee-106"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="6e1ee-107">Если вы видите сообщение об ошибке, прокси-адрес "smtp:<shared mailbox name" уже используется прокси-адресами или **\> LegacyExchangeDN \<name> ". Выберите другой прокси-адрес.** Это означает, что вы пытаетесь предоставить общему почтовому ящику имя, которое уже используется.</span><span class="sxs-lookup"><span data-stu-id="6e1ee-107">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="6e1ee-108">Например, предположим, что вам необходимо завести общие почтовые ящики с именами info@domain1 и info@domain2.</span><span class="sxs-lookup"><span data-stu-id="6e1ee-108">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="6e1ee-109">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="6e1ee-109">There are two ways to do this:</span></span>

  - <span data-ttu-id="6e1ee-110">Используйте Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e1ee-110">Use Windows PowerShell.</span></span> <span data-ttu-id="6e1ee-111">Инструкции по созданию общих почтовых ящиков с одинаковым псевдонимом в разных доменах см. в этой записи [блога](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="6e1ee-111">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="6e1ee-112">Назовем второй общий почтовый ящик чем-то другим, чтобы обойти ошибку.</span><span class="sxs-lookup"><span data-stu-id="6e1ee-112">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="6e1ee-113">Затем в Центре администрирования переименуем общий почтовый ящик в нужный вам почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="6e1ee-113">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="6e1ee-114">Ошибка без разрешений на отправку при использовании общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="6e1ee-114">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="6e1ee-115">Если вы создали общий почтовый ящик и пытаетесь отправить из него сообщение, вы можете получить:</span><span class="sxs-lookup"><span data-stu-id="6e1ee-115">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="6e1ee-116">**Не удалось отправить это сообщение. У вас нет разрешения на отправку сообщения от имени указанного пользователя.**</span><span class="sxs-lookup"><span data-stu-id="6e1ee-116">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="6e1ee-117">Это сообщение появляется, когда в Microsoft 365 возникает проблема задержки репликации.</span><span class="sxs-lookup"><span data-stu-id="6e1ee-117">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="6e1ee-118">Она должна пройти примерно через час, когда сведения о новом общем почтовом ящике (или добавленных пользователях) реплицированы во всех наших центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="6e1ee-118">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="6e1ee-119">Подождите час, а затем попробуйте еще раз отправить сообщение.</span><span class="sxs-lookup"><span data-stu-id="6e1ee-119">Wait an hour and then try again to send a message.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6e1ee-120">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="6e1ee-120">Related articles</span></span>

[<span data-ttu-id="6e1ee-121">Сведения об общих почтовых ящиках</span><span class="sxs-lookup"><span data-stu-id="6e1ee-121">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="6e1ee-122">Создание общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="6e1ee-122">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="6e1ee-123">Настройка общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="6e1ee-123">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="6e1ee-124">Преобразование почтового ящика пользователя в общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="6e1ee-124">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="6e1ee-125">Удаление лицензии из общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="6e1ee-125">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)


    

