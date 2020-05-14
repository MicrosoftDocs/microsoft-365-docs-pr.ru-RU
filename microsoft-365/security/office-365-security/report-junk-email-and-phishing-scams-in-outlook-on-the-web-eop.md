---
title: Отправка нежелательных и фишинговых сообщений электронной почты в Outlook в Интернете
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
description: Администраторы могут изучить встроенные параметры отчетов о нежелательной почте, нежелательной почте и фишинге в Outlook в Интернете (Outlook Web App) в Exchange Online, а также как отключить эти параметры отчетов для пользователей.
ms.openlocfilehash: dd4b23efa9e12a02ce69167712bc0466b3445c44
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224701"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="7ab3d-103">Отправка нежелательных и фишинговых сообщений электронной почты в Outlook в Интернете в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7ab3d-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

<span data-ttu-id="7ab3d-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online вы можете использовать встроенные параметры отчетов в Outlook в Интернете (прежнее название — Outlook Web App) для отправки ложных срабатываний (хороший адрес электронной почты отмечен как спам), ложные отрицательные (недопустимые сообщения электронной почты) и фишинговых сообщений в Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="7ab3d-104">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7ab3d-105">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="7ab3d-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7ab3d-106">Если вы являетесь администратором в Организации с почтовыми ящиками Exchange Online, рекомендуем использовать портал отправки в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="7ab3d-107">Дополнительные сведения см. в [статье Использование отправки администратором для отправки подозреваемой спама, фишинга, URL-адресов и файлов в корпорацию Майкрософт](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="7ab3d-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="7ab3d-108">Администраторы могут отключить или разрешить пользователям сообщать о сообщениях в корпорацию Майкрософт в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="7ab3d-109">Дополнительные сведения см. в разделе [Отключение или Включение отчетов о нежелательной почте в Outlook в Интернете](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="7ab3d-110">Можно настроить копирование или перенаправление сообщений, отправленных в указанный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-110">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="7ab3d-111">Дополнительные сведения см. [в статье определение почтового ящика для отправленных пользователем сообщений о нежелательной почте и фишинговых сообщениях в Exchange Online](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="7ab3d-111">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="7ab3d-112">Дополнительные сведения о сообщениях отчетов в корпорацию Майкрософт можно найти [в статье сообщения и файлы отчетов в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="7ab3d-112">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="7ab3d-113">Составление отчетов о нежелательной почте и фишинговых сообщениях в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="7ab3d-113">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="7ab3d-114">Для сообщений в папке "Входящие" или любой другой папке, кроме нежелательной почты, используйте один из следующих способов для создания отчетов о нежелательной почте и фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-114">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="7ab3d-115">Выберите сообщение, нажмите кнопку **Нежелательная почта** на панели инструментов, а затем выберите **нежелательные** или **Фишинг**.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-115">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Отправка нежелательных или фишинговых сообщений электронной почты с ленты](../../media/owa-report-junk.png)

   - <span data-ttu-id="7ab3d-117">Выберите одно или несколько сообщений, щелкните правой кнопкой мыши и выберите **Пометить как нежелательное**.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-117">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="7ab3d-118">В появившемся диалоговом окне нажмите **отчет**.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-118">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="7ab3d-119">Если вы передумали, щелкните **не сообщать**.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-119">If you change your mind, click **Don't Report**.</span></span>

   ![Диалоговое окно отчета о нежелательной почте](../../media/owa-report-as-junk-dialog.png)

   ![Диалоговое окно отчета в качестве фишинга](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="7ab3d-122">Выбранные сообщения будут отправлены в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-122">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="7ab3d-123">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-123">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="7ab3d-124">Отправка сообщений о сообщениях о нежелательной почте и фишинге из папки "Нежелательная почта" в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="7ab3d-124">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="7ab3d-125">В папке нежелательной почты используйте один из следующих способов, чтобы сообщить о ложных срабатываниях или фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-125">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="7ab3d-126">Выберите сообщение, щелкните **не спам** на панели инструментов, а затем выберите **не спам** или **Фишинг**.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-126">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Отправка нежелательных или фишинговых сообщений электронной почты с ленты](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="7ab3d-128">Выберите одно или несколько сообщений, щелкните правой кнопкой мыши и выберите пункт **Пометить как не являющееся нежелательным**.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-128">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="7ab3d-129">В появившемся диалоговом окне прочитайте сведения и щелкните **отчет**.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-129">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="7ab3d-130">Если вы передумали, щелкните **не сообщать**.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-130">If you change your mind, click **Don't Report**.</span></span>

   ![Диалоговое окно "сообщить как нежелательное"](../../media/owa-report-as-not-junk-dialog.png)

   ![Диалоговое окно отчета в качестве фишинга](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="7ab3d-133">Выбранные сообщения будут отправлены в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-133">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="7ab3d-134">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-134">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="7ab3d-135">Отключение и Включение отчетов о нежелательной почте в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="7ab3d-135">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="7ab3d-136">По умолчанию пользователи могут сообщать о ложных срабатываниях нежелательной почты, ложных негативных и фишинговых сообщениях в корпорацию Майкрософт для анализа в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-136">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="7ab3d-137">Администраторы могут настроить Outlook в политиках веб-почтовых ящиков в Exchange Online PowerShell, чтобы запретить пользователям сообщать о ложных срабатываниях и нежелательных сообщениях в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-137">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="7ab3d-138">Невозможно отключить возможность пользователей сообщать о phishing-сообщениях в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-138">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7ab3d-139">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="7ab3d-139">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7ab3d-140">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="7ab3d-140">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="7ab3d-141">Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-141">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="7ab3d-142">В частности, потребуются роли **получателей** или роли **получателей почты** в Exchange Online, которые назначаются группам ролей " **Управление организацией** " и " **Управление получателями** " по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-142">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="7ab3d-143">Дополнительные сведения о группах ролей в Exchange Online можно узнать в статье [изменение групп ролей в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span><span class="sxs-lookup"><span data-stu-id="7ab3d-143">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="7ab3d-144">Каждая организация имеет политику по умолчанию с именем OwaMailboxPolicy по умолчанию, но вы можете создавать настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-144">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="7ab3d-145">Настраиваемые политики применяются к пользователям с ограниченной областью действия перед политикой по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-145">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="7ab3d-146">Для получения дополнительных сведений о политиках почтовых ящиков Outlook в Интернете просмотрите [политики почтовых ящиков Outlook в Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span><span class="sxs-lookup"><span data-stu-id="7ab3d-146">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="7ab3d-147">Отключение отчетов о нежелательной почте не удаляет возможность пометить сообщение как нежелательное или не являющееся нежелательным в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-147">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="7ab3d-148">При выборе сообщения в папке "Нежелательная почта", если щелкнуть **не спам** , \> **Not junk** все равно перемещает сообщение обратно в папку "Входящие".</span><span class="sxs-lookup"><span data-stu-id="7ab3d-148">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="7ab3d-149">При выборе сообщения в любой другой папке электронной почты и **нажатии кнопки нежелательные** \> **Junk** сообщения все равно перемещаются в папку "Нежелательная почта".</span><span class="sxs-lookup"><span data-stu-id="7ab3d-149">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="7ab3d-150">Сведения о том, что больше недоступно — возможность отправки сообщения в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-150">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="7ab3d-151">Отключение и Включение отчетов о нежелательной почте в Outlook в Интернете с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ab3d-151">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="7ab3d-152">Чтобы найти существующие политики почтовых ящиков Outlook в Интернете и состояние отчетов о нежелательной почте, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7ab3d-152">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="7ab3d-153">Чтобы включить или отключить отчеты о нежелательной почте в Outlook в Интернете, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="7ab3d-153">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="7ab3d-154">В этом примере отключается создание отчетов о нежелательной почте в политике по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-154">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="7ab3d-155">В этом примере включается создание отчетов о нежелательной почте в пользовательской политике с именем Contoso Managers.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-155">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="7ab3d-156">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) и [Set/OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="7ab3d-156">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="7ab3d-157">Как проверить, все ли получилось?</span><span class="sxs-lookup"><span data-stu-id="7ab3d-157">How do you know this worked?</span></span>

<span data-ttu-id="7ab3d-158">Чтобы убедиться, что вы успешно включили или отключили отчеты о нежелательной почте в Outlook в Интернете, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-158">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="7ab3d-159">В Exchange Online PowerShell выполните следующую команду и проверьте значение свойства **репортжункемаиленаблед** :</span><span class="sxs-lookup"><span data-stu-id="7ab3d-159">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="7ab3d-160">Откройте почтовый ящик затронутого пользователя в Outlook в Интернете, выберите сообщение в папке "Входящие", **щелкните Нежелательная** \> **почта** и убедитесь, что сообщение не отображается в поле сообщить корпорации Майкрософт или не отображается.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ab3d-160">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="7ab3d-161">Откройте почтовый ящик затронутого пользователя в Outlook в Интернете, выберите сообщение в папке "Нежелательная почта" **, щелкните Нежелательная почта** \> **Junk** и убедитесь, что сообщение не отображается в поле сообщить корпорации Майкрософт.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ab3d-161">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="7ab3d-162"><sup>\*</sup>Пользователи могут скрыть приглашение, чтобы отправить отчет о сообщении, не отменяя сообщение.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-162"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="7ab3d-163">Чтобы проверить этот параметр в Outlook в Интернете, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-163">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="7ab3d-164">Щелкните **Параметры** ![ Outlook в значке веб-параметры, чтобы ](../../media/owa-settings-icon.png) \> **Просмотреть все** \> **нежелательные сообщения**в параметрах Outlook.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-164">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="7ab3d-165">В разделе **отчеты** проверьте значение: **спрашивать меня перед отправкой отчета**.</span><span class="sxs-lookup"><span data-stu-id="7ab3d-165">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Параметры отчетов о нежелательной почте в Интернете](../../media/owa-junk-email-reporting-options.png)
