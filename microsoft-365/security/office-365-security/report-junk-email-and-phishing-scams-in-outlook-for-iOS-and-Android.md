---
title: Сообщение о нежелательной и фишинговой почте в Outlook для iOS и Android
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать о встроенных вариантах отправки отчетов о нежелательной почте, а не о нежелательной почте и фишинговых сообщениях в Outlook для iOS и Android.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d702ab1d97c07c3e38430a9a7beff5f14db7b60a
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029284"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="20f72-103">Сообщение о нежелательной и фишинговой почте в Outlook для iOS и Android в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="20f72-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="20f72-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange [](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)Online или в локальном почтовом ящике с использованием гибридной современной проверки подлинности вы можете использовать встроенные параметры отчетов в Outlook для iOS и Android, чтобы отправлять ложные срабатывания (хорошая электронная почта помечена как спам), ложные отрицательные результаты (разрешено использование нежелательной почты) и фишинговые сообщения в Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="20f72-104">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="20f72-105">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="20f72-105">What do you need to know before you begin</span></span>

- <span data-ttu-id="20f72-106">Если вы администратор организации с почтовыми ящиками Exchange Online, рекомендуем использовать портал отправки в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="20f72-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="20f72-107">Дополнительные сведения см. в документе "Отправка администратора" для отправки подозрительной нежелательной [почты, фишинга, URL-адресов и файлов в корпорацию Майкрософт.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="20f72-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="20f72-108">Вы можете настроить копирование или перенаправление сообщений в задаемый почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="20f72-108">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="20f72-109">Дополнительные сведения [см. в политиках отправки пользователей.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="20f72-109">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="20f72-110">Дополнительные сведения об отчетах о сообщениях в корпорацию Майкрософт см. в отчете о [сообщениях и файлах корпорации Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="20f72-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="20f72-111">Если отчеты о нежелательной почте отключены для Outlook в политике отправки пользователей, нежелательные или фишинговые сообщения будут перемещены в папку нежелательной почты и не будут отправлены администратору или корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="20f72-111">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="20f72-112">Сообщение о спаме и фишинговых сообщениях в Outlook для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="20f72-112">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="20f72-113">Для сообщений в папке "Входящие" или любой другой папки электронной почты, кроме нежелательной почты, с помощью следующих действий можно сообщить о спаме и фишинговых сообщениях для iOS и Android:</span><span class="sxs-lookup"><span data-stu-id="20f72-113">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="20f72-114">Выберите одно или несколько сообщений.</span><span class="sxs-lookup"><span data-stu-id="20f72-114">Select one or more messages.</span></span>
2. <span data-ttu-id="20f72-115">В правом верхнем углу коснитесь трех вертикальных точек.</span><span class="sxs-lookup"><span data-stu-id="20f72-115">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="20f72-116">Откроется меню действий.</span><span class="sxs-lookup"><span data-stu-id="20f72-116">The action menu opens.</span></span>

   ![Сообщение о нежелательной или фишинговой почте из меню действий](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="20f72-118">Tap **Report junk** and then select **Junk** or **Phishing**.</span><span class="sxs-lookup"><span data-stu-id="20f72-118">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![Сообщение о нежелательной почте или фишинге](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="20f72-120">В от появляются диалоговое окно, вы можете выбрать **отчет** или **нет спасибо**.</span><span class="sxs-lookup"><span data-stu-id="20f72-120">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="20f72-121">При выборе пункта **"Нет спасибо",** если вы нарезали "Нежелатель", сообщение перемещается в папку нежелательной почты, если вы нарезали фишинг, сообщение перемещается в папку "Удаленные".  </span><span class="sxs-lookup"><span data-stu-id="20f72-121">On selecting **No Thanks**, if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="20f72-122">Выберите **"Отчет",** чтобы также отправить копию сообщения в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="20f72-122">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![Отчет о вариантах отправки отчетов о нежелательной почте или фишинге](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="20f72-124">Если вы передумаете, выберите **"Отменить"** во всплывающее уведомление.</span><span class="sxs-lookup"><span data-stu-id="20f72-124">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="20f72-125">Сообщение остается в папке "Входящие".</span><span class="sxs-lookup"><span data-stu-id="20f72-125">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="20f72-126">Сообщение о нежелательных сообщениях из папки нежелательной почты в Outlook для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="20f72-126">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="20f72-127">Чтобы сообщить о ложных срабатываниях нежелательной почты, в папке нежелательной почты с помощью следующих действий:</span><span class="sxs-lookup"><span data-stu-id="20f72-127">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="20f72-128">Выберите одно или несколько сообщений.</span><span class="sxs-lookup"><span data-stu-id="20f72-128">Select one or more messages.</span></span>
2. <span data-ttu-id="20f72-129">В правом верхнем углу коснитесь трех вертикальных точек.</span><span class="sxs-lookup"><span data-stu-id="20f72-129">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="20f72-130">Откроется меню действий.</span><span class="sxs-lookup"><span data-stu-id="20f72-130">The action menu opens.</span></span>

   ![Сообщение о нежелательной почте из меню действий](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="20f72-132">Tap **Not junk**.</span><span class="sxs-lookup"><span data-stu-id="20f72-132">Tap **Not junk**.</span></span>

<span data-ttu-id="20f72-133">Появится всплывающее уведомление о том, что сообщение перемещено в вашу учетную почту.</span><span class="sxs-lookup"><span data-stu-id="20f72-133">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="20f72-134">Если вы передумаете, выберите **"Отменить" во** всплывающее уведомление.</span><span class="sxs-lookup"><span data-stu-id="20f72-134">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="20f72-135">Сообщение остается в папке нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="20f72-135">The email remains in the Junk folder.</span></span>
