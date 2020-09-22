---
title: Службы для пользователей, не являющихся клиентами, отправляющих почту в Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: Чтобы обеспечить доверие пользователю при использовании электронной почты, корпорация Майкрософт разместит различные политики и технологии для защиты пользователей.
ms.openlocfilehash: e9389d52ee1d6c1c0bbab8630778749a6ed6005f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199581"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a><span data-ttu-id="cf85a-103">Службы для пользователей, не являющихся клиентами, отправляющих почту в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cf85a-103">Services for non-customers sending mail to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="cf85a-104">Сообщения о нарушениях, нежелательной почте и мошеннических сообщениях (фишинге) продолжают разделять всю экосистему электронной почты.</span><span class="sxs-lookup"><span data-stu-id="cf85a-104">Email abuse, junk email, and fraudulent emails (phishing) continue to burden the entire email ecosystem.</span></span> <span data-ttu-id="cf85a-105">Чтобы обеспечить доверие пользователям при использовании электронной почты, корпорация Майкрософт разместит различные политики и технологии на месте, чтобы помочь вам защитить пользователей.</span><span class="sxs-lookup"><span data-stu-id="cf85a-105">To help maintain user trust in the use of email, Microsoft has put various policies and technologies in place to help protect our users.</span></span> <span data-ttu-id="cf85a-106">Тем не менее, корпорация Майкрософт понимает, что легальные сообщения электронной почты не должны быть отрицательно затронуты.</span><span class="sxs-lookup"><span data-stu-id="cf85a-106">However, Microsoft understands that legitimate email should not be negatively affected.</span></span> <span data-ttu-id="cf85a-107">Таким образом, мы установили набор служб, чтобы помочь отправителю повысить возможность доставки электронной почты пользователям Microsoft 365, управляя своими репутациями отправки.</span><span class="sxs-lookup"><span data-stu-id="cf85a-107">Therefore, we have established a suite of services to help senders improve their ability to deliver email to Microsoft 365 users by proactively managing their sending reputation.</span></span>

<span data-ttu-id="cf85a-108">В этом обзоре представлены сведения о преимуществах, предоставляемых вашей организации, даже если у вас нет клиента.</span><span class="sxs-lookup"><span data-stu-id="cf85a-108">This overview provides information about benefits we provide to your organization even if you aren't a customer.</span></span>

## <a name="sender-solutions"></a><span data-ttu-id="cf85a-109">Решения для отправителей</span><span class="sxs-lookup"><span data-stu-id="cf85a-109">Sender solutions</span></span>

****

|<span data-ttu-id="cf85a-110">Служба</span><span class="sxs-lookup"><span data-stu-id="cf85a-110">Service</span></span>|<span data-ttu-id="cf85a-111">Преимущества</span><span class="sxs-lookup"><span data-stu-id="cf85a-111">Benefits</span></span>|
|---|---|
|<span data-ttu-id="cf85a-112">Содержимое интерактивной справки</span><span class="sxs-lookup"><span data-stu-id="cf85a-112">This online help content</span></span>|<span data-ttu-id="cf85a-113">—</span><span class="sxs-lookup"><span data-stu-id="cf85a-113">Provides:</span></span> <br/> <span data-ttu-id="cf85a-114">Отправная точка для вопросов, связанных с доставкой связи пользователям EOP.</span><span class="sxs-lookup"><span data-stu-id="cf85a-114">A starting point for any questions related to delivering communications to EOP users.</span></span> <br/><br/> <span data-ttu-id="cf85a-115">Включает простое электронное руководство с нашими политиками и требованиями.</span><span class="sxs-lookup"><span data-stu-id="cf85a-115">Includes a simple online guide with our policies and requirements.</span></span> <br/><br/> <span data-ttu-id="cf85a-116">Обзор фильтров нежелательной почты и технологий проверки подлинности, применяемых корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cf85a-116">An overview of the junk email filters and authentication technologies employed by Microsoft.</span></span>|
|[<span data-ttu-id="cf85a-117">Служба поддержки Майкрософт</span><span class="sxs-lookup"><span data-stu-id="cf85a-117">Microsoft support</span></span>](#microsoft-support)|<span data-ttu-id="cf85a-118">Предоставляет поддержку самостоятельного решения и эскалации для проблем с доставкой.</span><span class="sxs-lookup"><span data-stu-id="cf85a-118">Provides self-help and escalation support for delivery issues.</span></span>|
|[<span data-ttu-id="cf85a-119">Портал удаления нежелательной почты-списков для защиты от спама</span><span class="sxs-lookup"><span data-stu-id="cf85a-119">Anti-Spam IP Delist Portal</span></span>](#anti-spam-ip-delist-portal)|<span data-ttu-id="cf85a-120">Средство для отправления запроса на получение списка IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="cf85a-120">A tool to submit IP delist request.</span></span> <span data-ttu-id="cf85a-121">Перед отправкой этого запроса он является обязанностью отправителя, чтобы убедиться, что любая дальнейшая почта из рассматриваемого IP-адреса не является оскорбительной или вредоносной.</span><span class="sxs-lookup"><span data-stu-id="cf85a-121">Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.</span></span>|
|[<span data-ttu-id="cf85a-122">Сообщения о нарушениях и нежелательной почте, полученные из Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cf85a-122">Abuse and spam reporting for junk email originating from Exchange Online</span></span>](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|<span data-ttu-id="cf85a-123">Предотвращает отправку нежелательных сообщений и других нежелательных сообщений из Exchange Online и перенаправление в Интернет и почтовые системы.</span><span class="sxs-lookup"><span data-stu-id="cf85a-123">Keeps spam and other unwanted mail from being sent from Exchange Online and cluttering up the internet and your mail system.</span></span>|
|

## <a name="microsoft-support"></a><span data-ttu-id="cf85a-124">Служба поддержки Майкрософт</span><span class="sxs-lookup"><span data-stu-id="cf85a-124">Microsoft support</span></span>

<span data-ttu-id="cf85a-125">Корпорация Майкрософт предлагает несколько вариантов поддержки для людей, у которых есть проблемы с отправкой почты получателям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf85a-125">Microsoft offers several support options for people having trouble sending mail to Microsoft 365 recipients.</span></span> <span data-ttu-id="cf85a-126">Вот несколько рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="cf85a-126">We recommend that you:</span></span>

- <span data-ttu-id="cf85a-127">Следуйте инструкциям в любом отчете о недоставке, который вы получаете.</span><span class="sxs-lookup"><span data-stu-id="cf85a-127">Follow the instructions in any non-delivery report you receive.</span></span>

- <span data-ttu-id="cf85a-128">Узнайте о наиболее распространенных проблемах, с которыми сталкиваются пользователи, не являющиеся клиентами, при [устранении неполадок почты, отправленных в Office 365](troubleshooting-mail-sent-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="cf85a-128">Check out the most common problems that non-customers encounter in [Troubleshooting mail sent to Office 365](troubleshooting-mail-sent-to-office-365.md).</span></span>

- <span data-ttu-id="cf85a-129">Используйте [портал Microsoft 365](https://sender.office.com) , чтобы отправить запрос на удаление IP-адреса из списка заблокированных отправителей.</span><span class="sxs-lookup"><span data-stu-id="cf85a-129">Use the [Microsoft 365 delist portal](https://sender.office.com) to submit a request to have your IP removed from the blocked sender's list.</span></span>

- <span data-ttu-id="cf85a-130">Прочтите [форумы сообщества Майкрософт](https://community.office365.com/f/).</span><span class="sxs-lookup"><span data-stu-id="cf85a-130">Read the [Microsoft community forums](https://community.office365.com/f/).</span></span>

- <span data-ttu-id="cf85a-131">Обратитесь к клиенту, который вы пытаетесь отправить по электронной почте, используя другой способ, и попросите его обратиться в службу поддержки Майкрософт и открыть билет в службу поддержки от вашего имени.</span><span class="sxs-lookup"><span data-stu-id="cf85a-131">Contact the customer you're trying to email using another method and ask them to contact Microsoft Support and open a support ticket on your behalf.</span></span> <span data-ttu-id="cf85a-132">В некоторых случаях, по юридическим причинам, служба поддержки Майкрософт должна напрямую общаться с отправителем, которому принадлежит IP-пространство, которое блокируется.</span><span class="sxs-lookup"><span data-stu-id="cf85a-132">In some cases, for legal reasons, Microsoft Support must communicate directly with the sender who owns the IP space that is being blocked.</span></span> <span data-ttu-id="cf85a-133">Однако пользователи, не являющиеся клиентами, обычно не могут открыть билеты поддержки.</span><span class="sxs-lookup"><span data-stu-id="cf85a-133">However, non-customers typically can't open support tickets.</span></span>

  <span data-ttu-id="cf85a-134">Для получения дополнительных сведений о технической поддержке Microsoft для Office 365, ознакомьтесь со статьей [Поддержка](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support).</span><span class="sxs-lookup"><span data-stu-id="cf85a-134">For more information about Microsoft Technical support for Office 365, see [Support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support).</span></span>

## <a name="anti-spam-ip-delist-portal"></a><span data-ttu-id="cf85a-135">Портал удаления нежелательной почты-списков для защиты от спама</span><span class="sxs-lookup"><span data-stu-id="cf85a-135">Anti-Spam IP Delist Portal</span></span>

<span data-ttu-id="cf85a-136">Это портал самообслуживания, с помощью которого можно удалить себя из списка заблокированных отправителей Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf85a-136">This is a self-service portal you can use to remove yourself from the Microsoft 365 blocked senders list.</span></span> <span data-ttu-id="cf85a-137">Используйте этот портал, если вы получаете сообщение об ошибке при попытке отправить сообщение получателю, адрес электронной почты которого находится в Microsoft 365, и вы не считаете, что это необходимо.</span><span class="sxs-lookup"><span data-stu-id="cf85a-137">Use this portal if you are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365 and you don't think you should be.</span></span> <span data-ttu-id="cf85a-138">Дополнительные сведения см. в статье [Удаление себя из списка заблокированных отправителей с помощью портала удаления из списка](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span><span class="sxs-lookup"><span data-stu-id="cf85a-138">For more information, see [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a><span data-ttu-id="cf85a-139">Сообщения о нарушениях и нежелательной почте, полученные из Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cf85a-139">Abuse and spam reporting for junk email originating from Exchange Online</span></span>

<span data-ttu-id="cf85a-140">Иногда Microsoft365 используется третьими сторонами для отправки нежелательных сообщений, нарушая наши условия использования и политики.</span><span class="sxs-lookup"><span data-stu-id="cf85a-140">Sometimes Microsoft365 is used by third parties to send junk email, in violation of our terms of use and policy.</span></span> <span data-ttu-id="cf85a-141">Если вы получаете любую нежелательную почту из Office 365, вы можете отправить отчет об этих сообщениях в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cf85a-141">If you receive any junk email from Office 365, you can report these messages to Microsoft.</span></span> <span data-ttu-id="cf85a-142">Инструкции приведены [в статье сообщения отчетов и файлы в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="cf85a-142">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>
