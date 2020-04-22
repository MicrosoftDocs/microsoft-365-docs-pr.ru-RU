---
title: 'Создание отчетов о нежелательной почте и мошеннических сообщениях (фишинге) в Outlook в Интернете '
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Пользователи Microsoft 365 с почтовыми ящиками Exchange Online могут использовать Outlook в Интернете (Outlook Web App) для отправки нежелательной почты, нежелательной почты и фишинговых сообщений в корпорацию Майкрософт для анализа.
ms.openlocfilehash: 858224074ef7258d59318eef0c685a4ea4f9130f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632623"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-office-365"></a><span data-ttu-id="6b1df-103">Отправка нежелательных и фишинговых сообщений электронной почты в Outlook в Интернете в Office 365</span><span class="sxs-lookup"><span data-stu-id="6b1df-103">Report junk and phishing email in Outlook on the web in Office 365</span></span>

<span data-ttu-id="6b1df-104">Если вы являетесь клиентом Microsoft 365 с почтовыми ящиками Exchange Online, вы можете использовать встроенные параметры отчетов в Outlook в Интернете (прежнее название — Outlook Web App) для отправки ложных срабатываний (хорошее сообщение электронной почты отмечено как спам), ложные отрицательные (недопустимые письма) и фишинговые сообщения в Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="6b1df-104">If you're a Microsoft 365 customer with Exchange Online mailboxes, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6b1df-105">Что нужно знать перед началом работы?</span><span class="sxs-lookup"><span data-stu-id="6b1df-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6b1df-106">Если вы являетесь администратором в Организации с почтовыми ящиками Exchange Online, рекомендуем использовать портал отправки в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="6b1df-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="6b1df-107">Дополнительные сведения см. в [статье Использование отправки администратором для отправки подозреваемой спама, фишинга, URL-адресов и файлов в корпорацию Майкрософт](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="6b1df-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="6b1df-108">Администраторы могут отключить или разрешить пользователям сообщать о сообщениях в корпорацию Майкрософт в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="6b1df-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="6b1df-109">Дополнительные сведения см. в разделе [Отключение или Включение отчетов о нежелательной почте в Outlook в Интернете](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="6b1df-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="6b1df-110">Дополнительные сведения о сообщениях отчетов в корпорацию Майкрософт можно найти [в статье сообщения и файлы отчетов в корпорацию Майкрософт в Office 365](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="6b1df-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="6b1df-111">Составление отчетов о нежелательной почте и фишинговых сообщениях в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="6b1df-111">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="6b1df-112">Для сообщений в папке "Входящие" или любой другой папке, кроме нежелательной почты, используйте один из следующих способов для создания отчетов о нежелательной почте и фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="6b1df-112">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="6b1df-113">Выберите сообщение, нажмите кнопку **Нежелательная почта** на панели инструментов, а затем выберите **нежелательные** или **Фишинг**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-113">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Отправка нежелательных или фишинговых сообщений электронной почты с ленты](../../media/owa-report-junk.png)

   - <span data-ttu-id="6b1df-115">Выберите одно или несколько сообщений, щелкните правой кнопкой мыши и выберите **Пометить как нежелательное**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-115">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="6b1df-116">В появившемся диалоговом окне нажмите **отчет**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-116">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="6b1df-117">Если вы передумали, щелкните **не сообщать**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-117">If you change your mind, click **Don't Report**.</span></span>

   ![Диалоговое окно отчета о нежелательной почте](../../media/owa-report-as-junk-dialog.png)

   ![Диалоговое окно отчета в качестве фишинга](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="6b1df-120">Выбранные сообщения будут отправлены в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="6b1df-120">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="6b1df-121">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="6b1df-121">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="6b1df-122">Отправка сообщений о сообщениях о нежелательной почте и фишинге из папки "Нежелательная почта" в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="6b1df-122">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="6b1df-123">В папке нежелательной почты используйте один из следующих способов, чтобы сообщить о ложных срабатываниях или фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="6b1df-123">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="6b1df-124">Выберите сообщение, щелкните **не спам** на панели инструментов, а затем выберите **не спам** или **Фишинг**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-124">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Отправка нежелательных или фишинговых сообщений электронной почты с ленты](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="6b1df-126">Выберите одно или несколько сообщений, щелкните правой кнопкой мыши и выберите пункт **Пометить как не являющееся нежелательным**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-126">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="6b1df-127">В появившемся диалоговом окне прочитайте сведения и щелкните **отчет**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-127">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="6b1df-128">Если вы передумали, щелкните **не сообщать**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-128">If you change your mind, click **Don't Report**.</span></span>

   ![Диалоговое окно "сообщить как нежелательное"](../../media/owa-report-as-not-junk-dialog.png)

   ![Диалоговое окно отчета в качестве фишинга](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="6b1df-131">Выбранные сообщения будут отправлены в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="6b1df-131">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="6b1df-132">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="6b1df-132">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="6b1df-133">Отключение и Включение отчетов о нежелательной почте в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="6b1df-133">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="6b1df-134">По умолчанию пользователи могут сообщать о ложных срабатываниях нежелательной почты, ложных негативных и фишинговых сообщениях в корпорацию Майкрософт для анализа в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="6b1df-134">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="6b1df-135">Администраторы могут настроить Outlook в политиках веб-почтовых ящиков в Exchange Online PowerShell, чтобы запретить пользователям сообщать о ложных срабатываниях и нежелательных сообщениях в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6b1df-135">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="6b1df-136">Невозможно отключить возможность пользователей сообщать о phishing-сообщениях в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6b1df-136">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6b1df-137">Что нужно знать перед началом работы?</span><span class="sxs-lookup"><span data-stu-id="6b1df-137">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6b1df-138">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="6b1df-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="6b1df-139">Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="6b1df-139">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="6b1df-140">В частности, потребуются роли **получателей** или роли **получателей почты** в Exchange Online, которые назначаются группам ролей " **Управление организацией** " и " **Управление получателями** " по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6b1df-140">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="6b1df-141">Дополнительные сведения о группах ролей в Exchange Online можно узнать в статье [изменение групп ролей в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span><span class="sxs-lookup"><span data-stu-id="6b1df-141">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="6b1df-142">Каждая организация имеет политику по умолчанию с именем OwaMailboxPolicy по умолчанию, но вы можете создавать настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="6b1df-142">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="6b1df-143">Настраиваемые политики применяются к пользователям с ограниченной областью действия перед политикой по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6b1df-143">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="6b1df-144">Для получения дополнительных сведений о политиках почтовых ящиков Outlook в Интернете просмотрите [политики почтовых ящиков Outlook в Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span><span class="sxs-lookup"><span data-stu-id="6b1df-144">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="6b1df-145">Отключение отчетов о нежелательной почте не удаляет возможность пометить сообщение как нежелательное или не являющееся нежелательным в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="6b1df-145">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="6b1df-146">При выборе сообщения в папке "Нежелательная почта", если щелкнуть **не спам** \> **, все равно** перемещает сообщение обратно в папку "Входящие".</span><span class="sxs-lookup"><span data-stu-id="6b1df-146">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="6b1df-147">При выборе сообщения в любой другой папке электронной почты и **нажатии** \> кнопки нежелательные сообщения все равно перемещаются в папку " **Нежелательная** почта".</span><span class="sxs-lookup"><span data-stu-id="6b1df-147">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="6b1df-148">Сведения о том, что больше недоступно — возможность отправки сообщения в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6b1df-148">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="6b1df-149">Отключение и Включение отчетов о нежелательной почте в Outlook в Интернете с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b1df-149">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="6b1df-150">Чтобы найти существующие политики почтовых ящиков Outlook в Интернете и состояние отчетов о нежелательной почте, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6b1df-150">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="6b1df-151">Чтобы включить или отключить отчеты о нежелательной почте в Outlook в Интернете, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="6b1df-151">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="6b1df-152">В этом примере отключается создание отчетов о нежелательной почте в политике по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6b1df-152">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="6b1df-153">В этом примере включается создание отчетов о нежелательной почте в пользовательской политике с именем Contoso Managers.</span><span class="sxs-lookup"><span data-stu-id="6b1df-153">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="6b1df-154">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) и [Set/OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="6b1df-154">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="6b1df-155">Как проверить, все ли получилось?</span><span class="sxs-lookup"><span data-stu-id="6b1df-155">How do you know this worked?</span></span>

<span data-ttu-id="6b1df-156">Чтобы убедиться, что вы успешно включили или отключили отчеты о нежелательной почте в Outlook в Интернете, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="6b1df-156">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="6b1df-157">В Exchange Online PowerShell выполните следующую команду и проверьте значение свойства **репортжункемаиленаблед** :</span><span class="sxs-lookup"><span data-stu-id="6b1df-157">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="6b1df-158">Откройте почтовый ящик затронутого пользователя в Outlook в Интернете, выберите сообщение в папке "Входящие" \> , **щелкните Нежелательная** **почта** и убедитесь, что сообщение не отображается в поле сообщить корпорации Майкрософт или не отображается.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6b1df-158">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="6b1df-159">Откройте почтовый ящик затронутого пользователя в Outlook в Интернете, выберите сообщение в папке "Нежелательная почта" **, щелкните** \> **Junk** Нежелательная почта и убедитесь, что сообщение не отображается в поле сообщить корпорации Майкрософт.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6b1df-159">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="6b1df-160"><sup>\*</sup>Пользователи могут скрыть приглашение, чтобы отправить отчет о сообщении, не отменяя сообщение.</span><span class="sxs-lookup"><span data-stu-id="6b1df-160"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="6b1df-161">Чтобы проверить этот параметр в Outlook в Интернете, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="6b1df-161">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="6b1df-162">Щелкните **Параметры** ![Outlook](../../media/owa-settings-icon.png) \> в значке веб-параметры, чтобы просмотреть все **нежелательные сообщения**в **параметрах** \> Outlook.</span><span class="sxs-lookup"><span data-stu-id="6b1df-162">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="6b1df-163">В разделе **отчеты** проверьте значение: **спрашивать меня перед отправкой отчета**.</span><span class="sxs-lookup"><span data-stu-id="6b1df-163">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Параметры отчетов о нежелательной почте в Интернете](../../media/owa-junk-email-reporting-options.png)
