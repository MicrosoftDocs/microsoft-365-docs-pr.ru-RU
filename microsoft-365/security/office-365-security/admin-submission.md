---
title: Учетные данные администратора в Office 365, Office 365, проблема с нежелательной почтой, Office 365 Нежелательная почта, отправка сообщений об фишинге в Office 365, отправка электронной почты для сканирования, подозрительные сообщения электронной почты в Office 365, сканирование почты, сканирование почты с помощью Microsoft Scan для фишинга, сканирование почты, отправка почты Электронная почта, отправка электронной почты
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
ms.openlocfilehash: 5ca5eab2feab1243a83eb60c9320fd48dfb59f12
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37091532"
---
# <a name="how-to-submit-suspected-spam-phish-urls-and-files-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="0e422-103">Как отправлять сообщения о нежелательной почте, фишинге, URL-адресах и файлах в корпорацию Майкрософт для сканирования Office 365</span><span class="sxs-lookup"><span data-stu-id="0e422-103">How to submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="0e422-104">Администраторы могут отправлять сообщения электронной почты с помощью файлов или сетевых сообщений с ИДЕНТИФИКАТОРами, URL-адресами и файлами для сканирования корпорацией Майкрософт в Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e422-104">Admins can send emails by using file or network message ID, URLs, and files for scanning by Microsoft in Office 365.</span></span> <span data-ttu-id="0e422-105">В разделе обновленные отправки все еще включены сообщения о пользователях, доступные всем пользователям с помощью EOP.</span><span class="sxs-lookup"><span data-stu-id="0e422-105">The updated submissions section still includes user reported messages and available to all customers using EOP.</span></span>

<span data-ttu-id="0e422-106">При отсылке сообщения электронной почты вы получите сведения о политиках, которые могут разрешить входящую электронную почту в клиент, а также о том, как все URL-адреса и вложения в почте.</span><span class="sxs-lookup"><span data-stu-id="0e422-106">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="0e422-107">Политики, которые могут разрешить почту, включают список надежных отправителей отдельного пользователя, а также политики уровня клиента, такие как правила ETR.</span><span class="sxs-lookup"><span data-stu-id="0e422-107">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as ETR rules.</span></span> 

## <a name="how-to-submit-content-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="0e422-108">Как отсылать контент в Microsoft для Office 365 сканирование</span><span class="sxs-lookup"><span data-stu-id="0e422-108">How to submit content to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="0e422-109">Чтобы отправить контент в корпорацию Майкрософт, нажмите кнопку **создать отправку** в верхней левой части страницы отправки.</span><span class="sxs-lookup"><span data-stu-id="0e422-109">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="0e422-110">Откроется всплывающее окно с правой стороны страницы с возможностью отправки сообщения электронной почты, URL-адреса или файла.</span><span class="sxs-lookup"><span data-stu-id="0e422-110">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span> 

### <a name="submit-an-email-to-microsoft"></a><span data-ttu-id="0e422-111">Отправка электронного письма в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="0e422-111">Submit an email to Microsoft</span></span>
![Пример отправки электронной почты](../media/submission-flyout-email.PNG)
1. <span data-ttu-id="0e422-113">Чтобы отправить сообщение электронной почты, выберите пункт **Электронная почта** и укажите идентификатор почтового **сообщения** или отправьте файл электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0e422-113">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span> 

2. <span data-ttu-id="0e422-114">Укажите получателей, для которых требуется выполнить проверку политики.</span><span class="sxs-lookup"><span data-stu-id="0e422-114">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="0e422-115">Проверка политики определяет, пропускается ли сканирование сообщений электронной почты в соответствии с политиками уровня пользователя или клиента.</span><span class="sxs-lookup"><span data-stu-id="0e422-115">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span> 

3. <span data-ttu-id="0e422-116">Укажите, следует ли блокировать сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0e422-116">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="0e422-117">Если сообщение должно быть заблокировано, укажите, должно ли оно быть заблокировано как спам, фишинг или вредоносная программа.</span><span class="sxs-lookup"><span data-stu-id="0e422-117">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="0e422-118">Если вы не знаете, какой тип может быть выбран, используйте наилучшее.</span><span class="sxs-lookup"><span data-stu-id="0e422-118">If you are not sure what type it might be, use your best judgement.</span></span>  

* <span data-ttu-id="0e422-119">Если фильтр обходится из-за политик при отправке, вы увидите сведения об этой политике.</span><span class="sxs-lookup"><span data-stu-id="0e422-119">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

* <span data-ttu-id="0e422-120">Если фильтр не обходится из-за одной или нескольких политик, сканирование будет завершено через несколько минут.</span><span class="sxs-lookup"><span data-stu-id="0e422-120">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="0e422-121">Вы увидите дополнительные сведения об отправке, щелкнув ссылку состояние.</span><span class="sxs-lookup"><span data-stu-id="0e422-121">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="0e422-122">К ним относятся результаты проверки политики и вредоносности повторного сканирования.</span><span class="sxs-lookup"><span data-stu-id="0e422-122">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="0e422-123">Примечание Это не приводит к повторному выполнению электронной почты через стек полного фильтра Office 365 ATP, но выполняет частичное повторное сканирование, основанное на определенных атрибутах почты, URL-адреса или файла.</span><span class="sxs-lookup"><span data-stu-id="0e422-123">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span> 

4. <span data-ttu-id="0e422-124">Нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="0e422-124">Click the **Submit** button.</span></span>

### <a name="submit-a-url-to-microsoft"></a><span data-ttu-id="0e422-125">Предоставление URL-адреса в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="0e422-125">Submit a URL to Microsoft</span></span>
![Пример отправки электронной почты](../media/submission-url-flyout.png)
1. <span data-ttu-id="0e422-127">Чтобы добавить URL-адрес, выберите **URL-адрес** из всплывающего меню.</span><span class="sxs-lookup"><span data-stu-id="0e422-127">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="0e422-128">Введите полный URL-адрес, включая протокол (**https://**).</span><span class="sxs-lookup"><span data-stu-id="0e422-128">Type in the full URL including the protocol (**https://**).</span></span> 

* <span data-ttu-id="0e422-129">Если вы выбрали **фильтрацию**, укажите, является ли URL-адрес фишингом или вредоносным по.</span><span class="sxs-lookup"><span data-stu-id="0e422-129">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="0e422-130">Нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="0e422-130">Click the **Submit** button.</span></span> 


### <a name="submit-a-file-to-microsoft"></a><span data-ttu-id="0e422-131">Передача файла в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="0e422-131">Submit a file to Microsoft</span></span>
![Пример отправки электронной почты](../media/submission-file-flyout.PNG)
1. <span data-ttu-id="0e422-133">Чтобы отправить файл, выберите **файл** из всплывающего меню и отправьте файл, который требуется проверить.</span><span class="sxs-lookup"><span data-stu-id="0e422-133">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span> 

2. <span data-ttu-id="0e422-134">Нажмите кнопку " **послать** ".</span><span class="sxs-lookup"><span data-stu-id="0e422-134">Click the **Submit** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="0e422-135">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0e422-135">Related topics</span></span>

[<span data-ttu-id="0e422-136">Office 365 Advanced Threat protection (план 2)</span><span class="sxs-lookup"><span data-stu-id="0e422-136">Office 365 Advanced Threat Protection Plan 2</span></span>](office-365-ti.md)
  
[<span data-ttu-id="0e422-137">Защита от угроз в Office 365</span><span class="sxs-lookup"><span data-stu-id="0e422-137">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="0e422-138">Просмотр отчетов для Office 365 Advanced Threat protection</span><span class="sxs-lookup"><span data-stu-id="0e422-138">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

