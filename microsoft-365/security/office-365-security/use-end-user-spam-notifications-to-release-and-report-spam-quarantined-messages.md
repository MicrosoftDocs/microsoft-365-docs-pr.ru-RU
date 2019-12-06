---
title: Использование уведомлений о нежелательной почте конечных пользователей для освобождения нежелательных сообщений в карантине и отправки отчетов о них
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4b250bc9-0056-4426-8397-7b4398f1b026
ms.collection:
- M365-security-compliance
description: 'Пользователи, просматривающие сообщение с уведомлением о нежелательной почте от администратора о том, что почтовые сообщения помещены в карантин, могут выполнять эти действия с сообщениями. '
ms.openlocfilehash: e533a0292bed1c6cd5d70796da2a25a7d8411884
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871185"
---
# <a name="use-end-user-spam-notifications-to-release-and-report-spam-quarantined-messages"></a><span data-ttu-id="eeb47-103">Использование уведомлений о нежелательной почте конечных пользователей для освобождения нежелательных сообщений в карантине и отправки отчетов о них</span><span class="sxs-lookup"><span data-stu-id="eeb47-103">Use end-user spam notifications to release and report spam-quarantined messages</span></span>

<span data-ttu-id="eeb47-104">[![Текст на изображении, посвященном перемещению содержимого с сайта TechNet на сайт support.office.com](../media/ab7c897a-4798-4f31-8c84-f17a8409b133.png)](https://go.microsoft.com/fwlink/p/?LinkID=624152)</span><span class="sxs-lookup"><span data-stu-id="eeb47-104">[![Text in image about content moving from TechNet to support.office.com](../media/ab7c897a-4798-4f31-8c84-f17a8409b133.png)](https://go.microsoft.com/fwlink/p/?LinkID=624152)</span></span>

<span data-ttu-id="eeb47-p101">Если администратор включил уведомление пользователей о нежелательной почте, вы получите уведомлением о том, что сообщения, предназначенные для вашего почтового ящика, сочтены нежелательными и помещены в карантин. Это сообщение включает количество помещенных в карантин нежелательных сообщений, а также дату и время (в формате UTC) отправки последнего сообщения в списке. Из этого списка вы можете просмотреть указанные ниже сведения о каждом сообщении.</span><span class="sxs-lookup"><span data-stu-id="eeb47-p101">If your administrator enables end-user spam notifications, you'll receive a notification message that lists messages intended for your mailbox that were identified as spam and quarantined instead. This message includes the number of spam-quarantined messages listed, and the date and time (in Universal Coordinated Time (UTC)) of the last message in the list. From this list, you can view the following information about each message:</span></span>

- <span data-ttu-id="eeb47-108">**Отправитель.** Имя и адрес электронной почты отправителя помещенного в карантин сообщения.</span><span class="sxs-lookup"><span data-stu-id="eeb47-108">**Sender** The sender name and email address of the quarantined message.</span></span>

- <span data-ttu-id="eeb47-109">**Тема.** Текст в строке темы помещенного в карантин сообщения.</span><span class="sxs-lookup"><span data-stu-id="eeb47-109">**Subject** The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="eeb47-110">**Дата.** Дата и время (в формате UTC) помещения сообщения в карантин.</span><span class="sxs-lookup"><span data-stu-id="eeb47-110">**Date** The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="eeb47-111">**Размер.** Размер помещенного в карантин сообщения в килобайтах (КБ).</span><span class="sxs-lookup"><span data-stu-id="eeb47-111">**Size** The size of the quarantined message, in kilobytes (KBs).</span></span>

<span data-ttu-id="eeb47-112">Можно выполнять перечисленные ниже действия над каждым сообщением.</span><span class="sxs-lookup"><span data-stu-id="eeb47-112">You can perform the following actions on each message:</span></span>

- <span data-ttu-id="eeb47-113">**Освободить в папку "Входящие"**. После щелчка данной ссылки сообщение отправляется в папку "Входящие", где его можно просмотреть.</span><span class="sxs-lookup"><span data-stu-id="eeb47-113">**Release to Inbox** Clicking this link sends the message to your inbox where you can view it.</span></span>

- <span data-ttu-id="eeb47-p102">**Сообщить, что сообщение не является нежелательным.** После щелчка данной ссылки копия сообщения отправляется для анализа корпорации Майкрософт. Отдел анализа нежелательной почты оценивает и анализирует сообщение и в зависимости от результатов анализа настраивает правила фильтрации нежелательной почты, чтобы разрешить доставку сообщения.</span><span class="sxs-lookup"><span data-stu-id="eeb47-p102">**Report as Not Junk** Clicking this link sends a copy of the message to Microsoft for analysis. The spam team evaluates and analyzes the message, and, depending on the results of the analysis, adjusts the anti-spam filter rules to allow the message through.</span></span>

> [!NOTE]
> <span data-ttu-id="eeb47-116">Сообщения, помещенные в карантин из-за того, что правило обработки почтового процесса (также известное как), не включаются в сообщения, помещенные в карантин пользователя.</span><span class="sxs-lookup"><span data-stu-id="eeb47-116">Messages that are quarantined due to a mail flow rule (also known as a ) match are not included in end user spam quarantined messages.</span></span> <span data-ttu-id="eeb47-117">В список включаются только помещенные в карантин нежелательные сообщения.</span><span class="sxs-lookup"><span data-stu-id="eeb47-117">Only spam-quarantined messages are listed.</span></span> <br/><br/>  <span data-ttu-id="eeb47-118">Освободить сообщение и сообщить о ложном срабатывании (о том, что сообщение не является нежелательным) можно только один раз.</span><span class="sxs-lookup"><span data-stu-id="eeb47-118">You can only release a message and report it as a false positive (not junk) once.</span></span>
