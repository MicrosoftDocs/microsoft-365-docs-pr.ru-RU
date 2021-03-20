---
title: Сообщение нежелательной и фишинговой почты в Outlook в Интернете
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать о встроенных нежелательных, а не нежелательных и фишинговых вариантах сообщений электронной почты в Outlook в Интернете (Outlook Web App) в Exchange Online и о том, как отключить эти параметры отчетности для пользователей.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6caac60b32910ac06247bb89997ea6dbfc87d4f9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910634"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="311ac-103">Сообщение нежелательной и фишинговой почты в Outlook в Интернете в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="311ac-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="311ac-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="311ac-104">**Applies to**</span></span>
- [<span data-ttu-id="311ac-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="311ac-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="311ac-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="311ac-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="311ac-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="311ac-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="311ac-108">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online вы можете использовать встроенные параметры отчетности в Outlook в Интернете (ранее известный как Outlook Web App) для отправки ложных срабатывающих сообщений (хорошая электронная почта, помеченная как спам), ложных негативов (разрешенная плохая электронная почта) и фишинговых сообщений в Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="311ac-108">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="311ac-109">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="311ac-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="311ac-110">Если вы администратор в организации с почтовыми ящиками Exchange Online, рекомендуем использовать портал Отправки в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="311ac-110">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="311ac-111">Дополнительные сведения см. в материале Использование отправки администратора для отправки в Корпорацию Майкрософт подозрительных [спама, фишинга, URL-адресов и файлов.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="311ac-111">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="311ac-112">Администраторы могут отключить или включить возможность для пользователей сообщать о сообщениях в Microsoft в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="311ac-112">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="311ac-113">Подробные сведения см. в разделе Отключение или включить нежелательные сообщения электронной почты в [Outlook в веб-разделе](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) в этой статье.</span><span class="sxs-lookup"><span data-stu-id="311ac-113">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="311ac-114">Вы можете настроить сообщения, которые будут скопированы или перенаправлены в почтовый ящик, который указан.</span><span class="sxs-lookup"><span data-stu-id="311ac-114">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="311ac-115">Дополнительные сведения см. [в материале Политики отправки пользователей.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="311ac-115">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="311ac-116">Дополнительные сведения об отчетах о сообщениях в Корпорации Майкрософт см. в материалах [Report messages and files to Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="311ac-116">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="311ac-117">Сообщение о спаме и фишинговых сообщениях в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="311ac-117">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="311ac-118">Для сообщений в папке "Входящие" или любой другой папки электронной почты, за исключением нежелательной почты, используйте любой из следующих методов для сообщения о спаме и фишинге:</span><span class="sxs-lookup"><span data-stu-id="311ac-118">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="311ac-119">Выберите сообщение, **щелкните нежелательной на** панели инструментов, а затем выберите **нежелательной** или **фишинга**.</span><span class="sxs-lookup"><span data-stu-id="311ac-119">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Сообщение нежелательной или фишинговой электронной почты с ленты](../../media/owa-report-junk.png)

   - <span data-ttu-id="311ac-121">Выберите одно или несколько сообщений правой кнопкой мыши, а затем **выберите Mark в качестве нежелательной**.</span><span class="sxs-lookup"><span data-stu-id="311ac-121">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="311ac-122">В диалоговом октаге, который отображается, щелкните **Отчет**.</span><span class="sxs-lookup"><span data-stu-id="311ac-122">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="311ac-123">Если вы передумали, **нажмите кнопку Не сообщайте**.</span><span class="sxs-lookup"><span data-stu-id="311ac-123">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="311ac-124">Нежелательное</span><span class="sxs-lookup"><span data-stu-id="311ac-124">Junk</span></span>|<span data-ttu-id="311ac-125">Фишинговое</span><span class="sxs-lookup"><span data-stu-id="311ac-125">Phishing</span></span>|
   |:---:|:---:|
   |![Отчет как диалоговое окно нежелательной почты](../../media/owa-report-as-junk-dialog.png)|![Отчет как диалоговое окно фишинга](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="311ac-128">Выбранные сообщения будут отправлены в Корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="311ac-128">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="311ac-129">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="311ac-129">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="311ac-130">Сообщение о нежелательных и фишинговых сообщениях из папки нежелательной почты в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="311ac-130">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="311ac-131">В папке нежелательной почты используйте любой из следующих методов для сообщения о ложных срабатываниях нежелательной почты или фишинговых сообщениях:</span><span class="sxs-lookup"><span data-stu-id="311ac-131">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="311ac-132">Выберите сообщение, щелкните **Not Junk** на панели инструментов, а затем выберите **Not Junk** или **Phishing**.</span><span class="sxs-lookup"><span data-stu-id="311ac-132">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Сообщение не нежелательной или не фишинговой электронной почты с ленты](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="311ac-134">Выберите одно или несколько сообщений правой кнопкой мыши, а затем **выберите Mark как не нежелательное.**</span><span class="sxs-lookup"><span data-stu-id="311ac-134">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="311ac-135">В диалоговом окте, который появится, прочитайте сведения и нажмите **кнопку Отчет**.</span><span class="sxs-lookup"><span data-stu-id="311ac-135">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="311ac-136">Если вы передумали, **нажмите кнопку Не сообщайте**.</span><span class="sxs-lookup"><span data-stu-id="311ac-136">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="311ac-137">Не является нежелательным</span><span class="sxs-lookup"><span data-stu-id="311ac-137">Not Junk</span></span>|<span data-ttu-id="311ac-138">Фишинговое</span><span class="sxs-lookup"><span data-stu-id="311ac-138">Phishing</span></span>|
   |:---:|:---:|
   |![Отчет как не нежелательное диалоговое окно](../../media/owa-report-as-not-junk-dialog.png)|![Отчет как диалоговое окно фишинга](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="311ac-141">Выбранные сообщения будут отправлены в Корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="311ac-141">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="311ac-142">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="311ac-142">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="311ac-143">Отключить или включить нежелательные сообщения электронной почты в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="311ac-143">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="311ac-144">По умолчанию пользователи могут сообщать о ложных срабатываниях нежелательной почты, ложных негативах и фишинговых сообщениях в Microsoft для анализа в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="311ac-144">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="311ac-145">Администраторы могут настраивать Outlook для политик веб-почтовых ящиков в Exchange Online PowerShell, чтобы пользователи не сообщали о ложных срабатываваемых спама и нежелательных ложных негативах в Microsoft.</span><span class="sxs-lookup"><span data-stu-id="311ac-145">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="311ac-146">Нельзя отключить возможность для пользователей сообщать о фишинговых сообщениях в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="311ac-146">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="311ac-147">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="311ac-147">What do you need to know before you begin?</span></span>

- <span data-ttu-id="311ac-148">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="311ac-148">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="311ac-149">Вам необходимо получить разрешения в Exchange Online, прежде чем вы сможете сделать процедуры в этой статье.</span><span class="sxs-lookup"><span data-stu-id="311ac-149">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="311ac-150">В частности, вам нужны  роли **политики** получателей или получателей  почты, которые по умолчанию назначены группам ролей управления и управления получателями организации. </span><span class="sxs-lookup"><span data-stu-id="311ac-150">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="311ac-151">Дополнительные сведения о группах ролей в Exchange Online см. в рублях [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) и [Modify role groups in Exchange Online.](/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="311ac-151">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="311ac-152">Каждая организация имеет политику по умолчанию с именем OwaMailboxPolicy-Default, но можно создавать настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="311ac-152">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="311ac-153">Пользовательские политики применяются к пользователям с масштабами перед политикой по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="311ac-153">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="311ac-154">Дополнительные сведения о политиках Outlook для веб-почтовых ящиков см. в странице Outlook в политиках веб-почтовых [ящиков в Exchange Online.](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)</span><span class="sxs-lookup"><span data-stu-id="311ac-154">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="311ac-155">Отключение нежелательной отчетности по электронной почте не удаляет возможность пометить сообщение как нежелательное или нежелательное в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="311ac-155">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="311ac-156">Выбор сообщения в папке нежелательной почты и нажатие кнопки **Не** нежелательной не нежелательной по-прежнему перемещает сообщение обратно \>  в папку "Входящие".</span><span class="sxs-lookup"><span data-stu-id="311ac-156">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="311ac-157">Выбор сообщения в любой другой папке  электронной почты и нажатие нежелательной нежелательной почты по-прежнему перемещает сообщение \>  в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="311ac-157">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="311ac-158">Больше нет возможности сообщить об этом сообщении в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="311ac-158">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="311ac-159">Использование Exchange Online PowerShell для отключения или отключения нежелательной отчетности по электронной почте в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="311ac-159">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="311ac-160">Чтобы найти существующий Outlook в политиках веб-почтовых ящиков и состоянии нежелательной отчетности по электронной почте, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="311ac-160">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="311ac-161">Чтобы отключить или включить нежелательные сообщения электронной почты в Outlook в Интернете, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="311ac-161">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="311ac-162">В этом примере отключает нежелательные сообщения электронной почты в политике по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="311ac-162">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="311ac-163">В этом примере включается нежелательное сообщение электронной почты в настраиваемой политике под названием Contoso Managers.</span><span class="sxs-lookup"><span data-stu-id="311ac-163">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="311ac-164">Подробные сведения о синтаксисах и параметрах см. в [сведениях Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) и [Set-OwaMailboxPolicy.](/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="311ac-164">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="311ac-165">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="311ac-165">How do you know this worked?</span></span>

<span data-ttu-id="311ac-166">Чтобы убедиться, что вы успешно включили или отключили нежелательные сообщения электронной почты в Outlook в Интернете, используйте следующие действия:</span><span class="sxs-lookup"><span data-stu-id="311ac-166">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="311ac-167">В Exchange Online PowerShell запустите следующую команду и проверьте значение **свойства ReportJunkEmailEnabled:**</span><span class="sxs-lookup"><span data-stu-id="311ac-167">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="311ac-168">Откройте почтовый ящик пострадавшего пользователя в Outlook в Интернете, выберите  сообщение в почтовом ящике, нажмите нежелательной почты и убедитесь, что сообщение в Корпорацию Майкрософт отображается или не \>  отображается.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="311ac-168">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="311ac-169">Откройте почтовый ящик пострадавшего пользователя в Outlook в Интернете, выберите сообщение  в папке нежелательной почты, щелкните нежелательной почты и убедитесь, что запрос на сообщение в Корпорацию Майкрософт отображается или не \>  отображается.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="311ac-169">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="311ac-170"><sup>\*</sup> Пользователи могут скрыть запрос, чтобы сообщить о сообщении, но при этом сообщить о сообщении.</span><span class="sxs-lookup"><span data-stu-id="311ac-170"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="311ac-171">Чтобы проверить этот параметр в Outlook в Интернете:</span><span class="sxs-lookup"><span data-stu-id="311ac-171">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="311ac-172">Щелкните **Параметры** ![ Outlook на значке веб-параметров Просмотр всех ](../../media/owa-settings-icon.png) \> **параметров Outlook** \> **нежелательной почты**.</span><span class="sxs-lookup"><span data-stu-id="311ac-172">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="311ac-173">В разделе **Отчеты** проверьте значение: **Спросите меня перед отправкой отчета**.</span><span class="sxs-lookup"><span data-stu-id="311ac-173">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Outlook для параметров отчетов о нежелательной почте в Интернете](../../media/owa-junk-email-reporting-options.png)