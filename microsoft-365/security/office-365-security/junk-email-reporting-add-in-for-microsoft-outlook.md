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
description: Узнайте, как установить и использовать надстройку создания отчетов о нежелательной почте (Майкрософт), чтобы сообщать корпорации Майкрософт о нежелательной почте, сообщениях о нежелательной почте и фишинге.
ms.openlocfilehash: 096bd83c53149360e6cdd3ba8e73aacce5b1106f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199689"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="f335e-103">Установка и использование надстройки создания отчетов о нежелательной почте для Microsoft Outlook</span><span class="sxs-lookup"><span data-stu-id="f335e-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="f335e-104">Если вы еще не используете надстройку для создания отчетов о нежелательной почте, рекомендуем вместо этого [Добавить надстройку сообщения](enable-the-report-message-add-in.md) .</span><span class="sxs-lookup"><span data-stu-id="f335e-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) instead.</span></span> <span data-ttu-id="f335e-105">Для получения дополнительной информации см. [Отчет о сообщениях и файлах в Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="f335e-105">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="f335e-106">Надстройка создания отчетов о нежелательной почте для Microsoft Outlook позволяет пользователям отправлять ложные срабатывания (хорошее сообщение электронной почты с пометкой нежелательной почты), ложные отрицательные (недопустимые) и фишинговые сообщения в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f335e-106">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="f335e-107">Если в Организации не используется защита Exchange Online (например, локальное Exchange или службы электронной почты, отличные от Exchange Online), отправку отчета о нежелательной почте не повлияет на фильтрацию нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="f335e-107">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="f335e-108">В этом разделе объясняется, как установить и использовать надстройку создания отчетов о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="f335e-108">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f335e-109">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="f335e-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f335e-110">Чтобы установить надстройку создания отчетов о нежелательной почте, обратитесь к разделу [Установка надстройки создания отчетов о нежелательной почте](#install-the-junk-email-reporting-add-in) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="f335e-110">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this topic.</span></span>

- <span data-ttu-id="f335e-111">Надстройка создания отчетов о нежелательной почте работает со следующими версиями Outlook:</span><span class="sxs-lookup"><span data-stu-id="f335e-111">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="f335e-112">Outlook 2013 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="f335e-112">Outlook 2013 or later</span></span>
  - <span data-ttu-id="f335e-113">Outlook, входящий в состав приложений Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="f335e-113">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="f335e-114">Дополнительные сведения о сообщениях отчетов в корпорацию Майкрософт можно найти [в статье сообщения и файлы отчетов в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="f335e-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="f335e-115">Использование надстройки создания отчетов о нежелательной почте для создания отчетов о нежелательной почте и фишинговых сообщениях</span><span class="sxs-lookup"><span data-stu-id="f335e-115">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="f335e-116">Для сообщений в папке "Входящие" или любой другой папке, кроме нежелательной почты, используйте один из следующих способов для создания отчетов о нежелательной почте и фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="f335e-116">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="f335e-117">Выберите сообщение или откройте сообщение.</span><span class="sxs-lookup"><span data-stu-id="f335e-117">Select the message or open the message.</span></span> <span data-ttu-id="f335e-118">На вкладке " **Главная** " или " **сообщение** " на ленте выберите **Нежелательная почта**, а затем выберите **отчет как нежелательный** или **отчет как фишинг**.</span><span class="sxs-lookup"><span data-stu-id="f335e-118">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Отправка нежелательных или фишинговых сообщений электронной почты с ленты](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="f335e-120">Щелкните сообщение правой кнопкой мыши, выберите пункт **Нежелательная почта**, а затем выберите **отчет как нежелательный** или **отчет как фишинг**.</span><span class="sxs-lookup"><span data-stu-id="f335e-120">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Сообщить о нежелательных или фишинговых сообщениях, щелкнув правой кнопкой мыши](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="f335e-122">Выберите несколько сообщений, щелкните правой кнопкой мыши, а затем выберите **отчет как нежелательный** или **отчет как фишинг**.</span><span class="sxs-lookup"><span data-stu-id="f335e-122">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Отправка сообщений электронной почты из нескольких нежелательных или фишинговых сообщений щелчком правой кнопкой мыши](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="f335e-124">В появившемся диалоговом окне прочитайте сведения и щелкните **отчет**.</span><span class="sxs-lookup"><span data-stu-id="f335e-124">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="f335e-125">Если вы передумали, щелкните **не сообщать**.</span><span class="sxs-lookup"><span data-stu-id="f335e-125">If you change your mind, click **Don't Report**.</span></span>

   ![Диалоговое окно отчета о нежелательной почте](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Диалоговое окно отчета в качестве фишинга](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="f335e-128">Выбранные сообщения будут отправлены в корпорацию Майкрософт для анализа и:</span><span class="sxs-lookup"><span data-stu-id="f335e-128">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="f335e-129">Перемещено в папку нежелательной почты, если она была указана как нежелательная.</span><span class="sxs-lookup"><span data-stu-id="f335e-129">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="f335e-130">Удалено, если оно было сообщено как фишинг.</span><span class="sxs-lookup"><span data-stu-id="f335e-130">Deleted if it was reported as phishing.</span></span>
   
   <span data-ttu-id="f335e-131">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="f335e-131">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="f335e-132">Использование надстройки создания отчетов о нежелательной почте для отправки сообщений о сообщениях, не являющихся нежелательными, в папку нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="f335e-132">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="f335e-133">В папке нежелательной почты используйте любой из следующих способов, чтобы сообщить о ложных срабатываниях и фишинговых сообщениях.</span><span class="sxs-lookup"><span data-stu-id="f335e-133">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="f335e-134">Выберите сообщение или откройте сообщение.</span><span class="sxs-lookup"><span data-stu-id="f335e-134">Select the message or open the message.</span></span> <span data-ttu-id="f335e-135">На вкладке " **Главная** " или " **сообщение** " на ленте щелкните элемент **не спам**, а затем выберите пункт **отчет не является нежелательным** или **отчет как фишинг**.</span><span class="sxs-lookup"><span data-stu-id="f335e-135">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Отправка отчетов о нежелательных или фишинговых сообщениях из ленты в папке "Нежелательная почта"](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="f335e-137">Щелкните сообщение правой кнопкой мыши, выберите пункт **Нежелательная почта**, а затем выберите пункт **сообщить как не являющееся нежелательным** или **сообщить как фишинг**.</span><span class="sxs-lookup"><span data-stu-id="f335e-137">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Сообщать о нежелательных и фишинговых сообщениях, щелкнув правой кнопкой мыши в папке нежелательной почты](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="f335e-139">Выберите несколько сообщений, щелкните правой кнопкой мыши, а затем выберите пункт " **отчет не является нежелательным** " или " **сообщить как фишинг**".</span><span class="sxs-lookup"><span data-stu-id="f335e-139">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Отправка сообщений электронной почты из нескольких нежелательных или фишинговых сообщений из папки "Нежелательная почта".](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="f335e-141">В появившемся диалоговом окне прочитайте сведения и щелкните **отчет**.</span><span class="sxs-lookup"><span data-stu-id="f335e-141">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="f335e-142">Если вы передумали, щелкните **не сообщать**.</span><span class="sxs-lookup"><span data-stu-id="f335e-142">If you change your mind, click **Don't Report**.</span></span>

   ![Диалоговое окно "сообщить как нежелательное"](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Диалоговое окно отчета в качестве фишинга](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="f335e-145">Выбранные сообщения будут отправлены в корпорацию Майкрософт для анализа и:</span><span class="sxs-lookup"><span data-stu-id="f335e-145">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="f335e-146">Перемещено в папку нежелательной почты, если она была указана как нежелательная.</span><span class="sxs-lookup"><span data-stu-id="f335e-146">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="f335e-147">Удалено, если оно было сообщено как фишинг.</span><span class="sxs-lookup"><span data-stu-id="f335e-147">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="f335e-148">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="f335e-148">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="f335e-149">Установка надстройки создания отчетов о нежелательной почте</span><span class="sxs-lookup"><span data-stu-id="f335e-149">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="f335e-150">Необходимо иметь права администратора на компьютере, на котором выполняется установка надстройки.</span><span class="sxs-lookup"><span data-stu-id="f335e-150">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="f335e-151">Перейдите к нужному <https://www.microsoft.com/download/details.aspx?id=18275> каталогу Office и скачайте соответствующий файл MSI для вашей версии Office:</span><span class="sxs-lookup"><span data-stu-id="f335e-151">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="f335e-152">**32 бит**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="f335e-152">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="f335e-153">**64 бит**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="f335e-153">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="f335e-154">Для Outlook 2013 или более поздней версии единственным необходимым условием является Microsoft .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="f335e-154">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="f335e-155">В Windows 10 не следует устанавливать .NET Framework 2,0 из загрузки.</span><span class="sxs-lookup"><span data-stu-id="f335e-155">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="f335e-156">Установка надстройки создания отчетов о нежелательной почте с помощью мастера установки</span><span class="sxs-lookup"><span data-stu-id="f335e-156">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="f335e-157">Закройте Outlook на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f335e-157">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="f335e-158">В Windows 10 убедитесь, что платформа .NET Framework 2,0 включена.</span><span class="sxs-lookup"><span data-stu-id="f335e-158">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="f335e-159">Инструкции можно найти [в разделе Включение .NET Framework 3,5 на панели управления](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span><span class="sxs-lookup"><span data-stu-id="f335e-159">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="f335e-160">Выберите скачанный MSI файл и дважды щелкните его.</span><span class="sxs-lookup"><span data-stu-id="f335e-160">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="f335e-161">На странице **Добро пожаловать в мастер установки надстройки создания отчетов о нежелательной почте** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f335e-161">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="f335e-162">Ознакомьтесь с лицензионным соглашением, щелкните **я принимаю условия лицензионного соглашения** , если вы согласны с условиями, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f335e-162">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="f335e-163">После завершения мастера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="f335e-163">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="f335e-164">Запустите приложение Outlook.</span><span class="sxs-lookup"><span data-stu-id="f335e-164">Start Outlook.</span></span>

<span data-ttu-id="f335e-p109">Найдите кнопку **Нежелательная почта** в ленте Outlook. С ее помощью можно сообщить корпорации Майкрософт о нежелательных сообщениях электронной почты. Выберите эти письма в папке "Входящие" и нажмите кнопку **Сообщить о нежелательной почте**.</span><span class="sxs-lookup"><span data-stu-id="f335e-p109">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="f335e-p110">Нажмите стрелку вниз рядом с кнопкой **Нежелательная почта**, чтобы открыть дополнительные параметры, например **Фишинговое сообщение**, если вы хотите сообщить корпорации Майкрософт о фишинговых сообщениях. В папке нежелательной почты можно также выбрать параметр **Не является нежелательным**, если сообщение ошибочно помечено как нежелательное.</span><span class="sxs-lookup"><span data-stu-id="f335e-p110">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="f335e-169">Установка надстройки создания отчетов о нежелательной почте в автоматическом режиме</span><span class="sxs-lookup"><span data-stu-id="f335e-169">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="f335e-170">Закройте Outlook на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f335e-170">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="f335e-171">В Windows 10 установите .NET Framework 2,0, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f335e-171">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="f335e-172">Чтобы установить надстройку без вмешательства пользователя, откройте командную строку и используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="f335e-172">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="f335e-173">`MaxMessageSelection` Указывает максимальное количество сообщений, которые можно выбрать для одной отправки.</span><span class="sxs-lookup"><span data-stu-id="f335e-173">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="f335e-174">Допустимые значения: от 1 до 50.</span><span class="sxs-lookup"><span data-stu-id="f335e-174">Valid values are from 1 to 50.</span></span> <span data-ttu-id="f335e-175">Значение по умолчанию — 15.</span><span class="sxs-lookup"><span data-stu-id="f335e-175">The default value is 15.</span></span>

   - <span data-ttu-id="f335e-176">`BccEmailAddress` Задает дополнительные получатели скрытой копии, которые будут получать копию всех отправленных пользователей.</span><span class="sxs-lookup"><span data-stu-id="f335e-176">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="f335e-177">Значение по умолчанию — пустое (нет дополнительных получателей скрытой копии).</span><span class="sxs-lookup"><span data-stu-id="f335e-177">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="f335e-178">В этом примере устанавливается 64 — разрядная версия надстройки с параметрами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f335e-178">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="f335e-179">В этом примере выполняется установка 32 – разрядной версии надстройки по указанному пути со следующими дополнительными параметрами:</span><span class="sxs-lookup"><span data-stu-id="f335e-179">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="f335e-180">В одной отправке можно выбрать до 20 сообщений.</span><span class="sxs-lookup"><span data-stu-id="f335e-180">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="f335e-181">junkreports@contoso.com и hollyd@treyresearch.net получают копии скрытых копий всех отправленных данных.</span><span class="sxs-lookup"><span data-stu-id="f335e-181">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="f335e-182">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="f335e-182">How do you know this worked?</span></span>

<span data-ttu-id="f335e-183">Чтобы убедиться, что вы успешно установили надстройку создания отчетов о нежелательной почте, выполните одно из указанных ниже действий в Outlook.</span><span class="sxs-lookup"><span data-stu-id="f335e-183">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="f335e-184">Выберите сообщение или откройте сообщение.</span><span class="sxs-lookup"><span data-stu-id="f335e-184">Select the message or open the message.</span></span> <span data-ttu-id="f335e-185">На вкладке " **Главная** " или " **сообщение** " на ленте щелкните **Нежелательная почта**и убедитесь, что доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f335e-185">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="f335e-186">**Отчет о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="f335e-186">**Report as Junk**</span></span>
  - <span data-ttu-id="f335e-187">**Отчет в качестве фишинга**</span><span class="sxs-lookup"><span data-stu-id="f335e-187">**Report as Phishing**</span></span>
  - <span data-ttu-id="f335e-188">**Параметры отчетов о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="f335e-188">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="f335e-189">**Справка по нежелательной сети**</span><span class="sxs-lookup"><span data-stu-id="f335e-189">**Report Junk Online Help**</span></span>

  ![Отправка нежелательных или фишинговых сообщений электронной почты с ленты](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="f335e-191">Щелкните сообщение правой кнопкой мыши, выберите пункт **Нежелательная почта**и убедитесь, что доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f335e-191">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="f335e-192">**Отчет о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="f335e-192">**Report as Junk**</span></span>
  - <span data-ttu-id="f335e-193">**Отчет в качестве фишинга**</span><span class="sxs-lookup"><span data-stu-id="f335e-193">**Report as Phishing**</span></span>
  - <span data-ttu-id="f335e-194">**Параметры отчетов о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="f335e-194">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="f335e-195">**Справка по нежелательной сети**</span><span class="sxs-lookup"><span data-stu-id="f335e-195">**Report Junk Online Help**</span></span>

  ![Сообщить о нежелательных или фишинговых сообщениях, щелкнув правой кнопкой мыши](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="f335e-197">Выберите несколько сообщений, щелкните правой кнопкой мыши и убедитесь, что доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f335e-197">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="f335e-198">**Отчет о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="f335e-198">**Report as Junk**</span></span>
  - <span data-ttu-id="f335e-199">**Отчет в качестве фишинга**</span><span class="sxs-lookup"><span data-stu-id="f335e-199">**Report as Phishing**</span></span>

  ![Отправка сообщений электронной почты из нескольких нежелательных или фишинговых сообщений щелчком правой кнопкой мыши](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="f335e-201">Выполните предыдущие действия в папке **нежелательной почты** и проверьте, что предыдущие параметры **нежелательной** почты теперь **не являются нежелательными**.</span><span class="sxs-lookup"><span data-stu-id="f335e-201">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Отправка отчетов о нежелательных или фишинговых сообщениях из ленты в папке "Нежелательная почта"](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Сообщать о нежелательных и фишинговых сообщениях, щелкнув правой кнопкой мыши в папке нежелательной почты](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Отправка сообщений электронной почты из нескольких нежелательных или фишинговых сообщений из папки "Нежелательная почта".](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="f335e-205">Удаление надстройки создания отчетов о нежелательной почте</span><span class="sxs-lookup"><span data-stu-id="f335e-205">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="f335e-206">После закрытия Outlook выполните следующие действия, чтобы удалить надстройку создания отчетов о нежелательной почте:</span><span class="sxs-lookup"><span data-stu-id="f335e-206">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="f335e-207">**Панель управления**: нажмите клавиши Windows + R. В открывшемся диалоговом окне **запуска** введите, `control appwiz.cpl` а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f335e-207">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="f335e-208">В списке найдите и выберите **надстройка создание отчетов о нежелательной почте (Майкрософт** ), а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f335e-208">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="f335e-209">**Пакет установщика Windows**: Найдите или Скачайте соответствующий MSI файл, а затем дважды щелкните его.</span><span class="sxs-lookup"><span data-stu-id="f335e-209">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="f335e-210">**32 бит**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="f335e-210">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="f335e-211">**64 бит**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="f335e-211">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="f335e-212">В появившемся диалоговом окне выберите пункт **удалить надстройку создания отчетов о нежелательной почте Microsoft для Outlook** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f335e-212">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="f335e-213">**Автоматический режим**: Найдите или Скачайте соответствующий MSI файл.</span><span class="sxs-lookup"><span data-stu-id="f335e-213">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="f335e-214">В окне командной строки замените на \<PathToFile\> Расположение MSI файла и выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="f335e-214">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="f335e-215">**32 бит**:</span><span class="sxs-lookup"><span data-stu-id="f335e-215">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="f335e-216">**64 бит**:</span><span class="sxs-lookup"><span data-stu-id="f335e-216">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="f335e-217">При открытии Outlook после удаления необходимо проигнорировать параметры отчетов о нежелательной почте, нежелательной почте и фишинге.</span><span class="sxs-lookup"><span data-stu-id="f335e-217">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="f335e-218">Устранение неполадок надстройки создания отчетов о нежелательной почте</span><span class="sxs-lookup"><span data-stu-id="f335e-218">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="f335e-219">Иногда могут возникнуть проблемы с Outlook после добавления надстройки создания отчетов о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="f335e-219">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="f335e-220">В этом разделе описываются проблемы, которые могут возникнуть, а также советы по устранению этих проблем.</span><span class="sxs-lookup"><span data-stu-id="f335e-220">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="f335e-221">Устранение неполадок для пользователей</span><span class="sxs-lookup"><span data-stu-id="f335e-221">Troubleshooting for users</span></span>

<span data-ttu-id="f335e-222">Вы наблюдаем одну или несколько из приведенных ниже проблем.</span><span class="sxs-lookup"><span data-stu-id="f335e-222">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="f335e-223">После нажатия кнопки **Сообщить о нежелательной почте** ничего не происходит.</span><span class="sxs-lookup"><span data-stu-id="f335e-223">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="f335e-224">Служба Outlook не отвечает на запросы после вашего выбора сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f335e-224">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="f335e-225">Вследствие отказа в доставке не удается доставить нежелательные сообщения, в отношении которых отправлен отчет.</span><span class="sxs-lookup"><span data-stu-id="f335e-225">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="f335e-226">Чтобы устранить эту проблему, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f335e-226">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="f335e-227">Закройте и перезапустите Outlook.</span><span class="sxs-lookup"><span data-stu-id="f335e-227">Close and restart Outlook.</span></span>
2. <span data-ttu-id="f335e-228">Создайте и отправьте тестовое сообщение и убедитесь, что получатель получил сообщение.</span><span class="sxs-lookup"><span data-stu-id="f335e-228">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="f335e-229">Если проблема не исчезнет, обратитесь к администратору.</span><span class="sxs-lookup"><span data-stu-id="f335e-229">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="f335e-230">Другие методы, которые можно использовать для отправки сообщений в корпорацию Майкрософт, приведены [в статье сообщения отчетов и файлы в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="f335e-230">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="f335e-231">Устранение неполадок для администраторов</span><span class="sxs-lookup"><span data-stu-id="f335e-231">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="f335e-232">Проблема: появляется сообщение об ошибке, в котором пользователям предлагается обратиться к системному администратору</span><span class="sxs-lookup"><span data-stu-id="f335e-232">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="f335e-233">Проверьте или присвойте `LoggingLevel` разделу реестра значение "verbose":</span><span class="sxs-lookup"><span data-stu-id="f335e-233">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="f335e-234">**32 — Поразрядная версия Outlook в 32 — разрядная версия Windows**:</span><span class="sxs-lookup"><span data-stu-id="f335e-234">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="f335e-235">**32 — Поразрядная версия Outlook в 64 — разрядная версия Windows**:</span><span class="sxs-lookup"><span data-stu-id="f335e-235">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="f335e-236">**64 — Поразрядная версия Outlook**:</span><span class="sxs-lookup"><span data-stu-id="f335e-236">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="f335e-237">Перезапустите Outlook и попросите пользователей отправить отчет о сообщении об ошибке.</span><span class="sxs-lookup"><span data-stu-id="f335e-237">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="f335e-238">Соберите сведения журнала в следующем расположении.</span><span class="sxs-lookup"><span data-stu-id="f335e-238">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="f335e-239">Обратитесь в службу технической поддержки Exchange Online Protection и предоставьте ее сотрудникам сведения журнала.</span><span class="sxs-lookup"><span data-stu-id="f335e-239">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="f335e-240">Проблема: пользователи выбрали не получать запрос на подтверждение, когда они сообщают о сообщениях, и теперь хотят, чтобы они выдавали запрос.</span><span class="sxs-lookup"><span data-stu-id="f335e-240">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="f335e-241">Создайте `ConfirmReportJunk` раздел реестра со значением true:</span><span class="sxs-lookup"><span data-stu-id="f335e-241">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="f335e-242">Перезапустите Outlook.</span><span class="sxs-lookup"><span data-stu-id="f335e-242">Restart Outlook.</span></span>
