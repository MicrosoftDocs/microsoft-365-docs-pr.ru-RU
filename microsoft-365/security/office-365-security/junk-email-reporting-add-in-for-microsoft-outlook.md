---
title: Установка и использование надстройки создания отчетов о нежелательной почте для Microsoft Outlook
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
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Узнайте, как установить и использовать надстройку создания отчетов о нежелательной почте (Майкрософт), чтобы сообщать корпорации Майкрософт о нежелательной почте, сообщениях о нежелательной почте и фишинге.
ms.openlocfilehash: e39fb2f4ecba806c2d26d989fbbe6ddec137adc1
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033951"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook-in-office-365"></a><span data-ttu-id="6986f-103">Установка и использование надстройки создания отчетов о нежелательной почте для Microsoft Outlook в Office 365</span><span class="sxs-lookup"><span data-stu-id="6986f-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook in Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="6986f-104">Если вы еще не используете надстройку для создания отчетов о нежелательной почте, рекомендуем вместо этого [Добавить надстройку сообщения](enable-the-report-message-add-in.md) .</span><span class="sxs-lookup"><span data-stu-id="6986f-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) instead.</span></span>

<span data-ttu-id="6986f-105">Надстройка создания отчетов о нежелательной почте для Microsoft Outlook позволяет пользователям отправлять ложные срабатывания (хороший адрес электронной почты, помеченный как спам), ложные отрицательные (недопустимые сообщения электронной почты) и фишинговые сообщения в Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="6986f-105">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span> <span data-ttu-id="6986f-106">Если в Организации не используется EOP, отправку отчетов о нежелательной почте не повлияет на фильтрацию нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="6986f-106">If your organization doesn't use EOP, your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="6986f-107">В этом разделе объясняется, как установить и использовать надстройку создания отчетов о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="6986f-107">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6986f-108">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="6986f-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6986f-109">Чтобы установить надстройку создания отчетов о нежелательной почте, обратитесь к разделу [Установка надстройки создания отчетов о нежелательной почте](#install-the-junk-email-reporting-add-in) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="6986f-109">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this topic.</span></span>

- <span data-ttu-id="6986f-110">Надстройка создания отчетов о нежелательной почте работает со следующими версиями Outlook:</span><span class="sxs-lookup"><span data-stu-id="6986f-110">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="6986f-111">Outlook 2013 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="6986f-111">Outlook 2013 or later</span></span>
  - <span data-ttu-id="6986f-112">Outlook, включенный в Office 365 профессиональный плюс</span><span class="sxs-lookup"><span data-stu-id="6986f-112">Outlook included with Office 365 ProPlus</span></span>

- <span data-ttu-id="6986f-113">Дополнительные сведения о сообщениях отчетов в корпорацию Майкрософт можно найти [в статье сообщения и файлы отчетов в корпорацию Майкрософт в Office 365](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="6986f-113">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="6986f-114">Использование надстройки создания отчетов о нежелательной почте для создания отчетов о нежелательной почте и фишинговых сообщениях</span><span class="sxs-lookup"><span data-stu-id="6986f-114">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="6986f-115">Для сообщений в папке "Входящие" или любой другой папке, кроме нежелательной почты, используйте один из следующих способов для создания отчетов о нежелательной почте и фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="6986f-115">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="6986f-116">Выберите сообщение или откройте сообщение.</span><span class="sxs-lookup"><span data-stu-id="6986f-116">Select the message or open the message.</span></span> <span data-ttu-id="6986f-117">На вкладке " **Главная** " или " **сообщение** " на ленте выберите **Нежелательная почта**, а затем выберите **отчет как нежелательный** или **отчет как фишинг**.</span><span class="sxs-lookup"><span data-stu-id="6986f-117">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Отправка нежелательных или фишинговых сообщений электронной почты с ленты](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="6986f-119">Щелкните сообщение правой кнопкой мыши, выберите пункт **Нежелательная почта**, а затем выберите **отчет как нежелательный** или **отчет как фишинг**.</span><span class="sxs-lookup"><span data-stu-id="6986f-119">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Сообщить о нежелательных или фишинговых сообщениях, щелкнув правой кнопкой мыши](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="6986f-121">Выберите несколько сообщений, щелкните правой кнопкой мыши, а затем выберите **отчет как нежелательный** или **отчет как фишинг**.</span><span class="sxs-lookup"><span data-stu-id="6986f-121">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Отправка сообщений электронной почты из нескольких нежелательных или фишинговых сообщений щелчком правой кнопкой мыши](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="6986f-123">В появившемся диалоговом окне прочитайте сведения и щелкните **отчет**.</span><span class="sxs-lookup"><span data-stu-id="6986f-123">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="6986f-124">Если вы передумали, щелкните **не сообщать**.</span><span class="sxs-lookup"><span data-stu-id="6986f-124">If you change your mind, click **Don't Report**.</span></span>

   ![Диалоговое окно отчета о нежелательной почте](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Диалоговое окно отчета в качестве фишинга](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="6986f-p104">Выбранные сообщения будут перемещены в папку нежелательной почты и отправлены в корпорацию Майкрософт для анализа. Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="6986f-p104">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder. To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="6986f-129">Использование надстройки создания отчетов о нежелательной почте для отправки сообщений о сообщениях, не являющихся нежелательными, в папку нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="6986f-129">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="6986f-130">В папке нежелательной почты используйте любой из следующих способов, чтобы сообщить о ложных срабатываниях и фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="6986f-130">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="6986f-131">Выберите сообщение или откройте сообщение.</span><span class="sxs-lookup"><span data-stu-id="6986f-131">Select the message or open the message.</span></span> <span data-ttu-id="6986f-132">На вкладке " **Главная** " или " **сообщение** " на ленте щелкните элемент **не спам**, а затем выберите пункт **отчет не является нежелательным** или **отчет как фишинг**.</span><span class="sxs-lookup"><span data-stu-id="6986f-132">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Отправка отчетов о нежелательных или фишинговых сообщениях из ленты в папке "Нежелательная почта"](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="6986f-134">Щелкните сообщение правой кнопкой мыши, выберите пункт **Нежелательная почта**, а затем выберите пункт **сообщить как не являющееся нежелательным** или **сообщить как фишинг**.</span><span class="sxs-lookup"><span data-stu-id="6986f-134">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Сообщать о нежелательных и фишинговых сообщениях, щелкнув правой кнопкой мыши в папке нежелательной почты](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="6986f-136">Выберите несколько сообщений, щелкните правой кнопкой мыши, а затем выберите пункт " **отчет не является нежелательным** " или " **сообщить как фишинг**".</span><span class="sxs-lookup"><span data-stu-id="6986f-136">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Отправка сообщений электронной почты из нескольких нежелательных или фишинговых сообщений из папки "Нежелательная почта".](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="6986f-138">В появившемся диалоговом окне прочитайте сведения и щелкните **отчет**.</span><span class="sxs-lookup"><span data-stu-id="6986f-138">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="6986f-139">Если вы передумали, щелкните **не сообщать**.</span><span class="sxs-lookup"><span data-stu-id="6986f-139">If you change your mind, click **Don't Report**.</span></span>

   ![Диалоговое окно "сообщить как нежелательное"](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Диалоговое окно отчета в качестве фишинга](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="6986f-p107">Выбранные сообщения будут перемещены в папку нежелательной почты и отправлены в корпорацию Майкрософт для анализа. Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="6986f-p107">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder. To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="6986f-144">Установка надстройки создания отчетов о нежелательной почте</span><span class="sxs-lookup"><span data-stu-id="6986f-144">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="6986f-145">Необходимо иметь права администратора на компьютере, на котором выполняется установка надстройки.</span><span class="sxs-lookup"><span data-stu-id="6986f-145">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="6986f-146">Перейдите к <https://www.microsoft.com/download/details.aspx?id=18275> нужному каталогу Office и скачайте соответствующий файл MSI для вашей версии Office:</span><span class="sxs-lookup"><span data-stu-id="6986f-146">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="6986f-147">**32 бит**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="6986f-147">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="6986f-148">**64 бит**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="6986f-148">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="6986f-149">Для Outlook 2013 или более поздней версии единственным необходимым условием является Microsoft .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="6986f-149">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="6986f-150">В Windows 10 не следует устанавливать .NET Framework 2,0 из загрузки.</span><span class="sxs-lookup"><span data-stu-id="6986f-150">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="6986f-151">Установка надстройки создания отчетов о нежелательной почте с помощью мастера установки</span><span class="sxs-lookup"><span data-stu-id="6986f-151">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="6986f-152">Закройте Outlook на компьютере.</span><span class="sxs-lookup"><span data-stu-id="6986f-152">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="6986f-153">В Windows 10 убедитесь, что платформа .NET Framework 2,0 включена.</span><span class="sxs-lookup"><span data-stu-id="6986f-153">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="6986f-154">Инструкции можно найти [в разделе Включение .NET Framework 3,5 на панели управления](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span><span class="sxs-lookup"><span data-stu-id="6986f-154">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="6986f-155">Выберите скачанный MSI файл и дважды щелкните его.</span><span class="sxs-lookup"><span data-stu-id="6986f-155">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="6986f-156">На странице **Добро пожаловать в мастер установки надстройки создания отчетов о нежелательной почте** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6986f-156">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="6986f-157">Ознакомьтесь с лицензионным соглашением, щелкните **я принимаю условия лицензионного соглашения** , если вы согласны с условиями, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6986f-157">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="6986f-158">После завершения мастера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="6986f-158">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="6986f-159">Запустите приложение Outlook.</span><span class="sxs-lookup"><span data-stu-id="6986f-159">Start Outlook.</span></span>

<span data-ttu-id="6986f-p110">Найдите кнопку **Нежелательная почта** в ленте Outlook. С ее помощью можно сообщить корпорации Майкрософт о нежелательных сообщениях электронной почты. Выберите эти письма в папке "Входящие" и нажмите кнопку **Сообщить о нежелательной почте**.</span><span class="sxs-lookup"><span data-stu-id="6986f-p110">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="6986f-p111">Нажмите стрелку вниз рядом с кнопкой **Нежелательная почта**, чтобы открыть дополнительные параметры, например **Фишинговое сообщение**, если вы хотите сообщить корпорации Майкрософт о фишинговых сообщениях. В папке нежелательной почты можно также выбрать параметр **Не является нежелательным**, если сообщение ошибочно помечено как нежелательное.</span><span class="sxs-lookup"><span data-stu-id="6986f-p111">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="6986f-164">Установка надстройки создания отчетов о нежелательной почте в автоматическом режиме</span><span class="sxs-lookup"><span data-stu-id="6986f-164">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="6986f-165">Закройте Outlook на компьютере.</span><span class="sxs-lookup"><span data-stu-id="6986f-165">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="6986f-166">В Windows 10 установите .NET Framework 2,0, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6986f-166">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="6986f-167">Чтобы установить надстройку без вмешательства пользователя, откройте командную строку и используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="6986f-167">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="6986f-168">`MaxMessageSelection`Указывает максимальное количество сообщений, которые можно выбрать для одной отправки.</span><span class="sxs-lookup"><span data-stu-id="6986f-168">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="6986f-169">Допустимые значения: от 1 до 50.</span><span class="sxs-lookup"><span data-stu-id="6986f-169">Valid values are from 1 to 50.</span></span> <span data-ttu-id="6986f-170">Значение по умолчанию — 15.</span><span class="sxs-lookup"><span data-stu-id="6986f-170">The default value is 15.</span></span>

   - <span data-ttu-id="6986f-171">`BccEmailAddress`Задает дополнительные получатели скрытой копии, которые будут получать копию всех отправленных пользователей.</span><span class="sxs-lookup"><span data-stu-id="6986f-171">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="6986f-172">Значение по умолчанию — пустое (нет дополнительных получателей скрытой копии).</span><span class="sxs-lookup"><span data-stu-id="6986f-172">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="6986f-173">В этом примере устанавливается 64 — разрядная версия надстройки с параметрами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6986f-173">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="6986f-174">В этом примере выполняется установка 32 – разрядной версии надстройки по указанному пути со следующими дополнительными параметрами:</span><span class="sxs-lookup"><span data-stu-id="6986f-174">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="6986f-175">В одной отправке можно выбрать до 20 сообщений.</span><span class="sxs-lookup"><span data-stu-id="6986f-175">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="6986f-176">junkreports@contoso.com и hollyd@treyresearch.net получают копии скрытых копий всех отправленных данных.</span><span class="sxs-lookup"><span data-stu-id="6986f-176">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="6986f-177">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="6986f-177">How do you know this worked?</span></span>

<span data-ttu-id="6986f-178">Чтобы убедиться, что вы успешно установили надстройку создания отчетов о нежелательной почте, выполните одно из указанных ниже действий в Outlook.</span><span class="sxs-lookup"><span data-stu-id="6986f-178">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="6986f-179">Выберите сообщение или откройте сообщение.</span><span class="sxs-lookup"><span data-stu-id="6986f-179">Select the message or open the message.</span></span> <span data-ttu-id="6986f-180">На вкладке " **Главная** " или " **сообщение** " на ленте щелкните **Нежелательная почта**и убедитесь, что доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="6986f-180">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="6986f-181">**Отчет о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="6986f-181">**Report as Junk**</span></span>
  - <span data-ttu-id="6986f-182">**Отчет в качестве фишинга**</span><span class="sxs-lookup"><span data-stu-id="6986f-182">**Report as Phishing**</span></span>
  - <span data-ttu-id="6986f-183">**Параметры отчетов о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="6986f-183">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="6986f-184">**Справка по нежелательной сети**</span><span class="sxs-lookup"><span data-stu-id="6986f-184">**Report Junk Online Help**</span></span>

  ![Отправка нежелательных или фишинговых сообщений электронной почты с ленты](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="6986f-186">Щелкните сообщение правой кнопкой мыши, выберите пункт **Нежелательная почта**и убедитесь, что доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="6986f-186">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="6986f-187">**Отчет о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="6986f-187">**Report as Junk**</span></span>
  - <span data-ttu-id="6986f-188">**Отчет в качестве фишинга**</span><span class="sxs-lookup"><span data-stu-id="6986f-188">**Report as Phishing**</span></span>
  - <span data-ttu-id="6986f-189">**Параметры отчетов о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="6986f-189">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="6986f-190">**Справка по нежелательной сети**</span><span class="sxs-lookup"><span data-stu-id="6986f-190">**Report Junk Online Help**</span></span>

  ![Сообщить о нежелательных или фишинговых сообщениях, щелкнув правой кнопкой мыши](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="6986f-192">Выберите несколько сообщений, щелкните правой кнопкой мыши и убедитесь, что доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="6986f-192">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="6986f-193">**Отчет о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="6986f-193">**Report as Junk**</span></span>
  - <span data-ttu-id="6986f-194">**Отчет в качестве фишинга**</span><span class="sxs-lookup"><span data-stu-id="6986f-194">**Report as Phishing**</span></span>

  ![Отправка сообщений электронной почты из нескольких нежелательных или фишинговых сообщений щелчком правой кнопкой мыши](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="6986f-196">Выполните предыдущие действия в папке **нежелательной почты** и проверьте, что предыдущие параметры **нежелательной** почты теперь **не являются нежелательными**.</span><span class="sxs-lookup"><span data-stu-id="6986f-196">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Отправка отчетов о нежелательных или фишинговых сообщениях из ленты в папке "Нежелательная почта"](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Сообщать о нежелательных и фишинговых сообщениях, щелкнув правой кнопкой мыши в папке нежелательной почты](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Отправка сообщений электронной почты из нескольких нежелательных или фишинговых сообщений из папки "Нежелательная почта".](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="6986f-200">Удаление надстройки создания отчетов о нежелательной почте</span><span class="sxs-lookup"><span data-stu-id="6986f-200">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="6986f-201">После закрытия Outlook выполните следующие действия, чтобы удалить надстройку создания отчетов о нежелательной почте:</span><span class="sxs-lookup"><span data-stu-id="6986f-201">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="6986f-202">**Панель управления**: нажмите клавиши Windows + R. В открывшемся диалоговом окне **запуска** введите `control appwiz.cpl` , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6986f-202">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="6986f-203">В списке найдите и выберите **надстройка создание отчетов о нежелательной почте (Майкрософт** ), а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="6986f-203">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="6986f-204">**Пакет установщика Windows**: Найдите или Скачайте соответствующий MSI файл, а затем дважды щелкните его.</span><span class="sxs-lookup"><span data-stu-id="6986f-204">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="6986f-205">**32 бит**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="6986f-205">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="6986f-206">**64 бит**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="6986f-206">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="6986f-207">В появившемся диалоговом окне выберите пункт **удалить надстройку создания отчетов о нежелательной почте Microsoft для Outlook** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6986f-207">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="6986f-208">**Автоматический режим**: Найдите или Скачайте соответствующий MSI файл.</span><span class="sxs-lookup"><span data-stu-id="6986f-208">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="6986f-209">В окне командной строки замените \<пастофиле\> на расположение MSI файла и выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="6986f-209">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="6986f-210">**32 бит**:</span><span class="sxs-lookup"><span data-stu-id="6986f-210">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="6986f-211">**64 бит**:</span><span class="sxs-lookup"><span data-stu-id="6986f-211">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="6986f-212">При открытии Outlook после удаления необходимо проигнорировать параметры отчетов о нежелательной почте, нежелательной почте и фишинге.</span><span class="sxs-lookup"><span data-stu-id="6986f-212">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="6986f-213">Устранение неполадок надстройки создания отчетов о нежелательной почте</span><span class="sxs-lookup"><span data-stu-id="6986f-213">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="6986f-214">Иногда могут возникнуть проблемы с Outlook после добавления надстройки создания отчетов о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="6986f-214">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="6986f-215">В этом разделе описываются проблемы, которые могут возникнуть, а также советы по устранению этих проблем.</span><span class="sxs-lookup"><span data-stu-id="6986f-215">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="6986f-216">Устранение неполадок для пользователей</span><span class="sxs-lookup"><span data-stu-id="6986f-216">Troubleshooting for users</span></span>

<span data-ttu-id="6986f-217">Вы наблюдаем одну или несколько из приведенных ниже проблем.</span><span class="sxs-lookup"><span data-stu-id="6986f-217">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="6986f-218">После нажатия кнопки **Сообщить о нежелательной почте** ничего не происходит.</span><span class="sxs-lookup"><span data-stu-id="6986f-218">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="6986f-219">Служба Outlook не отвечает на запросы после вашего выбора сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="6986f-219">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="6986f-220">Вследствие отказа в доставке не удается доставить нежелательные сообщения, в отношении которых отправлен отчет.</span><span class="sxs-lookup"><span data-stu-id="6986f-220">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="6986f-221">Чтобы устранить эту проблему, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="6986f-221">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="6986f-222">Закройте и перезапустите Outlook.</span><span class="sxs-lookup"><span data-stu-id="6986f-222">Close and restart Outlook.</span></span>
2. <span data-ttu-id="6986f-223">Создайте и отправьте тестовое сообщение и убедитесь, что получатель получил сообщение.</span><span class="sxs-lookup"><span data-stu-id="6986f-223">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="6986f-224">Если проблема не исчезнет, обратитесь к администратору.</span><span class="sxs-lookup"><span data-stu-id="6986f-224">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="6986f-225">Другие методы, которые можно использовать для отправки сообщений в корпорацию Майкрософт, приведены [в статье сообщения отчетов и файлы в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="6986f-225">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="6986f-226">Устранение неполадок для администраторов</span><span class="sxs-lookup"><span data-stu-id="6986f-226">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="6986f-227">Проблема: появляется сообщение об ошибке, в котором пользователям предлагается обратиться к системному администратору</span><span class="sxs-lookup"><span data-stu-id="6986f-227">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="6986f-228">Проверьте или присвойте `LoggingLevel` разделу реестра значение "verbose":</span><span class="sxs-lookup"><span data-stu-id="6986f-228">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="6986f-229">**32 — Поразрядная версия Outlook в 32 — разрядная версия Windows**:</span><span class="sxs-lookup"><span data-stu-id="6986f-229">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="6986f-230">**32 — Поразрядная версия Outlook в 64 — разрядная версия Windows**:</span><span class="sxs-lookup"><span data-stu-id="6986f-230">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="6986f-231">**64 — Поразрядная версия Outlook**:</span><span class="sxs-lookup"><span data-stu-id="6986f-231">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="6986f-232">Перезапустите Outlook и попросите пользователей отправить отчет о сообщении об ошибке.</span><span class="sxs-lookup"><span data-stu-id="6986f-232">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="6986f-233">Соберите сведения журнала в следующем расположении.</span><span class="sxs-lookup"><span data-stu-id="6986f-233">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="6986f-234">Обратитесь в службу технической поддержки Exchange Online Protection и предоставьте ее сотрудникам сведения журнала.</span><span class="sxs-lookup"><span data-stu-id="6986f-234">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="6986f-235">Проблема: пользователи выбрали не получать запрос на подтверждение, когда они сообщают о сообщениях, и теперь хотят, чтобы они выдавали запрос.</span><span class="sxs-lookup"><span data-stu-id="6986f-235">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="6986f-236">Создайте раздел `ConfirmReportJunk`реестра вих со значением true:</span><span class="sxs-lookup"><span data-stu-id="6986f-236">Create the `ConfirmReportJunk`registry key wih the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="6986f-237">Перезапустите Outlook.</span><span class="sxs-lookup"><span data-stu-id="6986f-237">Restart Outlook.</span></span>
