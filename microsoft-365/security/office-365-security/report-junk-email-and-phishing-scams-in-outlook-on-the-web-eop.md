---
title: Создание отчетов о нежелательной почте и фишинге в Outlook в Интернете
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
description: Администраторы могут узнать о встроенных, не являющиеся нежелательными и фишинговыми отчетами о сообщениях в Outlook в Интернете в Exchange Online в Exchange Online и как отключить эти параметры отчетов для пользователей.
ms.openlocfilehash: a364afed9bb7e61d5f34ffc0206ede1c5155db65
ms.sourcegitcommit: c692bdc186fb29499816e8bb2addcddef34d23d3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46818337"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="661c6-103">Создание отчетов о нежелательной почте и фишинге в Outlook в Интернете в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="661c6-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

<span data-ttu-id="661c6-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online вы можете использовать встроенные возможности создания отчетов в Outlook в Интернете (прежнее название Outlook Web App), чтобы отправить ложные срабатывания (хорошие сообщения отмечены как спам), ложные отрицательные результаты (не допустимые электронные письма) и фишинговые сообщения в Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="661c6-104">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="661c6-105">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="661c6-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="661c6-106">Если вы являетесь администратором организации с почтовыми ящиками Exchange Online, рекомендуем использовать портал отправки в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="661c6-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="661c6-107">Дополнительные сведения см. в статье ["Использование функции отправки администратора" для отправки подозрительного спама, фишинга, URL-адресов и файлов в корпорацию Майкрософт.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="661c6-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="661c6-108">Администраторы могут отключить или разрешить пользователям отправлять сообщения в Майкрософт в Интернете.</span><span class="sxs-lookup"><span data-stu-id="661c6-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="661c6-109">Дополнительные сведения см. в разделе ["Отключение или включение отчетов о нежелательной почте в Outlook в](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) Интернете" далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="661c6-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="661c6-110">Вы можете настроить отправленные сообщения для копирования или перенаправления в заданный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="661c6-110">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="661c6-111">Дополнительные сведения см. в статье , посвященном почтовому ящику, для отправки нежелательных [и фишинговых сообщений в Exchange Online.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="661c6-111">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="661c6-112">Дополнительные сведения об отчетах в корпорацию Майкрософт см. в статье [Отчето о сообщениях и файлах в корпорацию Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="661c6-112">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="661c6-113">Отправка отчетов о спаме и фишинговых сообщениях в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="661c6-113">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="661c6-114">Для сообщений из папки "Входящие" или другой папки сообщений, кроме "Нежелательная почта", используйте один из следующих способов создания отчетов о спаме и фишинговых сообщениях:</span><span class="sxs-lookup"><span data-stu-id="661c6-114">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="661c6-115">Выберите сообщение, нажмите **кнопку "Нежелательно"** на панели инструментов, а затем **выберите "Нежелательная** **или фишинговое сообщение".**</span><span class="sxs-lookup"><span data-stu-id="661c6-115">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Сообщайте о нежелательной почте или фишинговых сообщениях с ленты](../../media/owa-report-junk.png)

   - <span data-ttu-id="661c6-117">Выберите одно или несколько сообщений, щелкните его правой кнопкой мыши и выберите пункт **"Пометить как нежелательное".**</span><span class="sxs-lookup"><span data-stu-id="661c6-117">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="661c6-118">В появившемся диалоговом окне нажмите кнопку **"Отчет".**</span><span class="sxs-lookup"><span data-stu-id="661c6-118">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="661c6-119">Если вы передумали, нажмите **"Не давать отчет".**</span><span class="sxs-lookup"><span data-stu-id="661c6-119">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="661c6-120">Нежелательное</span><span class="sxs-lookup"><span data-stu-id="661c6-120">Junk</span></span>|<span data-ttu-id="661c6-121">Фишинговое</span><span class="sxs-lookup"><span data-stu-id="661c6-121">Phishing</span></span>|
   |:---:|:---:|
   |![Диалоговое окно отчета о нежелательной почте](../../media/owa-report-as-junk-dialog.png)|![Сообщение в качестве диалогового окна фишинга](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="661c6-124">Выбранные сообщения будут отправлены корпорации Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="661c6-124">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="661c6-125">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="661c6-125">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="661c6-126">Отправка отчетов о нежелательных и фишинговых сообщениях из папки "Нежелательная почта" в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="661c6-126">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="661c6-127">В папке нежелательной почты отправьте сообщение о ложных срабатываниях или фишинговых сообщениях в папке "Нежелательная почта" либо один из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="661c6-127">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="661c6-128">Выберите сообщение, щелкните **"Не является нежелательным"** на панели инструментов, а затем выберите **"Не является нежелательным"** или **"Фишингом".**</span><span class="sxs-lookup"><span data-stu-id="661c6-128">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Сообщайте о нежелательной почте или фишинговых сообщениях с ленты](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="661c6-130">Выберите одно или несколько сообщений, щелкните его правой кнопкой мыши и выберите пункт **"Пометить как не является нежелательным".**</span><span class="sxs-lookup"><span data-stu-id="661c6-130">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="661c6-131">В отобразившемся диалоговом окне прочитайте сведения и щелкните **"Отчет".**</span><span class="sxs-lookup"><span data-stu-id="661c6-131">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="661c6-132">Если вы передумали, нажмите **"Не давать отчет".**</span><span class="sxs-lookup"><span data-stu-id="661c6-132">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="661c6-133">Не является нежелательным</span><span class="sxs-lookup"><span data-stu-id="661c6-133">Not Junk</span></span>|<span data-ttu-id="661c6-134">Фишинговое</span><span class="sxs-lookup"><span data-stu-id="661c6-134">Phishing</span></span>|
   |:---:|:---:|
   |![Диалоговое окно отчетов о не нежелательной почте](../../media/owa-report-as-not-junk-dialog.png)|![Сообщение в качестве диалогового окна фишинга](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="661c6-137">Выбранные сообщения будут отправлены корпорации Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="661c6-137">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="661c6-138">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="661c6-138">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="661c6-139">Отключение и включение отчетов о нежелательной почте в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="661c6-139">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="661c6-140">По умолчанию пользователи могут сообщать о ложных срабатываниях, ложных отрицательных и фишинговых сообщениях в корпорацию Майкрософт для анализа в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="661c6-140">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="661c6-141">Администраторы могут настроить политики почтовых ящиков Outlook в Интернете в Exchange Online PowerShell, чтобы предотвратить отправку пользователями отчетов о ложных срабатываниях спама и о триггерах нежелательных сообщений в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="661c6-141">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="661c6-142">Нельзя отключить для пользователей возможность отправки отчетов о фишинговых сообщениях в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="661c6-142">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="661c6-143">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="661c6-143">What do you need to know before you begin?</span></span>

- <span data-ttu-id="661c6-144">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="661c6-144">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="661c6-145">Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="661c6-145">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="661c6-146">Для частей, вам **нужны роли "Политики** **получателей" или "Получатели почты"** в Exchange Online, которые по умолчанию назначаются группам **ролей** Управление организацией и управление получателями. **Organization Management**</span><span class="sxs-lookup"><span data-stu-id="661c6-146">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="661c6-147">Дополнительные сведения о группах ролей в Exchange Online см. в разделе ["Изменение групп ролей в Exchange Online".](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="661c6-147">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="661c6-148">В каждой организации есть политика по умолчанию под названием OwaMailboxPolicy-Default, но можно создавать настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="661c6-148">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="661c6-149">Настраиваемые политики применяются к пользователям в области, прежде чем политика по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="661c6-149">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="661c6-150">Дополнительные сведения о политиках почтовых ящиков Outlook в Интернете см. в статье ["Политики почтовых ящиков Outlook в Интернете" в Exchange Online.](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)</span><span class="sxs-lookup"><span data-stu-id="661c6-150">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="661c6-151">Отключение отчетов о нежелательной почте не снижает возможность пометки сообщений как нежелательных или не являющиеся нежелательными в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="661c6-151">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="661c6-152">При выборе сообщения в папке **Not junk** "Нежелательная почта" сообщение о том, что сообщение не является нежелательным, по-прежнему \> **Not junk** перемещается обратно в папку "Входящие".</span><span class="sxs-lookup"><span data-stu-id="661c6-152">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="661c6-153">При выборе сообщения в любой **Junk** другой папке электронной почты, при щелчке \> **"Нежелательная** почта" сообщение по-прежнему будет перемещено в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="661c6-153">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="661c6-154">Теперь вы можете сообщать о сообщении в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="661c6-154">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="661c6-155">Использование Exchange Online PowerShell для отключения или включения отчетов о нежелательной почте в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="661c6-155">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="661c6-156">Чтобы найти существующие политики почтовых ящиков Outlook в Интернете и состояние отчетов о нежелательной почте, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="661c6-156">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="661c6-157">Чтобы отключить или включить создание отчетов о нежелательной почте в Outlook в Интернете, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="661c6-157">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="661c6-158">В этом примере показано, как отключить создание отчетов о нежелательной почте в политике по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="661c6-158">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="661c6-159">В этом примере показано, как сделать создание отчетов о нежелательной почте в настраиваемой политике Contoso Managers.</span><span class="sxs-lookup"><span data-stu-id="661c6-159">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="661c6-160">Дополнительные сведения о синтаксисе и параметрах см. в [разделах Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) [и Set-OwaMailboxPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="661c6-160">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="661c6-161">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="661c6-161">How do you know this worked?</span></span>

<span data-ttu-id="661c6-162">Чтобы убедиться, что вы успешно включили или отключили отчеты о нежелательной почте в Outlook в Интернете, выполните любое из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="661c6-162">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="661c6-163">В Exchange Online PowerShell выполните следующую команду и проверьте значение **свойства ReportJunkEmailEnabled:**</span><span class="sxs-lookup"><span data-stu-id="661c6-163">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="661c6-164">Откройте почтовый ящик затронутого пользователя в Outlook в Интернете, выберите сообщение в папке "Входящие", щелкните **"Нежелательное"** и проверьте запрос на отправку или неотображаться приглашение сообщать о сообщении \> **Junk** в корпорацию Майкрософт.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="661c6-164">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="661c6-165">Откройте почтовый ящик затронутого пользователя в Outlook в Интернете, выберите сообщение в папке "Нежелательная почта", щелкните **"Нежелательное"** и убедитесь, что нужно сообщить о сообщении \> **Junk** в корпорацию Майкрософт или не отображается.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="661c6-165">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="661c6-166"><sup>\*</sup> Пользователи могут скрывать подсказку о сообщении, сохраняя при этом отчет ы.</span><span class="sxs-lookup"><span data-stu-id="661c6-166"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="661c6-167">Чтобы проверить этот параметр в Outlook в Интернете:</span><span class="sxs-lookup"><span data-stu-id="661c6-167">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="661c6-168">Щелкните **значок** ![ "Параметры Outlook в Интернете" и ](../../media/owa-settings-icon.png) \> **щелкните значок "Параметры Outlook в Интернете" "Просмотреть все** \> **параметры нежелательной почты Outlook".**</span><span class="sxs-lookup"><span data-stu-id="661c6-168">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="661c6-169">В разделе **отчетов** проверьте значение **"Спросите меня перед отправкой отчета".**</span><span class="sxs-lookup"><span data-stu-id="661c6-169">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Параметры отчетов о нежелательной почте в Outlook в Интернете](../../media/owa-junk-email-reporting-options.png)
