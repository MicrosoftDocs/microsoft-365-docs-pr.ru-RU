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
ms.openlocfilehash: 2d18dd7f5dc702f08a722652394aeb0102f100ef
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409060"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="492ce-103">Использование функции отправки администратором для отправки подозрительного спама, фишинговых сообщений, URL-адресов и файлов в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="492ce-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="492ce-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="492ce-104">**Applies to**</span></span>
- [<span data-ttu-id="492ce-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="492ce-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="492ce-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="492ce-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="492ce-107">В Microsoft 365 организациях с Exchange Online почтовыми ящиками администраторы могут использовать портал Отправки на портале Microsoft 365 Defender для отправки сообщений электронной почты, URL-адресов и вложений в Корпорацию Майкрософт для сканирования.</span><span class="sxs-lookup"><span data-stu-id="492ce-107">In Microsoft 365 organizations with Exchange Online mailboxes, admins can use the Submissions portal in the Microsoft 365 Defender portal to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="492ce-108">При отправке сообщения электронной почты вы получите:</span><span class="sxs-lookup"><span data-stu-id="492ce-108">When you submit an email message, you will get:</span></span>

- <span data-ttu-id="492ce-109">**Проверка подлинности электронной** почты. Сведения о том, прошла ли проверка подлинности электронной почты при ее доставке или сбой.</span><span class="sxs-lookup"><span data-stu-id="492ce-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
- <span data-ttu-id="492ce-110">**Хиты** политики. Сведения о любых политиках, которые могли разрешить или заблокировать входящие сообщения электронной почты в клиента, переопределив наши решения фильтра службы.</span><span class="sxs-lookup"><span data-stu-id="492ce-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
- <span data-ttu-id="492ce-111">**Репутация и детонация полезной** нагрузки: проверка url-адресов и вложений в сообщении.</span><span class="sxs-lookup"><span data-stu-id="492ce-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
- <span data-ttu-id="492ce-112">**Анализ грейдера.** Проверка, сделанная грейдерами,чтобы подтвердить, являются ли сообщения вредоносными.</span><span class="sxs-lookup"><span data-stu-id="492ce-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="492ce-113">Анализ репутации/детонации и грейдера полезной нагрузки не проводится во всех клиентах.</span><span class="sxs-lookup"><span data-stu-id="492ce-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="492ce-114">Сведения не могут выходить за пределы организации, если данные не должны покидать границу клиента в целях соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="492ce-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="492ce-115">Другие способы отправки сообщений электронной почты, URL-адресов и вложений в Корпорацию Майкрософт см. в этой ссылке. [](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="492ce-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="492ce-116">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="492ce-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="492ce-117">Чтобы открыть портал Microsoft 365 Defender, перейдите на сайт <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="492ce-117">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="492ce-118">Чтобы перейти непосредственно на **страницу Отправки,** используйте <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="492ce-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="492ce-119">Чтобы отправить сообщения и файлы в Корпорацию Майкрософт, необходимо быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="492ce-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="492ce-120">**Управление организацией** или **чтение** безопасности [на Microsoft 365 Defender портале](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="492ce-120">**Organization Management** or **Security Reader** in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  
    <span data-ttu-id="492ce-121">Обратите внимание, что членство в [](#view-user-submissions-to-microsoft) этой группе ролей необходимо для просмотра пользовательских представлений в настраиваемом почтовом ящике, как описано выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="492ce-121">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-microsoft) as described later in this article.</span></span>

- <span data-ttu-id="492ce-122">Дополнительные сведения о том, как пользователи могут отправлять сообщения и файлы в Корпорацию Майкрософт, см. в материалах [Report messages and files to Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="492ce-122">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="492ce-123">Сообщение о подозрительном контенте в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="492ce-123">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="492ce-124">На портале Microsoft 365 Defender перейдите на электронную **почту &** \> **отправки совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="492ce-124">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="492ce-125">На странице **Отправки** убедитесь, что выбрана вкладка Отправка для анализа, а затем щелкните значок  ![ Ad Submit to Microsoft для ](../../media/m365-cc-sc-create-icon.png) **анализа.**</span><span class="sxs-lookup"><span data-stu-id="492ce-125">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected, and then click ![Ad icon](../../media/m365-cc-sc-create-icon.png) **Submit to Microsoft for analysis**.</span></span>

3. <span data-ttu-id="492ce-126">Используйте **отправку в Корпорацию Майкрософт** для проверки вылетов, которые, как представляется, представляют сообщение, URL-адрес или вложение электронной почты, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="492ce-126">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

   > [!NOTE]
   > <span data-ttu-id="492ce-127">Отправки файлов и URL-адресов недоступны в облаках, которые не позволяют данным выходить из среды.</span><span class="sxs-lookup"><span data-stu-id="492ce-127">File and URL submissions are not available in the clouds that do not allow for data to leave the environment.</span></span> <span data-ttu-id="492ce-128">Возможность выбора файла или URL-адреса будет оттеняться.</span><span class="sxs-lookup"><span data-stu-id="492ce-128">The ability to select File or URL will be greyed out.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="492ce-129">Отправка сомнительного сообщения электронной почты в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="492ce-129">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="492ce-130">В поле **Выберите тип отправки** убедитесь, что **электронная** почта выбрана в списке drop down.</span><span class="sxs-lookup"><span data-stu-id="492ce-130">In the **Select the submission type** box, verify that **Email** is selected in the drop down list.</span></span>

2. <span data-ttu-id="492ce-131">В разделе **Добавление сетевого сообщения или** отправка раздела файл электронной почты используйте один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="492ce-131">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>
   - <span data-ttu-id="492ce-132">Добавьте сетевой **ID** сообщения электронной почты. Это значение GUID, доступное в загонщике **X-MS-Exchange-Organization-Network-Message-Id** в сообщении или в **загоне X-MS-Office365-Filtering-Correlation-Id** в карантинных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="492ce-132">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>
   - <span data-ttu-id="492ce-133">**Upload файл электронной почты (.msg или .eml)**: Щелкните **Просмотр файлов**.</span><span class="sxs-lookup"><span data-stu-id="492ce-133">**Upload the email file (.msg or .eml)**: Click **Browse files**.</span></span> <span data-ttu-id="492ce-134">В открываемом диалоговом окте найти и выбрать файл .eml или .msg, а затем нажмите **кнопку Открыть**.</span><span class="sxs-lookup"><span data-stu-id="492ce-134">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="492ce-135">Возможность отправки сообщений в течение 30 дней была временно приостановлена для defender для Office 365 клиентов.</span><span class="sxs-lookup"><span data-stu-id="492ce-135">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="492ce-136">Администраторы смогут возвращаться только через 7 дней.</span><span class="sxs-lookup"><span data-stu-id="492ce-136">Admins will only be able to go back 7 days.</span></span>

3. <span data-ttu-id="492ce-137">В поле Выбор получателя с **проблемным полем** укажите получателя, против которого необходимо выполнить проверку политики.</span><span class="sxs-lookup"><span data-stu-id="492ce-137">In the **Choose a recipient who had an issue** box, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="492ce-138">Проверка политики определяет, не обходится ли проверка электронной почты из-за политики пользователя или организации.</span><span class="sxs-lookup"><span data-stu-id="492ce-138">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

4. <span data-ttu-id="492ce-139">В разделе **Выбор причины отправки в раздел Microsoft** выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="492ce-139">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="492ce-140">**Не должно было быть заблокировано (ложное срабатыва-**</span><span class="sxs-lookup"><span data-stu-id="492ce-140">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="492ce-141">**Должно было быть** заблокировано: В сообщении электронной почты следует классифицируются как раздел, который отображается, выберите одно из следующих значений (если вы не уверены, используйте свое наилучшее решение): </span><span class="sxs-lookup"><span data-stu-id="492ce-141">**Should have been blocked**: In the **The email should have been categorized as** section that appears, select one of the following values (if you're not sure, use your best judgement):</span></span>
     - <span data-ttu-id="492ce-142">**Фишинг**</span><span class="sxs-lookup"><span data-stu-id="492ce-142">**Phish**</span></span>
     - <span data-ttu-id="492ce-143">**Спам**</span><span class="sxs-lookup"><span data-stu-id="492ce-143">**Spam**</span></span>
     - <span data-ttu-id="492ce-144">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="492ce-144">**Malware**</span></span>

5. <span data-ttu-id="492ce-145">По завершению нажмите кнопку **Отправить.**</span><span class="sxs-lookup"><span data-stu-id="492ce-145">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="492ce-146">![Новый пример отправки URL-адресов](../../media/submission-flyout-email.png)</span><span class="sxs-lookup"><span data-stu-id="492ce-146">![New URL submission example](../../media/submission-flyout-email.png)</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="492ce-147">Отправка подозрительного URL-адреса в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="492ce-147">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="492ce-148">В поле **Выберите тип отправки** выберите **URL-адрес** из списка drop down.</span><span class="sxs-lookup"><span data-stu-id="492ce-148">In the **Select the submission type** box, select **URL** from the drop down list.</span></span>

2. <span data-ttu-id="492ce-149">В поле **URL-адреса,** которое отображается, введите полный URL-адрес (например, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="492ce-149">In the **URL** box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

3. <span data-ttu-id="492ce-150">В разделе **Выбор причины отправки в раздел Microsoft** выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="492ce-150">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="492ce-151">**Не должно было быть заблокировано (ложное срабатыва-**</span><span class="sxs-lookup"><span data-stu-id="492ce-151">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="492ce-152">**Должно было быть заблокировано:** В этом **URL-адресе** следует классифицируются как раздел, который отображается, выберите **фишинг или** вредоносные **программы**.</span><span class="sxs-lookup"><span data-stu-id="492ce-152">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, select **Phish** or **Malware**.</span></span>

4. <span data-ttu-id="492ce-153">По завершению нажмите кнопку **Отправить.**</span><span class="sxs-lookup"><span data-stu-id="492ce-153">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="492ce-154">![Новый пример отправки электронной почты](../../media/submission-url-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="492ce-154">![New Email submission example](../../media/submission-url-flyout.png)</span></span>

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="492ce-155">Отправка предполагаемого вложения электронной почты в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="492ce-155">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="492ce-156">В поле **Выберите тип отправки** выберите **Файл из** списка выпаданий.</span><span class="sxs-lookup"><span data-stu-id="492ce-156">In the **Select the submission type** box, select **File** from the drop down list.</span></span>

2. <span data-ttu-id="492ce-157">В разделе **Файл,** который появится, щелкните **Просмотр файлов**.</span><span class="sxs-lookup"><span data-stu-id="492ce-157">In the **File** section that appears, click **Browse files**.</span></span> <span data-ttu-id="492ce-158">В открываемом диалоговом окте найти и выбрать файл, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="492ce-158">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="492ce-159">В разделе **Выбор причины отправки в раздел Microsoft** выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="492ce-159">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="492ce-160">**Не должно было быть заблокировано (ложное срабатыва-**</span><span class="sxs-lookup"><span data-stu-id="492ce-160">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="492ce-161">**Должно быть заблокировано.** В этом **URL-адресе** должен быть классифицирован **раздел,** который отображается, вредоносные программы является единственным выбором, и автоматически выбирается.</span><span class="sxs-lookup"><span data-stu-id="492ce-161">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="492ce-162">По завершению нажмите кнопку **Отправить.**</span><span class="sxs-lookup"><span data-stu-id="492ce-162">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="492ce-163">![Пример отправки вложения](../../media/submission-file-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="492ce-163">![New Attachment submission example](../../media/submission-file-flyout.png)</span></span>

## <a name="view-admin-submissions-to-microsoft"></a><span data-ttu-id="492ce-164">Просмотр представлений администратора в Корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="492ce-164">View admin submissions to Microsoft</span></span>

1. <span data-ttu-id="492ce-165">На портале Microsoft 365 Defender перейдите на электронную **почту &** \> **отправки совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="492ce-165">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="492ce-166">На странице **Отправки** убедитесь, что выбрана вкладка **Отправка** для анализа.</span><span class="sxs-lookup"><span data-stu-id="492ce-166">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected.</span></span>

   - <span data-ttu-id="492ce-167">Вы можете сортировать записи, нажав на доступный столбец.</span><span class="sxs-lookup"><span data-stu-id="492ce-167">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="492ce-168">Нажмите **кнопку Настройка столбцов,** чтобы показать максимум семь столбцов.</span><span class="sxs-lookup"><span data-stu-id="492ce-168">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="492ce-169">Значения по умолчанию помечены звездочкой (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="492ce-169">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>
     - <span data-ttu-id="492ce-170">**Имя отправки**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="492ce-170">**Submission name**<sup>\*</sup></span></span>
     - <span data-ttu-id="492ce-171">**Отправитель**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="492ce-171">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="492ce-172">**Дата отправки**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="492ce-172">**Date submitted**<sup>\*</sup></span></span>
     - <span data-ttu-id="492ce-173">**Тип отправки**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="492ce-173">**Submission type**<sup>\*</sup></span></span>
     - <span data-ttu-id="492ce-174">**Причина отправки**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="492ce-174">**Reason for submitting**<sup>\*</sup></span></span>
     - <span data-ttu-id="492ce-175">**Состояние Rescan**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="492ce-175">**Rescan status**<sup>\*</sup></span></span>
     - <span data-ttu-id="492ce-176">**Результат Rescan**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="492ce-176">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="492ce-177">**Вердикт фильтра**</span><span class="sxs-lookup"><span data-stu-id="492ce-177">**Filter verdict**</span></span>
     - <span data-ttu-id="492ce-178">**Причина доставки/блокировки**</span><span class="sxs-lookup"><span data-stu-id="492ce-178">**Delivery/Block reason**</span></span>
     - <span data-ttu-id="492ce-179">**ID отправки**</span><span class="sxs-lookup"><span data-stu-id="492ce-179">**Submission ID**</span></span>
     - <span data-ttu-id="492ce-180">**Сетевой ID/Object ID**</span><span class="sxs-lookup"><span data-stu-id="492ce-180">**Network Message ID/Object ID**</span></span>
     - <span data-ttu-id="492ce-181">**Direction**</span><span class="sxs-lookup"><span data-stu-id="492ce-181">**Direction**</span></span>
     - <span data-ttu-id="492ce-182">**IP-адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="492ce-182">**Sender IP**</span></span>
     - <span data-ttu-id="492ce-183">**Объемный уровень совместимый (BCL)**</span><span class="sxs-lookup"><span data-stu-id="492ce-183">**Bulk compliant level (BCL)**</span></span>
     - <span data-ttu-id="492ce-184">**Destination**</span><span class="sxs-lookup"><span data-stu-id="492ce-184">**Destination**</span></span>
     - <span data-ttu-id="492ce-185">**Действие политики**</span><span class="sxs-lookup"><span data-stu-id="492ce-185">**Policy action**</span></span>
     - <span data-ttu-id="492ce-186">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="492ce-186">**Submitted by**</span></span>

     <span data-ttu-id="492ce-187">По завершению нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="492ce-187">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="492ce-188">Чтобы отфильтровать записи, щелкните **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="492ce-188">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="492ce-189">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="492ce-189">The available filters are:</span></span>
     - <span data-ttu-id="492ce-190">**Дата отправки:** **дата начала и** дата **окончания**.</span><span class="sxs-lookup"><span data-stu-id="492ce-190">**Date submitted**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="492ce-191">**Тип отправки:** **электронная** **почта, URL-адрес** или **файл.**</span><span class="sxs-lookup"><span data-stu-id="492ce-191">**Submission type**: **Email**, **URL**, or **File**.</span></span>
     - <span data-ttu-id="492ce-192">**ID отправки:** значение GUID, назначенное каждой отправке.</span><span class="sxs-lookup"><span data-stu-id="492ce-192">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
     - <span data-ttu-id="492ce-193">**ID сетевого сообщения**</span><span class="sxs-lookup"><span data-stu-id="492ce-193">**Network Message ID**</span></span>
     - <span data-ttu-id="492ce-194">**Sender**</span><span class="sxs-lookup"><span data-stu-id="492ce-194">**Sender**</span></span>

     <span data-ttu-id="492ce-195">По завершению нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="492ce-195">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="492ce-196">![Новые параметры фильтра для отправки администратора](../../media/admin-submission-filters.png)</span><span class="sxs-lookup"><span data-stu-id="492ce-196">![New Filter options for admin submissions](../../media/admin-submission-filters.png)</span></span>

   - <span data-ttu-id="492ce-197">Чтобы сгруппить записи, щелкните **Группу** и выберите одно из следующих значений из списка drop down:</span><span class="sxs-lookup"><span data-stu-id="492ce-197">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="492ce-198">**Нет**</span><span class="sxs-lookup"><span data-stu-id="492ce-198">**None**</span></span>
     - <span data-ttu-id="492ce-199">**Тип**</span><span class="sxs-lookup"><span data-stu-id="492ce-199">**Type**</span></span>
     - <span data-ttu-id="492ce-200">**Причина**</span><span class="sxs-lookup"><span data-stu-id="492ce-200">**Reason**</span></span>
     - <span data-ttu-id="492ce-201">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="492ce-201">**Status**</span></span>
     - <span data-ttu-id="492ce-202">**Результат Rescan**</span><span class="sxs-lookup"><span data-stu-id="492ce-202">**Rescan result**</span></span>

   - <span data-ttu-id="492ce-203">Чтобы экспортировать записи, щелкните **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="492ce-203">To export the entries, click **Export**.</span></span> <span data-ttu-id="492ce-204">В диалоговом окте, который отображается, сохраните .csv файл.</span><span class="sxs-lookup"><span data-stu-id="492ce-204">In the dialog that appears, save the .csv file.</span></span>

### <a name="admin-submission-rescan-details"></a><span data-ttu-id="492ce-205">Сведения о повторном представлении администратора</span><span class="sxs-lookup"><span data-stu-id="492ce-205">Admin submission rescan details</span></span>

<span data-ttu-id="492ce-206">Сообщения, представленные в представлениях администратора, рассматриваются и результаты, показанные в вылете подробных сообщений:</span><span class="sxs-lookup"><span data-stu-id="492ce-206">Messages that are submitted in admin submissions are reviewed and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="492ce-207">Возникновение сбоя при проверке подлинности электронной почты отправителя в момент доставки.</span><span class="sxs-lookup"><span data-stu-id="492ce-207">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="492ce-208">Сведения о любых совпадениях политик, которые могут повлиять на решение по безопасности касательно сообщения или переопределить его.</span><span class="sxs-lookup"><span data-stu-id="492ce-208">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="492ce-209">Текущие результаты отключения, чтобы определить, были ли URL-адреса или файлы, содержащиеся в сообщении, вредоносными или нет.</span><span class="sxs-lookup"><span data-stu-id="492ce-209">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="492ce-210">Отзывы от грейдеров.</span><span class="sxs-lookup"><span data-stu-id="492ce-210">Feedback from graders.</span></span>

<span data-ttu-id="492ce-211">Если было обнаружено переопределение, повторное сканирование должно завершиться через несколько минут.</span><span class="sxs-lookup"><span data-stu-id="492ce-211">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="492ce-212">Если в проверке подлинности или доставке электронной почты не возникло проблем с переопределением, то отзывы от грейдеров могут занять до одного дня.</span><span class="sxs-lookup"><span data-stu-id="492ce-212">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="492ce-213">Просмотр пользовательских представлений в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="492ce-213">View user submissions to Microsoft</span></span>

<span data-ttu-id="492ce-214">Если вы развернули надстройку [Report Message](enable-the-report-message-add-in.md), надстройку [Report Phishing](enable-the-report-phish-add-in.md)или пользователи используют встроенную отчетность в [Outlook в Интернете,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)вы можете увидеть, какие отчеты пользователи сообщают на вкладке Сообщение пользователя. </span><span class="sxs-lookup"><span data-stu-id="492ce-214">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User reported message** tab.</span></span>

1. <span data-ttu-id="492ce-215">На портале Microsoft 365 Defender перейдите на электронную **почту &** \> **отправки совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="492ce-215">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="492ce-216">На странице **Отправки** выберите вкладку **Сообщения** пользователя.</span><span class="sxs-lookup"><span data-stu-id="492ce-216">On the **Submissions** page, select the **User reported messages** tab.</span></span>

   - <span data-ttu-id="492ce-217">Вы можете сортировать записи, нажав на доступный столбец.</span><span class="sxs-lookup"><span data-stu-id="492ce-217">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="492ce-218">Нажмите **кнопку Настройка столбцов,** чтобы показать максимум семь столбцов.</span><span class="sxs-lookup"><span data-stu-id="492ce-218">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="492ce-219">Значения по умолчанию помечены звездочкой (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="492ce-219">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

     - <span data-ttu-id="492ce-220">**Тема электронной почты**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="492ce-220">**Email subject**<sup>\*</sup></span></span>
     - <span data-ttu-id="492ce-221">**Reported by**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="492ce-221">**Reported by**<sup>\*</sup></span></span>
     - <span data-ttu-id="492ce-222">**Дата сообщается**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="492ce-222">**Date reported**<sup>\*</sup></span></span>
     - <span data-ttu-id="492ce-223">**Отправитель**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="492ce-223">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="492ce-224">**Сообщаемая причина**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="492ce-224">**Reported reason**<sup>\*</sup></span></span>
     - <span data-ttu-id="492ce-225">**Результат Rescan**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="492ce-225">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="492ce-226">**ID сообщения**</span><span class="sxs-lookup"><span data-stu-id="492ce-226">**Message reported ID**</span></span>
     - <span data-ttu-id="492ce-227">**ID сетевого сообщения**</span><span class="sxs-lookup"><span data-stu-id="492ce-227">**Network Message ID**</span></span>
     - <span data-ttu-id="492ce-228">**IP-адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="492ce-228">**Sender IP**</span></span>
     - <span data-ttu-id="492ce-229">**Имитация фишинга**</span><span class="sxs-lookup"><span data-stu-id="492ce-229">**Phish simulation**</span></span>

     <span data-ttu-id="492ce-230">По завершению нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="492ce-230">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="492ce-231">Чтобы отфильтровать записи, щелкните **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="492ce-231">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="492ce-232">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="492ce-232">The available filters are:</span></span>
     - <span data-ttu-id="492ce-233">**Дата сообщается:** **дата начала и** **даты окончания**.</span><span class="sxs-lookup"><span data-stu-id="492ce-233">**Date reported**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="492ce-234">**Reported by (Сообщил)**</span><span class="sxs-lookup"><span data-stu-id="492ce-234">**Reported by**</span></span>
     - <span data-ttu-id="492ce-235">**Тема письма**</span><span class="sxs-lookup"><span data-stu-id="492ce-235">**Email subject**</span></span>
     - <span data-ttu-id="492ce-236">**ID сообщения**</span><span class="sxs-lookup"><span data-stu-id="492ce-236">**Message reported ID**</span></span>
     - <span data-ttu-id="492ce-237">**ID сетевого сообщения**</span><span class="sxs-lookup"><span data-stu-id="492ce-237">**Network Message ID**</span></span>
     - <span data-ttu-id="492ce-238">**Sender**</span><span class="sxs-lookup"><span data-stu-id="492ce-238">**Sender**</span></span>
     - <span data-ttu-id="492ce-239">**Сообщаемая причина:** **не нежелательной,** **фишинг** или **спам**.</span><span class="sxs-lookup"><span data-stu-id="492ce-239">**Reported reason**: **Not junk**, **Phish**, or **Spam**.</span></span>
     - <span data-ttu-id="492ce-240">**Фишинговое моделирование:** **да** или **нет**</span><span class="sxs-lookup"><span data-stu-id="492ce-240">**Phish simulation**: **Yes** or **No**</span></span>

     <span data-ttu-id="492ce-241">По завершению нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="492ce-241">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="492ce-242">![Новые параметры фильтра для пользовательских представлений](../../media/admin-submission-reported-messages.png)</span><span class="sxs-lookup"><span data-stu-id="492ce-242">![New Filter options for user submissions](../../media/admin-submission-reported-messages.png)</span></span>

   - <span data-ttu-id="492ce-243">Чтобы сгруппить записи, щелкните **Группу** и выберите одно из следующих значений из списка drop down:</span><span class="sxs-lookup"><span data-stu-id="492ce-243">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="492ce-244">**Нет**</span><span class="sxs-lookup"><span data-stu-id="492ce-244">**None**</span></span>
     - <span data-ttu-id="492ce-245">**Причина**</span><span class="sxs-lookup"><span data-stu-id="492ce-245">**Reason**</span></span>
     - <span data-ttu-id="492ce-246">**Sender**</span><span class="sxs-lookup"><span data-stu-id="492ce-246">**Sender**</span></span>
     - <span data-ttu-id="492ce-247">**Reported by (Сообщил)**</span><span class="sxs-lookup"><span data-stu-id="492ce-247">**Reported by**</span></span>
     - <span data-ttu-id="492ce-248">**Результат Rescan**</span><span class="sxs-lookup"><span data-stu-id="492ce-248">**Rescan result**</span></span>
     - <span data-ttu-id="492ce-249">**Имитация фишинга**</span><span class="sxs-lookup"><span data-stu-id="492ce-249">**Phish simulation**</span></span>

   - <span data-ttu-id="492ce-250">Чтобы экспортировать записи, щелкните **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="492ce-250">To export the entries, click **Export**.</span></span> <span data-ttu-id="492ce-251">В диалоговом окте, который отображается, сохраните .csv файл.</span><span class="sxs-lookup"><span data-stu-id="492ce-251">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="492ce-252">Если организации настроены на отправку сообщений пользователей только в настраиваемый почтовый ящик, сообщения не  будут отправляться на rescan, а результаты сообщений пользователей всегда будут пустыми.</span><span class="sxs-lookup"><span data-stu-id="492ce-252">If organizations are configured to send user reported messages to the custom mailbox only, reported messages will not be sent for rescan and the results in **User reported messages** will always be empty.</span></span>

### <a name="undo-user-submissions"></a><span data-ttu-id="492ce-253">Отмена отправки пользователей</span><span class="sxs-lookup"><span data-stu-id="492ce-253">Undo user submissions</span></span>

<span data-ttu-id="492ce-254">После отправки подозрительной электронной почты в настраиваемый почтовый ящик у пользователя и администратора нет возможности отменить отправку.</span><span class="sxs-lookup"><span data-stu-id="492ce-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="492ce-255">Если пользователь хочет восстановить электронную почту, она будет доступна для восстановления в папках "Удаленные элементы" или "Нежелательной почты".</span><span class="sxs-lookup"><span data-stu-id="492ce-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="492ce-256">Отправка сообщений в Корпорацию Майкрософт из пользовательского почтового ящика</span><span class="sxs-lookup"><span data-stu-id="492ce-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="492ce-257">Если настраивается настраиваемый почтовый ящик для перехвата сообщений, сообщаемых пользователями, без отправки сообщений в Корпорацию Майкрософт, вы можете найти и отправить определенные сообщения в Корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="492ce-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="492ce-258">Это эффективно перемещает отправку пользователя в отправку администратора.</span><span class="sxs-lookup"><span data-stu-id="492ce-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="492ce-259">На **вкладке Сообщения** пользователя выберите сообщение в списке, щелкните Отправить в **Microsoft** для анализа, а затем выберите одно из следующих значений из списка drop down:</span><span class="sxs-lookup"><span data-stu-id="492ce-259">On the **User reported messages** tab, select a message in the list, click **Submit to Microsoft for analysis**, and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="492ce-260">**Отчет о чистоте**</span><span class="sxs-lookup"><span data-stu-id="492ce-260">**Report clean**</span></span>
- <span data-ttu-id="492ce-261">**Сообщение о фишинге**</span><span class="sxs-lookup"><span data-stu-id="492ce-261">**Report phishing**</span></span>
- <span data-ttu-id="492ce-262">**Отчет о вредоносных программах**</span><span class="sxs-lookup"><span data-stu-id="492ce-262">**Report malware**</span></span>
- <span data-ttu-id="492ce-263">**Сообщение о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="492ce-263">**Report spam**</span></span>
- <span data-ttu-id="492ce-264">**Триггерное исследование**</span><span class="sxs-lookup"><span data-stu-id="492ce-264">**Trigger investigation**</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="492ce-265">![Новые параметры на кнопке Действие](../../media/admin-submission-main-action-button.png)</span><span class="sxs-lookup"><span data-stu-id="492ce-265">![New Options on the Action button](../../media/admin-submission-main-action-button.png)</span></span>
