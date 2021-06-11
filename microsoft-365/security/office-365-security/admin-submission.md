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
ms.openlocfilehash: 5e2fc859ea7df5e85ef65d1ad6f2a09f8806dd58
ms.sourcegitcommit: d0c160e89e17f451199bc4a85699effd2d935213
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2021
ms.locfileid: "52893756"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="e6ab3-103">Использование функции отправки администратором для отправки подозрительного спама, фишинговых сообщений, URL-адресов и файлов в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e6ab3-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e6ab3-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-104">**Applies to**</span></span>
- [<span data-ttu-id="e6ab3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e6ab3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e6ab3-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="e6ab3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="e6ab3-107">В Microsoft 365 организациях с Exchange Online почтовыми ящиками администраторы могут использовать портал Отправки на портале Microsoft 365 Defender для отправки сообщений электронной почты, URL-адресов и вложений в Корпорацию Майкрософт для сканирования.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-107">In Microsoft 365 organizations with Exchange Online mailboxes, admins can use the Submissions portal in the Microsoft 365 Defender portal to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="e6ab3-108">При отправке сообщения электронной почты вы получите:</span><span class="sxs-lookup"><span data-stu-id="e6ab3-108">When you submit an email message, you will get:</span></span>

- <span data-ttu-id="e6ab3-109">**Проверка подлинности электронной** почты. Сведения о том, прошла ли проверка подлинности электронной почты при ее доставке или сбой.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
- <span data-ttu-id="e6ab3-110">**Хиты** политики. Сведения о любых политиках, которые могли разрешить или заблокировать входящие сообщения электронной почты в клиента, переопределив наши решения фильтра службы.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
- <span data-ttu-id="e6ab3-111">**Репутация и детонация полезной** нагрузки: проверка url-адресов и вложений в сообщении.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
- <span data-ttu-id="e6ab3-112">**Анализ грейдера.** Проверка, сделанная грейдерами,чтобы подтвердить, являются ли сообщения вредоносными.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6ab3-113">Анализ репутации/детонации и грейдера полезной нагрузки не проводится во всех клиентах.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="e6ab3-114">Сведения не могут выходить за пределы организации, если данные не должны покидать границу клиента в целях соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="e6ab3-115">Другие способы отправки сообщений электронной почты, URL-адресов и вложений в Корпорацию Майкрософт см. в этой ссылке. [](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="e6ab3-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e6ab3-116">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="e6ab3-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e6ab3-117">Вы открываете портал Microsoft 365 Defender по <https://security.microsoft.com/> ссылке .</span><span class="sxs-lookup"><span data-stu-id="e6ab3-117">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="e6ab3-118">Чтобы перейти непосредственно на **страницу Отправки,** используйте <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="e6ab3-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="e6ab3-119">Чтобы отправить сообщения и файлы в Корпорацию Майкрософт, необходимо быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="e6ab3-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="e6ab3-120">**Управление организацией** или **чтение** безопасности [на портале Microsoft 365 Defender](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="e6ab3-120">**Organization Management** or **Security Reader** in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="e6ab3-121">**Управление организацией** [в Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="e6ab3-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="e6ab3-122">Обратите внимание, что членство в [](#view-user-submissions-to-microsoft) этой группе ролей необходимо для просмотра пользовательских представлений в настраиваемом почтовом ящике, как описано выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-microsoft) as described later in this article.</span></span>

- <span data-ttu-id="e6ab3-123">Дополнительные сведения о том, как пользователи могут отправлять сообщения и файлы в Корпорацию Майкрософт, см. в материалах [Report messages and files to Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="e6ab3-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="e6ab3-124">Сообщение о подозрительном контенте в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e6ab3-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="e6ab3-125">На портале Microsoft 365 Defender перейдите на электронную **почту &** \> **отправки совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-125">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="e6ab3-126">На странице **Отправки** убедитесь, что выбрана вкладка Отправка для анализа, а затем щелкните значок  ![ Ad Submit to Microsoft для ](../../media/m365-cc-sc-create-icon.png) **анализа.**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-126">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected, and then click ![Ad icon](../../media/m365-cc-sc-create-icon.png) **Submit to Microsoft for analysis**.</span></span>

3. <span data-ttu-id="e6ab3-127">Используйте **отправку в Корпорацию Майкрософт** для проверки вылетов, которые, как представляется, представляют сообщение, URL-адрес или вложение электронной почты, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-127">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="e6ab3-128">Отправка сомнительного сообщения электронной почты в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e6ab3-128">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="e6ab3-129">В поле **Выберите тип отправки** убедитесь, что **электронная** почта выбрана в списке drop down.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-129">In the **Select the submission type** box, verify that **Email** is selected in the drop down list.</span></span>

2. <span data-ttu-id="e6ab3-130">В разделе **Добавление сетевого сообщения или** отправка раздела файл электронной почты используйте один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="e6ab3-130">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>
   - <span data-ttu-id="e6ab3-131">Добавьте сетевой **ID** сообщения электронной почты. Это значение GUID, доступное в загонщике **X-MS-Exchange-Organization-Network-Message-Id** в сообщении или в **загоне X-MS-Office365-Filtering-Correlation-Id** в карантинных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-131">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>
   - <span data-ttu-id="e6ab3-132">**Upload файл электронной почты (.msg или .eml)**: Щелкните **Просмотр файлов**.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-132">**Upload the email file (.msg or .eml)**: Click **Browse files**.</span></span> <span data-ttu-id="e6ab3-133">В открываемом диалоговом окте найти и выбрать файл .eml или .msg, а затем нажмите **кнопку Открыть**.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-133">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e6ab3-134">Возможность отправки сообщений в течение 30 дней была временно приостановлена для defender для Office 365 клиентов.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-134">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="e6ab3-135">Администраторы смогут возвращаться только через 7 дней.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-135">Admins will only be able to go back 7 days.</span></span>

3. <span data-ttu-id="e6ab3-136">В поле Выбор получателя с **проблемным полем** укажите получателя, против которого необходимо выполнить проверку политики.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-136">In the **Choose a recipient who had an issue** box, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="e6ab3-137">Проверка политики определяет, не обходится ли проверка электронной почты из-за политики пользователя или организации.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-137">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

4. <span data-ttu-id="e6ab3-138">В разделе **Выбор причины отправки в раздел Microsoft** выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="e6ab3-138">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="e6ab3-139">**Не должно было быть заблокировано (ложное срабатыва-**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-139">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="e6ab3-140">**Должно было быть** заблокировано: В сообщении электронной почты следует классифицируются как раздел, который отображается, выберите одно из следующих значений (если вы не уверены, используйте свое наилучшее решение): </span><span class="sxs-lookup"><span data-stu-id="e6ab3-140">**Should have been blocked**: In the **The email should have been categorized as** section that appears, select one of the following values (if you're not sure, use your best judgement):</span></span>
     - <span data-ttu-id="e6ab3-141">**Фишинг**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-141">**Phish**</span></span>
     - <span data-ttu-id="e6ab3-142">**Спам**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-142">**Spam**</span></span>
     - <span data-ttu-id="e6ab3-143">**Вредоносная программа**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-143">**Malware**</span></span>

5. <span data-ttu-id="e6ab3-144">По завершению нажмите кнопку **Отправить.**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-144">When you're finished, click the **Submit** button.</span></span>

   ![Новый пример отправки URL-адресов](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="e6ab3-146">Отправка подозрительного URL-адреса в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e6ab3-146">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="e6ab3-147">В поле **Выберите тип отправки** выберите **URL-адрес** из списка drop down.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-147">In the **Select the submission type** box, select **URL** from the drop down list.</span></span>

2. <span data-ttu-id="e6ab3-148">В поле **URL-адреса,** которое отображается, введите полный URL-адрес (например, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="e6ab3-148">In the **URL** box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

3. <span data-ttu-id="e6ab3-149">В разделе **Выбор причины отправки в раздел Microsoft** выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="e6ab3-149">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="e6ab3-150">**Не должно было быть заблокировано (ложное срабатыва-**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-150">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="e6ab3-151">**Должно было быть заблокировано:** В этом **URL-адресе** следует классифицируются как раздел, который отображается, выберите **фишинг или** вредоносные **программы**.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-151">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, select **Phish** or **Malware**.</span></span>

4. <span data-ttu-id="e6ab3-152">По завершению нажмите кнопку **Отправить.**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-152">When you're finished, click the **Submit** button.</span></span>

   ![Новый пример отправки электронной почты](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="e6ab3-154">Отправка предполагаемого вложения электронной почты в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e6ab3-154">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="e6ab3-155">В поле **Выберите тип отправки** выберите **Файл из** списка выпаданий.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-155">In the **Select the submission type** box, select **File** from the drop down list.</span></span>

2. <span data-ttu-id="e6ab3-156">В разделе **Файл,** который появится, щелкните **Просмотр файлов**.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-156">In the **File** section that appears, click **Browse files**.</span></span> <span data-ttu-id="e6ab3-157">В открываемом диалоговом окте найти и выбрать файл, а затем нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-157">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="e6ab3-158">В разделе **Выбор причины отправки в раздел Microsoft** выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="e6ab3-158">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="e6ab3-159">**Не должно было быть заблокировано (ложное срабатыва-**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-159">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="e6ab3-160">**Должно быть заблокировано.** В этом **URL-адресе** должен быть классифицирован **раздел,** который отображается, вредоносные программы является единственным выбором, и автоматически выбирается.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-160">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="e6ab3-161">По завершению нажмите кнопку **Отправить.**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-161">When you're finished, click the **Submit** button.</span></span>

   ![Пример отправки вложения](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions-to-microsoft"></a><span data-ttu-id="e6ab3-163">Просмотр представлений администратора в Корпорации Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e6ab3-163">View admin submissions to Microsoft</span></span>

1. <span data-ttu-id="e6ab3-164">На портале Microsoft 365 Defender перейдите на электронную **почту &** \> **отправки совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-164">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="e6ab3-165">На странице **Отправки** убедитесь, что выбрана вкладка **Отправка** для анализа.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-165">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected.</span></span>

   - <span data-ttu-id="e6ab3-166">Вы можете сортировать записи, нажав на доступный столбец.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-166">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="e6ab3-167">Нажмите **кнопку Настройка столбцов,** чтобы показать максимум семь столбцов.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-167">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="e6ab3-168">Значения по умолчанию помечены звездочкой (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="e6ab3-168">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>
     - <span data-ttu-id="e6ab3-169">**Имя отправки**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ab3-169">**Submission name**<sup>\*</sup></span></span>
     - <span data-ttu-id="e6ab3-170">**Отправитель**<su>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ab3-170">**Sender**<su>\*</sup></span></span>
     - <span data-ttu-id="e6ab3-171">**Дата отправки**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ab3-171">**Date submitted**<sup>\*</sup></span></span>
     - <span data-ttu-id="e6ab3-172">**Тип отправки**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ab3-172">**Submission type**<sup>\*</sup></span></span>
     - <span data-ttu-id="e6ab3-173">**Причина отправки**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ab3-173">**Reason for submitting**<sup>\*</sup></span></span>
     - <span data-ttu-id="e6ab3-174">**Состояние Rescan**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ab3-174">**Rescan status**<sup>\*</sup></span></span>
     - <span data-ttu-id="e6ab3-175">**Результат Rescan**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ab3-175">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="e6ab3-176">**Вердикт фильтра**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-176">**Filter verdict**</span></span>
     - <span data-ttu-id="e6ab3-177">**Причина доставки/блокировки**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-177">**Delivery/Block reason**</span></span>
     - <span data-ttu-id="e6ab3-178">**ID отправки**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-178">**Submission ID**</span></span>
     - <span data-ttu-id="e6ab3-179">**Сетевой ID/Object ID**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-179">**Network Message ID/Object ID**</span></span>
     - <span data-ttu-id="e6ab3-180">**Направление**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-180">**Direction**</span></span>
     - <span data-ttu-id="e6ab3-181">**IP-адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-181">**Sender IP**</span></span>
     - <span data-ttu-id="e6ab3-182">**Объемный уровень совместимый (BCL)**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-182">**Bulk compliant level (BCL)**</span></span>
     - <span data-ttu-id="e6ab3-183">**Destination**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-183">**Destination**</span></span>
     - <span data-ttu-id="e6ab3-184">**Действие политики**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-184">**Policy action**</span></span>
     - <span data-ttu-id="e6ab3-185">**Отправлено**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-185">**Submitted by**</span></span>

     <span data-ttu-id="e6ab3-186">По завершению нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-186">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="e6ab3-187">Чтобы отфильтровать записи, щелкните **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-187">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="e6ab3-188">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="e6ab3-188">The available filters are:</span></span>
     - <span data-ttu-id="e6ab3-189">**Дата отправки:** **дата начала и** дата **окончания**.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-189">**Date submitted**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="e6ab3-190">**Тип отправки:** **электронная** **почта, URL-адрес** или **файл.**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-190">**Submission type**: **Email**, **URL**, or **File**.</span></span>
     - <span data-ttu-id="e6ab3-191">**ID отправки:** значение GUID, назначенное каждой отправке.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-191">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
     - <span data-ttu-id="e6ab3-192">**ID сетевого сообщения**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-192">**Network Message ID**</span></span>
     - <span data-ttu-id="e6ab3-193">**Sender**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-193">**Sender**</span></span>

     <span data-ttu-id="e6ab3-194">По завершению нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-194">When you're finished, click **Apply**.</span></span>

     ![Новые параметры фильтра для отправки администратора](../../media/admin-submission-email-filter-options.png)

   - <span data-ttu-id="e6ab3-196">Чтобы сгруппить записи, щелкните **Группу** и выберите одно из следующих значений из списка drop down:</span><span class="sxs-lookup"><span data-stu-id="e6ab3-196">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="e6ab3-197">**Нет**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-197">**None**</span></span>
     - <span data-ttu-id="e6ab3-198">**Тип**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-198">**Type**</span></span>
     - <span data-ttu-id="e6ab3-199">**Причина**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-199">**Reason**</span></span>
     - <span data-ttu-id="e6ab3-200">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-200">**Status**</span></span>
     - <span data-ttu-id="e6ab3-201">**Результат Rescan**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-201">**Rescan result**</span></span>

   - <span data-ttu-id="e6ab3-202">Чтобы экспортировать записи, щелкните **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-202">To export the entries, click **Export**.</span></span> <span data-ttu-id="e6ab3-203">В диалоговом окте, который отображается, сохраните .csv файл.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-203">In the dialog that appears, save the .csv file.</span></span>

### <a name="admin-submission-rescan-details"></a><span data-ttu-id="e6ab3-204">Сведения о повторном представлении администратора</span><span class="sxs-lookup"><span data-stu-id="e6ab3-204">Admin submission rescan details</span></span>

<span data-ttu-id="e6ab3-205">Сообщения, отправленные в представлениях администратора, rescanned и результаты, показанные в вылете детализации представлений:</span><span class="sxs-lookup"><span data-stu-id="e6ab3-205">Messages that are submitted in admin submissions are rescanned and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="e6ab3-206">Возникновение сбоя при проверке подлинности электронной почты отправителя в момент доставки.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-206">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="e6ab3-207">Сведения о любых совпадениях политик, которые могут повлиять на решение по безопасности касательно сообщения или переопределить его.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-207">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="e6ab3-208">Текущие результаты отключения, чтобы определить, были ли URL-адреса или файлы, содержащиеся в сообщении, вредоносными или нет.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-208">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="e6ab3-209">Отзывы от грейдеров.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-209">Feedback from graders.</span></span>

<span data-ttu-id="e6ab3-210">Если было обнаружено переопределение, повторное сканирование должно завершиться через несколько минут.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-210">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="e6ab3-211">Если в проверке подлинности или доставке электронной почты не возникло проблем с переопределением, то отзывы от грейдеров могут занять до одного дня.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-211">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="e6ab3-212">Просмотр пользовательских представлений в Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="e6ab3-212">View user submissions to Microsoft</span></span>

<span data-ttu-id="e6ab3-213">Если вы развернули надстройку [Report Message,](enable-the-report-message-add-in.md)надстройку [Report Phishing](enable-the-report-phish-add-in.md) [или](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)пользователи используют встроенную отчетность в Outlook в Интернете,  вы можете увидеть, какие отчеты пользователи сообщают на вкладке сообщение пользователя.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-213">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User reported message** tab.</span></span>

1. <span data-ttu-id="e6ab3-214">На портале Microsoft 365 Defender перейдите на электронную **почту &** \> **отправки совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-214">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="e6ab3-215">На странице **Отправки** выберите вкладку **Сообщения** пользователя.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-215">On the **Submissions** page, select the **User reported messages** tab.</span></span>

   - <span data-ttu-id="e6ab3-216">Вы можете сортировать записи, нажав на доступный столбец.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-216">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="e6ab3-217">Нажмите **кнопку Настройка столбцов,** чтобы показать максимум семь столбцов.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-217">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="e6ab3-218">Значения по умолчанию помечены звездочкой (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="e6ab3-218">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

     - <span data-ttu-id="e6ab3-219">**Тема электронной почты**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ab3-219">**Email subject**<sup>\*</sup></span></span>
     - <span data-ttu-id="e6ab3-220">**Reported by**<su>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ab3-220">**Reported by**<su>\*</sup></span></span>
     - <span data-ttu-id="e6ab3-221">**Дата сообщается**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ab3-221">**Date reported**<sup>\*</sup></span></span>
     - <span data-ttu-id="e6ab3-222">**Отправитель**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ab3-222">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="e6ab3-223">**Сообщаемая причина**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ab3-223">**Reported reason**<sup>\*</sup></span></span>
     - <span data-ttu-id="e6ab3-224">**Результат Rescan**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ab3-224">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="e6ab3-225">**ID сообщения**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-225">**Message reported ID**</span></span>
     - <span data-ttu-id="e6ab3-226">**ID сетевого сообщения**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-226">**Network Message ID**</span></span>
     - <span data-ttu-id="e6ab3-227">**IP-адрес отправителя**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-227">**Sender IP**</span></span>
     - <span data-ttu-id="e6ab3-228">**Имитация фишинга**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-228">**Phish simulation**</span></span>

     <span data-ttu-id="e6ab3-229">По завершению нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-229">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="e6ab3-230">Чтобы отфильтровать записи, щелкните **Фильтр**.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-230">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="e6ab3-231">Доступные фильтры:</span><span class="sxs-lookup"><span data-stu-id="e6ab3-231">The available filters are:</span></span>
     - <span data-ttu-id="e6ab3-232">**Дата сообщается:** **дата начала и** **даты окончания**.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-232">**Date reported**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="e6ab3-233">**Reported by (Сообщил)**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-233">**Reported by**</span></span>
     - <span data-ttu-id="e6ab3-234">**Тема письма**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-234">**Email subject**</span></span>
     - <span data-ttu-id="e6ab3-235">**ID сообщения**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-235">**Message reported ID**</span></span>
     - <span data-ttu-id="e6ab3-236">**ID сетевого сообщения**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-236">**Network Message ID**</span></span>
     - <span data-ttu-id="e6ab3-237">**Sender**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-237">**Sender**</span></span>
     - <span data-ttu-id="e6ab3-238">**Сообщаемая причина:** **не нежелательной,** **фишинг** или **спам**.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-238">**Reported reason**: **Not junk**, **Phish**, or **Spam**.</span></span>
     - <span data-ttu-id="e6ab3-239">**Фишинговое моделирование:** **да** или **нет**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-239">**Phish simulation**: **Yes** or **No**</span></span>

     <span data-ttu-id="e6ab3-240">По завершению нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-240">When you're finished, click **Apply**.</span></span>

    ![Новые параметры фильтра для пользовательских представлений](../../media/user-submissions-filter-options.png)

   - <span data-ttu-id="e6ab3-242">Чтобы сгруппить записи, щелкните **Группу** и выберите одно из следующих значений из списка drop down:</span><span class="sxs-lookup"><span data-stu-id="e6ab3-242">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="e6ab3-243">**Нет**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-243">**None**</span></span>
     - <span data-ttu-id="e6ab3-244">**Причина**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-244">**Reason**</span></span>
     - <span data-ttu-id="e6ab3-245">**Sender**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-245">**Sender**</span></span>
     - <span data-ttu-id="e6ab3-246">**Reported by (Сообщил)**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-246">**Reported by**</span></span>
     - <span data-ttu-id="e6ab3-247">**Результат Rescan**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-247">**Rescan result**</span></span>
     - <span data-ttu-id="e6ab3-248">**Имитация фишинга**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-248">**Phish simulation**</span></span>

   - <span data-ttu-id="e6ab3-249">Чтобы экспортировать записи, щелкните **Экспорт**.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-249">To export the entries, click **Export**.</span></span> <span data-ttu-id="e6ab3-250">В диалоговом окте, который отображается, сохраните .csv файл.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-250">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="e6ab3-251">Если организации настроены на отправку сообщений пользователей только в настраиваемый почтовый ящик, сообщения не  будут отправляться на rescan, а результаты сообщений пользователей всегда будут пустыми.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-251">If organizations are configured to send user reported messages to the custom mailbox only, reported messages will not be sent for rescan and the results in **User reported messages** will always be empty.</span></span>

### <a name="undo-user-submissions"></a><span data-ttu-id="e6ab3-252">Отмена отправки пользователей</span><span class="sxs-lookup"><span data-stu-id="e6ab3-252">Undo user submissions</span></span>

<span data-ttu-id="e6ab3-253">После отправки подозрительной электронной почты в настраиваемый почтовый ящик у пользователя и администратора нет возможности отменить отправку.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-253">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="e6ab3-254">Если пользователь хочет восстановить электронную почту, она будет доступна для восстановления в папках "Удаленные элементы" или "Нежелательной почты".</span><span class="sxs-lookup"><span data-stu-id="e6ab3-254">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="e6ab3-255">Отправка сообщений в Корпорацию Майкрософт из пользовательского почтового ящика</span><span class="sxs-lookup"><span data-stu-id="e6ab3-255">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="e6ab3-256">Если настраивается настраиваемый почтовый ящик для перехвата сообщений, сообщаемых пользователями, без отправки сообщений в Корпорацию Майкрософт, вы можете найти и отправить определенные сообщения в Корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-256">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="e6ab3-257">Это эффективно перемещает отправку пользователя в отправку администратора.</span><span class="sxs-lookup"><span data-stu-id="e6ab3-257">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="e6ab3-258">На **вкладке Сообщения** пользователя выберите сообщение в списке, щелкните Отправить в **Microsoft** для анализа, а затем выберите одно из следующих значений из списка drop down:</span><span class="sxs-lookup"><span data-stu-id="e6ab3-258">On the **User reported messages** tab, select a message in the list, click **Submit to Microsoft for analysis**, and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="e6ab3-259">**Отчет о чистоте**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-259">**Report clean**</span></span>
- <span data-ttu-id="e6ab3-260">**Сообщение о фишинге**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-260">**Report phishing**</span></span>
- <span data-ttu-id="e6ab3-261">**Отчет о вредоносных программах**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-261">**Report malware**</span></span>
- <span data-ttu-id="e6ab3-262">**Сообщение о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-262">**Report spam**</span></span>
- <span data-ttu-id="e6ab3-263">**Триггерное исследование**</span><span class="sxs-lookup"><span data-stu-id="e6ab3-263">**Trigger investigation**</span></span>

![Новые параметры на кнопке Действие](../../media/user-submission-custom-mailbox-action-button.png)
