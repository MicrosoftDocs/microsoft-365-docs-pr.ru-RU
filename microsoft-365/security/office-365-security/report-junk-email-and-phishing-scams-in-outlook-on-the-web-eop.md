---
title: Отправка отчетов о нежелательной и фишинговой почте в Outlook в Интернете
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
description: Администраторы могут узнать о встроенных параметрах отчетов о нежелательной почте, а не о нежелательной почте и фишинговых сообщениях в Outlook в Интернете (Outlook Web App) в Exchange Online, а также о том, как отключить эти параметры отчетности для пользователей.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0af57aceed608ae80e72e3ae18724925c1168e26
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029214"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="1670e-103">Сообщение о нежелательной и фишинговой почте в Outlook в Интернете в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1670e-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="1670e-104">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online вы можете использовать встроенные параметры отчетов в Outlook в Интернете (прежнее название — Outlook Web App) для отправки ложных срабатывающих сообщений (хорошей почты, помеченной как нежелательная почта), ложных отрицательных результатов (разрешено использование нежелательной почты) и фишинговых сообщений в Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="1670e-104">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1670e-105">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="1670e-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1670e-106">Если вы администратор организации с почтовыми ящиками Exchange Online, рекомендуем использовать портал отправки в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="1670e-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="1670e-107">Дополнительные сведения см. в документе "Отправка администратора" для отправки подозрительной нежелательной [почты, фишинга, URL-адресов и файлов в корпорацию Майкрософт.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="1670e-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="1670e-108">Администраторы могут отключить или включить для пользователей возможность сообщать о сообщениях в Корпорацию Майкрософт в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="1670e-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="1670e-109">Подробные сведения см. в разделе "Отключение или отключение отчетов о нежелательной почте" в [Outlook в](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) Интернете далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="1670e-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="1670e-110">Вы можете настроить копирование или перенаправление сообщений в задаемый почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="1670e-110">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="1670e-111">Дополнительные сведения [см. в политиках отправки пользователей.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="1670e-111">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="1670e-112">Дополнительные сведения об отчетах о сообщениях в корпорацию Майкрософт см. в отчете о [сообщениях и файлах корпорации Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="1670e-112">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="1670e-113">Сообщение о спаме и фишинговых сообщениях в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="1670e-113">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="1670e-114">Для сообщений в папке "Входящие" или любой другой папке электронной почты, кроме нежелательной почты, используйте один из следующих методов для отправки отчетов о спаме и фишинговых сообщениях:</span><span class="sxs-lookup"><span data-stu-id="1670e-114">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="1670e-115">Выберите сообщение, **щелкните** "Нежеланая почта" на панели инструментов, а затем **выберите** "Нежеланая почта" или **"Фишинг".**</span><span class="sxs-lookup"><span data-stu-id="1670e-115">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Сообщение о нежелательной или фишинговой почте с ленты](../../media/owa-report-junk.png)

   - <span data-ttu-id="1670e-117">Выберите одно или несколько сообщений, щелкните правой кнопкой мыши и выберите **"Пометить как нежелательное".**</span><span class="sxs-lookup"><span data-stu-id="1670e-117">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="1670e-118">В от появляются диалоговое окно нажмите кнопку **"Отчет"**.</span><span class="sxs-lookup"><span data-stu-id="1670e-118">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="1670e-119">Если вы передумаете, нажмите кнопку **"Не сообщать".**</span><span class="sxs-lookup"><span data-stu-id="1670e-119">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="1670e-120">Нежелательное</span><span class="sxs-lookup"><span data-stu-id="1670e-120">Junk</span></span>|<span data-ttu-id="1670e-121">Фишинговое</span><span class="sxs-lookup"><span data-stu-id="1670e-121">Phishing</span></span>|
   |:---:|:---:|
   |![Диалоговое окно отчета о нежелательной почте](../../media/owa-report-as-junk-dialog.png)|![Диалоговое окно "Отчет о фишинге"](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="1670e-124">Выбранные сообщения будут отправлены в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="1670e-124">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="1670e-125">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="1670e-125">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="1670e-126">Отправка отчетов о нежелательных и фишинговых сообщениях из папки нежелательной почты в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="1670e-126">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="1670e-127">В папке нежелательной почты используйте один из следующих методов для сообщения о ложных срабатываниях или фишинговых сообщениях:</span><span class="sxs-lookup"><span data-stu-id="1670e-127">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="1670e-128">Выберите сообщение, нажмите кнопку **"Не** является нежелательным" на панели инструментов, а затем выберите **"Не** является нежелательным" или **"Фишинг".**</span><span class="sxs-lookup"><span data-stu-id="1670e-128">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Сообщение о том, что сообщение не является нежелательным или не является фишингом с ленты](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="1670e-130">Выберите одно или несколько сообщений, щелкните правой кнопкой мыши и выберите **"Пометить как не является нежелательным".**</span><span class="sxs-lookup"><span data-stu-id="1670e-130">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="1670e-131">В от появляются диалоговое окно, прочитыв сведения и нажмите кнопку **"Отчет"**.</span><span class="sxs-lookup"><span data-stu-id="1670e-131">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="1670e-132">Если вы передумаете, нажмите кнопку **"Не сообщать".**</span><span class="sxs-lookup"><span data-stu-id="1670e-132">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="1670e-133">Не является нежелательным</span><span class="sxs-lookup"><span data-stu-id="1670e-133">Not Junk</span></span>|<span data-ttu-id="1670e-134">Фишинговое</span><span class="sxs-lookup"><span data-stu-id="1670e-134">Phishing</span></span>|
   |:---:|:---:|
   |![Диалоговое окно "Отчет как не является нежелательным"](../../media/owa-report-as-not-junk-dialog.png)|![Диалоговое окно "Отчет о фишинге"](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="1670e-137">Выбранные сообщения будут отправлены в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="1670e-137">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="1670e-138">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="1670e-138">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="1670e-139">Отключение или отключение отчетов о нежелательной почте в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="1670e-139">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="1670e-140">По умолчанию пользователи могут сообщать корпорации Майкрософт о ложных срабатываниях, ложных отрицательных результатах и фишинговых сообщениях для анализа в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="1670e-140">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="1670e-141">Администраторы могут настраивать политики почтовых ящиков Outlook в Интернете в Exchange Online PowerShell, чтобы запретить пользователям сообщать о ложных срабатываемых сообщениях и ложных отрицательных результатах нежелательной почты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1670e-141">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="1670e-142">Вы не можете отключить для пользователей возможность сообщать о фишинговых сообщениях в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1670e-142">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1670e-143">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="1670e-143">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1670e-144">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1670e-144">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="1670e-145">Для работы с процедурами, которые данной статьи, вам должны быть назначены разрешения в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1670e-145">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="1670e-146">В частности, необходимы роли  **"Политики** получателей" или "Получатели почты", которые по умолчанию назначены группам ролей "Управление организацией" и "Управление получателями".  </span><span class="sxs-lookup"><span data-stu-id="1670e-146">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="1670e-147">Дополнительные сведения о группах ролей в Exchange Online см. в ["Разрешениях"](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) в Exchange Online и ["Изменение групп ролей" в Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="1670e-147">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="1670e-148">Каждая организация имеет политику по умолчанию с именем OwaMailboxPolicy-Default, но вы можете создавать настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="1670e-148">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="1670e-149">Настраиваемые политики применяются к пользователям с областью действия до применения политики по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1670e-149">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="1670e-150">Дополнительные сведения о политиках почтовых ящиков Outlook в Интернете см. в политиках почтовых ящиков Outlook в [Интернете в Exchange Online.](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)</span><span class="sxs-lookup"><span data-stu-id="1670e-150">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="1670e-151">Отключение отчетов о нежелательной почте не удаляет возможность пометки сообщения как нежелательного или нежелательного в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="1670e-151">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="1670e-152">При выборе сообщения в папке нежелательной  почты и нажатии кнопки "Не нежелательное сообщение не является нежелательным" сообщение по-прежнему перемещается обратно \>  в папку "Входящие".</span><span class="sxs-lookup"><span data-stu-id="1670e-152">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="1670e-153">При выборе сообщения в любой другой папке электронной почты и нажатии кнопки "Нежелаая почта" сообщение перемещается в папку нежелательной  \>  почты.</span><span class="sxs-lookup"><span data-stu-id="1670e-153">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="1670e-154">Больше недоступна возможность сообщить о сообщении в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="1670e-154">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="1670e-155">Отключение или отключение отчетов о нежелательной почте в Outlook в Интернете с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="1670e-155">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="1670e-156">Чтобы найти существующие политики почтовых ящиков Outlook в Интернете и состояние отчетов о нежелательной почте, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1670e-156">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="1670e-157">Чтобы отключить или включить отчеты о нежелательной почте в Outlook в Интернете, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="1670e-157">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="1670e-158">В этом примере отключается отправка отчетов о нежелательной почте в политике по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1670e-158">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="1670e-159">В этом примере включается отправка отчетов о нежелательной почте в настраиваемой политике с именем Contoso Managers.</span><span class="sxs-lookup"><span data-stu-id="1670e-159">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="1670e-160">Подробные сведения о синтаксисах и параметрах см. в описании [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) и [Set-OwaMailboxPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="1670e-160">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="1670e-161">Как проверить, все ли получилось?</span><span class="sxs-lookup"><span data-stu-id="1670e-161">How do you know this worked?</span></span>

<span data-ttu-id="1670e-162">Чтобы убедиться, что вы успешно включили или отключили отчеты о нежелательной почте в Outlook в Интернете, с помощью любого из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="1670e-162">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="1670e-163">В Exchange Online PowerShell запустите следующую команду и проверьте значение свойства **ReportJunkEmailEnabled:**</span><span class="sxs-lookup"><span data-stu-id="1670e-163">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="1670e-164">Откройте почтовый ящик затронутного пользователя в Outlook в Интернете, выберите  сообщение в почтовом ящике, щелкните "Нежеланая почта" и убедитесь, что запрос на сообщение корпорации Майкрософт отображается или не \>  отображается.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1670e-164">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="1670e-165">Откройте почтовый ящик затронутного пользователя в Outlook в Интернете, выберите сообщение  в папке нежелательной почты, щелкните "Нежеланая почта" и убедитесь, что запрос на отправку сообщения корпорации Майкрософт отображается или не \>  отображается.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1670e-165">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="1670e-166"><sup>\*</sup> Пользователи могут скрыть запрос на отчет о сообщении, при этом сообщая о сообщении.</span><span class="sxs-lookup"><span data-stu-id="1670e-166"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="1670e-167">Чтобы проверить этот параметр в Outlook в Интернете:</span><span class="sxs-lookup"><span data-stu-id="1670e-167">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="1670e-168">Click **Settings** ![ Outlook on the web settings icon View all Outlook ](../../media/owa-settings-icon.png) \> **settings** Junk \> **email**.</span><span class="sxs-lookup"><span data-stu-id="1670e-168">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="1670e-169">В разделе **"Отчеты"** проверьте значение: **спросите меня перед отправкой отчета.**</span><span class="sxs-lookup"><span data-stu-id="1670e-169">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Параметры создания отчетов о нежелательной почте в Outlook в Интернете](../../media/owa-junk-email-reporting-options.png)
