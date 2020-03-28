---
title: Учетные данные администратора в Office 365, Office 365, проблема с нежелательной почтой, Office 365 Нежелательная почта, отправка сообщений об фишинге в Office 365, отправка электронной почты для сканирования, подозрительные сообщения электронной почты в Office 365, сканирование почты, сканирование почты с помощью Microsoft Scan для фишинга, сканирование почты, отправка почты Электронная почта, отправка электронной почты, додги электронной почты, ненадежных почтовых ящиков, подозрительных сообщений, непроверенных сообщений, отчетов о phishing-сообщениях в корпорацию Майкрософт, отчетов о phishing-сообщениях в корпорацию Майкрософт, отправки сообщений электронной почты в корпорацию Майкрософт, отправки сообщений по электронной почте корпорации Майкрософт, спама Электронная почта в папке "Входящие" Office 365, вирус в Office 365
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
description: Сведения о том, как отправлять подозрительные сообщения электронной почты, подозреваемые фишинговые сообщения, нежелательные сообщения и другие потенциально опасные сообщения, URL-адреса и файлы из клиента Office 365 в корпорацию Майкрософт для сканирования.
ms.openlocfilehash: 539d09f03a8a9c5956f2d1e3584f893b0e4ffbb4
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033618"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="b2e46-103">Использование отправки администратором для отправки сообщений с подозрением, фишинга, URL-адресов и файлов в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b2e46-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="b2e46-104">Если вы являетесь администратором в организации Office 365 с почтовыми ящиками в Exchange Online, вы можете использовать портал отправки в центре безопасности & соответствия требованиям Office 365 для отправки электронных сообщений, URL-адресов и вложений в корпорацию Майкрософт для сканирования.</span><span class="sxs-lookup"><span data-stu-id="b2e46-104">If you're an admin in an Office 365 organization with mailboxes in Exchange Online, you can use the Submissions portal in the Office 365 Security & Compliance Center to submit email messages, URLs and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="b2e46-105">При отсылке сообщения электронной почты вы получите сведения о политиках, которые могут разрешить входящую электронную почту в клиент, а также о том, как все URL-адреса и вложения в почте.</span><span class="sxs-lookup"><span data-stu-id="b2e46-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="b2e46-106">Политики, которые могут разрешить почту, включают список надежных отправителей отдельного пользователя, а также политики уровня клиента, такие как правила для обработки почты Exchange (также называемые правилами транспорта).</span><span class="sxs-lookup"><span data-stu-id="b2e46-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="b2e46-107">Другие способы отправки сообщений электронной почты, URL-адресов и вложений в корпорацию Майкрософт приведены в статье</span><span class="sxs-lookup"><span data-stu-id="b2e46-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b2e46-108">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="b2e46-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b2e46-109">Откройте Центр безопасности и соответствия требованиям по ссылке <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b2e46-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b2e46-110">Чтобы перейти непосредственно на страницу **отправки** , используйте <https://protection.office.com/reportsubmission>.</span><span class="sxs-lookup"><span data-stu-id="b2e46-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="b2e46-111">Сведения о подключении к Exchange Online PowerShell см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b2e46-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="b2e46-112">Сведения о подключении к автономной службе Exchange Online Protection PowerShell см. в статье [Подключение к PowerShell для Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="b2e46-112">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b2e46-113">Для выполнения этих процедур необходимы соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="b2e46-113">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="b2e46-114">Для добавления, изменения и удаления политик защиты от нежелательной почты необходимо быть участником группы ролей " **Управление организацией**", " **администратор безопасности**" или " **читатель безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="b2e46-114">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="b2e46-115">Дополнительные сведения о группах ролей в Центре безопасности и соответствия требованиям см. в статье [Разрешения в Центре безопасности и соответствия требованиям Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b2e46-115">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="b2e46-116">Для получения дополнительных сведений о том, как пользователи могут отправить сообщения и файлы в корпорацию Майкрософт, просмотрите [сообщения отчетов и файлы в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="b2e46-116">For more information about how users can submit messages and files to Microsoft see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="b2e46-117">Как поправлять подозрительные материалы в корпорацию Майкрософт для сканирования Office 365</span><span class="sxs-lookup"><span data-stu-id="b2e46-117">How to direct suspicious content to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="b2e46-118">Чтобы отправить контент в корпорацию Майкрософт, нажмите кнопку **создать отправку** в верхней левой части страницы отправки.</span><span class="sxs-lookup"><span data-stu-id="b2e46-118">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="b2e46-119">Откроется всплывающее окно с правой стороны страницы с возможностью отправки сообщения электронной почты, URL-адреса или файла.</span><span class="sxs-lookup"><span data-stu-id="b2e46-119">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="b2e46-120">Отправка сомнительных сообщений электронной почты в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b2e46-120">Submit a questionable email to Microsoft</span></span>

![Пример отправки электронной почты](../../media/submission-flyout-email.PNG)

1. <span data-ttu-id="b2e46-122">Чтобы отправить сообщение электронной почты, выберите пункт **Электронная почта** и укажите идентификатор почтового **сообщения** или отправьте файл электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b2e46-122">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span>

2. <span data-ttu-id="b2e46-123">Укажите получателей, для которых требуется выполнить проверку политики.</span><span class="sxs-lookup"><span data-stu-id="b2e46-123">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="b2e46-124">Проверка политики определяет, пропускается ли сканирование сообщений электронной почты в соответствии с политиками уровня пользователя или клиента.</span><span class="sxs-lookup"><span data-stu-id="b2e46-124">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span>

3. <span data-ttu-id="b2e46-125">Укажите, следует ли блокировать сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b2e46-125">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="b2e46-126">Если сообщение должно быть заблокировано, укажите, должно ли оно быть заблокировано как спам, фишинг или вредоносная программа.</span><span class="sxs-lookup"><span data-stu-id="b2e46-126">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="b2e46-127">Если вы не знаете, какой тип может быть выбран, используйте наиболее ненужные.</span><span class="sxs-lookup"><span data-stu-id="b2e46-127">If you are not sure what type it might be, use your best judgment.</span></span>

   - <span data-ttu-id="b2e46-128">Если фильтр обходится из-за политик при отправке, вы увидите сведения об этой политике.</span><span class="sxs-lookup"><span data-stu-id="b2e46-128">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   - <span data-ttu-id="b2e46-129">Если фильтр не обходится из-за одной или нескольких политик, сканирование будет завершено через несколько минут.</span><span class="sxs-lookup"><span data-stu-id="b2e46-129">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="b2e46-130">Вы увидите дополнительные сведения об отправке, щелкнув ссылку состояние.</span><span class="sxs-lookup"><span data-stu-id="b2e46-130">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="b2e46-131">К ним относятся результаты проверки политики и вредоносности повторного сканирования.</span><span class="sxs-lookup"><span data-stu-id="b2e46-131">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="b2e46-132">Примечание Это не приводит к повторному выполнению электронной почты через стек полного фильтра Office 365 ATP, но выполняет частичное повторное сканирование, основанное на определенных атрибутах почты, URL-адреса или файла.</span><span class="sxs-lookup"><span data-stu-id="b2e46-132">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

4. <span data-ttu-id="b2e46-133">Нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="b2e46-133">Click the **Submit** button.</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="b2e46-134">Отправка подозрительного URL-адреса корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b2e46-134">Send a suspect URL to Microsoft</span></span>

![Пример отправки электронной почты](../../media/submission-url-flyout.png)

1. <span data-ttu-id="b2e46-136">Чтобы добавить URL-адрес, выберите **URL-адрес** из всплывающего меню.</span><span class="sxs-lookup"><span data-stu-id="b2e46-136">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="b2e46-137">Введите полный URL-адрес, включая протокол (**https://**).</span><span class="sxs-lookup"><span data-stu-id="b2e46-137">Type in the full URL including the protocol (**https://**).</span></span>

   <span data-ttu-id="b2e46-138">Если вы выбрали **фильтрацию**, укажите, является ли URL-адрес фишингом или вредоносным по.</span><span class="sxs-lookup"><span data-stu-id="b2e46-138">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="b2e46-139">Нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="b2e46-139">Click the **Submit** button.</span></span>

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="b2e46-140">Передача подозреваемого файла в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="b2e46-140">Submit a suspected file to Microsoft</span></span>

![Пример отправки электронной почты](../../media/submission-file-flyout.PNG)

1. <span data-ttu-id="b2e46-142">Чтобы отправить файл, выберите **файл** из всплывающего меню и отправьте файл, который требуется проверить.</span><span class="sxs-lookup"><span data-stu-id="b2e46-142">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span>

2. <span data-ttu-id="b2e46-143">Нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="b2e46-143">Click the **Submit** button.</span></span>
