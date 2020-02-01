---
title: Учетные данные администратора в Office 365, Office 365, проблема с нежелательной почтой, Office 365 Нежелательная почта, отправка сообщений об фишинге в Office 365, отправка электронной почты для сканирования, подозрительные сообщения электронной почты в Office 365, сканирование почты, сканирование почты с помощью Microsoft Scan для фишинга, сканирование почты, отправка почты Электронная почта, отправка электронной почты, додги электронной почты, ненадежных почтовых ящиков, подозрительных сообщений, непроверенных сообщений, отчетов о phishing-сообщениях в корпорацию Майкрософт, отчетов о phishing-сообщениях в корпорацию Майкрософт, отправки сообщений электронной почты в корпорацию Майкрософт, отправки сообщений по электронной почте корпорации Майкрософт, спама Электронная почта в папке "Входящие" Office 365, вирус в Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 08/06/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Сведения о том, как отправлять подозрительные сообщения электронной почты, подозреваемые фишинговые сообщения, нежелательные сообщения и другие потенциально опасные сообщения, URL-адреса и файлы из клиента Office 365 в корпорацию Майкрософт для сканирования.
ms.openlocfilehash: a12981ee302ea72e112826104996fb775e4ac3fb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599986"
---
# <a name="how-to-submit-suspected-spam-phish-urls-and-files-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="8e15c-103">Как отправлять сообщения о нежелательной почте, фишинге, URL-адресах и файлах в корпорацию Майкрософт для сканирования Office 365</span><span class="sxs-lookup"><span data-stu-id="8e15c-103">How to submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="8e15c-104">Администраторы могут отправлять сообщения электронной почты с помощью файлов или сетевых сообщений с ИДЕНТИФИКАТОРами, URL-адресами и файлами для сканирования корпорацией Майкрософт в Office 365.</span><span class="sxs-lookup"><span data-stu-id="8e15c-104">Admins can send emails by using file or network message ID, URLs, and files for scanning by Microsoft in Office 365.</span></span>
<span data-ttu-id="8e15c-105">В разделе обновленные отправки все еще включены сообщения о пользователях, доступные всем пользователям с помощью EOP.</span><span class="sxs-lookup"><span data-stu-id="8e15c-105">The updated submissions section still includes user reported messages and available to all customers using EOP.</span></span>

<span data-ttu-id="8e15c-106">При отсылке сообщения электронной почты вы получите сведения о политиках, которые могут разрешить входящую электронную почту в клиент, а также о том, как все URL-адреса и вложения в почте.</span><span class="sxs-lookup"><span data-stu-id="8e15c-106">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="8e15c-107">Политики, которые могут разрешить почту, включают список надежных отправителей отдельного пользователя, а также политики уровня клиента, такие как правила для обработки почты Exchange (также называемые правилами транспорта).</span><span class="sxs-lookup"><span data-stu-id="8e15c-107">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="8e15c-108">Как поправлять подозрительные материалы в корпорацию Майкрософт для сканирования Office 365</span><span class="sxs-lookup"><span data-stu-id="8e15c-108">How to direct suspicious content to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="8e15c-109">Чтобы отправить контент в корпорацию Майкрософт, нажмите кнопку **создать отправку** в верхней левой части страницы отправки.</span><span class="sxs-lookup"><span data-stu-id="8e15c-109">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="8e15c-110">Откроется всплывающее окно с правой стороны страницы с возможностью отправки сообщения электронной почты, URL-адреса или файла.</span><span class="sxs-lookup"><span data-stu-id="8e15c-110">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="8e15c-111">Отправка сомнительных сообщений электронной почты в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8e15c-111">Submit a questionable email to Microsoft</span></span>

![Пример отправки электронной почты](../media/submission-flyout-email.PNG)

1. <span data-ttu-id="8e15c-113">Чтобы отправить сообщение электронной почты, выберите пункт **Электронная почта** и укажите идентификатор почтового **сообщения** или отправьте файл электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8e15c-113">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span>

2. <span data-ttu-id="8e15c-114">Укажите получателей, для которых требуется выполнить проверку политики.</span><span class="sxs-lookup"><span data-stu-id="8e15c-114">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="8e15c-115">Проверка политики определяет, пропускается ли сканирование сообщений электронной почты в соответствии с политиками уровня пользователя или клиента.</span><span class="sxs-lookup"><span data-stu-id="8e15c-115">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span>

3. <span data-ttu-id="8e15c-116">Укажите, следует ли блокировать сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8e15c-116">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="8e15c-117">Если сообщение должно быть заблокировано, укажите, должно ли оно быть заблокировано как спам, фишинг или вредоносная программа.</span><span class="sxs-lookup"><span data-stu-id="8e15c-117">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="8e15c-118">Если вы не знаете, какой тип может быть выбран, используйте наилучшее.</span><span class="sxs-lookup"><span data-stu-id="8e15c-118">If you are not sure what type it might be, use your best judgement.</span></span>

   - <span data-ttu-id="8e15c-119">Если фильтр обходится из-за политик при отправке, вы увидите сведения об этой политике.</span><span class="sxs-lookup"><span data-stu-id="8e15c-119">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   - <span data-ttu-id="8e15c-120">Если фильтр не обходится из-за одной или нескольких политик, сканирование будет завершено через несколько минут.</span><span class="sxs-lookup"><span data-stu-id="8e15c-120">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="8e15c-121">Вы увидите дополнительные сведения об отправке, щелкнув ссылку состояние.</span><span class="sxs-lookup"><span data-stu-id="8e15c-121">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="8e15c-122">К ним относятся результаты проверки политики и вредоносности повторного сканирования.</span><span class="sxs-lookup"><span data-stu-id="8e15c-122">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="8e15c-123">Примечание Это не приводит к повторному выполнению электронной почты через стек полного фильтра Office 365 ATP, но выполняет частичное повторное сканирование, основанное на определенных атрибутах почты, URL-адреса или файла.</span><span class="sxs-lookup"><span data-stu-id="8e15c-123">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

4. <span data-ttu-id="8e15c-124">Нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="8e15c-124">Click the **Submit** button.</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="8e15c-125">Отправка подозрительного URL-адреса корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8e15c-125">Send a suspect URL to Microsoft</span></span>

![Пример отправки электронной почты](../media/submission-url-flyout.png)

1. <span data-ttu-id="8e15c-127">Чтобы добавить URL-адрес, выберите **URL-адрес** из всплывающего меню.</span><span class="sxs-lookup"><span data-stu-id="8e15c-127">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="8e15c-128">Введите полный URL-адрес, включая протокол (**https://**).</span><span class="sxs-lookup"><span data-stu-id="8e15c-128">Type in the full URL including the protocol (**https://**).</span></span>

   <span data-ttu-id="8e15c-129">Если вы выбрали **фильтрацию**, укажите, является ли URL-адрес фишингом или вредоносным по.</span><span class="sxs-lookup"><span data-stu-id="8e15c-129">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="8e15c-130">Нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="8e15c-130">Click the **Submit** button.</span></span>

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="8e15c-131">Передача подозреваемого файла в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8e15c-131">Submit a suspected file to Microsoft</span></span>

![Пример отправки электронной почты](../media/submission-file-flyout.PNG)

1. <span data-ttu-id="8e15c-133">Чтобы отправить файл, выберите **файл** из всплывающего меню и отправьте файл, который требуется проверить.</span><span class="sxs-lookup"><span data-stu-id="8e15c-133">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span>

2. <span data-ttu-id="8e15c-134">Нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="8e15c-134">Click the **Submit** button.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8e15c-135">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="8e15c-135">Related topics</span></span>

[<span data-ttu-id="8e15c-136">Office 365 Advanced Threat Protection (план 2)</span><span class="sxs-lookup"><span data-stu-id="8e15c-136">Office 365 Advanced Threat Protection Plan 2</span></span>](office-365-ti.md)

[<span data-ttu-id="8e15c-137">Защита от угроз в Office 365</span><span class="sxs-lookup"><span data-stu-id="8e15c-137">Protect against threats in Office 365</span></span>](protect-against-threats.md)

[<span data-ttu-id="8e15c-138">Просмотр отчетов для Office 365 Advanced Threat protection</span><span class="sxs-lookup"><span data-stu-id="8e15c-138">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
