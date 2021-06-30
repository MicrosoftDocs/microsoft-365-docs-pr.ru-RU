---
title: Представления администратора
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
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать, как использовать портал Отправки на портале Microsoft 365 Defender для отправки подозрительных сообщений электронной почты, подозрительных фишинговых сообщений, нежелательной почты и других потенциально вредных сообщений, URL-адресов и вложений электронной почты в Корпорацию Майкрософт для повторного использования.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eecb635972be85e1a1a4f95c2786f209ee249745
ms.sourcegitcommit: 99e67bfe1d677c2f51712b05dcc54908b343cf6f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2021
ms.locfileid: "53203284"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="f0526-103">Использование функции отправки администратором для отправки подозрительного спама, фишинговых сообщений, URL-адресов и файлов в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f0526-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f0526-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="f0526-104">**Applies to**</span></span>
- [<span data-ttu-id="f0526-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f0526-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f0526-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="f0526-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="f0526-107">В Microsoft 365 организациях с Exchange Online почтовыми ящиками администраторы могут использовать портал Отправки на портале Microsoft 365 Defender для отправки сообщений электронной почты, URL-адресов и вложений в Корпорацию Майкрософт для сканирования.</span><span class="sxs-lookup"><span data-stu-id="f0526-107">In Microsoft 365 organizations with Exchange Online mailboxes, admins can use the Submissions portal in the Microsoft 365 Defender portal to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="f0526-108">При отправке сообщения электронной почты вы получите:</span><span class="sxs-lookup"><span data-stu-id="f0526-108">When you submit an email message, you will get:</span></span>

- <span data-ttu-id="f0526-109">**Проверка подлинности электронной** почты. Сведения о том, прошла ли проверка подлинности электронной почты при ее доставке или сбой.</span><span class="sxs-lookup"><span data-stu-id="f0526-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
- <span data-ttu-id="f0526-110">**Хиты** политики. Сведения о любых политиках, которые могли разрешить или заблокировать входящие сообщения электронной почты в клиента, переопределив наши решения фильтра службы.</span><span class="sxs-lookup"><span data-stu-id="f0526-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
- <span data-ttu-id="f0526-111">**Репутация и детонация полезной** нагрузки: проверка url-адресов и вложений в сообщении.</span><span class="sxs-lookup"><span data-stu-id="f0526-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
- <span data-ttu-id="f0526-112">**Анализ грейдера.** Проверка, сделанная грейдерами,чтобы подтвердить, являются ли сообщения вредоносными.</span><span class="sxs-lookup"><span data-stu-id="f0526-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0526-113">Анализ репутации/детонации и грейдера полезной нагрузки не проводится во всех клиентах.</span><span class="sxs-lookup"><span data-stu-id="f0526-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="f0526-114">Сведения не могут выходить за пределы организации, если данные не должны покидать границу клиента в целях соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="f0526-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="f0526-115">Другие способы отправки сообщений электронной почты, URL-адресов и вложений в Корпорацию Майкрософт см. в этой ссылке. [](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="f0526-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f0526-116">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="f0526-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f0526-117">Чтобы открыть портал Microsoft 365 Defender, перейдите на сайт <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="f0526-117">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="f0526-118">Чтобы перейти непосредственно на **страницу Отправки,** используйте <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="f0526-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="f0526-119">Чтобы отправить сообщения и файлы в Корпорацию Майкрософт, необходимо быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="f0526-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="f0526-120">**Управление организацией** или **чтение** безопасности [на Microsoft 365 Defender портале](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="f0526-120">**Organization Management** or **Security Reader** in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  
    <span data-ttu-id="f0526-121">Обратите внимание, что членство в [](#view-user-submissions-to-microsoft) этой группе ролей необходимо для просмотра пользовательских представлений в настраиваемом почтовом ящике, как описано выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="f0526-121">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-microsoft) as described later in this article.</span></span>

- <span data-ttu-id="f0526-122">Дополнительные сведения о том, как пользователи могут отправлять сообщения и файлы в Корпорацию Майкрософт, см. в материалах [Report messages and files to Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="f0526-122">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="f0526-123">Сообщение о подозрительном контенте в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f0526-123">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="f0526-124">На портале Microsoft 365 Defender перейдите на электронную **почту &** \> **отправки совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="f0526-124">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="f0526-125">На странице **Отправки** убедитесь, что выбрана вкладка Отправка для анализа, а затем щелкните значок  ![ Ad Submit to Microsoft для ](../../media/m365-cc-sc-create-icon.png) **анализа.**</span><span class="sxs-lookup"><span data-stu-id="f0526-125">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected, and then click ![Ad icon](../../media/m365-cc-sc-create-icon.png) **Submit to Microsoft for analysis**.</span></span>

3. <span data-ttu-id="f0526-126">Используйте **отправку в Корпорацию Майкрософт** для проверки вылетов, которые, как представляется, представляют сообщение, URL-адрес или вложение электронной почты, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="f0526-126">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="f0526-127">Отправка сомнительного сообщения электронной почты в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f0526-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="f0526-128">В поле **Выберите тип отправки** убедитесь, что **электронная** почта выбрана в списке drop down.</span><span class="sxs-lookup"><span data-stu-id="f0526-128">In the **Select the submission type** box, verify that **Email** is selected in the drop down list.</span></span>

2. <span data-ttu-id="f0526-129">В разделе **Добавление сетевого сообщения или** отправка раздела файл электронной почты используйте один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="f0526-129">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>
   - <span data-ttu-id="f0526-130">Добавьте сетевой **ID** сообщения электронной почты. Это значение GUID, доступное в загонщике **X-MS-Exchange-Organization-Network-Message-Id** в сообщении или в **загоне X-MS-Office365-Filtering-Correlation-Id** в карантинных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="f0526-130">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>
   - <span data-ttu-id="f0526-131">**Upload файл электронной почты (.msg или .eml)**: Щелкните **Просмотр файлов**.</span><span class="sxs-lookup"><span data-stu-id="f0526-131">**Upload the email file (.msg or .eml)**: Click **Browse files**.</span></span> <span data-ttu-id="f0526-132">В открываемом диалоговом окте найти и выбрать файл .eml или .msg, а затем нажмите **кнопку Открыть**.</span><span class="sxs-lookup"><span data-stu-id="f0526-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f0526-133">Возможность отправки сообщений в течение 30 дней была временно приостановлена для defender для Office 365 клиентов.</span><span class="sxs-lookup"><span data-stu-id="f0526-133">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="f0526-134">Администраторы смогут возвращаться только через 7 дней.</span><span class="sxs-lookup"><span data-stu-id="f0526-134">Admins will only be able to go back 7 days.</span></span>

3. <span data-ttu-id="f0526-135">В поле Выбор получателя с **проблемным полем** укажите получателя, против которого необходимо выполнить проверку политики.</span><span class="sxs-lookup"><span data-stu-id="f0526-135">In the **Choose a recipient who had an issue** box, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="f0526-136">Проверка политики определяет, не обходится ли проверка электронной почты из-за политики пользователя или организации.</span><span class="sxs-lookup"><span data-stu-id="f0526-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

4. <span data-ttu-id="f0526-137">В разделе **Выбор причины отправки в раздел Microsoft** выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="f0526-137">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="f0526-138">**Не должно было быть заблокировано (ложное срабатыва-**</span><span class="sxs-lookup"><span data-stu-id="f0526-138">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="f0526-139">**Должно было быть** заблокировано: В сообщении электронной почты следует классифицируются как раздел, который отображается, выберите одно из следующих значений (если вы не уверены, используйте свое наилучшее решение): </span><span class="sxs-lookup"><span data-stu-id="f0526-139">**Should have been blocked**: In the **The email should have been categorized as** section that appears, select one of the following values (if you're not sure, use your best judgement):</span></span>
     - <span data-ttu-id="f0526-140">**Фишинг**</span><span class="sxs-lookup"><span data-stu-id="f0526-140">**Phish**</span></span>
     - <span data-ttu-id="f0526-141">**Спам**</span><span class="sxs-lookup"><span data-stu-id="f0526-141">**Spam**</span></span>
     - <span data-ttu-id="f0526-142">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="f0526-142">**Malware**</span></span>

5. <span data-ttu-id="f0526-143">По завершению нажмите кнопку **Отправить.**</span><span class="sxs-lookup"><span data-stu-id="f0526-143">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f0526-144">![Новый пример отправки URL-адресов](../../media/submission-flyout-email.png)</span><span class="sxs-lookup"><span data-stu-id="f0526-144">![New URL submission example](../../media/submission-flyout-email.png)</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="f0526-145">Отправка подозрительного URL-адреса в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f0526-145">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="f0526-146">В поле **Выберите тип отправки** выберите **URL-адрес** из списка drop down.</span><span class="sxs-lookup"><span data-stu-id="f0526-146">In the **Select the submission type** box, select **URL** from the drop down list.</span></span>

2. <span data-ttu-id="f0526-147">В поле **URL-адреса,** которое отображается, введите полный URL-адрес (например, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="f0526-147">In the **URL** box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

3. <span data-ttu-id="f0526-148">В разделе **Выбор причины отправки в раздел Microsoft** выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="f0526-148">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="f0526-149">**Не должно было быть заблокировано (ложное срабатыва-**</span><span class="sxs-lookup"><span data-stu-id="f0526-149">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="f0526-150">**Должно было быть заблокировано:** В этом **URL-адресе** следует классифицируются как раздел, который отображается, выберите **фишинг или** вредоносные **программы**.</span><span class="sxs-lookup"><span data-stu-id="f0526-150">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, select **Phish** or **Malware**.</span></span>

4. <span data-ttu-id="f0526-151">По завершению нажмите кнопку **Отправить.**</span><span class="sxs-lookup"><span data-stu-id="f0526-151">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f0526-152">![Новый пример отправки электронной почты](../../media/submission-url-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="f0526-152">![New Email submission example](../../media/submission-url-flyout.png)</span></span>

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="f0526-153">Отправка предполагаемого вложения электронной почты в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f0526-153">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="f0526-154">В поле **Выберите тип отправки** выберите **Файл из** списка выпаданий.</span><span class="sxs-lookup"><span data-stu-id="f0526-154">In the **Select the submission type** box, select **File** from the drop down list.</span></span>

2. <span data-ttu-id="f0526-155">В разделе **Файл,** который появится, щелкните **Просмотр файлов**.</span><span class="sxs-lookup"><span data-stu-id="f0526-155">In the **File** section that appears, click **Browse files**.</span></span> <span data-ttu-id="f0526-156">В открываемом диалоговом окте найти и выбрать файл, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="f0526-156">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="f0526-157">В разделе **Выбор причины отправки в раздел Microsoft** выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="f0526-157">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="f0526-158">**Не должно было быть заблокировано (ложное срабатыва-**</span><span class="sxs-lookup"><span data-stu-id="f0526-158">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="f0526-159">**Должно быть заблокировано.** В этом **URL-адресе** должен быть классифицирован **раздел,** который отображается, вредоносные программы является единственным выбором, и автоматически выбирается.</span><span class="sxs-lookup"><span data-stu-id="f0526-159">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="f0526-160">По завершению нажмите кнопку **Отправить.**</span><span class="sxs-lookup"><span data-stu-id="f0526-160">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f0526-161">![Пример отправки вложения](../../media/submission-file-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="f0526-161">![New Attachment submission example](../../media/submission-file-flyout.png)</span></span>

## <a name="view-admin-submissions-to-microsoft"></a><span data-ttu-id="f0526-162">Просмотр представлений администратора в Корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f0526-162">View admin submissions to Microsoft</span></span>

1. <span data-ttu-id="f0526-163">На портале Microsoft 365 Defender перейдите на электронную **почту &** \> **отправки совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="f0526-163">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="f0526-164">На странице **Отправки** убедитесь, что выбрана вкладка **Отправка** для анализа.</span><span class="sxs-lookup"><span data-stu-id="f0526-164">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected.</span></span>

   - <span data-ttu-id="f0526-165">Вы можете сортировать записи, нажав на доступный столбец.</span><span class="sxs-lookup"><span data-stu-id="f0526-165">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="f0526-166">Нажмите **кнопку Настройка столбцов,** чтобы показать максимум семь столбцов.</span><span class="sxs-lookup"><span data-stu-id="f0526-166">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="f0526-167">Значения по умолчанию помечены звездочкой (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="f0526-167">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>
     - <span data-ttu-id="f0526-168">**Имя отправки**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f0526-168">**Submission name**<sup>\*</sup></span></span>
     - <span data-ttu-id="f0526-169">**Отправитель**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f0526-169">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="f0526-170">**Дата отправки**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f0526-170">**Date submitted**<sup>\*</sup></span></span>
     - <span data-ttu-id="f0526-171">**Тип отправки**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f0526-171">**Submission type**<sup>\*</sup></span></span>
     - <span data-ttu-id="f0526-172">**Причина отправки**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f0526-172">**Reason for submitting**<sup>\*</sup></span></span>
     - <span data-ttu-id="f0526-173">**Состояние Rescan**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f0526-173">**Rescan status**<sup>\*</sup></span></span>
     - <span data-ttu-id="f0526-174">**Результат Rescan**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f0526-174">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="f0526-175">**Вердикт фильтра**</span><span class="sxs-lookup"><span data-stu-id="f0526-175">**Filter verdict**</span></span>
     - <span data-ttu-id="f0526-176">**Причина доставки/блокировки**</span><span class="sxs-lookup"><span data-stu-id="f0526-176">**Delivery/Block reason**</span></span>
     - <span data-ttu-id="f0526-177">**ID отправки**</span><span class="sxs-lookup"><span data-stu-id="f0526-177">**Submission ID**</span></span>
     - <span data-ttu-id="f0526-178">**Сетевой ID/Object ID**</span><span class="sxs-lookup"><span data-stu-id="f0526-178">**Network Message ID/Object ID**</span></span>
     - <span data-ttu-id="f0526-179">**Direction**</span><span class="sxs-lookup"><span data-stu-id="f0526-179">**Direction**</span></span>
     - <span data-ttu-id="f0526-180">**IP-адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="f0526-180">**Sender IP**</span></span>
     - <span data-ttu-id="f0526-181">**Объемный уровень совместимый (BCL)**</span><span class="sxs-lookup"><span data-stu-id="f0526-181">**Bulk compliant level (BCL)**</span></span>
     - <span data-ttu-id="f0526-182">**Destination**</span><span class="sxs-lookup"><span data-stu-id="f0526-182">**Destination**</span></span>
     - <span data-ttu-id="f0526-183">**Действие политики**</span><span class="sxs-lookup"><span data-stu-id="f0526-183">**Policy action**</span></span>
     - <span data-ttu-id="f0526-184">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="f0526-184">**Submitted by**</span></span>

     <span data-ttu-id="f0526-185">По завершению нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="f0526-185">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="f0526-186">Чтобы отфильтровать записи, щелкните **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="f0526-186">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="f0526-187">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="f0526-187">The available filters are:</span></span>
     - <span data-ttu-id="f0526-188">**Дата отправки:** **дата начала и** дата **окончания**.</span><span class="sxs-lookup"><span data-stu-id="f0526-188">**Date submitted**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="f0526-189">**Тип отправки:** **электронная** **почта, URL-адрес** или **файл.**</span><span class="sxs-lookup"><span data-stu-id="f0526-189">**Submission type**: **Email**, **URL**, or **File**.</span></span>
     - <span data-ttu-id="f0526-190">**ID отправки:** значение GUID, назначенное каждой отправке.</span><span class="sxs-lookup"><span data-stu-id="f0526-190">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
     - <span data-ttu-id="f0526-191">**ID сетевого сообщения**</span><span class="sxs-lookup"><span data-stu-id="f0526-191">**Network Message ID**</span></span>
     - <span data-ttu-id="f0526-192">**Sender**</span><span class="sxs-lookup"><span data-stu-id="f0526-192">**Sender**</span></span>

     <span data-ttu-id="f0526-193">По завершению нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="f0526-193">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="f0526-194">![Новые параметры фильтра для отправки администратора](../../media/admin-submission-filters.png)</span><span class="sxs-lookup"><span data-stu-id="f0526-194">![New Filter options for admin submissions](../../media/admin-submission-filters.png)</span></span>

   - <span data-ttu-id="f0526-195">Чтобы сгруппить записи, щелкните **Группу** и выберите одно из следующих значений из списка drop down:</span><span class="sxs-lookup"><span data-stu-id="f0526-195">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="f0526-196">**Нет**</span><span class="sxs-lookup"><span data-stu-id="f0526-196">**None**</span></span>
     - <span data-ttu-id="f0526-197">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f0526-197">**Type**</span></span>
     - <span data-ttu-id="f0526-198">**Причина**</span><span class="sxs-lookup"><span data-stu-id="f0526-198">**Reason**</span></span>
     - <span data-ttu-id="f0526-199">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="f0526-199">**Status**</span></span>
     - <span data-ttu-id="f0526-200">**Результат Rescan**</span><span class="sxs-lookup"><span data-stu-id="f0526-200">**Rescan result**</span></span>

   - <span data-ttu-id="f0526-201">Чтобы экспортировать записи, щелкните **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="f0526-201">To export the entries, click **Export**.</span></span> <span data-ttu-id="f0526-202">В диалоговом окте, который отображается, сохраните .csv файл.</span><span class="sxs-lookup"><span data-stu-id="f0526-202">In the dialog that appears, save the .csv file.</span></span>

### <a name="admin-submission-rescan-details"></a><span data-ttu-id="f0526-203">Сведения о повторном представлении администратора</span><span class="sxs-lookup"><span data-stu-id="f0526-203">Admin submission rescan details</span></span>

<span data-ttu-id="f0526-204">Сообщения, представленные в представлениях администратора, рассматриваются и результаты, показанные в вылете подробных сообщений:</span><span class="sxs-lookup"><span data-stu-id="f0526-204">Messages that are submitted in admin submissions are reviewed and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="f0526-205">Возникновение сбоя при проверке подлинности электронной почты отправителя в момент доставки.</span><span class="sxs-lookup"><span data-stu-id="f0526-205">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="f0526-206">Сведения о любых совпадениях политик, которые могут повлиять на решение по безопасности касательно сообщения или переопределить его.</span><span class="sxs-lookup"><span data-stu-id="f0526-206">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="f0526-207">Текущие результаты отключения, чтобы определить, были ли URL-адреса или файлы, содержащиеся в сообщении, вредоносными или нет.</span><span class="sxs-lookup"><span data-stu-id="f0526-207">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="f0526-208">Отзывы от грейдеров.</span><span class="sxs-lookup"><span data-stu-id="f0526-208">Feedback from graders.</span></span>

<span data-ttu-id="f0526-209">Если было обнаружено переопределение, повторное сканирование должно завершиться через несколько минут.</span><span class="sxs-lookup"><span data-stu-id="f0526-209">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="f0526-210">Если в проверке подлинности или доставке электронной почты не возникло проблем с переопределением, то отзывы от грейдеров могут занять до одного дня.</span><span class="sxs-lookup"><span data-stu-id="f0526-210">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="f0526-211">Просмотр пользовательских представлений в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f0526-211">View user submissions to Microsoft</span></span>

<span data-ttu-id="f0526-212">Если вы развернули надстройку [Report Message](enable-the-report-message-add-in.md), надстройку [Report Phishing](enable-the-report-phish-add-in.md)или пользователи используют встроенную отчетность в [Outlook в Интернете,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)вы можете увидеть, какие отчеты пользователи сообщают на вкладке Сообщение пользователя. </span><span class="sxs-lookup"><span data-stu-id="f0526-212">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User reported message** tab.</span></span>

1. <span data-ttu-id="f0526-213">На портале Microsoft 365 Defender перейдите на электронную **почту &** \> **отправки совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="f0526-213">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="f0526-214">На странице **Отправки** выберите вкладку **Сообщения** пользователя.</span><span class="sxs-lookup"><span data-stu-id="f0526-214">On the **Submissions** page, select the **User reported messages** tab.</span></span>

   - <span data-ttu-id="f0526-215">Вы можете сортировать записи, нажав на доступный столбец.</span><span class="sxs-lookup"><span data-stu-id="f0526-215">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="f0526-216">Нажмите **кнопку Настройка столбцов,** чтобы показать максимум семь столбцов.</span><span class="sxs-lookup"><span data-stu-id="f0526-216">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="f0526-217">Значения по умолчанию помечены звездочкой (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="f0526-217">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

     - <span data-ttu-id="f0526-218">**Тема электронной почты**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f0526-218">**Email subject**<sup>\*</sup></span></span>
     - <span data-ttu-id="f0526-219">**Reported by**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f0526-219">**Reported by**<sup>\*</sup></span></span>
     - <span data-ttu-id="f0526-220">**Дата сообщается**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f0526-220">**Date reported**<sup>\*</sup></span></span>
     - <span data-ttu-id="f0526-221">**Отправитель**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f0526-221">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="f0526-222">**Сообщаемая причина**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f0526-222">**Reported reason**<sup>\*</sup></span></span>
     - <span data-ttu-id="f0526-223">**Результат Rescan**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f0526-223">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="f0526-224">**ID сообщения**</span><span class="sxs-lookup"><span data-stu-id="f0526-224">**Message reported ID**</span></span>
     - <span data-ttu-id="f0526-225">**ID сетевого сообщения**</span><span class="sxs-lookup"><span data-stu-id="f0526-225">**Network Message ID**</span></span>
     - <span data-ttu-id="f0526-226">**IP-адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="f0526-226">**Sender IP**</span></span>
     - <span data-ttu-id="f0526-227">**Имитация фишинга**</span><span class="sxs-lookup"><span data-stu-id="f0526-227">**Phish simulation**</span></span>

     <span data-ttu-id="f0526-228">По завершению нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="f0526-228">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="f0526-229">Чтобы отфильтровать записи, щелкните **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="f0526-229">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="f0526-230">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="f0526-230">The available filters are:</span></span>
     - <span data-ttu-id="f0526-231">**Дата сообщается:** **дата начала и** **даты окончания**.</span><span class="sxs-lookup"><span data-stu-id="f0526-231">**Date reported**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="f0526-232">**Reported by (Сообщил)**</span><span class="sxs-lookup"><span data-stu-id="f0526-232">**Reported by**</span></span>
     - <span data-ttu-id="f0526-233">**Тема письма**</span><span class="sxs-lookup"><span data-stu-id="f0526-233">**Email subject**</span></span>
     - <span data-ttu-id="f0526-234">**ID сообщения**</span><span class="sxs-lookup"><span data-stu-id="f0526-234">**Message reported ID**</span></span>
     - <span data-ttu-id="f0526-235">**ID сетевого сообщения**</span><span class="sxs-lookup"><span data-stu-id="f0526-235">**Network Message ID**</span></span>
     - <span data-ttu-id="f0526-236">**Sender**</span><span class="sxs-lookup"><span data-stu-id="f0526-236">**Sender**</span></span>
     - <span data-ttu-id="f0526-237">**Сообщаемая причина:** **не нежелательной,** **фишинг** или **спам**.</span><span class="sxs-lookup"><span data-stu-id="f0526-237">**Reported reason**: **Not junk**, **Phish**, or **Spam**.</span></span>
     - <span data-ttu-id="f0526-238">**Фишинговое моделирование:** **да** или **нет**</span><span class="sxs-lookup"><span data-stu-id="f0526-238">**Phish simulation**: **Yes** or **No**</span></span>

     <span data-ttu-id="f0526-239">По завершению нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="f0526-239">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="f0526-240">![Новые параметры фильтра для пользовательских представлений](../../media/admin-submission-reported-messages.png)</span><span class="sxs-lookup"><span data-stu-id="f0526-240">![New Filter options for user submissions](../../media/admin-submission-reported-messages.png)</span></span>

   - <span data-ttu-id="f0526-241">Чтобы сгруппить записи, щелкните **Группу** и выберите одно из следующих значений из списка drop down:</span><span class="sxs-lookup"><span data-stu-id="f0526-241">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="f0526-242">**Нет**</span><span class="sxs-lookup"><span data-stu-id="f0526-242">**None**</span></span>
     - <span data-ttu-id="f0526-243">**Причина**</span><span class="sxs-lookup"><span data-stu-id="f0526-243">**Reason**</span></span>
     - <span data-ttu-id="f0526-244">**Sender**</span><span class="sxs-lookup"><span data-stu-id="f0526-244">**Sender**</span></span>
     - <span data-ttu-id="f0526-245">**Reported by (Сообщил)**</span><span class="sxs-lookup"><span data-stu-id="f0526-245">**Reported by**</span></span>
     - <span data-ttu-id="f0526-246">**Результат Rescan**</span><span class="sxs-lookup"><span data-stu-id="f0526-246">**Rescan result**</span></span>
     - <span data-ttu-id="f0526-247">**Имитация фишинга**</span><span class="sxs-lookup"><span data-stu-id="f0526-247">**Phish simulation**</span></span>

   - <span data-ttu-id="f0526-248">Чтобы экспортировать записи, щелкните **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="f0526-248">To export the entries, click **Export**.</span></span> <span data-ttu-id="f0526-249">В диалоговом окте, который отображается, сохраните .csv файл.</span><span class="sxs-lookup"><span data-stu-id="f0526-249">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="f0526-250">Если организации настроены на отправку сообщений пользователей только в настраиваемый почтовый ящик, сообщения не  будут отправляться на rescan, а результаты сообщений пользователей всегда будут пустыми.</span><span class="sxs-lookup"><span data-stu-id="f0526-250">If organizations are configured to send user reported messages to the custom mailbox only, reported messages will not be sent for rescan and the results in **User reported messages** will always be empty.</span></span>

### <a name="undo-user-submissions"></a><span data-ttu-id="f0526-251">Отмена отправки пользователей</span><span class="sxs-lookup"><span data-stu-id="f0526-251">Undo user submissions</span></span>

<span data-ttu-id="f0526-252">После отправки подозрительной электронной почты в настраиваемый почтовый ящик у пользователя и администратора нет возможности отменить отправку.</span><span class="sxs-lookup"><span data-stu-id="f0526-252">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="f0526-253">Если пользователь хочет восстановить электронную почту, она будет доступна для восстановления в папках "Удаленные элементы" или "Нежелательной почты".</span><span class="sxs-lookup"><span data-stu-id="f0526-253">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="f0526-254">Отправка сообщений в Корпорацию Майкрософт из пользовательского почтового ящика</span><span class="sxs-lookup"><span data-stu-id="f0526-254">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="f0526-255">Если настраивается настраиваемый почтовый ящик для перехвата сообщений, сообщаемых пользователями, без отправки сообщений в Корпорацию Майкрософт, вы можете найти и отправить определенные сообщения в Корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="f0526-255">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="f0526-256">Это эффективно перемещает отправку пользователя в отправку администратора.</span><span class="sxs-lookup"><span data-stu-id="f0526-256">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="f0526-257">На **вкладке Сообщения** пользователя выберите сообщение в списке, щелкните Отправить в **Microsoft** для анализа, а затем выберите одно из следующих значений из списка drop down:</span><span class="sxs-lookup"><span data-stu-id="f0526-257">On the **User reported messages** tab, select a message in the list, click **Submit to Microsoft for analysis**, and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="f0526-258">**Отчет о чистоте**</span><span class="sxs-lookup"><span data-stu-id="f0526-258">**Report clean**</span></span>
- <span data-ttu-id="f0526-259">**Сообщение о фишинге**</span><span class="sxs-lookup"><span data-stu-id="f0526-259">**Report phishing**</span></span>
- <span data-ttu-id="f0526-260">**Отчет о вредоносных программах**</span><span class="sxs-lookup"><span data-stu-id="f0526-260">**Report malware**</span></span>
- <span data-ttu-id="f0526-261">**Сообщение о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="f0526-261">**Report spam**</span></span>
- <span data-ttu-id="f0526-262">**Триггерное исследование**</span><span class="sxs-lookup"><span data-stu-id="f0526-262">**Trigger investigation**</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f0526-263">![Новые параметры на кнопке Действие](../../media/admin-submission-main-action-button.png)</span><span class="sxs-lookup"><span data-stu-id="f0526-263">![New Options on the Action button](../../media/admin-submission-main-action-button.png)</span></span>
