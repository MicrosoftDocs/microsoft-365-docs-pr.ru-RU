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
ms.openlocfilehash: 5c0b802bea89a0f0f62952261bf0d2864842024f
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208831"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="097c1-103">Установка и использование надстройки создания отчетов о нежелательной почте для Microsoft Outlook</span><span class="sxs-lookup"><span data-stu-id="097c1-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

> [!NOTE]
> <span data-ttu-id="097c1-104">Если вы еще не используете надстройку для создания отчетов о нежелательной почте, рекомендуем вместо этого [Добавить надстройку сообщения](enable-the-report-message-add-in.md) .</span><span class="sxs-lookup"><span data-stu-id="097c1-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) instead.</span></span> <span data-ttu-id="097c1-105">Для получения дополнительной информации см. [Отчет о сообщениях и файлах в Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="097c1-105">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="097c1-106">Надстройка создания отчетов о нежелательной почте для Microsoft Outlook позволяет пользователям отправлять ложные срабатывания (хорошее сообщение электронной почты с пометкой нежелательной почты), ложные отрицательные (недопустимые) и фишинговые сообщения в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="097c1-106">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="097c1-107">Если в Организации не используется защита Exchange Online (например, локальное Exchange или службы электронной почты, отличные от Exchange Online), отправку отчета о нежелательной почте не повлияет на фильтрацию нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="097c1-107">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="097c1-108">В этом разделе объясняется, как установить и использовать надстройку создания отчетов о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="097c1-108">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="097c1-109">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="097c1-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="097c1-110">Чтобы установить надстройку создания отчетов о нежелательной почте, обратитесь к разделу [Установка надстройки создания отчетов о нежелательной почте](#install-the-junk-email-reporting-add-in) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="097c1-110">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this topic.</span></span>

- <span data-ttu-id="097c1-111">Надстройка создания отчетов о нежелательной почте работает со следующими версиями Outlook:</span><span class="sxs-lookup"><span data-stu-id="097c1-111">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="097c1-112">Outlook 2013 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="097c1-112">Outlook 2013 or later</span></span>
  - <span data-ttu-id="097c1-113">Outlook, входящий в состав приложений Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="097c1-113">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="097c1-114">Дополнительные сведения о сообщениях отчетов в корпорацию Майкрософт можно найти [в статье сообщения и файлы отчетов в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="097c1-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="097c1-115">Использование надстройки создания отчетов о нежелательной почте для создания отчетов о нежелательной почте и фишинговых сообщениях</span><span class="sxs-lookup"><span data-stu-id="097c1-115">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="097c1-116">Для сообщений в папке "Входящие" или любой другой папке, кроме нежелательной почты, используйте один из следующих способов для создания отчетов о нежелательной почте и фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="097c1-116">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="097c1-117">Выберите сообщение или откройте сообщение.</span><span class="sxs-lookup"><span data-stu-id="097c1-117">Select the message or open the message.</span></span> <span data-ttu-id="097c1-118">На вкладке " **Главная** " или " **сообщение** " на ленте выберите **Нежелательная почта**, а затем выберите **отчет как нежелательный** или **отчет как фишинг**.</span><span class="sxs-lookup"><span data-stu-id="097c1-118">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Отправка нежелательных или фишинговых сообщений электронной почты с ленты](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="097c1-120">Щелкните сообщение правой кнопкой мыши, выберите пункт **Нежелательная почта**, а затем выберите **отчет как нежелательный** или **отчет как фишинг**.</span><span class="sxs-lookup"><span data-stu-id="097c1-120">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Сообщить о нежелательных или фишинговых сообщениях, щелкнув правой кнопкой мыши](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="097c1-122">Выберите несколько сообщений, щелкните правой кнопкой мыши, а затем выберите **отчет как нежелательный** или **отчет как фишинг**.</span><span class="sxs-lookup"><span data-stu-id="097c1-122">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Отправка сообщений электронной почты из нескольких нежелательных или фишинговых сообщений щелчком правой кнопкой мыши](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="097c1-124">В появившемся диалоговом окне прочитайте сведения и щелкните **отчет**.</span><span class="sxs-lookup"><span data-stu-id="097c1-124">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="097c1-125">Если вы передумали, щелкните **не сообщать**.</span><span class="sxs-lookup"><span data-stu-id="097c1-125">If you change your mind, click **Don't Report**.</span></span>

   ![Диалоговое окно отчета о нежелательной почте](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Диалоговое окно отчета в качестве фишинга](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="097c1-p105">Выбранные сообщения будут перемещены в папку нежелательной почты и отправлены в корпорацию Майкрософт для анализа. Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="097c1-p105">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder. To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="097c1-130">Использование надстройки создания отчетов о нежелательной почте для отправки сообщений о сообщениях, не являющихся нежелательными, в папку нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="097c1-130">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="097c1-131">В папке нежелательной почты используйте любой из следующих способов, чтобы сообщить о ложных срабатываниях и фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="097c1-131">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="097c1-132">Выберите сообщение или откройте сообщение.</span><span class="sxs-lookup"><span data-stu-id="097c1-132">Select the message or open the message.</span></span> <span data-ttu-id="097c1-133">На вкладке " **Главная** " или " **сообщение** " на ленте щелкните элемент **не спам**, а затем выберите пункт **отчет не является нежелательным** или **отчет как фишинг**.</span><span class="sxs-lookup"><span data-stu-id="097c1-133">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Отправка отчетов о нежелательных или фишинговых сообщениях из ленты в папке "Нежелательная почта"](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="097c1-135">Щелкните сообщение правой кнопкой мыши, выберите пункт **Нежелательная почта**, а затем выберите пункт **сообщить как не являющееся нежелательным** или **сообщить как фишинг**.</span><span class="sxs-lookup"><span data-stu-id="097c1-135">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Сообщать о нежелательных и фишинговых сообщениях, щелкнув правой кнопкой мыши в папке нежелательной почты](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="097c1-137">Выберите несколько сообщений, щелкните правой кнопкой мыши, а затем выберите пункт " **отчет не является нежелательным** " или " **сообщить как фишинг**".</span><span class="sxs-lookup"><span data-stu-id="097c1-137">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Отправка сообщений электронной почты из нескольких нежелательных или фишинговых сообщений из папки "Нежелательная почта".](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="097c1-139">В появившемся диалоговом окне прочитайте сведения и щелкните **отчет**.</span><span class="sxs-lookup"><span data-stu-id="097c1-139">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="097c1-140">Если вы передумали, щелкните **не сообщать**.</span><span class="sxs-lookup"><span data-stu-id="097c1-140">If you change your mind, click **Don't Report**.</span></span>

   ![Диалоговое окно "сообщить как нежелательное"](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Диалоговое окно отчета в качестве фишинга](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="097c1-p108">Выбранные сообщения будут перемещены в папку нежелательной почты и отправлены в корпорацию Майкрософт для анализа. Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="097c1-p108">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder. To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="097c1-145">Установка надстройки создания отчетов о нежелательной почте</span><span class="sxs-lookup"><span data-stu-id="097c1-145">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="097c1-146">Необходимо иметь права администратора на компьютере, на котором выполняется установка надстройки.</span><span class="sxs-lookup"><span data-stu-id="097c1-146">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="097c1-147">Перейдите к нужному <https://www.microsoft.com/download/details.aspx?id=18275> каталогу Office и скачайте соответствующий файл MSI для вашей версии Office:</span><span class="sxs-lookup"><span data-stu-id="097c1-147">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="097c1-148">**32 бит**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="097c1-148">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="097c1-149">**64 бит**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="097c1-149">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="097c1-150">Для Outlook 2013 или более поздней версии единственным необходимым условием является Microsoft .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="097c1-150">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="097c1-151">В Windows 10 не следует устанавливать .NET Framework 2,0 из загрузки.</span><span class="sxs-lookup"><span data-stu-id="097c1-151">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="097c1-152">Установка надстройки создания отчетов о нежелательной почте с помощью мастера установки</span><span class="sxs-lookup"><span data-stu-id="097c1-152">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="097c1-153">Закройте Outlook на компьютере.</span><span class="sxs-lookup"><span data-stu-id="097c1-153">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="097c1-154">В Windows 10 убедитесь, что платформа .NET Framework 2,0 включена.</span><span class="sxs-lookup"><span data-stu-id="097c1-154">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="097c1-155">Инструкции можно найти [в разделе Включение .NET Framework 3,5 на панели управления](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span><span class="sxs-lookup"><span data-stu-id="097c1-155">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="097c1-156">Выберите скачанный MSI файл и дважды щелкните его.</span><span class="sxs-lookup"><span data-stu-id="097c1-156">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="097c1-157">На странице **Добро пожаловать в мастер установки надстройки создания отчетов о нежелательной почте** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="097c1-157">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="097c1-158">Ознакомьтесь с лицензионным соглашением, щелкните **я принимаю условия лицензионного соглашения** , если вы согласны с условиями, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="097c1-158">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="097c1-159">После завершения мастера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="097c1-159">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="097c1-160">Запустите приложение Outlook.</span><span class="sxs-lookup"><span data-stu-id="097c1-160">Start Outlook.</span></span>

<span data-ttu-id="097c1-p111">Найдите кнопку **Нежелательная почта** в ленте Outlook. С ее помощью можно сообщить корпорации Майкрософт о нежелательных сообщениях электронной почты. Выберите эти письма в папке "Входящие" и нажмите кнопку **Сообщить о нежелательной почте**.</span><span class="sxs-lookup"><span data-stu-id="097c1-p111">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="097c1-p112">Нажмите стрелку вниз рядом с кнопкой **Нежелательная почта**, чтобы открыть дополнительные параметры, например **Фишинговое сообщение**, если вы хотите сообщить корпорации Майкрософт о фишинговых сообщениях. В папке нежелательной почты можно также выбрать параметр **Не является нежелательным**, если сообщение ошибочно помечено как нежелательное.</span><span class="sxs-lookup"><span data-stu-id="097c1-p112">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="097c1-165">Установка надстройки создания отчетов о нежелательной почте в автоматическом режиме</span><span class="sxs-lookup"><span data-stu-id="097c1-165">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="097c1-166">Закройте Outlook на компьютере.</span><span class="sxs-lookup"><span data-stu-id="097c1-166">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="097c1-167">В Windows 10 установите .NET Framework 2,0, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="097c1-167">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="097c1-168">Чтобы установить надстройку без вмешательства пользователя, откройте командную строку и используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="097c1-168">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="097c1-169">`MaxMessageSelection`Указывает максимальное количество сообщений, которые можно выбрать для одной отправки.</span><span class="sxs-lookup"><span data-stu-id="097c1-169">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="097c1-170">Допустимые значения: от 1 до 50.</span><span class="sxs-lookup"><span data-stu-id="097c1-170">Valid values are from 1 to 50.</span></span> <span data-ttu-id="097c1-171">Значение по умолчанию — 15.</span><span class="sxs-lookup"><span data-stu-id="097c1-171">The default value is 15.</span></span>

   - <span data-ttu-id="097c1-172">`BccEmailAddress`Задает дополнительные получатели скрытой копии, которые будут получать копию всех отправленных пользователей.</span><span class="sxs-lookup"><span data-stu-id="097c1-172">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="097c1-173">Значение по умолчанию — пустое (нет дополнительных получателей скрытой копии).</span><span class="sxs-lookup"><span data-stu-id="097c1-173">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="097c1-174">В этом примере устанавливается 64 — разрядная версия надстройки с параметрами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="097c1-174">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="097c1-175">В этом примере выполняется установка 32 – разрядной версии надстройки по указанному пути со следующими дополнительными параметрами:</span><span class="sxs-lookup"><span data-stu-id="097c1-175">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="097c1-176">В одной отправке можно выбрать до 20 сообщений.</span><span class="sxs-lookup"><span data-stu-id="097c1-176">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="097c1-177">junkreports@contoso.com и hollyd@treyresearch.net получают копии скрытых копий всех отправленных данных.</span><span class="sxs-lookup"><span data-stu-id="097c1-177">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="097c1-178">Как проверить, все ли получилось?</span><span class="sxs-lookup"><span data-stu-id="097c1-178">How do you know this worked?</span></span>

<span data-ttu-id="097c1-179">Чтобы убедиться, что вы успешно установили надстройку создания отчетов о нежелательной почте, выполните одно из указанных ниже действий в Outlook.</span><span class="sxs-lookup"><span data-stu-id="097c1-179">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="097c1-180">Выберите сообщение или откройте сообщение.</span><span class="sxs-lookup"><span data-stu-id="097c1-180">Select the message or open the message.</span></span> <span data-ttu-id="097c1-181">На вкладке " **Главная** " или " **сообщение** " на ленте щелкните **Нежелательная почта**и убедитесь, что доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="097c1-181">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="097c1-182">**Отчет о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="097c1-182">**Report as Junk**</span></span>
  - <span data-ttu-id="097c1-183">**Отчет в качестве фишинга**</span><span class="sxs-lookup"><span data-stu-id="097c1-183">**Report as Phishing**</span></span>
  - <span data-ttu-id="097c1-184">**Параметры отчетов о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="097c1-184">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="097c1-185">**Справка по нежелательной сети**</span><span class="sxs-lookup"><span data-stu-id="097c1-185">**Report Junk Online Help**</span></span>

  ![Отправка нежелательных или фишинговых сообщений электронной почты с ленты](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="097c1-187">Щелкните сообщение правой кнопкой мыши, выберите пункт **Нежелательная почта**и убедитесь, что доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="097c1-187">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="097c1-188">**Отчет о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="097c1-188">**Report as Junk**</span></span>
  - <span data-ttu-id="097c1-189">**Отчет в качестве фишинга**</span><span class="sxs-lookup"><span data-stu-id="097c1-189">**Report as Phishing**</span></span>
  - <span data-ttu-id="097c1-190">**Параметры отчетов о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="097c1-190">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="097c1-191">**Справка по нежелательной сети**</span><span class="sxs-lookup"><span data-stu-id="097c1-191">**Report Junk Online Help**</span></span>

  ![Сообщить о нежелательных или фишинговых сообщениях, щелкнув правой кнопкой мыши](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="097c1-193">Выберите несколько сообщений, щелкните правой кнопкой мыши и убедитесь, что доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="097c1-193">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="097c1-194">**Отчет о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="097c1-194">**Report as Junk**</span></span>
  - <span data-ttu-id="097c1-195">**Отчет в качестве фишинга**</span><span class="sxs-lookup"><span data-stu-id="097c1-195">**Report as Phishing**</span></span>

  ![Отправка сообщений электронной почты из нескольких нежелательных или фишинговых сообщений щелчком правой кнопкой мыши](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="097c1-197">Выполните предыдущие действия в папке **нежелательной почты** и проверьте, что предыдущие параметры **нежелательной** почты теперь **не являются нежелательными**.</span><span class="sxs-lookup"><span data-stu-id="097c1-197">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Отправка отчетов о нежелательных или фишинговых сообщениях из ленты в папке "Нежелательная почта"](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Сообщать о нежелательных и фишинговых сообщениях, щелкнув правой кнопкой мыши в папке нежелательной почты](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Отправка сообщений электронной почты из нескольких нежелательных или фишинговых сообщений из папки "Нежелательная почта".](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="097c1-201">Удаление надстройки создания отчетов о нежелательной почте</span><span class="sxs-lookup"><span data-stu-id="097c1-201">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="097c1-202">После закрытия Outlook выполните следующие действия, чтобы удалить надстройку создания отчетов о нежелательной почте:</span><span class="sxs-lookup"><span data-stu-id="097c1-202">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="097c1-203">**Панель управления**: нажмите клавиши Windows + R. В открывшемся диалоговом окне **запуска** введите, `control appwiz.cpl` а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="097c1-203">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="097c1-204">В списке найдите и выберите **надстройка создание отчетов о нежелательной почте (Майкрософт** ), а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="097c1-204">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="097c1-205">**Пакет установщика Windows**: Найдите или Скачайте соответствующий MSI файл, а затем дважды щелкните его.</span><span class="sxs-lookup"><span data-stu-id="097c1-205">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="097c1-206">**32 бит**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="097c1-206">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="097c1-207">**64 бит**:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="097c1-207">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="097c1-208">В появившемся диалоговом окне выберите пункт **удалить надстройку создания отчетов о нежелательной почте Microsoft для Outlook** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="097c1-208">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="097c1-209">**Автоматический режим**: Найдите или Скачайте соответствующий MSI файл.</span><span class="sxs-lookup"><span data-stu-id="097c1-209">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="097c1-210">В окне командной строки замените \< пастофиле \> на расположение MSI файла и выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="097c1-210">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="097c1-211">**32 бит**:</span><span class="sxs-lookup"><span data-stu-id="097c1-211">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="097c1-212">**64 бит**:</span><span class="sxs-lookup"><span data-stu-id="097c1-212">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="097c1-213">При открытии Outlook после удаления необходимо проигнорировать параметры отчетов о нежелательной почте, нежелательной почте и фишинге.</span><span class="sxs-lookup"><span data-stu-id="097c1-213">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="097c1-214">Устранение неполадок надстройки создания отчетов о нежелательной почте</span><span class="sxs-lookup"><span data-stu-id="097c1-214">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="097c1-215">Иногда могут возникнуть проблемы с Outlook после добавления надстройки создания отчетов о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="097c1-215">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="097c1-216">В этом разделе описываются проблемы, которые могут возникнуть, а также советы по устранению этих проблем.</span><span class="sxs-lookup"><span data-stu-id="097c1-216">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="097c1-217">Устранение неполадок для пользователей</span><span class="sxs-lookup"><span data-stu-id="097c1-217">Troubleshooting for users</span></span>

<span data-ttu-id="097c1-218">Вы наблюдаем одну или несколько из приведенных ниже проблем.</span><span class="sxs-lookup"><span data-stu-id="097c1-218">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="097c1-219">После нажатия кнопки **Сообщить о нежелательной почте** ничего не происходит.</span><span class="sxs-lookup"><span data-stu-id="097c1-219">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="097c1-220">Служба Outlook не отвечает на запросы после вашего выбора сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="097c1-220">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="097c1-221">Вследствие отказа в доставке не удается доставить нежелательные сообщения, в отношении которых отправлен отчет.</span><span class="sxs-lookup"><span data-stu-id="097c1-221">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="097c1-222">Чтобы устранить эту проблему, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="097c1-222">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="097c1-223">Закройте и перезапустите Outlook.</span><span class="sxs-lookup"><span data-stu-id="097c1-223">Close and restart Outlook.</span></span>
2. <span data-ttu-id="097c1-224">Создайте и отправьте тестовое сообщение и убедитесь, что получатель получил сообщение.</span><span class="sxs-lookup"><span data-stu-id="097c1-224">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="097c1-225">Если проблема не исчезнет, обратитесь к администратору.</span><span class="sxs-lookup"><span data-stu-id="097c1-225">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="097c1-226">Другие методы, которые можно использовать для отправки сообщений в корпорацию Майкрософт, приведены [в статье сообщения отчетов и файлы в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="097c1-226">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="097c1-227">Устранение неполадок для администраторов</span><span class="sxs-lookup"><span data-stu-id="097c1-227">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="097c1-228">Проблема: появляется сообщение об ошибке, в котором пользователям предлагается обратиться к системному администратору</span><span class="sxs-lookup"><span data-stu-id="097c1-228">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="097c1-229">Проверьте или присвойте `LoggingLevel` разделу реестра значение "verbose":</span><span class="sxs-lookup"><span data-stu-id="097c1-229">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="097c1-230">**32 — Поразрядная версия Outlook в 32 — разрядная версия Windows**:</span><span class="sxs-lookup"><span data-stu-id="097c1-230">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="097c1-231">**32 — Поразрядная версия Outlook в 64 — разрядная версия Windows**:</span><span class="sxs-lookup"><span data-stu-id="097c1-231">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="097c1-232">**64 — Поразрядная версия Outlook**:</span><span class="sxs-lookup"><span data-stu-id="097c1-232">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="097c1-233">Перезапустите Outlook и попросите пользователей отправить отчет о сообщении об ошибке.</span><span class="sxs-lookup"><span data-stu-id="097c1-233">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="097c1-234">Соберите сведения журнала в следующем расположении.</span><span class="sxs-lookup"><span data-stu-id="097c1-234">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="097c1-235">Обратитесь в службу технической поддержки Exchange Online Protection и предоставьте ее сотрудникам сведения журнала.</span><span class="sxs-lookup"><span data-stu-id="097c1-235">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="097c1-236">Проблема: пользователи выбрали не получать запрос на подтверждение, когда они сообщают о сообщениях, и теперь хотят, чтобы они выдавали запрос.</span><span class="sxs-lookup"><span data-stu-id="097c1-236">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="097c1-237">Создайте `ConfirmReportJunk` раздел реестра вих со значением true:</span><span class="sxs-lookup"><span data-stu-id="097c1-237">Create the `ConfirmReportJunk`registry key wih the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="097c1-238">Перезапустите Outlook.</span><span class="sxs-lookup"><span data-stu-id="097c1-238">Restart Outlook.</span></span>
