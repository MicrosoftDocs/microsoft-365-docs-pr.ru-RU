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
ms.openlocfilehash: e3e3a2d77c978649e7496d09f78301add397fb9d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289177"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="65757-103">Сообщение о нежелательной и фишинговой почте в Outlook для iOS и Android в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="65757-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="65757-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="65757-104">**Applies to**</span></span>
- [<span data-ttu-id="65757-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="65757-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="65757-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="65757-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="65757-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65757-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="65757-108">В организациях Microsoft 365 с почтовыми ящиками в Exchange [](../../enterprise/hybrid-modern-auth-overview.md)Online или в локальном почтовом ящике с использованием гибридной современной проверки подлинности вы можете использовать встроенные параметры отчетов в Outlook для iOS и Android, чтобы отправлять ложные срабатывания (хорошая электронная почта помечена как спам), ложные отрицательные результаты (разрешено использование нежелательной почты) и фишинговые сообщения в Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="65757-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="65757-109">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="65757-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="65757-110">Для наилучшего пользовательского интерфейса отправки рекомендуется использовать надстройки Report Message и Report Phishing. Дополнительные [сведения см.](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) в подстройки "Включить сообщение отчета" и "Включить надстройку report [Phishing".](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in)</span><span class="sxs-lookup"><span data-stu-id="65757-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) and [Enable the Report Phishing add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) for more information.</span></span>

- <span data-ttu-id="65757-111">Если вы администратор организации с почтовыми ящиками Exchange Online, рекомендуем использовать портал отправки в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="65757-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="65757-112">Дополнительные сведения см. в документе "Отправка администратора" для отправки подозрительной нежелательной [почты, фишинга, URL-адресов и файлов в корпорацию Майкрософт.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="65757-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="65757-113">Вы можете настроить копирование или перенаправление сообщений в задаемый почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="65757-113">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="65757-114">Дополнительные сведения [см. в политиках отправки пользователей.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="65757-114">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="65757-115">Дополнительные сведения об отчетах о сообщениях в корпорацию Майкрософт см. в отчете о [сообщениях и файлах корпорации Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="65757-115">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="65757-116">Если отчеты о нежелательной почте отключены для Outlook в политике отправки пользователей, нежелательные или фишинговые сообщения будут перемещены в папку нежелательной почты и не будут отправлены администратору или корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="65757-116">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>