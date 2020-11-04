---
title: Отправка нежелательных и фишинговых сообщений электронной почты в Outlook для iOS и Android
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Администраторы могут изучить встроенные параметры отчетов о нежелательной почте, нежелательной почте и phishing-атаках в Outlook для iOS и Android.
ms.openlocfilehash: 1c842ac5349f9c2804c637fa4c5598b06e8f489f
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877295"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="35096-103">Отправка нежелательных и фишинговых сообщений электронной почты в Outlook для iOS и Android в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="35096-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="35096-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или локальных почтовых ящиков с помощью [гибридной современной проверки подлинности](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)можно использовать встроенные параметры отчетов в Outlook для iOS и Android для отправки ложных срабатываний (хороший адрес электронной почты, помеченный как спам), ложные отрицательные (недопустимые сообщения электронной почты) и фишинговые сообщения для Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="35096-104">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="35096-105">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="35096-105">What do you need to know before you begin</span></span>

- <span data-ttu-id="35096-106">Если вы являетесь администратором в Организации с почтовыми ящиками Exchange Online, рекомендуем использовать портал отправки в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="35096-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="35096-107">Дополнительные сведения см. в [статье Использование отправки администратором для отправки подозреваемой спама, фишинга, URL-адресов и файлов в корпорацию Майкрософт](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="35096-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="35096-108">Можно настроить копирование или перенаправление сообщений, отправленных в указанный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="35096-108">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="35096-109">Для получения дополнительных сведений обратитесь к разделу [политики отправки пользователей](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="35096-109">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="35096-110">Дополнительные сведения о сообщениях отчетов в корпорацию Майкрософт можно найти [в статье сообщения и файлы отчетов в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="35096-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="35096-111">Если в политике отправки пользователей отключена поддержка отчетов о нежелательной почте, Нежелательная почта или фишинговые сообщения перемещаются в папку "Нежелательная почта", а не сообщаются администратору или корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="35096-111">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="35096-112">Составление отчетов о нежелательной почте и фишинговых сообщениях в Outlook для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="35096-112">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="35096-113">Для сообщений в папке "Входящие" или любой другой папке, кроме нежелательной почты, выполните следующие действия, чтобы сообщить о нежелательной почте и мошеннических сообщениях для iOS и Android:</span><span class="sxs-lookup"><span data-stu-id="35096-113">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="35096-114">Выберите одно или несколько сообщений.</span><span class="sxs-lookup"><span data-stu-id="35096-114">Select one or more messages.</span></span>
2. <span data-ttu-id="35096-115">В правом верхнем углу коснитесь трех точек по вертикали.</span><span class="sxs-lookup"><span data-stu-id="35096-115">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="35096-116">Откроется меню Action (действие).</span><span class="sxs-lookup"><span data-stu-id="35096-116">The action menu opens.</span></span>

   ![Сообщить о нежелательных или фишинговых сообщениях из меню действий](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="35096-118">Коснитесь **отчета Нежелательная почта** , а затем выберите **нежелательные** или **Фишинг**.</span><span class="sxs-lookup"><span data-stu-id="35096-118">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![Сообщить о нежелательных или фишинговых сообщениях](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="35096-120">В появившемся диалоговом окне можно выбрать пункт **отчет** или **нет**.</span><span class="sxs-lookup"><span data-stu-id="35096-120">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="35096-121">При выборе **нет** , если вы нажали **нежелательную** почту, сообщение перемещается в папку "Нежелательная почта", если вы нажали **поддельное** сообщение перемещается в папку "Удаленные".</span><span class="sxs-lookup"><span data-stu-id="35096-121">On selecting **No Thanks** , if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="35096-122">Выберите **отчет** , чтобы отправить копию сообщения в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="35096-122">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![Отправка отчетов о нежелательных и фишинговых сообщениях электронной почты](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="35096-124">Если вы передумали, нажмите кнопку **отменить** в появившемся всплывающем уведомлении.</span><span class="sxs-lookup"><span data-stu-id="35096-124">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="35096-125">Сообщение остается в папке "Входящие".</span><span class="sxs-lookup"><span data-stu-id="35096-125">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="35096-126">Отправка сообщений о сообщениях, не являющихся нежелательными, из папки "спам" в Outlook для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="35096-126">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="35096-127">В папке нежелательной почты выполните следующие действия, чтобы сообщить о ложных срабатываниях:</span><span class="sxs-lookup"><span data-stu-id="35096-127">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="35096-128">Выберите одно или несколько сообщений.</span><span class="sxs-lookup"><span data-stu-id="35096-128">Select one or more messages.</span></span>
2. <span data-ttu-id="35096-129">В правом верхнем углу коснитесь трех точек по вертикали.</span><span class="sxs-lookup"><span data-stu-id="35096-129">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="35096-130">Откроется меню Action (действие).</span><span class="sxs-lookup"><span data-stu-id="35096-130">The action menu opens.</span></span>

   ![Отчет о нежелательной почте из меню действий](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="35096-132">Коснитесь, а **не Нежелательная почта**.</span><span class="sxs-lookup"><span data-stu-id="35096-132">Tap **Not junk**.</span></span>

<span data-ttu-id="35096-133">Появится всплывающее уведомление о том, что сообщение перемещено в папку "Входящие".</span><span class="sxs-lookup"><span data-stu-id="35096-133">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="35096-134">Если вы передумали, нажмите кнопку **отменить** в уведомлении.</span><span class="sxs-lookup"><span data-stu-id="35096-134">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="35096-135">Сообщение электронной почты остается в папке "Нежелательная почта".</span><span class="sxs-lookup"><span data-stu-id="35096-135">The email remains in the Junk folder.</span></span>
