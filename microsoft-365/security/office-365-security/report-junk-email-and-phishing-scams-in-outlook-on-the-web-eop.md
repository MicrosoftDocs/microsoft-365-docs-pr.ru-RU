---
title: Отправка нежелательных и фишинговых сообщений электронной почты в Outlook в Интернете
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Администраторы могут изучить встроенные параметры отчетов о нежелательной почте, нежелательной почте и фишинге в Outlook в Интернете (Outlook Web App) в Exchange Online, а также как отключить эти параметры отчетов для пользователей.
ms.openlocfilehash: 75be22d6ec38ca3c8d11836ea28c7af74b93f14c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201247"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="cc8b0-103">Отправка нежелательных и фишинговых сообщений электронной почты в Outlook в Интернете в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cc8b0-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="cc8b0-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online вы можете использовать встроенные параметры отчетов в Outlook в Интернете (прежнее название — Outlook Web App) для отправки ложных срабатываний (хороший адрес электронной почты отмечен как спам), ложные отрицательные (недопустимые сообщения электронной почты) и фишинговых сообщений в Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="cc8b0-104">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cc8b0-105">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="cc8b0-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cc8b0-106">Если вы являетесь администратором в Организации с почтовыми ящиками Exchange Online, рекомендуем использовать портал отправки в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="cc8b0-107">Дополнительные сведения см. в [статье Использование отправки администратором для отправки подозреваемой спама, фишинга, URL-адресов и файлов в корпорацию Майкрософт](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="cc8b0-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="cc8b0-108">Администраторы могут отключить или разрешить пользователям сообщать о сообщениях в корпорацию Майкрософт в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="cc8b0-109">Дополнительные сведения см. в разделе [Отключение или Включение отчетов о нежелательной почте в Outlook в Интернете](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="cc8b0-110">Можно настроить копирование или перенаправление сообщений, отправленных в указанный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-110">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="cc8b0-111">Дополнительные сведения см. [в статье определение почтового ящика для отправленных пользователем сообщений о нежелательной почте и фишинговых сообщениях в Exchange Online](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="cc8b0-111">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="cc8b0-112">Дополнительные сведения о сообщениях отчетов в корпорацию Майкрософт можно найти [в статье сообщения и файлы отчетов в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="cc8b0-112">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="cc8b0-113">Составление отчетов о нежелательной почте и фишинговых сообщениях в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="cc8b0-113">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="cc8b0-114">Для сообщений в папке "Входящие" или любой другой папке, кроме нежелательной почты, используйте один из следующих способов для создания отчетов о нежелательной почте и фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-114">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="cc8b0-115">Выберите сообщение, нажмите кнопку **Нежелательная почта** на панели инструментов, а затем выберите **нежелательные** или **Фишинг**.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-115">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Отправка нежелательных или фишинговых сообщений электронной почты с ленты](../../media/owa-report-junk.png)

   - <span data-ttu-id="cc8b0-117">Выберите одно или несколько сообщений, щелкните правой кнопкой мыши и выберите **Пометить как нежелательное**.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-117">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="cc8b0-118">В появившемся диалоговом окне нажмите **отчет**.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-118">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="cc8b0-119">Если вы передумали, щелкните **не сообщать**.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-119">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="cc8b0-120">Нежелательное</span><span class="sxs-lookup"><span data-stu-id="cc8b0-120">Junk</span></span>|<span data-ttu-id="cc8b0-121">Фишинговое</span><span class="sxs-lookup"><span data-stu-id="cc8b0-121">Phishing</span></span>|
   |:---:|:---:|
   |![Диалоговое окно отчета о нежелательной почте](../../media/owa-report-as-junk-dialog.png)|![Диалоговое окно отчета в качестве фишинга](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="cc8b0-124">Выбранные сообщения будут отправлены в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-124">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="cc8b0-125">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-125">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="cc8b0-126">Отправка сообщений о сообщениях о нежелательной почте и фишинге из папки "Нежелательная почта" в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="cc8b0-126">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="cc8b0-127">В папке нежелательной почты используйте один из следующих способов, чтобы сообщить о ложных срабатываниях или фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-127">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="cc8b0-128">Выберите сообщение, щелкните **не спам** на панели инструментов, а затем выберите **не спам** или **Фишинг**.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-128">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Отправка нежелательных или фишинговых сообщений электронной почты с ленты](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="cc8b0-130">Выберите одно или несколько сообщений, щелкните правой кнопкой мыши и выберите пункт **Пометить как не являющееся нежелательным**.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-130">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="cc8b0-131">В появившемся диалоговом окне прочитайте сведения и щелкните **отчет**.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-131">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="cc8b0-132">Если вы передумали, щелкните **не сообщать**.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-132">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="cc8b0-133">Не является нежелательным</span><span class="sxs-lookup"><span data-stu-id="cc8b0-133">Not Junk</span></span>|<span data-ttu-id="cc8b0-134">Фишинговое</span><span class="sxs-lookup"><span data-stu-id="cc8b0-134">Phishing</span></span>|
   |:---:|:---:|
   |![Диалоговое окно "сообщить как нежелательное"](../../media/owa-report-as-not-junk-dialog.png)|![Диалоговое окно отчета в качестве фишинга](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="cc8b0-137">Выбранные сообщения будут отправлены в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-137">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="cc8b0-138">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-138">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="cc8b0-139">Отключение и Включение отчетов о нежелательной почте в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="cc8b0-139">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="cc8b0-140">По умолчанию пользователи могут сообщать о ложных срабатываниях нежелательной почты, ложных негативных и фишинговых сообщениях в корпорацию Майкрософт для анализа в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-140">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="cc8b0-141">Администраторы могут настроить Outlook в политиках веб-почтовых ящиков в Exchange Online PowerShell, чтобы запретить пользователям сообщать о ложных срабатываниях и нежелательных сообщениях в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-141">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="cc8b0-142">Невозможно отключить возможность пользователей сообщать о phishing-сообщениях в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-142">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cc8b0-143">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="cc8b0-143">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cc8b0-144">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="cc8b0-144">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="cc8b0-145">Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-145">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="cc8b0-146">В частности, потребуются роли **получателей** или роли **получателей почты** в Exchange Online, которые назначаются группам ролей " **Управление организацией** " и " **Управление получателями** " по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-146">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="cc8b0-147">Дополнительные сведения о группах ролей в Exchange Online можно узнать в статье [изменение групп ролей в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span><span class="sxs-lookup"><span data-stu-id="cc8b0-147">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="cc8b0-148">Каждая организация имеет политику по умолчанию с именем OwaMailboxPolicy по умолчанию, но вы можете создавать настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-148">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="cc8b0-149">Настраиваемые политики применяются к пользователям с ограниченной областью действия перед политикой по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-149">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="cc8b0-150">Для получения дополнительных сведений о политиках почтовых ящиков Outlook в Интернете просмотрите [политики почтовых ящиков Outlook в Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span><span class="sxs-lookup"><span data-stu-id="cc8b0-150">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="cc8b0-151">Отключение отчетов о нежелательной почте не удаляет возможность пометить сообщение как нежелательное или не являющееся нежелательным в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-151">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="cc8b0-152">При выборе сообщения в папке "Нежелательная почта", если щелкнуть **не спам** , \> **Not junk** все равно перемещает сообщение обратно в папку "Входящие".</span><span class="sxs-lookup"><span data-stu-id="cc8b0-152">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="cc8b0-153">При выборе сообщения в любой другой папке электронной почты и **нажатии кнопки нежелательные** \> **Junk** сообщения все равно перемещаются в папку "Нежелательная почта".</span><span class="sxs-lookup"><span data-stu-id="cc8b0-153">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="cc8b0-154">Сведения о том, что больше недоступно — возможность отправки сообщения в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-154">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="cc8b0-155">Отключение и Включение отчетов о нежелательной почте в Outlook в Интернете с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc8b0-155">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="cc8b0-156">Чтобы найти существующие политики почтовых ящиков Outlook в Интернете и состояние отчетов о нежелательной почте, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="cc8b0-156">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="cc8b0-157">Чтобы включить или отключить отчеты о нежелательной почте в Outlook в Интернете, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="cc8b0-157">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="cc8b0-158">В этом примере отключается создание отчетов о нежелательной почте в политике по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-158">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="cc8b0-159">В этом примере включается создание отчетов о нежелательной почте в пользовательской политике с именем Contoso Managers.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-159">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="cc8b0-160">Подробные сведения о синтаксисе и параметрах можно найти в статье [Get – OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) и [Set/OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="cc8b0-160">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="cc8b0-161">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="cc8b0-161">How do you know this worked?</span></span>

<span data-ttu-id="cc8b0-162">Чтобы убедиться, что вы успешно включили или отключили отчеты о нежелательной почте в Outlook в Интернете, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-162">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="cc8b0-163">В Exchange Online PowerShell выполните следующую команду и проверьте значение свойства **репортжункемаиленаблед** :</span><span class="sxs-lookup"><span data-stu-id="cc8b0-163">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="cc8b0-164">Откройте почтовый ящик затронутого пользователя в Outlook в Интернете, выберите сообщение в папке "Входящие", **щелкните Нежелательная** \> **почта** и убедитесь, что сообщение не отображается в поле сообщить корпорации Майкрософт или не отображается.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc8b0-164">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="cc8b0-165">Откройте почтовый ящик затронутого пользователя в Outlook в Интернете, выберите сообщение в папке "Нежелательная почта" **, щелкните Нежелательная почта** \> **Junk** и убедитесь, что сообщение не отображается в поле сообщить корпорации Майкрософт.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc8b0-165">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="cc8b0-166"><sup>\*</sup> Пользователи могут скрыть приглашение, чтобы отправить отчет о сообщении, не отменяя сообщение.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-166"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="cc8b0-167">Чтобы проверить этот параметр в Outlook в Интернете, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-167">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="cc8b0-168">Щелкните **Параметры** ![ Outlook в значке веб-параметры, чтобы ](../../media/owa-settings-icon.png) \> **Просмотреть все** \> **нежелательные сообщения**в параметрах Outlook.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-168">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="cc8b0-169">В разделе **отчеты** проверьте значение: **спрашивать меня перед отправкой отчета**.</span><span class="sxs-lookup"><span data-stu-id="cc8b0-169">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Параметры отчетов о нежелательной почте в Интернете](../../media/owa-junk-email-reporting-options.png)
