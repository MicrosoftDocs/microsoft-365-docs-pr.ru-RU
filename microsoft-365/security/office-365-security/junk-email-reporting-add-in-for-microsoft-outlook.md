---
title: Установка и использование надстройки "Отчеты о нежелательной почте" для Microsoft Outlook
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
description: Узнайте, как установить и использовать надстройку отчетов о нежелательной почте Майкрософт для отправки корпорации Майкрософт сообщений о нежелательной почте, нежелательных и фишинговых сообщениях.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 171bdc43e565a0890cddcd1e48208b49774a5315
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167351"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="e3168-103">Установка и использование надстройки "Отчеты о нежелательной почте" для Microsoft Outlook</span><span class="sxs-lookup"><span data-stu-id="e3168-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e3168-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="e3168-104">**Applies to**</span></span>
- [<span data-ttu-id="e3168-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e3168-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="e3168-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="e3168-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="e3168-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3168-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!NOTE]
> <span data-ttu-id="e3168-108">Если вы в настоящее время не используете надстройку "Отчеты о нежелательной почте", рекомендуем использовать надстройку [Report Message](enable-the-report-message-add-in.md) или надстройку [Report Phishing.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="e3168-108">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md) instead.</span></span> <span data-ttu-id="e3168-109">Для получения дополнительной информации см. [Отчет о сообщениях и файлах в Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="e3168-109">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="e3168-110">Надстройка отчетов о нежелательной почте для Microsoft Outlook позволяет пользователям отправлять в корпорацию Майкрософт ложные срабатывания (хорошая почта помечена как нежелательная почта), ложные отрицательные результаты (разрешены нежелательные сообщения) и фишинговые сообщения.</span><span class="sxs-lookup"><span data-stu-id="e3168-110">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="e3168-111">Если ваша организация не использует Exchange Online Protection (например, локальное exchange или службы электронной почты, кроме Exchange Online), отправка отчета о нежелательной почте не повлияет на фильтрацию нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="e3168-111">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="e3168-112">В этом разделе объясняется, как установить и использовать надстройки отчетов о нежелательной почте.</span><span class="sxs-lookup"><span data-stu-id="e3168-112">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e3168-113">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="e3168-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e3168-114">Чтобы установить надстройки отчетов о нежелательной почте, см. раздел "Установка надстройки отчетов о нежелательной [почте"](#install-the-junk-email-reporting-add-in) далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e3168-114">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this article.</span></span>

- <span data-ttu-id="e3168-115">Надстройка отчетов о нежелательной почте работает со следующими версиями Outlook:</span><span class="sxs-lookup"><span data-stu-id="e3168-115">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="e3168-116">Outlook 2013 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="e3168-116">Outlook 2013 or later</span></span>
  - <span data-ttu-id="e3168-117">Outlook, включенный в приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="e3168-117">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="e3168-118">Дополнительные сведения об отчетах о сообщениях в корпорацию Майкрософт см. в отчете о [сообщениях и файлах корпорации Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="e3168-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="e3168-119">Использование надстройки "Отчеты о нежелательной почте" для отправки отчетов о спаме и фишинговых сообщениях</span><span class="sxs-lookup"><span data-stu-id="e3168-119">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="e3168-120">Для сообщений в папке "Входящие" или любой другой папке электронной почты, кроме нежелательной почты, используйте любой из следующих методов для отправки отчетов о спаме и фишинговых сообщениях:</span><span class="sxs-lookup"><span data-stu-id="e3168-120">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="e3168-121">Выберите сообщение или откройте его.</span><span class="sxs-lookup"><span data-stu-id="e3168-121">Select the message or open the message.</span></span> <span data-ttu-id="e3168-122">На **вкладке "Главная"** или **"Сообщение"** на ленте щелкните "Нежелаическая почта", а затем выберите "Отчет **как** нежелательный" или "Сообщить как **фишинг".**</span><span class="sxs-lookup"><span data-stu-id="e3168-122">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Сообщение о нежелательной или фишинговой почте с ленты](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="e3168-124">Щелкните сообщение правой кнопкой мыши, **выберите**"Нежеланая почта", а затем выберите "Отчет **как** спам" или "Отчет **как фишинг".**</span><span class="sxs-lookup"><span data-stu-id="e3168-124">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Отправка отчетов о нежелательной или фишинговой почте правой кнопкой мыши](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="e3168-126">Выберите несколько сообщений, щелкните правой кнопкой мыши и выберите **"Отчет как** спам" или **"Отчет как фишинг".**</span><span class="sxs-lookup"><span data-stu-id="e3168-126">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Отправка отчетов о нескольких нежелательных или фишинговых сообщениях электронной почты щелчком правой кнопкой мыши](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="e3168-128">В от появляются диалоговое окно прочитать сведения и нажмите кнопку **Report**.</span><span class="sxs-lookup"><span data-stu-id="e3168-128">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="e3168-129">Если вы передумаете, нажмите кнопку **"Не сообщать".**</span><span class="sxs-lookup"><span data-stu-id="e3168-129">If you change your mind, click **Don't Report**.</span></span>

   ![Диалоговое окно отчета о нежелательной почте](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Диалоговое окно "Отчет о фишинге"](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="e3168-132">Выбранные сообщения будут отправлены корпорации Майкрософт для анализа и:</span><span class="sxs-lookup"><span data-stu-id="e3168-132">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="e3168-133">Перемещается в папку нежелательной почты, если она была отправлена в качестве нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="e3168-133">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="e3168-134">Удалено, если оно было засчитано как фишинговое.</span><span class="sxs-lookup"><span data-stu-id="e3168-134">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="e3168-135">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="e3168-135">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="e3168-136">Использование надстройки "Отчеты о нежелательной почте" для отправки отчетов о нежелательных и фишинговых сообщениях из папки нежелательной почты</span><span class="sxs-lookup"><span data-stu-id="e3168-136">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="e3168-137">В папке нежелательной почты используйте любой из следующих методов для сообщения о ложных срабатываниях или фишинговых сообщениях:</span><span class="sxs-lookup"><span data-stu-id="e3168-137">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="e3168-138">Выберите сообщение или откройте его.</span><span class="sxs-lookup"><span data-stu-id="e3168-138">Select the message or open the message.</span></span> <span data-ttu-id="e3168-139">На **вкладке "Главная"** или  **"Сообщение"** на ленте щелкните "Не является нежелательным" и выберите "Отчет **как** не является нежелательным" или "Сообщить **как фишинг".**</span><span class="sxs-lookup"><span data-stu-id="e3168-139">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Сообщение о том, что сообщение не является нежелательным или фишинговое, с ленты в папке "Нежелаическая почта"](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="e3168-141">Щелкните сообщение правой кнопкой мыши и выберите "Отчет **как** не является нежелательным" или "Сообщить **как фишинг".** </span><span class="sxs-lookup"><span data-stu-id="e3168-141">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Отправка отчетов о том, что сообщения не являются нежелательными или фишинговыми, при щелчке правой кнопкой мыши в папке нежелательной почты](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="e3168-143">Выберите несколько сообщений, щелкните правой кнопкой мыши и выберите **"Отчет как** не является нежелательным" или **"Сообщить как фишинг".**</span><span class="sxs-lookup"><span data-stu-id="e3168-143">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Отправка отчетов о нескольких нежелательных или фишинговых сообщениях электронной почты щелчком правой кнопкой мыши в папке нежелательной почты](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="e3168-145">В от появляются диалоговое окно прочитать сведения и нажмите кнопку **Report**.</span><span class="sxs-lookup"><span data-stu-id="e3168-145">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="e3168-146">Если вы передумаете, нажмите кнопку **"Не сообщать".**</span><span class="sxs-lookup"><span data-stu-id="e3168-146">If you change your mind, click **Don't Report**.</span></span>

   ![Диалоговое окно "Отчет как не является нежелательным"](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Диалоговое окно "Отчет о фишинге"](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="e3168-149">Выбранные сообщения будут отправлены корпорации Майкрософт для анализа и:</span><span class="sxs-lookup"><span data-stu-id="e3168-149">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="e3168-150">Перемещается в папку нежелательной почты, если она была отправлена в качестве нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="e3168-150">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="e3168-151">Удалено, если оно было засчитано как фишинговое.</span><span class="sxs-lookup"><span data-stu-id="e3168-151">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="e3168-152">Чтобы убедиться, что сообщения отправлены, откройте папку **Отправленные** и просмотрите отправленные сообщения.</span><span class="sxs-lookup"><span data-stu-id="e3168-152">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="e3168-153">Установка надстройки "Отчеты о нежелательной почте"</span><span class="sxs-lookup"><span data-stu-id="e3168-153">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="e3168-154">На компьютере, на котором устанавливается надстройка, необходимы права администратора.</span><span class="sxs-lookup"><span data-stu-id="e3168-154">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="e3168-155">Перейдите в папку, которую легко найти, и скачайте соответствующий MSI-файл для вашей версии <https://www.microsoft.com/download/details.aspx?id=18275> Office:</span><span class="sxs-lookup"><span data-stu-id="e3168-155">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="e3168-156">**32-битная:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="e3168-156">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="e3168-157">**64-битная:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="e3168-157">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="e3168-158">Для Outlook 2013 или более поздней 2013 единственным необходимым условием является Microsoft .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="e3168-158">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="e3168-159">В Windows 10 не устанавливается .NET Framework 2.0 из загружаемой версии.</span><span class="sxs-lookup"><span data-stu-id="e3168-159">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="e3168-160">Установка надстройки отчетов о нежелательной почте с помощью мастера установки</span><span class="sxs-lookup"><span data-stu-id="e3168-160">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="e3168-161">Закройте Outlook на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e3168-161">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="e3168-162">Убедитесь, что в Windows 10 включена .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="e3168-162">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="e3168-163">Инструкции см. в под [управлением .NET Framework 3.5 на панели управления.](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)</span><span class="sxs-lookup"><span data-stu-id="e3168-163">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="e3168-164">Найдите загруженный MSI-файл и дважды щелкните его.</span><span class="sxs-lookup"><span data-stu-id="e3168-164">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="e3168-165">На странице **Добро пожаловать в мастер установки надстройки создания отчетов о нежелательной почте** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e3168-165">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="e3168-166">Просмотрите лицензионный договор, щелкните **"Я принимаю** условия лицензионного соглашения", если вы согласны с условиями лицензионного соглашения, и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="e3168-166">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="e3168-167">После завершения мастера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e3168-167">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="e3168-168">Запустите приложение Outlook.</span><span class="sxs-lookup"><span data-stu-id="e3168-168">Start Outlook.</span></span>

<span data-ttu-id="e3168-p109">Найдите кнопку **Нежелательная почта** в ленте Outlook. С ее помощью можно сообщить корпорации Майкрософт о нежелательных сообщениях электронной почты. Выберите эти письма в папке "Входящие" и нажмите кнопку **Сообщить о нежелательной почте**.</span><span class="sxs-lookup"><span data-stu-id="e3168-p109">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="e3168-p110">Нажмите стрелку вниз рядом с кнопкой **Нежелательная почта**, чтобы открыть дополнительные параметры, например **Фишинговое сообщение**, если вы хотите сообщить корпорации Майкрософт о фишинговых сообщениях. В папке нежелательной почты можно также выбрать параметр **Не является нежелательным**, если сообщение ошибочно помечено как нежелательное.</span><span class="sxs-lookup"><span data-stu-id="e3168-p110">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="e3168-173">Установка надстройки создания отчетов о нежелательной почте в автоматическом режиме</span><span class="sxs-lookup"><span data-stu-id="e3168-173">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="e3168-174">Закройте Outlook на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e3168-174">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="e3168-175">В Windows 10 установите .NET Framework 2.0 с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="e3168-175">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="e3168-176">Чтобы установить надстройку без участия пользователя, откройте командную подсказку и используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e3168-176">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="e3168-177">`MaxMessageSelection` указывает максимальное количество сообщений, которые можно выбрать для одной отправки.</span><span class="sxs-lookup"><span data-stu-id="e3168-177">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="e3168-178">Допустимые значения: от 1 до 50.</span><span class="sxs-lookup"><span data-stu-id="e3168-178">Valid values are from 1 to 50.</span></span> <span data-ttu-id="e3168-179">Значение по умолчанию — 15.</span><span class="sxs-lookup"><span data-stu-id="e3168-179">The default value is 15.</span></span>

   - <span data-ttu-id="e3168-180">`BccEmailAddress` указывает дополнительных получателей копии, которые будут получать копии всех от отправленных пользователем сообщений.</span><span class="sxs-lookup"><span data-stu-id="e3168-180">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="e3168-181">Значение по умолчанию пустое (без дополнительных получателей в ск. ).</span><span class="sxs-lookup"><span data-stu-id="e3168-181">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="e3168-182">В этом примере устанавливается 64-битная версия надстройки по указанному пути с настройками по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e3168-182">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="e3168-183">В этом примере по указанному пути устанавливается 32-битная версия надстройки со следующими дополнительными настройками:</span><span class="sxs-lookup"><span data-stu-id="e3168-183">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="e3168-184">В одной отправке можно выбрать до 20 сообщений.</span><span class="sxs-lookup"><span data-stu-id="e3168-184">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="e3168-185">junkreports@contoso.com и hollyd@treyresearch.net копии всех от отправленных сообщений.</span><span class="sxs-lookup"><span data-stu-id="e3168-185">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e3168-186">Как проверить, все ли получилось?</span><span class="sxs-lookup"><span data-stu-id="e3168-186">How do you know this worked?</span></span>

<span data-ttu-id="e3168-187">Чтобы убедиться, что надстройка отчетов о нежелательной почте успешно установлена, сделайте в Outlook любое из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="e3168-187">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="e3168-188">Выберите сообщение или откройте его.</span><span class="sxs-lookup"><span data-stu-id="e3168-188">Select the message or open the message.</span></span> <span data-ttu-id="e3168-189">На **вкладке "Главная"** или  **"Сообщение"** на ленте щелкните "Нежелаическая почта" и убедитесь, что доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e3168-189">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="e3168-190">**Отчет как нежелательный**</span><span class="sxs-lookup"><span data-stu-id="e3168-190">**Report as Junk**</span></span>
  - <span data-ttu-id="e3168-191">**Сообщение как фишинговое**</span><span class="sxs-lookup"><span data-stu-id="e3168-191">**Report as Phishing**</span></span>
  - <span data-ttu-id="e3168-192">**Параметры отчетов о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="e3168-192">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="e3168-193">**Отчет о нежелательной справке в Интернете**</span><span class="sxs-lookup"><span data-stu-id="e3168-193">**Report Junk Online Help**</span></span>

  ![Сообщение о нежелательной или фишинговой почте с ленты](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="e3168-195">Щелкните сообщение правой кнопкой мыши, **выберите**"Нежеланая почта" и убедитесь, что доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e3168-195">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="e3168-196">**Отчет как нежелательный**</span><span class="sxs-lookup"><span data-stu-id="e3168-196">**Report as Junk**</span></span>
  - <span data-ttu-id="e3168-197">**Сообщение как фишинговое**</span><span class="sxs-lookup"><span data-stu-id="e3168-197">**Report as Phishing**</span></span>
  - <span data-ttu-id="e3168-198">**Параметры отчетов о нежелательной почте**</span><span class="sxs-lookup"><span data-stu-id="e3168-198">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="e3168-199">**Отчет о нежелательной справке в Интернете**</span><span class="sxs-lookup"><span data-stu-id="e3168-199">**Report Junk Online Help**</span></span>

  ![Отправка отчетов о нежелательной или фишинговой почте правой кнопкой мыши](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="e3168-201">Выберите несколько сообщений, щелкните правой кнопкой мыши и убедитесь, что доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="e3168-201">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="e3168-202">**Отчет как нежелательный**</span><span class="sxs-lookup"><span data-stu-id="e3168-202">**Report as Junk**</span></span>
  - <span data-ttu-id="e3168-203">**Сообщение как фишинговое**</span><span class="sxs-lookup"><span data-stu-id="e3168-203">**Report as Phishing**</span></span>

  ![Отправка отчетов о нескольких нежелательных или фишинговых сообщениях электронной почты щелчком правой кнопкой мыши](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="e3168-205">Сделайте предыдущие действия в папке **нежелательной** почты и убедитесь, что предыдущие параметры отчетов о нежелательной почте теперь **не являются нежелательными.** </span><span class="sxs-lookup"><span data-stu-id="e3168-205">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Сообщение о том, что сообщение не является нежелательным или фишинговое, с ленты в папке "Нежелаическая почта"](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Отправка отчетов о том, что сообщения не являются нежелательными или фишинговыми, при щелчке правой кнопкой мыши в папке нежелательной почты](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Отправка отчетов о нескольких нежелательных или фишинговых сообщениях электронной почты щелчком правой кнопкой мыши в папке нежелательной почты](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="e3168-209">Удаление надстройки создания отчетов о нежелательной почте</span><span class="sxs-lookup"><span data-stu-id="e3168-209">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="e3168-210">После закрытия Outlook используйте любую из следующих процедур, чтобы удалить надстройку отчетов о нежелательной почте:</span><span class="sxs-lookup"><span data-stu-id="e3168-210">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="e3168-211">**Панель управления:** нажмите клавиши Windows + R. В **открываемом** диалоговом окте "Выполнить" введите и `control appwiz.cpl` нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="e3168-211">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="e3168-212">Найдите и выберите **в** списке надстройку отчетов о нежелательной почте Майкрософт и нажмите кнопку **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="e3168-212">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="e3168-213">**Пакет установщика Windows:** найдите или скачайте соответствующий MSI-файл и дважды щелкните его.</span><span class="sxs-lookup"><span data-stu-id="e3168-213">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="e3168-214">**32-битная:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="e3168-214">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="e3168-215">**64-битная:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="e3168-215">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="e3168-216">В отображемом диалоговом окте выберите "Удалить надстройки **отчетов** о нежелательной почте (Майкрософт) для Outlook", а затем нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="e3168-216">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="e3168-217">**В тихом** режиме: найдите или скачайте соответствующий MSI-файл.</span><span class="sxs-lookup"><span data-stu-id="e3168-217">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="e3168-218">В окне командной подсказки замените расположение MSI-файла и запустите одну из \<PathToFile\> следующих команд:</span><span class="sxs-lookup"><span data-stu-id="e3168-218">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="e3168-219">**32-битная:**</span><span class="sxs-lookup"><span data-stu-id="e3168-219">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="e3168-220">**64-битная:**</span><span class="sxs-lookup"><span data-stu-id="e3168-220">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="e3168-221">Когда вы открываете Outlook после этого, параметры нежелательной почты, а не нежелательной почты и фишинговых отчетов не должны быть доступны.</span><span class="sxs-lookup"><span data-stu-id="e3168-221">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="e3168-222">Устранение неполадок надстройки "Отчеты о нежелательной почте"</span><span class="sxs-lookup"><span data-stu-id="e3168-222">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="e3168-223">Иногда после добавления надстройки отчетов о нежелательной почте могут возникнуть проблемы с Outlook.</span><span class="sxs-lookup"><span data-stu-id="e3168-223">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="e3168-224">В этом разделе описываются проблемы, которые могут возникнуть, а также советы по их устранению.</span><span class="sxs-lookup"><span data-stu-id="e3168-224">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="e3168-225">Устранение неполадок для пользователей</span><span class="sxs-lookup"><span data-stu-id="e3168-225">Troubleshooting for users</span></span>

<span data-ttu-id="e3168-226">У вас есть одна или несколько из следующих проблем:</span><span class="sxs-lookup"><span data-stu-id="e3168-226">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="e3168-227">После нажатия кнопки **Сообщить о нежелательной почте** ничего не происходит.</span><span class="sxs-lookup"><span data-stu-id="e3168-227">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="e3168-228">Служба Outlook не отвечает на запросы после вашего выбора сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e3168-228">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="e3168-229">Вследствие отказа в доставке не удается доставить нежелательные сообщения, в отношении которых отправлен отчет.</span><span class="sxs-lookup"><span data-stu-id="e3168-229">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="e3168-230">Чтобы устранить эту проблему, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="e3168-230">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="e3168-231">Закроем и перезапустите Outlook.</span><span class="sxs-lookup"><span data-stu-id="e3168-231">Close and restart Outlook.</span></span>
2. <span data-ttu-id="e3168-232">Создайте и отправьте тестового сообщения и убедитесь, что получатель получил сообщение.</span><span class="sxs-lookup"><span data-stu-id="e3168-232">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="e3168-233">Если проблема сохраняется, обратитесь к администратору.</span><span class="sxs-lookup"><span data-stu-id="e3168-233">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="e3168-234">Другие методы, которые можно использовать для отправки сообщений в корпорацию Майкрософт, см. в отчете о [сообщениях и файлах в корпорацию Майкрософт.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="e3168-234">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="e3168-235">Устранение неполадок для администраторов</span><span class="sxs-lookup"><span data-stu-id="e3168-235">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="e3168-236">Проблема: постоянно появляется сообщение об ошибке с запросом на обращение к системным администраторам</span><span class="sxs-lookup"><span data-stu-id="e3168-236">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="e3168-237">Проверьте или установите для `LoggingLevel` ключа реестра значение Verbose:</span><span class="sxs-lookup"><span data-stu-id="e3168-237">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="e3168-238">**32-битная версия Outlook в 32-битной версии Windows:**</span><span class="sxs-lookup"><span data-stu-id="e3168-238">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="e3168-239">**32-битная версия Outlook в 64-битной версии Windows:**</span><span class="sxs-lookup"><span data-stu-id="e3168-239">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="e3168-240">**64-битный Outlook:**</span><span class="sxs-lookup"><span data-stu-id="e3168-240">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="e3168-241">Перезапустите Outlook и попросите пользователей сообщить о них, когда они увидят сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="e3168-241">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="e3168-242">Соберите сведения журнала в следующем расположении.</span><span class="sxs-lookup"><span data-stu-id="e3168-242">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="e3168-243">Обратитесь в службу технической поддержки Exchange Online Protection и предоставьте ее сотрудникам сведения журнала.</span><span class="sxs-lookup"><span data-stu-id="e3168-243">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="e3168-244">Проблема: пользователи не получали запрос подтверждения при сообщении, а теперь хотят вернуть запрос</span><span class="sxs-lookup"><span data-stu-id="e3168-244">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="e3168-245">Создайте `ConfirmReportJunk` ключ реестра со значением True:</span><span class="sxs-lookup"><span data-stu-id="e3168-245">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="e3168-246">Перезапустите Outlook.</span><span class="sxs-lookup"><span data-stu-id="e3168-246">Restart Outlook.</span></span>
