---
title: Отправки, отправки, проблемы с нежелательной почтой администраторами, false (неотрицательные), отправить фишинг, отправлять электронную почту для сканирования, подозрительные сообщения электронной почты в Office 365, сканировать почту, сканировать почту, отправлять сообщения электронной почты, отправлять сообщения электронной почты, сообщения электронной почты, подозрительные сообщения, подозрительные сообщения электронной почты в корпорацию Майкрософт, сообщать о мошеннических сообщениях в корпорацию Майкрософт. , отчитываться о вредоносных сообщениях в Майкрософт, спаме в папке "Входящие", вирусы в электронной почте
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Сведения о том, как отправлять подозрительные сообщения электронной почты, подозрительные фишинговые сообщения, спам и другие потенциально опасные сообщения, URL-адреса и файлы из компании в корпорацию Майкрософт для сканирования.
ms.openlocfilehash: 2d86555854f9babd202764f1bad8b548daf52c70
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631385"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="d7d64-103">Использование функции отправки администратором для отправки подозрительного спама, фишинговых сообщений, URL-адресов и файлов в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d7d64-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="d7d64-104">Если вы являетесь администратором в организации Microsoft 365 с почтовыми ящиками в Exchange Online, вы можете использовать портал отправки в центре безопасности & соответствия требованиям, чтобы отправлять сообщения электронной почты, URL-адреса и вложения в корпорацию Майкрософт для сканирования.</span><span class="sxs-lookup"><span data-stu-id="d7d64-104">If you're an admin in a Microsoft 365 organization with mailboxes in Exchange Online, you can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="d7d64-105">При отсылке сообщения электронной почты вы получите сведения о политиках, которые могут разрешить входящую электронную почту в клиент, а также о том, как все URL-адреса и вложения в почте.</span><span class="sxs-lookup"><span data-stu-id="d7d64-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="d7d64-106">Политики, которые могут разрешить почту, включают список надежных отправителей отдельного пользователя, а также политики уровня клиента, такие как правила для обработки почты Exchange (также называемые правилами транспорта).</span><span class="sxs-lookup"><span data-stu-id="d7d64-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="d7d64-107">Другие способы отправки сообщений электронной почты, URL-адресов и вложений в корпорацию Майкрософт приведены в статье</span><span class="sxs-lookup"><span data-stu-id="d7d64-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d7d64-108">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="d7d64-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d7d64-109">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="d7d64-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d7d64-110">Чтобы перейти непосредственно на страницу **отправки** , используйте <https://protection.office.com/reportsubmission>.</span><span class="sxs-lookup"><span data-stu-id="d7d64-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="d7d64-111">Сведения о подключении к Exchange Online PowerShell см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d7d64-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d7d64-112">Сведения о подключении к автономной службе Exchange Online Protection PowerShell см. в статье [Подключение к PowerShell для Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="d7d64-112">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d7d64-113">Для выполнения этих процедур необходимы соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="d7d64-113">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="d7d64-114">Для добавления, изменения и удаления политик защиты от нежелательной почты необходимо быть участником группы ролей " **Управление организацией**", " **администратор безопасности**" или " **читатель безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="d7d64-114">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="d7d64-115">Дополнительные сведения о группах ролей в центре безопасности & соответствия требованиям приведены в разделе [разрешения в центре безопасности &](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d7d64-115">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="d7d64-116">Для получения дополнительных сведений о том, как пользователи могут отправить сообщения и файлы в корпорацию Майкрософт, просмотрите [сообщения отчетов и файлы в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="d7d64-116">For more information about how users can submit messages and files to Microsoft see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="how-to-direct-suspicious-content-to-microsoft-scanning"></a><span data-ttu-id="d7d64-117">Как направить подозрительный контент в сканирование Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d7d64-117">How to direct suspicious content to Microsoft scanning</span></span>

<span data-ttu-id="d7d64-118">Чтобы отправить контент в корпорацию Майкрософт, нажмите кнопку **создать отправку** в верхней левой части страницы отправки.</span><span class="sxs-lookup"><span data-stu-id="d7d64-118">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="d7d64-119">Откроется всплывающее окно с правой стороны страницы с возможностью отправки сообщения электронной почты, URL-адреса или файла.</span><span class="sxs-lookup"><span data-stu-id="d7d64-119">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="d7d64-120">Отправка сомнительных сообщений электронной почты в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d7d64-120">Submit a questionable email to Microsoft</span></span>

![Пример отправки электронной почты](../../media/submission-flyout-email.PNG)

1. <span data-ttu-id="d7d64-122">Чтобы отправить сообщение электронной почты, выберите пункт **Электронная почта** и укажите идентификатор почтового **сообщения** или отправьте файл электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d7d64-122">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span>

2. <span data-ttu-id="d7d64-123">Укажите получателей, для которых требуется выполнить проверку политики.</span><span class="sxs-lookup"><span data-stu-id="d7d64-123">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="d7d64-124">Проверка политики определяет, пропускается ли сканирование сообщений электронной почты в соответствии с политиками уровня пользователя или клиента.</span><span class="sxs-lookup"><span data-stu-id="d7d64-124">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span>

3. <span data-ttu-id="d7d64-125">Укажите, следует ли блокировать сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d7d64-125">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="d7d64-126">Если сообщение должно быть заблокировано, укажите, должно ли оно быть заблокировано как спам, фишинг или вредоносная программа.</span><span class="sxs-lookup"><span data-stu-id="d7d64-126">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="d7d64-127">Если вы не знаете, какой тип может быть выбран, используйте наиболее ненужные.</span><span class="sxs-lookup"><span data-stu-id="d7d64-127">If you are not sure what type it might be, use your best judgment.</span></span>

   - <span data-ttu-id="d7d64-128">Если фильтр обходится из-за политик при отправке, вы увидите сведения об этой политике.</span><span class="sxs-lookup"><span data-stu-id="d7d64-128">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   - <span data-ttu-id="d7d64-129">Если фильтр не обходится из-за одной или нескольких политик, сканирование будет завершено через несколько минут.</span><span class="sxs-lookup"><span data-stu-id="d7d64-129">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="d7d64-130">Вы увидите дополнительные сведения об отправке, щелкнув ссылку состояние.</span><span class="sxs-lookup"><span data-stu-id="d7d64-130">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="d7d64-131">К ним относятся результаты проверки политики и вредоносности повторного сканирования.</span><span class="sxs-lookup"><span data-stu-id="d7d64-131">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="d7d64-132">Примечание Это не приводит к повторному выполнению электронной почты через стек полного фильтра Office 365 ATP, но выполняет частичное повторное сканирование, основанное на определенных атрибутах почты, URL-адреса или файла.</span><span class="sxs-lookup"><span data-stu-id="d7d64-132">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

4. <span data-ttu-id="d7d64-133">Нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="d7d64-133">Click the **Submit** button.</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="d7d64-134">Отправка подозрительного URL-адреса корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d7d64-134">Send a suspect URL to Microsoft</span></span>

![Пример отправки электронной почты](../../media/submission-url-flyout.png)

1. <span data-ttu-id="d7d64-136">Чтобы добавить URL-адрес, выберите **URL-адрес** из всплывающего меню.</span><span class="sxs-lookup"><span data-stu-id="d7d64-136">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="d7d64-137">Введите полный URL-адрес, включая протокол (**https://**).</span><span class="sxs-lookup"><span data-stu-id="d7d64-137">Type in the full URL including the protocol (**https://**).</span></span>

   <span data-ttu-id="d7d64-138">Если вы выбрали **фильтрацию**, укажите, является ли URL-адрес фишингом или вредоносным по.</span><span class="sxs-lookup"><span data-stu-id="d7d64-138">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="d7d64-139">Нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="d7d64-139">Click the **Submit** button.</span></span>

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="d7d64-140">Передача подозреваемого файла в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="d7d64-140">Submit a suspected file to Microsoft</span></span>

![Пример отправки электронной почты](../../media/submission-file-flyout.PNG)

1. <span data-ttu-id="d7d64-142">Чтобы отправить файл, выберите **файл** из всплывающего меню и отправьте файл, который требуется проверить.</span><span class="sxs-lookup"><span data-stu-id="d7d64-142">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span>

2. <span data-ttu-id="d7d64-143">Нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="d7d64-143">Click the **Submit** button.</span></span>
