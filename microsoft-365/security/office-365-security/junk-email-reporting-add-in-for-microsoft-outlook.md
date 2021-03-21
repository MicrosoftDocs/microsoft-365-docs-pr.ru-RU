---
title: Установка и использование надстройки отчетов о нежелательной почте для Microsoft Outlook
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Узнайте, как установить и использовать надстройку Microsoft Junk Email Reporting для отправки сообщений о спаме, не спаме и фишинговых сообщениях в Корпорацию Майкрософт.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a6386307b24d879cac9dd2390d9080cd2cb8b5b5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920364"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="53616-103">Установка и использование надстройки отчетов о нежелательной почте для Microsoft Outlook</span><span class="sxs-lookup"><span data-stu-id="53616-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="53616-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="53616-104">**Applies to**</span></span>
- [<span data-ttu-id="53616-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="53616-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="53616-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="53616-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="53616-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="53616-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> <span data-ttu-id="53616-108">Если в настоящее время не используется надстройка "Отчеты о нежелательной почте", рекомендуется надстройка "Сообщение отчетов" или надстройка [Report Phishing.](enable-the-report-phish-add-in.md) [](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="53616-108">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md) instead.</span></span> <span data-ttu-id="53616-109">Для получения дополнительной информации см. [Отчет о сообщениях и файлах в Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="53616-109">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="53616-110">Надстройка отчетов о нежелательной почте для Microsoft Outlook позволяет пользователям отправлять в Корпорацию Майкрософт ложные срабатывания (хорошая электронная почта, помеченная как спам), ложные негативы (разрешенная плохая электронная почта) и фишинговые сообщения.</span><span class="sxs-lookup"><span data-stu-id="53616-110">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="53616-111">Если ваша организация не использует Exchange Online Protection (например, локальное exchange или службы электронной почты, кроме Exchange Online), отправка нежелательной почты не повлияет на фильтрацию нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="53616-111">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="53616-112">В этом разделе рассказывается об установке и использовании надстройки "Отчеты о нежелательной почте".</span><span class="sxs-lookup"><span data-stu-id="53616-112">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="53616-113">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="53616-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="53616-114">Чтобы установить надстройка отчетов о нежелательной почте, см. в разделе [Установка](#install-the-junk-email-reporting-add-in) надстройки отчетов о нежелательной почте в этой статье.</span><span class="sxs-lookup"><span data-stu-id="53616-114">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this article.</span></span>

- <span data-ttu-id="53616-115">Надстройка отчетов о нежелательной почте работает со следующими версиями Outlook:</span><span class="sxs-lookup"><span data-stu-id="53616-115">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="53616-116">Outlook 2013 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="53616-116">Outlook 2013 or later</span></span>
  - <span data-ttu-id="53616-117">Outlook, включенный в microsoft 365 Apps для предприятия</span><span class="sxs-lookup"><span data-stu-id="53616-117">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="53616-118">Дополнительные сведения об отчетах о сообщениях в Корпорации Майкрософт см. в материалах [Report messages and files to Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="53616-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="53616-119">Используйте надстройку отчетов о нежелательной почте, чтобы сообщать о спаме и фишинговых сообщениях</span><span class="sxs-lookup"><span data-stu-id="53616-119">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="53616-120">Для сообщений в папке "Входящие" или любой другой папки электронной почты, за исключением нежелательной почты, используйте любой из следующих методов для сообщения о нежелательной почте и фишинге:</span><span class="sxs-lookup"><span data-stu-id="53616-120">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="53616-121">Выберите сообщение или откройте сообщение.</span><span class="sxs-lookup"><span data-stu-id="53616-121">Select the message or open the message.</span></span> <span data-ttu-id="53616-122">На **вкладке "Главная"** или **"Сообщение"** в ленте нажмите кнопку **Нежелательной,** а затем выберите **Отчет** как нежелательный или **Отчет как фишинг.**</span><span class="sxs-lookup"><span data-stu-id="53616-122">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Сообщение нежелательной или фишинговой электронной почты с ленты](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="53616-124">Нажмите правой кнопкой мыши на сообщение, выберите **нежелательной**, а затем выберите **Отчет как нежелательной или** Отчет как **фишинг**.</span><span class="sxs-lookup"><span data-stu-id="53616-124">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Сообщение нежелательной или фишинговой электронной почты правой кнопкой мыши](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="53616-126">Выберите несколько сообщений, щелкните правой кнопкой мыши и выберите Отчет как **нежелательный** или **Отчет как фишинг.**</span><span class="sxs-lookup"><span data-stu-id="53616-126">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Сообщение о нескольких нежелательных или фишинговых сообщениях электронной почты правой кнопкой мыши](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="53616-128">В диалоговом окте, который появится, прочитайте сведения и нажмите **кнопку Отчет**.</span><span class="sxs-lookup"><span data-stu-id="53616-128">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="53616-129">Если вы передумали, **нажмите кнопку Не сообщайте**.</span><span class="sxs-lookup"><span data-stu-id="53616-129">If you change your mind, click **Don't Report**.</span></span>

   ![Отчет как диалоговое окно нежелательной почты](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Отчет как диалоговое окно фишинга](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="53616-132">Выбранные сообщения будут отправлены в Корпорацию Майкрософт для анализа и:</span><span class="sxs-lookup"><span data-stu-id="53616-132">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="53616-133">Перемещается в папку нежелательной почты, если сообщение о ней сообщается как спам.</span><span class="sxs-lookup"><span data-stu-id="53616-133">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="53616-134">Удаляется, если оно было отчитано как фишинг.</span><span class="sxs-lookup"><span data-stu-id="53616-134">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="53616-135">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="53616-135">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="53616-136">Используйте надстройку отчетов о нежелательной почте, чтобы сообщать о нежелательных и фишинговых сообщениях из папки нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="53616-136">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="53616-137">В папке нежелательной почты используйте любой из следующих методов для сообщения о ложных срабатываниях нежелательной почты или фишинговых сообщениях:</span><span class="sxs-lookup"><span data-stu-id="53616-137">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="53616-138">Выберите сообщение или откройте сообщение.</span><span class="sxs-lookup"><span data-stu-id="53616-138">Select the message or open the message.</span></span> <span data-ttu-id="53616-139">В **вкладке Главная** или **Сообщение** в ленте нажмите **кнопку Не** нежелательной, а затем выберите Отчет как **Не** нежелательной или Отчет **как фишинг**.</span><span class="sxs-lookup"><span data-stu-id="53616-139">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Сообщение не нежелательной или фишинговой электронной почты из ленты в папке нежелательной почты](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="53616-141">Щелкните правой кнопкой мыши по сообщению, щелкните **нежелательной,** а затем выберите **Отчет как Не нежелательной** или **Отчет как фишинг**.</span><span class="sxs-lookup"><span data-stu-id="53616-141">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Сообщение не нежелательной или фишинговой электронной почты правой кнопкой мыши в папке нежелательной почты](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="53616-143">Выберите несколько сообщений, щелкните правой кнопкой мыши, а затем выберите **Отчет как Не нежелательной** или **Отчет как фишинг**.</span><span class="sxs-lookup"><span data-stu-id="53616-143">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Сообщаем о нескольких нежелательных или фишинговых сообщениях электронной почты правой кнопкой мыши в папке нежелательной почты](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="53616-145">В диалоговом окте, который появится, прочитайте сведения и нажмите **кнопку Отчет**.</span><span class="sxs-lookup"><span data-stu-id="53616-145">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="53616-146">Если вы передумали, **нажмите кнопку Не сообщайте**.</span><span class="sxs-lookup"><span data-stu-id="53616-146">If you change your mind, click **Don't Report**.</span></span>

   ![Отчет как не нежелательное диалоговое окно](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Отчет как диалоговое окно фишинга](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="53616-149">Выбранные сообщения будут отправлены в Корпорацию Майкрософт для анализа и:</span><span class="sxs-lookup"><span data-stu-id="53616-149">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="53616-150">Перемещается в папку нежелательной почты, если сообщение о ней сообщается как спам.</span><span class="sxs-lookup"><span data-stu-id="53616-150">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="53616-151">Удаляется, если оно было отчитано как фишинг.</span><span class="sxs-lookup"><span data-stu-id="53616-151">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="53616-152">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="53616-152">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="53616-153">Установка надстройки отчетов о нежелательной почте</span><span class="sxs-lookup"><span data-stu-id="53616-153">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="53616-154">На компьютере, на котором устанавливается надстройка, должны быть привилегии администратора.</span><span class="sxs-lookup"><span data-stu-id="53616-154">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="53616-155">Перейдите <https://www.microsoft.com/download/details.aspx?id=18275> и скачайте соответствующий файл msi для версии Office в удобное для поиска расположение:</span><span class="sxs-lookup"><span data-stu-id="53616-155">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="53616-156">**32-битная:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="53616-156">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="53616-157">**64-битная:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="53616-157">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="53616-158">Для Outlook 2013 или более поздней 2013 года единственным обязательным условием является microsoft платформа .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="53616-158">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="53616-159">В Windows 10 не устанавливается платформа .NET Framework 2.0 с скачивания.</span><span class="sxs-lookup"><span data-stu-id="53616-159">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="53616-160">Установка надстройки отчетов о нежелательной почте с помощью мастера установки</span><span class="sxs-lookup"><span data-stu-id="53616-160">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="53616-161">Закройте Outlook на компьютере.</span><span class="sxs-lookup"><span data-stu-id="53616-161">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="53616-162">В Windows 10 убедитесь, что платформа .NET Framework включена версия 2.0.</span><span class="sxs-lookup"><span data-stu-id="53616-162">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="53616-163">Инструкции см. в [платформа .NET Framework 3.5 в панели управления.](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)</span><span class="sxs-lookup"><span data-stu-id="53616-163">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="53616-164">Найдите скачаный файл .msi и дважды щелкните его.</span><span class="sxs-lookup"><span data-stu-id="53616-164">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="53616-165">На странице **Добро пожаловать в мастер установки надстройки создания отчетов о нежелательной почте** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="53616-165">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="53616-166">Просмотрите лицензионный договор, нажмите **кнопку Я принимаю** условия лицензионного соглашения, если вы согласны с условиями, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="53616-166">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="53616-167">После завершения мастера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="53616-167">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="53616-168">Запустите приложение Outlook.</span><span class="sxs-lookup"><span data-stu-id="53616-168">Start Outlook.</span></span>

<span data-ttu-id="53616-p109">Найдите кнопку **Нежелательная почта** в ленте Outlook. С ее помощью можно сообщить корпорации Майкрософт о нежелательных сообщениях электронной почты. Выберите эти письма в папке "Входящие" и нажмите кнопку **Сообщить о нежелательной почте**.</span><span class="sxs-lookup"><span data-stu-id="53616-p109">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="53616-p110">Нажмите стрелку вниз рядом с кнопкой **Нежелательная почта**, чтобы открыть дополнительные параметры, например **Фишинговое сообщение**, если вы хотите сообщить корпорации Майкрософт о фишинговых сообщениях. В папке нежелательной почты можно также выбрать параметр **Не является нежелательным**, если сообщение ошибочно помечено как нежелательное.</span><span class="sxs-lookup"><span data-stu-id="53616-p110">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="53616-173">Установка надстройки создания отчетов о нежелательной почте в автоматическом режиме</span><span class="sxs-lookup"><span data-stu-id="53616-173">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="53616-174">Закройте Outlook на компьютере.</span><span class="sxs-lookup"><span data-stu-id="53616-174">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="53616-175">В Windows 10 установите платформа .NET Framework 2.0, подав следующую команду:</span><span class="sxs-lookup"><span data-stu-id="53616-175">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="53616-176">Чтобы установить надстройку без взаимодействия с пользователем, откройте командную подсказку и используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="53616-176">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="53616-177">`MaxMessageSelection` указывает максимальное количество сообщений, которые можно выбрать для одной отправки.</span><span class="sxs-lookup"><span data-stu-id="53616-177">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="53616-178">Допустимые значения — от 1 до 50.</span><span class="sxs-lookup"><span data-stu-id="53616-178">Valid values are from 1 to 50.</span></span> <span data-ttu-id="53616-179">Значение по умолчанию — 15.</span><span class="sxs-lookup"><span data-stu-id="53616-179">The default value is 15.</span></span>

   - <span data-ttu-id="53616-180">`BccEmailAddress` указывает дополнительных получателей Bcc, которые получат копию всех пользовательских представлений.</span><span class="sxs-lookup"><span data-stu-id="53616-180">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="53616-181">Значение по умолчанию пусто (без дополнительных получателей Bcc).</span><span class="sxs-lookup"><span data-stu-id="53616-181">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="53616-182">В этом примере устанавливается 64-битная версия надстройки с указанного пути с настройками по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="53616-182">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="53616-183">В этом примере устанавливается 32-битная версия надстройки с указанного пути со следующими дополнительными настройками:</span><span class="sxs-lookup"><span data-stu-id="53616-183">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="53616-184">В одной отправке можно выбрать до 20 сообщений.</span><span class="sxs-lookup"><span data-stu-id="53616-184">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="53616-185">junkreports@contoso.com и hollyd@treyresearch.net Bcc копии всех отправлений.</span><span class="sxs-lookup"><span data-stu-id="53616-185">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="53616-186">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="53616-186">How do you know this worked?</span></span>

<span data-ttu-id="53616-187">Чтобы убедиться, что надстройка отчетов о нежелательной почте успешно установлена, сделайте все следующие действия в Outlook:</span><span class="sxs-lookup"><span data-stu-id="53616-187">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="53616-188">Выберите сообщение или откройте сообщение.</span><span class="sxs-lookup"><span data-stu-id="53616-188">Select the message or open the message.</span></span> <span data-ttu-id="53616-189">На **вкладке "Главная"** или **"Сообщение"** в ленте нажмите кнопку **Нежелательной** и убедитесь, что доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="53616-189">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="53616-190">**Отчет как нежелательный**</span><span class="sxs-lookup"><span data-stu-id="53616-190">**Report as Junk**</span></span>
  - <span data-ttu-id="53616-191">**Отчет как фишинг**</span><span class="sxs-lookup"><span data-stu-id="53616-191">**Report as Phishing**</span></span>
  - <span data-ttu-id="53616-192">**Параметры нежелательной отчетности**</span><span class="sxs-lookup"><span data-stu-id="53616-192">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="53616-193">**Справка о нежелательной сети**</span><span class="sxs-lookup"><span data-stu-id="53616-193">**Report Junk Online Help**</span></span>

  ![Сообщение нежелательной или фишинговой электронной почты с ленты](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="53616-195">Щелкните правой кнопкой мыши сообщение, выберите **нежелательное** сообщение и убедитесь, что доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="53616-195">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="53616-196">**Отчет как нежелательный**</span><span class="sxs-lookup"><span data-stu-id="53616-196">**Report as Junk**</span></span>
  - <span data-ttu-id="53616-197">**Отчет как фишинг**</span><span class="sxs-lookup"><span data-stu-id="53616-197">**Report as Phishing**</span></span>
  - <span data-ttu-id="53616-198">**Параметры нежелательной отчетности**</span><span class="sxs-lookup"><span data-stu-id="53616-198">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="53616-199">**Справка о нежелательной сети**</span><span class="sxs-lookup"><span data-stu-id="53616-199">**Report Junk Online Help**</span></span>

  ![Сообщение нежелательной или фишинговой электронной почты правой кнопкой мыши](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="53616-201">Выберите несколько сообщений, щелкните правой кнопкой мыши и убедитесь, что доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="53616-201">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="53616-202">**Отчет как нежелательный**</span><span class="sxs-lookup"><span data-stu-id="53616-202">**Report as Junk**</span></span>
  - <span data-ttu-id="53616-203">**Отчет как фишинг**</span><span class="sxs-lookup"><span data-stu-id="53616-203">**Report as Phishing**</span></span>

  ![Сообщение о нескольких нежелательных или фишинговых сообщениях электронной почты правой кнопкой мыши](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="53616-205">У предыдущих действий в **папке нежелательной почты** и проверить предыдущие параметры нежелательной **отчетности** теперь **не нежелательной**.</span><span class="sxs-lookup"><span data-stu-id="53616-205">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Сообщение не нежелательной или фишинговой электронной почты из ленты в папке нежелательной почты](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Сообщение не нежелательной или фишинговой электронной почты правой кнопкой мыши в папке нежелательной почты](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Сообщаем о нескольких нежелательных или фишинговых сообщениях электронной почты правой кнопкой мыши в папке нежелательной почты](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="53616-209">Удаление надстройки создания отчетов о нежелательной почте</span><span class="sxs-lookup"><span data-stu-id="53616-209">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="53616-210">После закрытия Outlook используйте любую из следующих процедур, чтобы удалить надстройку отчетов о нежелательной почте:</span><span class="sxs-lookup"><span data-stu-id="53616-210">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="53616-211">**Панель управления:** нажмите клавишу Windows + R. В **открываемом** диалоговом ок. Введите и `control appwiz.cpl` нажмите **кнопку ОК.**</span><span class="sxs-lookup"><span data-stu-id="53616-211">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="53616-212">Найдите и выберите **надстройку microsoft Junk Email Reporting** в списке, а затем нажмите **Кнопку Удалить**.</span><span class="sxs-lookup"><span data-stu-id="53616-212">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="53616-213">**Пакет установки Windows.** Найдите или скачайте соответствующий файл msi и дважды щелкните его.</span><span class="sxs-lookup"><span data-stu-id="53616-213">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="53616-214">**32-битная:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="53616-214">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="53616-215">**64-битная:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="53616-215">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="53616-216">В диалоговом октаге, который появится, выберите Удаление надстройки **microsoft Junk Email Reporting для Outlook** и нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="53616-216">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="53616-217">**Silent Mode.** Найдите или скачайте соответствующий файл msi.</span><span class="sxs-lookup"><span data-stu-id="53616-217">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="53616-218">В окне Командная подсказка замените расположение файла .msi и запустите одну \<PathToFile\> из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="53616-218">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="53616-219">**32-битная:**</span><span class="sxs-lookup"><span data-stu-id="53616-219">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="53616-220">**64-битная:**</span><span class="sxs-lookup"><span data-stu-id="53616-220">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="53616-221">При открываемом Outlook после удалить нежелательное, а не нежелательное и фишинговое сообщение следует удалить.</span><span class="sxs-lookup"><span data-stu-id="53616-221">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="53616-222">Устранение неполадок надстройки отчетов о нежелательной почте</span><span class="sxs-lookup"><span data-stu-id="53616-222">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="53616-223">Иногда могут возникнуть проблемы с Outlook после добавления надстройки отчетов о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="53616-223">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="53616-224">В этом разделе описываются проблемы, с которыми вы можете столкнуться, а также советы по их устранению.</span><span class="sxs-lookup"><span data-stu-id="53616-224">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="53616-225">Устранение неполадок для пользователей</span><span class="sxs-lookup"><span data-stu-id="53616-225">Troubleshooting for users</span></span>

<span data-ttu-id="53616-226">Вы испытываете одну или несколько следующих проблем:</span><span class="sxs-lookup"><span data-stu-id="53616-226">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="53616-227">После нажатия кнопки **Сообщить о нежелательной почте** ничего не происходит.</span><span class="sxs-lookup"><span data-stu-id="53616-227">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="53616-228">Служба Outlook не отвечает на запросы после вашего выбора сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="53616-228">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="53616-229">Вследствие отказа в доставке не удается доставить нежелательные сообщения, в отношении которых отправлен отчет.</span><span class="sxs-lookup"><span data-stu-id="53616-229">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="53616-230">Чтобы устранить эту проблему, сделайте следующие действия:</span><span class="sxs-lookup"><span data-stu-id="53616-230">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="53616-231">Закрыть и перезапустить Outlook.</span><span class="sxs-lookup"><span data-stu-id="53616-231">Close and restart Outlook.</span></span>
2. <span data-ttu-id="53616-232">Создание и отправка тестового сообщения и проверка того, что получатель получил сообщение.</span><span class="sxs-lookup"><span data-stu-id="53616-232">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="53616-233">Если проблема сохраняется, обратитесь к администратору.</span><span class="sxs-lookup"><span data-stu-id="53616-233">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="53616-234">Другие методы, которые можно использовать для отправки сообщений в Корпорацию Майкрософт, см. в статью [Report messages and files to Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="53616-234">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="53616-235">Устранение неполадок для администраторов</span><span class="sxs-lookup"><span data-stu-id="53616-235">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="53616-236">Проблема: постоянно появляется сообщение об ошибке, которое просит пользователей связаться со своим системным администратором</span><span class="sxs-lookup"><span data-stu-id="53616-236">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="53616-237">Проверка или настройка `LoggingLevel` ключа реестра к значению "Verbose":</span><span class="sxs-lookup"><span data-stu-id="53616-237">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="53616-238">**32-битный Outlook для 32-битной Windows:**</span><span class="sxs-lookup"><span data-stu-id="53616-238">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="53616-239">**32-битный Outlook для 64-битной Windows:**</span><span class="sxs-lookup"><span data-stu-id="53616-239">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="53616-240">**64-битный Outlook:**</span><span class="sxs-lookup"><span data-stu-id="53616-240">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="53616-241">Перезапустите Outlook и попросите пользователей сообщить об этом, когда они увидят сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="53616-241">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="53616-242">Соберите сведения журнала в следующем расположении.</span><span class="sxs-lookup"><span data-stu-id="53616-242">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="53616-243">Обратитесь в службу технической поддержки Exchange Online Protection и предоставьте ее сотрудникам сведения журнала.</span><span class="sxs-lookup"><span data-stu-id="53616-243">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="53616-244">Проблема. Пользователи, выбранные для того, чтобы не получать запрос на подтверждение при сообщении сообщений, и теперь они хотят получить запрос обратно.</span><span class="sxs-lookup"><span data-stu-id="53616-244">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="53616-245">Создайте `ConfirmReportJunk` ключ реестра со значением "True":</span><span class="sxs-lookup"><span data-stu-id="53616-245">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="53616-246">Перезапустите Outlook.</span><span class="sxs-lookup"><span data-stu-id="53616-246">Restart Outlook.</span></span>