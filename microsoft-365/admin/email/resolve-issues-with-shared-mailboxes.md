---
title: Решение проблем с общими почтовыми ящиками
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
description: Используйте эти решения при возникновении проблем с общими почтовыми ящиками.
ms.openlocfilehash: b45c2eefa8cb4fb5fa34808223efbc1f0023161d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255167"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="e3efc-103">Решение проблем с общими почтовыми ящиками</span><span class="sxs-lookup"><span data-stu-id="e3efc-103">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="e3efc-104">Если вы видите сообщение об ошибке при создании или использовании общего почтового ящика, попробуйте эти решения.</span><span class="sxs-lookup"><span data-stu-id="e3efc-104">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="e3efc-105">Ошибка при создании общих почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="e3efc-105">Error when creating shared mailboxes</span></span>
<span data-ttu-id="e3efc-106"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="e3efc-106"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="e3efc-107">Если отображается сообщение об ошибке, **прокси-адрес "SMTP: <имя\>общего почтового ящика" уже используется прокси-адресами или LegacyExchangeDN "\<Name>". Выберите другой адрес прокси-сервера**, это означает, что вы пытаетесь присвоить общему почтовому ящику имя, которое уже используется.</span><span class="sxs-lookup"><span data-stu-id="e3efc-107">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="e3efc-108">Например, предположим, что вам необходимо завести общие почтовые ящики с именами info@domain1 и info@domain2.</span><span class="sxs-lookup"><span data-stu-id="e3efc-108">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="e3efc-109">Это можно сделать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="e3efc-109">There are two ways to do this:</span></span>

  - <span data-ttu-id="e3efc-110">Используйте Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3efc-110">Use Windows PowerShell.</span></span> <span data-ttu-id="e3efc-111">В этой записи блога приведены инструкции по [созданию общих почтовых ящиков с одинаковым псевдонимом в разных доменах в Office 365](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="e3efc-111">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains in Office 365](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="e3efc-112">Назовите второй общий почтовый ящик, который отличается от начального, чтобы получить сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="e3efc-112">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="e3efc-113">Затем в центре администрирования переименуйте общий почтовый ящик в то, что нужно.</span><span class="sxs-lookup"><span data-stu-id="e3efc-113">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="e3efc-114">Ошибка при использовании общего почтового ящика при отсутствии разрешений на отправку</span><span class="sxs-lookup"><span data-stu-id="e3efc-114">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="e3efc-115">Если вы создали общий почтовый ящик, а затем попытаетесь отправить ему сообщение, вы можете сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="e3efc-115">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="e3efc-116">**Не удалось отправить это сообщение. У вас нет разрешения на отправку сообщения от имени указанного пользователя.**</span><span class="sxs-lookup"><span data-stu-id="e3efc-116">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="e3efc-117">Это сообщение появляется в том случае, если в Office 365 возникла проблема с задержкой репликации.</span><span class="sxs-lookup"><span data-stu-id="e3efc-117">This message appears when Office 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="e3efc-118">Он должен отброситься в течение часа или таким образом, когда информация о новом общем почтовом ящике (или добавленном пользователе) реплицируется во всех наших центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="e3efc-118">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="e3efc-119">Подождите час и повторите попытку отправки сообщения.</span><span class="sxs-lookup"><span data-stu-id="e3efc-119">Wait an hour and then try again to send a message.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e3efc-120">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e3efc-120">Related articles</span></span>

[<span data-ttu-id="e3efc-121">Сведения об общих почтовых ящиках</span><span class="sxs-lookup"><span data-stu-id="e3efc-121">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="e3efc-122">Создание общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="e3efc-122">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="e3efc-123">Настройка общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="e3efc-123">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="e3efc-124">Преобразование почтового ящика пользователя в общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="e3efc-124">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="e3efc-125">Удаление лицензии из общего почтового ящика</span><span class="sxs-lookup"><span data-stu-id="e3efc-125">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)


    

