---
title: Службы для не клиентов, отправляя почту в Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: Чтобы поддерживать доверие пользователей к использованию электронной почты, Корпорация Майкрософт влала различные политики и технологии для защиты пользователей.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3213cae1b04b3f1a1b861e8f2cfc698576013546
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206517"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a><span data-ttu-id="491ec-103">Службы для не клиентов, отправляя почту в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="491ec-103">Services for non-customers sending mail to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="491ec-104">Злоупотребление электронной почтой, нежелательной почты и мошеннические сообщения (фишинг) по-прежнему обременяют всю экосистему электронной почты.</span><span class="sxs-lookup"><span data-stu-id="491ec-104">Email abuse, junk email, and fraudulent emails (phishing) continue to burden the entire email ecosystem.</span></span> <span data-ttu-id="491ec-105">Чтобы поддерживать доверие пользователей к использованию электронной почты, корпорация Майкрософт использует различные политики и технологии для защиты пользователей.</span><span class="sxs-lookup"><span data-stu-id="491ec-105">To help maintain user trust in the use of email, Microsoft has put various policies and technologies in place to help protect our users.</span></span> <span data-ttu-id="491ec-106">Однако Корпорация Майкрософт понимает, что законное сообщение электронной почты не должно быть негативно затронуто.</span><span class="sxs-lookup"><span data-stu-id="491ec-106">However, Microsoft understands that legitimate email should not be negatively affected.</span></span> <span data-ttu-id="491ec-107">Поэтому мы создали набор служб, которые помогут отправителям улучшить их возможность доставки электронной почты пользователям Microsoft 365, активно управляя своей репутацией отправки.</span><span class="sxs-lookup"><span data-stu-id="491ec-107">Therefore, we have established a suite of services to help senders improve their ability to deliver email to Microsoft 365 users by proactively managing their sending reputation.</span></span>

<span data-ttu-id="491ec-108">В этом обзоре дается информация о преимуществах, которые мы предоставляем вашей организации, даже если вы не клиент.</span><span class="sxs-lookup"><span data-stu-id="491ec-108">This overview provides information about benefits we provide to your organization even if you aren't a customer.</span></span>

## <a name="sender-solutions"></a><span data-ttu-id="491ec-109">Решения отправитель</span><span class="sxs-lookup"><span data-stu-id="491ec-109">Sender solutions</span></span>

****

|<span data-ttu-id="491ec-110">Служба</span><span class="sxs-lookup"><span data-stu-id="491ec-110">Service</span></span>|<span data-ttu-id="491ec-111">Преимущества</span><span class="sxs-lookup"><span data-stu-id="491ec-111">Benefits</span></span>|
|---|---|
|<span data-ttu-id="491ec-112">Это содержимое справки в Интернете</span><span class="sxs-lookup"><span data-stu-id="491ec-112">This online help content</span></span>|<span data-ttu-id="491ec-113">Предоставляет:</span><span class="sxs-lookup"><span data-stu-id="491ec-113">Provides:</span></span> <ul><li><span data-ttu-id="491ec-114">Отправная точка для любых вопросов, связанных с доставкой сообщений пользователям EOP.</span><span class="sxs-lookup"><span data-stu-id="491ec-114">A starting point for any questions related to delivering communications to EOP users.</span></span></li><li><span data-ttu-id="491ec-115">Включает простое руководство по интернету с нашими политиками и требованиями.</span><span class="sxs-lookup"><span data-stu-id="491ec-115">Includes a simple online guide with our policies and requirements.</span></span></li><li><span data-ttu-id="491ec-116">Обзор фильтров нежелательной почты и технологий проверки подлинности, используемых Корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="491ec-116">An overview of the junk email filters and authentication technologies employed by Microsoft.</span></span></li><ul>|
|[<span data-ttu-id="491ec-117">Служба поддержки Майкрософт</span><span class="sxs-lookup"><span data-stu-id="491ec-117">Microsoft support</span></span>](#microsoft-support)|<span data-ttu-id="491ec-118">Обеспечивает самопомеху и поддержку эскалации для проблем с доставкой.</span><span class="sxs-lookup"><span data-stu-id="491ec-118">Provides self-help and escalation support for delivery issues.</span></span>|
|[<span data-ttu-id="491ec-119">Портал делиста IP-адресов для защиты от нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="491ec-119">Anti-Spam IP Delist Portal</span></span>](#anti-spam-ip-delist-portal)|<span data-ttu-id="491ec-120">Средство для отправки запроса на делистинг IP.</span><span class="sxs-lookup"><span data-stu-id="491ec-120">A tool to submit IP delist request.</span></span> <span data-ttu-id="491ec-121">Перед отправкой этого запроса отправитель несет ответственность за то, чтобы любая дальнейшая почта, исходимая из IP-адреса, не была оскорбительной или вредоносной.</span><span class="sxs-lookup"><span data-stu-id="491ec-121">Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.</span></span>|
|[<span data-ttu-id="491ec-122">Сообщения о злоупотреблениях и спаме для нежелательной почты, исходя из Exchange Online</span><span class="sxs-lookup"><span data-stu-id="491ec-122">Abuse and spam reporting for junk email originating from Exchange Online</span></span>](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|<span data-ttu-id="491ec-123">Сохраняет нежелательной почты и нежелательной почты от отправлений из Exchange Online и захламления в Интернете и вашей почтовой системе.</span><span class="sxs-lookup"><span data-stu-id="491ec-123">Keeps spam and other unwanted mail from being sent from Exchange Online and cluttering up the internet and your mail system.</span></span>|
|

## <a name="microsoft-support"></a><span data-ttu-id="491ec-124">Служба поддержки Майкрософт</span><span class="sxs-lookup"><span data-stu-id="491ec-124">Microsoft support</span></span>

<span data-ttu-id="491ec-125">Корпорация Майкрософт предлагает несколько вариантов поддержки для людей, у которых возникли проблемы с отправкой почты получателям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="491ec-125">Microsoft offers several support options for people having trouble sending mail to Microsoft 365 recipients.</span></span> <span data-ttu-id="491ec-126">Вот несколько рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="491ec-126">We recommend that you:</span></span>

- <span data-ttu-id="491ec-127">Следуйте инструкциям в любом получаемом отчете о невывозе.</span><span class="sxs-lookup"><span data-stu-id="491ec-127">Follow the instructions in any non-delivery report you receive.</span></span>

- <span data-ttu-id="491ec-128">Ознакомьтесь с наиболее распространенными проблемами, с которыми сталкиваются пользователи, не связанные с устранением неполадок при устранении неполадок, отправленных [в Office 365.](troubleshooting-mail-sent-to-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="491ec-128">Check out the most common problems that non-customers encounter in [Troubleshooting mail sent to Office 365](troubleshooting-mail-sent-to-office-365.md).</span></span>

- <span data-ttu-id="491ec-129">Чтобы отправить запрос на удаление IP-адреса из списка заблокированного отправщика, используйте портал делистинг microsoft [365.](https://sender.office.com)</span><span class="sxs-lookup"><span data-stu-id="491ec-129">Use the [Microsoft 365 delist portal](https://sender.office.com) to submit a request to have your IP removed from the blocked sender's list.</span></span>

- <span data-ttu-id="491ec-130">Ознакомьтесь [с форумами сообщества Майкрософт.](https://community.office365.com/f/)</span><span class="sxs-lookup"><span data-stu-id="491ec-130">Read the [Microsoft community forums](https://community.office365.com/f/).</span></span>

- <span data-ttu-id="491ec-131">Свяжитесь с клиентом, с помощью другого метода, и попросите его связаться с службой поддержки Майкрософт и открыть билет на поддержку от вашего имени.</span><span class="sxs-lookup"><span data-stu-id="491ec-131">Contact the customer you're trying to email using another method and ask them to contact Microsoft Support and open a support ticket on your behalf.</span></span> <span data-ttu-id="491ec-132">В некоторых случаях по юридическим причинам Служба поддержки Майкрософт должна напрямую взаимодействовать с отправительом, которому принадлежит заблокированное IP-пространство.</span><span class="sxs-lookup"><span data-stu-id="491ec-132">In some cases, for legal reasons, Microsoft Support must communicate directly with the sender who owns the IP space that is being blocked.</span></span> <span data-ttu-id="491ec-133">Тем не менее, не-клиенты обычно не могут открыть билеты поддержки.</span><span class="sxs-lookup"><span data-stu-id="491ec-133">However, non-customers typically can't open support tickets.</span></span>

  <span data-ttu-id="491ec-134">Дополнительные сведения о технической поддержке Microsoft для Office 365 см. в [этой информации.](/office365/servicedescriptions/office-365-platform-service-description/support)</span><span class="sxs-lookup"><span data-stu-id="491ec-134">For more information about Microsoft Technical support for Office 365, see [Support](/office365/servicedescriptions/office-365-platform-service-description/support).</span></span>

## <a name="anti-spam-ip-delist-portal"></a><span data-ttu-id="491ec-135">Портал делиста IP-адресов для защиты от нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="491ec-135">Anti-Spam IP Delist Portal</span></span>

<span data-ttu-id="491ec-136">Это портал самообслуживаний, который можно использовать для удаления из списка заблокированных отправителей Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="491ec-136">This is a self-service portal you can use to remove yourself from the Microsoft 365 blocked senders list.</span></span> <span data-ttu-id="491ec-137">Используйте этот портал, если вы получаете сообщение об ошибке при попытке отправить сообщение электронной почты получателю, адрес электронной почты которого находится в Microsoft 365, и вы не думаете, что должны быть.</span><span class="sxs-lookup"><span data-stu-id="491ec-137">Use this portal if you are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365 and you don't think you should be.</span></span> <span data-ttu-id="491ec-138">Дополнительные сведения см. в статье [Удаление себя из списка заблокированных отправителей с помощью портала удаления из списка](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span><span class="sxs-lookup"><span data-stu-id="491ec-138">For more information, see [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a><span data-ttu-id="491ec-139">Сообщения о злоупотреблениях и спаме для нежелательной почты, исходя из Exchange Online</span><span class="sxs-lookup"><span data-stu-id="491ec-139">Abuse and spam reporting for junk email originating from Exchange Online</span></span>

<span data-ttu-id="491ec-140">Иногда Microsoft365 используется третьими лицами для отправки нежелательной почты в нарушение условий использования и политики.</span><span class="sxs-lookup"><span data-stu-id="491ec-140">Sometimes Microsoft365 is used by third parties to send junk email, in violation of our terms of use and policy.</span></span> <span data-ttu-id="491ec-141">Если вы получаете нежелательное письмо из Office 365, вы можете сообщить об этих сообщениях в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="491ec-141">If you receive any junk email from Office 365, you can report these messages to Microsoft.</span></span> <span data-ttu-id="491ec-142">Инструкции см. в [отчете о сообщениях и файлах в Корпорации Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="491ec-142">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>