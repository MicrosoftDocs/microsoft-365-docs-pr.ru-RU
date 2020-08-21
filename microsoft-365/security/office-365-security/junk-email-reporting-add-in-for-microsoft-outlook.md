---
title: Установка и использование надстройки создания отчетов о нежелательной почте для Microsoft Outlook
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
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Узнайте, как установить и использовать надстройку сообщения о нежелательной почте для отправки отчетов о спаме, нежелательных и фишинговых сообщениях в корпорацию Майкрософт.
ms.openlocfilehash: 42b38830b55ae3dbee4ec74a0e96531d920c24a5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827103"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="7ff40-103">Установка и использование надстройки создания отчетов о нежелательной почте для Microsoft Outlook</span><span class="sxs-lookup"><span data-stu-id="7ff40-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

> [!NOTE]
> <span data-ttu-id="7ff40-104">Если вы не используете эту надстройку, рекомендуем использовать [надстройку Report Message.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="7ff40-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) instead.</span></span> <span data-ttu-id="7ff40-105">Для получения дополнительной информации см. [Отчет о сообщениях и файлах в Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="7ff40-105">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="7ff40-106">Надстройка сообщения о нежелательной почте для Microsoft Outlook позволяет пользователям отправлять ложные срабатывания (в качестве нежелательной почты), ложные отрицательные результаты (не допустимые письма) и фишинговые сообщения в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7ff40-106">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="7ff40-107">Если ваша организация не использует Exchange Online Protection (например, локальная организация Exchange или другие службы электронной почты, кроме Exchange Online), отправка отчетов о нежелательной почте не повлияет на фильтрацию нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="7ff40-107">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="7ff40-108">В этой статье описывается установка и использование надстройки создания отчетов о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="7ff40-108">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7ff40-109">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="7ff40-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7ff40-110">Сведения о том, как установить надстройку создания отчетов о нежелательной почте, [см.](#install-the-junk-email-reporting-add-in) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="7ff40-110">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this topic.</span></span>

- <span data-ttu-id="7ff40-111">Надстройка создания отчетов о нежелательной почте работает со следующими версиями Outlook:</span><span class="sxs-lookup"><span data-stu-id="7ff40-111">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="7ff40-112">Outlook 2013 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="7ff40-112">Outlook 2013 or later</span></span>
  - <span data-ttu-id="7ff40-113">Outlook входит в состав приложений Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="7ff40-113">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="7ff40-114">Дополнительные сведения об отчетах в корпорацию Майкрософт см. в статье [Отчето о сообщениях и файлах в корпорацию Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="7ff40-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="7ff40-115">Использование надстройки создания отчетов о нежелательной почте для отправки отчетов о спаме и фишинговых сообщениях</span><span class="sxs-lookup"><span data-stu-id="7ff40-115">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="7ff40-116">Для сообщений из папки "Входящие" или другой папки сообщений, кроме "Нежелательная почта", отправляйте сообщения о спаме и фишинге с помощью любого из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="7ff40-116">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="7ff40-117">Выберите сообщение или откройте его.</span><span class="sxs-lookup"><span data-stu-id="7ff40-117">Select the message or open the message.</span></span> <span data-ttu-id="7ff40-118">На **вкладке "Главная"** **или "Сообщение"** ленты щелкните **"Нежелательная**почта" и выберите пункт **"Отчет о нежелательной** почте" или **"Отчет о фишинге".**</span><span class="sxs-lookup"><span data-stu-id="7ff40-118">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Сообщайте о нежелательной почте или фишинговых сообщениях с ленты](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="7ff40-120">Щелкните сообщение правой кнопкой мыши, выберите пункт **"Нежелательная**почта" и затем "Отчет о **нежелательной** почте" или **"Отчет о фишинге".**</span><span class="sxs-lookup"><span data-stu-id="7ff40-120">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Отправка отчетов о нежелательной почте или фишинге](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="7ff40-122">Выберите несколько сообщений, щелчок правой кнопкой мыши и затем выберите пункт **"Отчет о нежелательной** **почте или отчете как фишинг".**</span><span class="sxs-lookup"><span data-stu-id="7ff40-122">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Сообщение о нескольких нежелательных сообщениях или фишинговых сообщениях одним щелчком правой кнопкой мыши](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="7ff40-124">В отобразившемся диалоговом окне прочитайте сведения и щелкните **"Отчет".**</span><span class="sxs-lookup"><span data-stu-id="7ff40-124">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="7ff40-125">Если вы передумали, нажмите **"Не давать отчет".**</span><span class="sxs-lookup"><span data-stu-id="7ff40-125">If you change your mind, click **Don't Report**.</span></span>

   ![Диалоговое окно отчета о нежелательной почте](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Сообщение в качестве диалогового окна фишинга](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="7ff40-128">Выбранные сообщения будут отправлены в корпорацию Майкрософт для анализа и:</span><span class="sxs-lookup"><span data-stu-id="7ff40-128">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="7ff40-129">Перемещено в папку нежелательной почты, если она служит для сообщения о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="7ff40-129">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="7ff40-130">Удален, если сообщение поступило как фишинговое.</span><span class="sxs-lookup"><span data-stu-id="7ff40-130">Deleted if it was reported as phishing.</span></span>
   
   <span data-ttu-id="7ff40-131">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="7ff40-131">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="7ff40-132">Использование надстройки создания отчетов о нежелательной почте для сообщения о сообщениях, которые не является нежелательными и мошенническими, из папки "Нежелательная почта"</span><span class="sxs-lookup"><span data-stu-id="7ff40-132">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="7ff40-133">В папке "Нежелательная почта" отправьте сведения о ложных срабатываниях или фишинговых сообщениях в папке "Нежелательная почта" любым из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="7ff40-133">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="7ff40-134">Выберите сообщение или откройте его.</span><span class="sxs-lookup"><span data-stu-id="7ff40-134">Select the message or open the message.</span></span> <span data-ttu-id="7ff40-135">На **вкладке "Главная"** **или "Сообщение"** ленты щелкните **"Не является нежелательным",** а затем выберите "Отчет о **том, что сообщение не** является нежелательным" **или "Отчет о фишинге".**</span><span class="sxs-lookup"><span data-stu-id="7ff40-135">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Сообщает о том, что сообщение не является нежелательным или фишинговым, на ленте в папке "Нежелательная почта"](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="7ff40-137">Щелкните сообщение правой кнопкой мыши, нажмите **"Нежелательная**почта", а затем выберите **пункт "Отчет о том, что сообщение не** является нежелательным или **отчетом как о фишинге".**</span><span class="sxs-lookup"><span data-stu-id="7ff40-137">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Сообщить о том, что сообщение не является нежелательным или фишинговым, щелкнув правой кнопкой мыши в папке "Нежелательная почта"](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="7ff40-139">Выберите несколько сообщений, щелчок правой кнопкой мыши и выберите пункт **"Отчет о не нежелательной** **почте" или "Отчет о фишинге".**</span><span class="sxs-lookup"><span data-stu-id="7ff40-139">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Сообщение, которое не является нежелательным или мошенничим, щелчком правой кнопкой мыши в папке "Нежелательная почта"](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="7ff40-141">В отобразившемся диалоговом окне прочитайте сведения и щелкните **"Отчет".**</span><span class="sxs-lookup"><span data-stu-id="7ff40-141">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="7ff40-142">Если вы передумали, нажмите **"Не давать отчет".**</span><span class="sxs-lookup"><span data-stu-id="7ff40-142">If you change your mind, click **Don't Report**.</span></span>

   ![Диалоговое окно отчетов о не нежелательной почте](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Сообщение в качестве диалогового окна фишинга](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="7ff40-145">Выбранные сообщения будут отправлены в корпорацию Майкрософт для анализа и:</span><span class="sxs-lookup"><span data-stu-id="7ff40-145">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="7ff40-146">Перемещено в папку нежелательной почты, если она служит для сообщения о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="7ff40-146">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="7ff40-147">Удален, если сообщение поступило как фишинговое.</span><span class="sxs-lookup"><span data-stu-id="7ff40-147">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="7ff40-148">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="7ff40-148">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="7ff40-149">Установка надстройки создания отчетов о нежелательной почте</span><span class="sxs-lookup"><span data-stu-id="7ff40-149">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="7ff40-150">Необходимы права администратора на компьютере, на котором устанавливается надстройка.</span><span class="sxs-lookup"><span data-stu-id="7ff40-150">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="7ff40-151">Перейдите <https://www.microsoft.com/download/details.aspx?id=18275> к соответствующему MSI-файлу своей версии Office и скачайте его в удобное расположение:</span><span class="sxs-lookup"><span data-stu-id="7ff40-151">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="7ff40-152">**32-разрядная**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="7ff40-152">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="7ff40-153">**64-разрядный**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="7ff40-153">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="7ff40-154">Для Outlook 2013 или более поздних версий единственным необходимым условием является Microsoft .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="7ff40-154">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="7ff40-155">В Windows 10 не устанавливается платформа .NET Framework 2.0 при загрузке.</span><span class="sxs-lookup"><span data-stu-id="7ff40-155">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="7ff40-156">Установка надстройки создания отчетов о нежелательной почте с помощью мастера установки</span><span class="sxs-lookup"><span data-stu-id="7ff40-156">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="7ff40-157">Закройте Outlook на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7ff40-157">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="7ff40-158">В Windows 10 убедитесь, что платформа .NET Framework 2.0 включена.</span><span class="sxs-lookup"><span data-stu-id="7ff40-158">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="7ff40-159">Инструкции см. в [разделе "Включение .NET Framework 3.5 в панели управления".](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)</span><span class="sxs-lookup"><span data-stu-id="7ff40-159">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="7ff40-160">Найдите скачанный MSI-файл и дважды щелкните его.</span><span class="sxs-lookup"><span data-stu-id="7ff40-160">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="7ff40-161">На странице **Добро пожаловать в мастер установки надстройки создания отчетов о нежелательной почте** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7ff40-161">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="7ff40-162">Ознакомьтесь с условиями лицензионного соглашения, нажмите кнопку **"Принимаю** условия лицензионного соглашения", если вы согласны с условиями, а затем нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="7ff40-162">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="7ff40-163">После завершения мастера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="7ff40-163">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="7ff40-164">Запустите приложение Outlook.</span><span class="sxs-lookup"><span data-stu-id="7ff40-164">Start Outlook.</span></span>

<span data-ttu-id="7ff40-p109">Найдите кнопку **Нежелательная почта** в ленте Outlook. С ее помощью можно сообщить корпорации Майкрософт о нежелательных сообщениях электронной почты. Выберите эти письма в папке "Входящие" и нажмите кнопку **Сообщить о нежелательной почте**.</span><span class="sxs-lookup"><span data-stu-id="7ff40-p109">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="7ff40-p110">Нажмите стрелку вниз рядом с кнопкой **Нежелательная почта**, чтобы открыть дополнительные параметры, например **Фишинговое сообщение**, если вы хотите сообщить корпорации Майкрософт о фишинговых сообщениях. В папке нежелательной почты можно также выбрать параметр **Не является нежелательным**, если сообщение ошибочно помечено как нежелательное.</span><span class="sxs-lookup"><span data-stu-id="7ff40-p110">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="7ff40-169">Установка надстройки создания отчетов о нежелательной почте в автоматическом режиме</span><span class="sxs-lookup"><span data-stu-id="7ff40-169">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="7ff40-170">Закройте Outlook на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7ff40-170">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="7ff40-171">В Windows 10 установите .NET Framework 2.0, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7ff40-171">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="7ff40-172">Чтобы установить надстройку без взаимодействия с пользователем, откройте командную строку и используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="7ff40-172">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="7ff40-173">`MaxMessageSelection` определяет максимальное число сообщений, которое можно выбрать при одной отправке.</span><span class="sxs-lookup"><span data-stu-id="7ff40-173">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="7ff40-174">Допустимые значения: от 1 до 50.</span><span class="sxs-lookup"><span data-stu-id="7ff40-174">Valid values are from 1 to 50.</span></span> <span data-ttu-id="7ff40-175">Значение по умолчанию — 15.</span><span class="sxs-lookup"><span data-stu-id="7ff40-175">The default value is 15.</span></span>

   - <span data-ttu-id="7ff40-176">`BccEmailAddress` указывает дополнительных получателей", которые будут получать копии всех отправленных пользователем.</span><span class="sxs-lookup"><span data-stu-id="7ff40-176">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="7ff40-177">Значение по умолчанию остается пустым (дополнительных получателей сК отсутствуют).</span><span class="sxs-lookup"><span data-stu-id="7ff40-177">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="7ff40-178">В этом примере устанавливается 64-разрядная версия надстройки с указанного пути с параметрами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7ff40-178">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="7ff40-179">В этом примере устанавливается 32-разрядная версия надстройки с указанного пути с указанными ниже дополнительными параметрами.</span><span class="sxs-lookup"><span data-stu-id="7ff40-179">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="7ff40-180">В одной отправке можно выбрать до 20 сообщений.</span><span class="sxs-lookup"><span data-stu-id="7ff40-180">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="7ff40-181">junkreports@contoso.com и hollyd@treyresearch.net спецификации будут получать копии всех отправок.</span><span class="sxs-lookup"><span data-stu-id="7ff40-181">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="7ff40-182">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="7ff40-182">How do you know this worked?</span></span>

<span data-ttu-id="7ff40-183">Чтобы убедиться, что надстройка создания отчетов о нежелательной почте успешно установлена, выполните одно из указанных ниже действий в Outlook.</span><span class="sxs-lookup"><span data-stu-id="7ff40-183">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="7ff40-184">Выберите сообщение или откройте его.</span><span class="sxs-lookup"><span data-stu-id="7ff40-184">Select the message or open the message.</span></span> <span data-ttu-id="7ff40-185">На **вкладке** **"Главная"** или "Сообщение" ленты щелкните **"Нежелательное"** и убедитесь в наличии следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="7ff40-185">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="7ff40-186">**Report as Junk**</span><span class="sxs-lookup"><span data-stu-id="7ff40-186">**Report as Junk**</span></span>
  - <span data-ttu-id="7ff40-187">**Отчет о фишинге**</span><span class="sxs-lookup"><span data-stu-id="7ff40-187">**Report as Phishing**</span></span>
  - <span data-ttu-id="7ff40-188">**Параметры создания отчетов о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="7ff40-188">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="7ff40-189">**Создание отчета о нежелательной почте в Интернете**</span><span class="sxs-lookup"><span data-stu-id="7ff40-189">**Report Junk Online Help**</span></span>

  ![Сообщайте о нежелательной почте или фишинговых сообщениях с ленты](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="7ff40-191">Щелкните сообщение правой кнопкой мыши, выберите **"Нежелательное"** и убедитесь в доступности следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="7ff40-191">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="7ff40-192">**Report as Junk**</span><span class="sxs-lookup"><span data-stu-id="7ff40-192">**Report as Junk**</span></span>
  - <span data-ttu-id="7ff40-193">**Отчет о фишинге**</span><span class="sxs-lookup"><span data-stu-id="7ff40-193">**Report as Phishing**</span></span>
  - <span data-ttu-id="7ff40-194">**Параметры создания отчетов о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="7ff40-194">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="7ff40-195">**Создание отчета о нежелательной почте в Интернете**</span><span class="sxs-lookup"><span data-stu-id="7ff40-195">**Report Junk Online Help**</span></span>

  ![Отправка отчетов о нежелательной почте или фишинге](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="7ff40-197">Выберите несколько сообщений, щелкните его правой кнопкой мыши и убедитесь в наличии следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="7ff40-197">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="7ff40-198">**Report as Junk**</span><span class="sxs-lookup"><span data-stu-id="7ff40-198">**Report as Junk**</span></span>
  - <span data-ttu-id="7ff40-199">**Отчет о фишинге**</span><span class="sxs-lookup"><span data-stu-id="7ff40-199">**Report as Phishing**</span></span>

  ![Сообщение о нескольких нежелательных сообщениях или фишинговых сообщениях одним щелчком правой кнопкой мыши](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="7ff40-201">Выполните описанные выше действия в **папке "Нежелательная почта" и убедитесь,** что в нем не являются **"Не является** нежелательным", предыдущие **действия.**</span><span class="sxs-lookup"><span data-stu-id="7ff40-201">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Сообщает о том, что сообщение не является нежелательным или фишинговым, на ленте в папке "Нежелательная почта"](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Сообщить о том, что сообщение не является нежелательным или фишинговым, щелкнув правой кнопкой мыши в папке "Нежелательная почта"](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Сообщение, которое не является нежелательным или мошенничим, щелчком правой кнопкой мыши в папке "Нежелательная почта"](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="7ff40-205">Удаление надстройки создания отчетов о нежелательной почте</span><span class="sxs-lookup"><span data-stu-id="7ff40-205">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="7ff40-206">После закрытия Outlook для удаления надстройки создания отчетов о нежелательной почте используйте любую из следующих процедур.</span><span class="sxs-lookup"><span data-stu-id="7ff40-206">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="7ff40-207">**Панель управления:** нажмите клавиши Windows+R. В **открывшемся диалоговом окне** "Запуск" введите и `control appwiz.cpl` нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="7ff40-207">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="7ff40-208">Найдите и **выберите надстройку создания отчетов о нежелательной почте** майкрософт в списке, а затем нажмите кнопку **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="7ff40-208">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="7ff40-209">**Пакет установщика Windows:** найдите или скачайте соответствующий MSI-файл и дважды щелкните на нем.</span><span class="sxs-lookup"><span data-stu-id="7ff40-209">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="7ff40-210">**32-разрядная**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="7ff40-210">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="7ff40-211">**64-разрядный**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="7ff40-211">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="7ff40-212">В появившемся диалоговом окне выберите пункт **"Удалить надстройку создания отчетов о нежелательной почте для Outlook" и** нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="7ff40-212">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="7ff40-213">**Автоматический режим:** поиск или скачивание соответствующего MSI-файла.</span><span class="sxs-lookup"><span data-stu-id="7ff40-213">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="7ff40-214">В окне командной строки \<PathToFile\> замените расположение MSI-файла и выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="7ff40-214">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="7ff40-215">**32-разрядная**:</span><span class="sxs-lookup"><span data-stu-id="7ff40-215">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="7ff40-216">**64-разрядный**:</span><span class="sxs-lookup"><span data-stu-id="7ff40-216">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="7ff40-217">When you open Outlook after the uninstall, the junk, not junk, not junk, and phishing reporting options should be gone.</span><span class="sxs-lookup"><span data-stu-id="7ff40-217">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="7ff40-218">Устранение неполадок надстройки создания отчетов о нежелательной почте</span><span class="sxs-lookup"><span data-stu-id="7ff40-218">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="7ff40-219">Иногда у вас могут возникать проблемы Outlook после добавления надстройки создания отчетов о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="7ff40-219">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="7ff40-220">В этом разделе описываются проблемы, которые могут возникнуть, а также советы по их устранению.</span><span class="sxs-lookup"><span data-stu-id="7ff40-220">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="7ff40-221">Устранение неполадок пользователями</span><span class="sxs-lookup"><span data-stu-id="7ff40-221">Troubleshooting for users</span></span>

<span data-ttu-id="7ff40-222">Возникает одна или несколько из следующих причин:</span><span class="sxs-lookup"><span data-stu-id="7ff40-222">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="7ff40-223">После нажатия кнопки **Сообщить о нежелательной почте** ничего не происходит.</span><span class="sxs-lookup"><span data-stu-id="7ff40-223">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="7ff40-224">Служба Outlook не отвечает на запросы после вашего выбора сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="7ff40-224">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="7ff40-225">Вследствие отказа в доставке не удается доставить нежелательные сообщения, в отношении которых отправлен отчет.</span><span class="sxs-lookup"><span data-stu-id="7ff40-225">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="7ff40-226">Чтобы устранить эту проблему, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="7ff40-226">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="7ff40-227">Закройте и перезапустите Outlook.</span><span class="sxs-lookup"><span data-stu-id="7ff40-227">Close and restart Outlook.</span></span>
2. <span data-ttu-id="7ff40-228">Создайте и отправьте проверочное сообщение, а также убедитесь, что получатель принял сообщение.</span><span class="sxs-lookup"><span data-stu-id="7ff40-228">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="7ff40-229">Если проблема повторяется, обратитесь к администратору.</span><span class="sxs-lookup"><span data-stu-id="7ff40-229">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="7ff40-230">Другие методы, которые можно использовать для отправки сообщений корпорации Майкрософт, см. в статье ["Отчет о сообщениях и файлах" корпорации Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="7ff40-230">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="7ff40-231">Устранение неполадок для администраторов</span><span class="sxs-lookup"><span data-stu-id="7ff40-231">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="7ff40-232">Проблема: постоянно отображается сообщение об ошибке с запросом у пользователей обратиться к системного администратора</span><span class="sxs-lookup"><span data-stu-id="7ff40-232">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="7ff40-233">Проверьте или задайте `LoggingLevel` для раздела реестра значение Verbose:</span><span class="sxs-lookup"><span data-stu-id="7ff40-233">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="7ff40-234">**32-разрядная версия Outlook в 32-разрядной версии Windows:**</span><span class="sxs-lookup"><span data-stu-id="7ff40-234">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="7ff40-235">**32-разрядная версия Outlook в 64-разрядной версии Windows:**</span><span class="sxs-lookup"><span data-stu-id="7ff40-235">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="7ff40-236">**64-разрядная версия Outlook:**</span><span class="sxs-lookup"><span data-stu-id="7ff40-236">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="7ff40-237">Перезапустите Outlook и попросите пользователей сообщать о появлении сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="7ff40-237">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="7ff40-238">Соберите сведения журнала в следующем расположении.</span><span class="sxs-lookup"><span data-stu-id="7ff40-238">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="7ff40-239">Обратитесь в службу технической поддержки Exchange Online Protection и предоставьте ее сотрудникам сведения журнала.</span><span class="sxs-lookup"><span data-stu-id="7ff40-239">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="7ff40-240">Проблема: теперь при отправке запроса о сообщениях теперь пользователи не получали запрос ы подтверждения, и теперь они хотят получить подсказку</span><span class="sxs-lookup"><span data-stu-id="7ff40-240">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="7ff40-241">Создайте `ConfirmReportJunk` раздел реестра со значением "True":</span><span class="sxs-lookup"><span data-stu-id="7ff40-241">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="7ff40-242">Перезапустите Outlook.</span><span class="sxs-lookup"><span data-stu-id="7ff40-242">Restart Outlook.</span></span>
