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
ms.openlocfilehash: 0bd2da9b774b3557ebb820102ba86c17ebe44c69
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289225"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="87c6c-103">Отправка отчетов о нежелательной и фишинговой почте в Outlook в Интернете в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="87c6c-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="87c6c-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="87c6c-104">**Applies to**</span></span>
- [<span data-ttu-id="87c6c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="87c6c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="87c6c-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="87c6c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="87c6c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87c6c-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="87c6c-108">В организациях Microsoft 365 с почтовыми ящиками в Exchange Online вы можете использовать встроенные параметры отчетов в Outlook в Интернете (прежнее название — Outlook Web App) для отправки ложных срабатывающих сообщений (хорошей почты, помеченной как нежелательная почта), ложных отрицательных результатов (разрешено использование нежелательной почты) и фишинговых сообщений в Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="87c6c-108">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="87c6c-109">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="87c6c-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="87c6c-110">Если вы администратор организации с почтовыми ящиками Exchange Online, рекомендуем использовать портал отправки в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="87c6c-110">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="87c6c-111">Дополнительные сведения см. в документе "Отправка администратора" для отправки подозрительной нежелательной [почты, фишинга, URL-адресов и файлов в корпорацию Майкрософт.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="87c6c-111">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="87c6c-112">Администраторы могут отключить или включить для пользователей возможность сообщать о сообщениях в Корпорацию Майкрософт в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="87c6c-112">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="87c6c-113">Подробные сведения см. в разделе "Отключение или отключение [отчетов](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) о нежелательной почте" в Outlook в Интернете далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="87c6c-113">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="87c6c-114">Вы можете настроить копирование или перенаправление сообщений в задаемый почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="87c6c-114">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="87c6c-115">Дополнительные сведения [см. в политиках отправки пользователей.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="87c6c-115">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="87c6c-116">Дополнительные сведения об отчетах о сообщениях в корпорацию Майкрософт см. в отчете о [сообщениях и файлах корпорации Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="87c6c-116">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="87c6c-117">Сообщение о спаме и фишинговых сообщениях в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="87c6c-117">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="87c6c-118">Для сообщений в папке "Входящие" или любой другой папке электронной почты, кроме нежелательной почты, используйте один из следующих методов для отправки отчетов о спаме и фишинговых сообщениях:</span><span class="sxs-lookup"><span data-stu-id="87c6c-118">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="87c6c-119">Выберите сообщение, **щелкните** "Нежеланая почта" на панели инструментов, а затем **выберите** "Нежеланая почта" или **"Фишинг".**</span><span class="sxs-lookup"><span data-stu-id="87c6c-119">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Сообщение о нежелательной или фишинговой почте с ленты](../../media/owa-report-junk.png)

   - <span data-ttu-id="87c6c-121">Выберите одно или несколько сообщений, щелкните правой кнопкой мыши и выберите **"Пометить как нежелательное".**</span><span class="sxs-lookup"><span data-stu-id="87c6c-121">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="87c6c-122">В от появляются диалоговое окно нажмите кнопку **"Отчет"**.</span><span class="sxs-lookup"><span data-stu-id="87c6c-122">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="87c6c-123">Если вы передумаете, нажмите кнопку **"Не сообщать".**</span><span class="sxs-lookup"><span data-stu-id="87c6c-123">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="87c6c-124">Нежелательное</span><span class="sxs-lookup"><span data-stu-id="87c6c-124">Junk</span></span>|<span data-ttu-id="87c6c-125">Фишинговое</span><span class="sxs-lookup"><span data-stu-id="87c6c-125">Phishing</span></span>|
   |:---:|:---:|
   |![Диалоговое окно отчета о нежелательной почте](../../media/owa-report-as-junk-dialog.png)|![Диалоговое окно "Отчет о фишинге"](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="87c6c-128">Выбранные сообщения будут отправлены в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="87c6c-128">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="87c6c-129">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="87c6c-129">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="87c6c-130">Отправка отчетов о нежелательных и фишинговых сообщениях из папки нежелательной почты в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="87c6c-130">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="87c6c-131">В папке нежелательной почты используйте один из следующих методов для сообщения о ложных срабатываниях или фишинговых сообщениях:</span><span class="sxs-lookup"><span data-stu-id="87c6c-131">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="87c6c-132">Выберите сообщение, нажмите кнопку **"Не** является нежелательным" на панели инструментов, а затем выберите **"Не** является нежелательным" или **"Фишинг".**</span><span class="sxs-lookup"><span data-stu-id="87c6c-132">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Сообщение о том, что сообщение не является нежелательным или не является фишингом с ленты](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="87c6c-134">Выберите одно или несколько сообщений, щелкните правой кнопкой мыши и выберите **"Пометить как не является нежелательным".**</span><span class="sxs-lookup"><span data-stu-id="87c6c-134">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="87c6c-135">В от появляются диалоговое окно, прочитыв сведения и нажмите кнопку **"Отчет"**.</span><span class="sxs-lookup"><span data-stu-id="87c6c-135">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="87c6c-136">Если вы передумаете, нажмите кнопку **"Не сообщать".**</span><span class="sxs-lookup"><span data-stu-id="87c6c-136">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="87c6c-137">Не является нежелательным</span><span class="sxs-lookup"><span data-stu-id="87c6c-137">Not Junk</span></span>|<span data-ttu-id="87c6c-138">Фишинговое</span><span class="sxs-lookup"><span data-stu-id="87c6c-138">Phishing</span></span>|
   |:---:|:---:|
   |![Диалоговое окно "Отчет как не является нежелательным"](../../media/owa-report-as-not-junk-dialog.png)|![Диалоговое окно "Отчет о фишинге"](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="87c6c-141">Выбранные сообщения будут отправлены в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="87c6c-141">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="87c6c-142">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="87c6c-142">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="87c6c-143">Отключение или отключение отчетов о нежелательной почте в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="87c6c-143">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="87c6c-144">По умолчанию пользователи могут сообщать корпорации Майкрософт о ложных срабатываниях, ложных отрицательных результатах и фишинговых сообщениях для анализа в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="87c6c-144">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="87c6c-145">Администраторы могут настраивать политики почтовых ящиков Outlook в Интернете в Exchange Online PowerShell, чтобы запретить пользователям сообщать о ложных срабатываемых сообщениях и ложных отрицательных результатах нежелательной почты корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="87c6c-145">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="87c6c-146">Вы не можете отключить для пользователей возможность сообщать о фишинговых сообщениях в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="87c6c-146">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="87c6c-147">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="87c6c-147">What do you need to know before you begin?</span></span>

- <span data-ttu-id="87c6c-148">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="87c6c-148">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="87c6c-149">Для работы с процедурами, которые данной статьи, вам должны быть назначены разрешения в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="87c6c-149">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="87c6c-150">В частности, необходимы роли  **"Политики** получателей" или "Получатели почты", которые по умолчанию назначены группам ролей "Управление организацией" и "Управление получателями".  </span><span class="sxs-lookup"><span data-stu-id="87c6c-150">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="87c6c-151">Дополнительные сведения о группах ролей в Exchange Online см. в ["Разрешениях"](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) в Exchange Online и ["Изменение групп ролей" в Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="87c6c-151">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="87c6c-152">Каждая организация имеет политику по умолчанию с именем OwaMailboxPolicy-Default, но вы можете создавать настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="87c6c-152">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="87c6c-153">Настраиваемые политики применяются к пользователям с за областью действия до применения политики по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="87c6c-153">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="87c6c-154">Дополнительные сведения о политиках почтовых ящиков Outlook в Интернете см. в политиках почтовых ящиков Outlook в [Интернете в Exchange Online.](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)</span><span class="sxs-lookup"><span data-stu-id="87c6c-154">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="87c6c-155">Отключение отчетов о нежелательной почте не удаляет возможность пометки сообщения как нежелательного или не является нежелательным в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="87c6c-155">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="87c6c-156">При выборе сообщения в папке нежелательной  почты и нажатии кнопки "Не нежелательное сообщение не является нежелательным" сообщение по-прежнему перемещается обратно \>  в папку "Входящие".</span><span class="sxs-lookup"><span data-stu-id="87c6c-156">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="87c6c-157">Выбор сообщения в любой другой папке  электронной почты и нажатие кнопки "Нежелаая почта" перемещает сообщение в папку нежелательной \>  почты.</span><span class="sxs-lookup"><span data-stu-id="87c6c-157">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="87c6c-158">Больше недоступна возможность сообщить о сообщении в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="87c6c-158">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="87c6c-159">Отключение или отключение отчетов о нежелательной почте в Outlook в Интернете с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="87c6c-159">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="87c6c-160">Чтобы найти существующие политики почтовых ящиков Outlook в Интернете и состояние отчетов о нежелательной почте, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="87c6c-160">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="87c6c-161">Чтобы отключить или включить отчеты о нежелательной почте в Outlook в Интернете, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="87c6c-161">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="87c6c-162">В этом примере отключается отправка отчетов о нежелательной почте в политике по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="87c6c-162">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="87c6c-163">В этом примере включается отправка отчетов о нежелательной почте в настраиваемой политике с именем Contoso Managers.</span><span class="sxs-lookup"><span data-stu-id="87c6c-163">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="87c6c-164">Подробные сведения о синтаксисах и параметрах см. в описании [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) и [Set-OwaMailboxPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="87c6c-164">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="87c6c-165">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="87c6c-165">How do you know this worked?</span></span>

<span data-ttu-id="87c6c-166">Чтобы убедиться, что вы успешно включили или отключили отчеты о нежелательной почте в Outlook в Интернете, с помощью любого из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="87c6c-166">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="87c6c-167">В Exchange Online PowerShell запустите следующую команду и проверьте значение свойства **ReportJunkEmailEnabled:**</span><span class="sxs-lookup"><span data-stu-id="87c6c-167">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="87c6c-168">Откройте почтовый ящик затронутного пользователя в Outlook в Интернете, выберите  сообщение в почтовом ящике, щелкните "Нежелаемая почта" и убедитесь, что сообщение отправлено корпорации Майкрософт или не \>  отображается.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="87c6c-168">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="87c6c-169">Откройте почтовый ящик затронутного пользователя в Outlook в Интернете, выберите сообщение  в папке нежелательной почты, щелкните "Нежелаая почта" и убедитесь, что запрос на отправку сообщения корпорации Майкрософт отображается или не \>  отображается.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="87c6c-169">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="87c6c-170"><sup>\*</sup> Пользователи могут скрыть запрос на отчет о сообщении, при этом сообщая о сообщении.</span><span class="sxs-lookup"><span data-stu-id="87c6c-170"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="87c6c-171">Чтобы проверить этот параметр в Outlook в Интернете:</span><span class="sxs-lookup"><span data-stu-id="87c6c-171">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="87c6c-172">Click **Settings** ![ Outlook on the web settings icon View all Outlook ](../../media/owa-settings-icon.png) \> **settings** Junk \> **email**.</span><span class="sxs-lookup"><span data-stu-id="87c6c-172">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="87c6c-173">В разделе **"Отчеты"** проверьте значение: **спросите меня перед отправкой отчета.**</span><span class="sxs-lookup"><span data-stu-id="87c6c-173">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Параметры создания отчетов о нежелательной почте в Outlook в Интернете](../../media/owa-junk-email-reporting-options.png)
