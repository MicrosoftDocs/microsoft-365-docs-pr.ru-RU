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
ms.openlocfilehash: 58027f7589280b1266cddc8cfbf44db9e4f0ece4
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166823"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="3608d-103">Отправка отчетов о нежелательной и фишинговой почте в Outlook для iOS и Android в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3608d-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3608d-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="3608d-104">**Applies to**</span></span>
- [<span data-ttu-id="3608d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3608d-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="3608d-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="3608d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="3608d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3608d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="3608d-108">В организациях Microsoft 365 с почтовыми ящиками в Exchange [](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview)Online или в локальном почтовом ящике с использованием гибридной современной проверки подлинности вы можете использовать встроенные параметры отчетов в Outlook для iOS и Android, чтобы отправлять ложные срабатывания (хорошая электронная почта помечена как спам), ложные отрицательные результаты (разрешено использование нежелательной почты) и фишинговые сообщения в Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="3608d-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3608d-109">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="3608d-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="3608d-110">Если вы администратор организации с почтовыми ящиками Exchange Online, рекомендуем использовать портал отправки в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="3608d-110">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="3608d-111">Дополнительные сведения см. в документе "Отправка администратора" для отправки подозрительной нежелательной [почты, фишинга, URL-адресов и файлов в корпорацию Майкрософт.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="3608d-111">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="3608d-112">Вы можете настроить копирование или перенаправление сообщений в задаемый почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="3608d-112">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="3608d-113">Дополнительные сведения [см. в политиках отправки пользователей.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="3608d-113">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="3608d-114">Дополнительные сведения об отчетах о сообщениях в корпорацию Майкрософт см. в отчете о [сообщениях и файлах корпорации Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="3608d-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="3608d-115">Если отчеты о нежелательной почте отключены для Outlook в политике отправки пользователей, нежелательные или фишинговые сообщения будут перемещены в папку нежелательной почты и не будут отправлены администратору или корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3608d-115">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a><span data-ttu-id="3608d-116">Сообщение о спаме и фишинговых сообщениях в Outlook для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="3608d-116">Report spam and phishing messages in Outlook for iOS and Android</span></span>

<span data-ttu-id="3608d-117">Для сообщений в папке "Входящие" или любой другой папки электронной почты, кроме нежелательной почты, с помощью следующих действий можно сообщить о спаме и фишинговых сообщениях для iOS и Android:</span><span class="sxs-lookup"><span data-stu-id="3608d-117">For messages in the Inbox, or any other email folder except Junk Email, use the following steps to report spam and phishing messages for iOS and Android:</span></span>

1. <span data-ttu-id="3608d-118">Выберите одно или несколько сообщений.</span><span class="sxs-lookup"><span data-stu-id="3608d-118">Select one or more messages.</span></span>
2. <span data-ttu-id="3608d-119">В правом верхнем углу коснитесь трех вертикальных точек.</span><span class="sxs-lookup"><span data-stu-id="3608d-119">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="3608d-120">Откроется меню действий.</span><span class="sxs-lookup"><span data-stu-id="3608d-120">The action menu opens.</span></span>

   ![Сообщение о нежелательной или фишинговой почте из меню действий](../../media/Android-report-as-junk-dialog.png)

3. <span data-ttu-id="3608d-122">Tap **Report junk** and then select **Junk** or **Phishing**.</span><span class="sxs-lookup"><span data-stu-id="3608d-122">Tap **Report junk** and then select **Junk** or **Phishing**.</span></span>

   ![Сообщение о нежелательной почте или фишинге](../../media/Android-report-junk-or-phishing.png)

4. <span data-ttu-id="3608d-124">В от появляются диалоговое окно, вы можете выбрать **отчет** или **нет спасибо**.</span><span class="sxs-lookup"><span data-stu-id="3608d-124">In the dialog that appears, you can choose **Report** or **No Thanks**.</span></span> <span data-ttu-id="3608d-125">При выборе пункта **"Нет спасибо",** если вы нарезали "Нежелатель", сообщение перемещается в папку нежелательной почты, если вы нарезали фишинг, сообщение перемещается в папку "Удаленные".  </span><span class="sxs-lookup"><span data-stu-id="3608d-125">On selecting **No Thanks**, if you tapped **Junk** the message moves to the Junk Email folder, if you tapped **Phishing** the message moves to the Deleted Items folder.</span></span> <span data-ttu-id="3608d-126">Выберите **"Отчет",** чтобы также отправить копию сообщения в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="3608d-126">Select **Report** to also send a copy of the message to Microsoft.</span></span>

   ![Отчет о вариантах отправки отчетов о нежелательной почте или фишинге](../../media/Android-junk-email-reporting-options.png)

<span data-ttu-id="3608d-128">Если вы передумаете, выберите **"Отменить"** во всплывающее уведомление.</span><span class="sxs-lookup"><span data-stu-id="3608d-128">If you change your mind, select **Undo** on the toast notification that appears.</span></span> <span data-ttu-id="3608d-129">Сообщение остается в папке "Входящие".</span><span class="sxs-lookup"><span data-stu-id="3608d-129">The message remains in the Inbox folder.</span></span>

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a><span data-ttu-id="3608d-130">Сообщение о нежелательных сообщениях из папки нежелательной почты в Outlook для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="3608d-130">Report non-spam messages from the Junk folder in Outlook for iOS and Android</span></span>

<span data-ttu-id="3608d-131">Чтобы сообщить о ложных срабатываниях нежелательной почты, в папке нежелательной почты с помощью следующих действий:</span><span class="sxs-lookup"><span data-stu-id="3608d-131">In the Junk folder, use the following steps to report spam false positives:</span></span>

1. <span data-ttu-id="3608d-132">Выберите одно или несколько сообщений.</span><span class="sxs-lookup"><span data-stu-id="3608d-132">Select one or more messages.</span></span>
2. <span data-ttu-id="3608d-133">В правом верхнем углу коснитесь трех вертикальных точек.</span><span class="sxs-lookup"><span data-stu-id="3608d-133">In the top-right corner tap on the three vertical dots.</span></span> <span data-ttu-id="3608d-134">Откроется меню действий.</span><span class="sxs-lookup"><span data-stu-id="3608d-134">The action menu opens.</span></span>

   ![Сообщение о нежелательной почте из меню действий](../../media/Android-not-junk-email.png)

3. <span data-ttu-id="3608d-136">Tap **Not junk**.</span><span class="sxs-lookup"><span data-stu-id="3608d-136">Tap **Not junk**.</span></span>

<span data-ttu-id="3608d-137">Появится всплывающее уведомление о том, что сообщение перемещено в вашу учетную почту.</span><span class="sxs-lookup"><span data-stu-id="3608d-137">A toast notification appears that the email has moved to your Inbox.</span></span> <span data-ttu-id="3608d-138">Если вы передумаете, выберите **"Отменить" во** всплывающее уведомление.</span><span class="sxs-lookup"><span data-stu-id="3608d-138">If you change your mind, select **Undo** on the toast notification.</span></span> <span data-ttu-id="3608d-139">Сообщение остается в папке нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="3608d-139">The email remains in the Junk folder.</span></span>
