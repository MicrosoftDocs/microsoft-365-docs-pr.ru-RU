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
description: При настройках общих почтовых ящиков могут возникнуть ошибки. Попробуйте эти решения, если у вас возникли проблемы с общими почтовыми ящиками.
ms.openlocfilehash: 89cdfbe29ab035b1eb6c3a0183629eef59d67477
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706134"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="7d8a2-104">Решение проблем с общими почтовыми ящиками</span><span class="sxs-lookup"><span data-stu-id="7d8a2-104">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="7d8a2-105">Если вы видите сообщения об ошибках при создании или использовании общего почтового ящика, попробуйте эти возможные решения.</span><span class="sxs-lookup"><span data-stu-id="7d8a2-105">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="7d8a2-106">Ошибка при создании общих почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="7d8a2-106">Error when creating shared mailboxes</span></span>
<span data-ttu-id="7d8a2-107"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="7d8a2-107"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="7d8a2-108">Если вы видите сообщение об ошибке, прокси-адрес "smtp:<имя общего почтового ящика" уже используется прокси-адресами или **\> LegacyExchangeDN \<name> ". Выберите другой прокси-адрес,** это означает, что вы пытаетесь дать общему почтовому ящику имя, которое уже используется.</span><span class="sxs-lookup"><span data-stu-id="7d8a2-108">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="7d8a2-109">Например, предположим, что вам необходимо завести общие почтовые ящики с именами info@domain1 и info@domain2.</span><span class="sxs-lookup"><span data-stu-id="7d8a2-109">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="7d8a2-110">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="7d8a2-110">There are two ways to do this:</span></span>

  - <span data-ttu-id="7d8a2-111">Используйте Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d8a2-111">Use Windows PowerShell.</span></span> <span data-ttu-id="7d8a2-112">Инструкции по созданию общих почтовых ящиков с одинаковыми псевдонимами в различных доменах см. в этой [записи блога.](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="7d8a2-112">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="7d8a2-113">Назови второй общий почтовый ящик, который отличается от начала, чтобы обойти ошибку.</span><span class="sxs-lookup"><span data-stu-id="7d8a2-113">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="7d8a2-114">Затем в центре администрирования переименуем общий почтовый ящик в нужный вам адрес.</span><span class="sxs-lookup"><span data-stu-id="7d8a2-114">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="7d8a2-115">Ошибка при не отправке разрешений при использовании общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="7d8a2-115">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="7d8a2-116">Если вы создали общий почтовый ящик, а затем попробуете отправить из него сообщение, вы можете получить это:</span><span class="sxs-lookup"><span data-stu-id="7d8a2-116">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="7d8a2-117">**Это сообщение не удалось отправить. У вас нет разрешения на отправку сообщения от имени указанного пользователя.**</span><span class="sxs-lookup"><span data-stu-id="7d8a2-117">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="7d8a2-118">Это сообщение появляется, Microsoft 365 возникает проблема задержки репликации.</span><span class="sxs-lookup"><span data-stu-id="7d8a2-118">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="7d8a2-119">Он должен уйти примерно через час, когда сведения о новом общем почтовом ящике (или добавленных пользователях) будут реплицированы во всех центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="7d8a2-119">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="7d8a2-120">Подождите час, а затем попробуйте еще раз отправить сообщение.</span><span class="sxs-lookup"><span data-stu-id="7d8a2-120">Wait an hour and then try again to send a message.</span></span>

## <a name="related-content"></a><span data-ttu-id="7d8a2-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="7d8a2-121">Related content</span></span>

<span data-ttu-id="7d8a2-122">[Сведения об общих почтовых ящиках](about-shared-mailboxes.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="7d8a2-122">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="7d8a2-123">[Создание общего почтового ящика](create-a-shared-mailbox.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="7d8a2-123">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="7d8a2-124">[Настройка общего почтового ящика](configure-a-shared-mailbox.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="7d8a2-124">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="7d8a2-125">[Преобразование почтового ящика пользователя в общий почтовый ящик](convert-user-mailbox-to-shared-mailbox.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="7d8a2-125">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="7d8a2-126">[Удаление лицензии из общего почтового ящика](remove-license-from-shared-mailbox.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="7d8a2-126">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>


    

