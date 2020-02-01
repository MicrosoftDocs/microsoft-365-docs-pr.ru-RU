---
title: Установка надстройки создания отчетов о нежелательной почте для Microsoft Outlook
f1.keywords:
- NOCSH
ms.author: MSFTTracyP
author: tracyp
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8dcc752f-e22e-44ce-a104-4cc4d7e439f3
ms.collection:
- M365-security-compliance
description: В этом Артиклесуппортед Лангуажесинсталл создание сообщения о нежелательной почте Добавление дополнительных сведений о надстройке создания отчетов о нежелательной почте
ms.openlocfilehash: 0f7a5a3cbaddf9aef5e518db38ffb36c397cd1f0
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599156"
---
# <a name="install-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="1d3b5-103">Установка надстройки создания отчетов о нежелательной почте для Microsoft Outlook</span><span class="sxs-lookup"><span data-stu-id="1d3b5-103">Install the Junk Email Reporting Add-in for Microsoft Outlook</span></span>

<span data-ttu-id="1d3b5-104">В этом разделе описывается установка и удаление надстройки создания отчетов о нежелательной почте для Microsoft Outlook на клиентских компьютерах в организации.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-104">This topic describes how to install (and uninstall) the Microsoft Junk Email Reporting Add-in for Outlook on client computers in your organization.</span></span> <span data-ttu-id="1d3b5-105">В текущей версии надстройки (Январь 2016) включена поддержка Outlook 2016, Outlook 2013 и Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-105">The current version of the add-in (January 2016) includes support for Outlook 2016, Outlook 2013, and Outlook 2010.</span></span>

<span data-ttu-id="1d3b5-p102">Надстройка позволяет сообщать о нежелательной почте непосредственно в ленте Outlook (для всех поддерживаемых языков). В английской версии надстройки непосредственно из ленты также можно сообщать о других проблемах с электронной почтой:</span><span class="sxs-lookup"><span data-stu-id="1d3b5-p102">The add-in (for all supported languages) allows you to report junk email directly from the Outlook ribbon. The English version of the add-in includes additional options for reporting email issues to Microsoft, directly from the ribbon:</span></span>

- <span data-ttu-id="1d3b5-108">полученных фишинговых сообщениях;</span><span class="sxs-lookup"><span data-stu-id="1d3b5-108">Report phishing scam emails that you receive</span></span>

- <span data-ttu-id="1d3b5-109">сообщениях, ошибочно помеченных как нежелательные.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-109">Report email incorrectly identified as junk mail.</span></span>

## <a name="supported-languages"></a><span data-ttu-id="1d3b5-110">Поддерживаемые языки</span><span class="sxs-lookup"><span data-stu-id="1d3b5-110">Supported Languages</span></span>
<span data-ttu-id="1d3b5-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="1d3b5-111"><a name="sectionSection0"> </a></span></span>

<span data-ttu-id="1d3b5-112">Надстройка создания отчетов о нежелательной почте поддерживает следующие языки:</span><span class="sxs-lookup"><span data-stu-id="1d3b5-112">The Junk Email Reporting Add-in supports the following languages:</span></span>

- <span data-ttu-id="1d3b5-113">китайский (упрощенное письмо)</span><span class="sxs-lookup"><span data-stu-id="1d3b5-113">Simplified Chinese</span></span>

- <span data-ttu-id="1d3b5-114">китайский (традиционное письмо)</span><span class="sxs-lookup"><span data-stu-id="1d3b5-114">Traditional Chinese</span></span>

- <span data-ttu-id="1d3b5-115">голландский;</span><span class="sxs-lookup"><span data-stu-id="1d3b5-115">Dutch</span></span>

- <span data-ttu-id="1d3b5-116">английский;</span><span class="sxs-lookup"><span data-stu-id="1d3b5-116">English</span></span>

- <span data-ttu-id="1d3b5-117">французский;</span><span class="sxs-lookup"><span data-stu-id="1d3b5-117">French</span></span>

- <span data-ttu-id="1d3b5-118">немецкий;</span><span class="sxs-lookup"><span data-stu-id="1d3b5-118">German</span></span>

- <span data-ttu-id="1d3b5-119">итальянский;</span><span class="sxs-lookup"><span data-stu-id="1d3b5-119">Italian</span></span>

- <span data-ttu-id="1d3b5-120">японский;</span><span class="sxs-lookup"><span data-stu-id="1d3b5-120">Japanese</span></span>

- <span data-ttu-id="1d3b5-121">Корейский</span><span class="sxs-lookup"><span data-stu-id="1d3b5-121">Korean</span></span>

- <span data-ttu-id="1d3b5-122">Португальский</span><span class="sxs-lookup"><span data-stu-id="1d3b5-122">Portuguese</span></span>

- <span data-ttu-id="1d3b5-123">Португальский (Бразилия)</span><span class="sxs-lookup"><span data-stu-id="1d3b5-123">Portuguese (Brazil)</span></span>

- <span data-ttu-id="1d3b5-124">Испанский</span><span class="sxs-lookup"><span data-stu-id="1d3b5-124">Spanish</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="1d3b5-125">Установка надстройки создания отчетов о нежелательной почте</span><span class="sxs-lookup"><span data-stu-id="1d3b5-125">Install the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="1d3b5-126">Как установить надстройку создания отчетов о нежелательной почте</span><span class="sxs-lookup"><span data-stu-id="1d3b5-126">You can install the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="1d3b5-127">C помощью пакета установщика Windows, который запускается так же, как любой другой MSI-файл.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-127">By running the Windows Installer package as you would any other .msi file.</span></span> <span data-ttu-id="1d3b5-128">При установке надстройки откроется графический интерфейс пользователя, который состоит из последовательных экранов установки с запросами.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-128">When you install the add-in, a GUI interface opens and prompts you through the installation screens.</span></span> <span data-ttu-id="1d3b5-129">Дополнительные сведения см. [в статье Установка надстройки создания отчетов о нежелательной почте с помощью мастера установки](#install-the-junk-email-reporting-add-in-using-the-setup-wizard).</span><span class="sxs-lookup"><span data-stu-id="1d3b5-129">For more information, see [Install the Junk Email Reporting Add-In using the Setup wizard](#install-the-junk-email-reporting-add-in-using-the-setup-wizard).</span></span>

<span data-ttu-id="1d3b5-130">ИЛИ</span><span class="sxs-lookup"><span data-stu-id="1d3b5-130">OR</span></span>

- <span data-ttu-id="1d3b5-p104">Запустив автоматическую установку, которая подавляет пользовательский интерфейс установки. Вместо него указываются параметры командной строки, которые управляют сценарием установки. При установке надстройки доступны дополнительные параметры конфигурации, которых нет в графическом интерфейсе пользователя. Подробнее см. в разделе [Установка надстройки создания отчетов о нежелательной почте в автоматическом режиме](#install-the-junk-email-reporting-add-in-using-silent-mode).</span><span class="sxs-lookup"><span data-stu-id="1d3b5-p104">By running a silent installation which suppresses the installation user interface. Instead, you specify command-line options which run an installation script. When you install the add-in, additional configuration options are available which are not available through the GUI interface. For more information, see [Install the Junk Email Reporting Add-In using Silent Mode](#install-the-junk-email-reporting-add-in-using-silent-mode).</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1d3b5-135">Что нужно знать перед началом работы?</span><span class="sxs-lookup"><span data-stu-id="1d3b5-135">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1d3b5-136">Ознакомьтесь с **требованиями к системе** для надстройки создания отчетов о нежелательной почте по адресу [https://www.microsoft.com/download/details.aspx?id=18275](https://www.microsoft.com/download/details.aspx?id=18275).</span><span class="sxs-lookup"><span data-stu-id="1d3b5-136">See the **System Requirements** for the Junk Email Reporting Add-in at [https://www.microsoft.com/download/details.aspx?id=18275](https://www.microsoft.com/download/details.aspx?id=18275).</span></span>

> [!NOTE]
> <span data-ttu-id="1d3b5-137">Требуются права администратора на компьютере, на котором устанавливается надстройка.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-137">You must have administrator privileges on the computer on which you are installing the add-in.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="1d3b5-138">Установка надстройки создания отчетов о нежелательной почте с помощью мастера установки</span><span class="sxs-lookup"><span data-stu-id="1d3b5-138">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="1d3b5-139">Закройте Outlook на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-139">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="1d3b5-140">В разделе **сведения** [надстройки создания отчетов о нежелательной почте для Microsoft Outlook](https://www.microsoft.com/download/details.aspx?id=18275)Скачайте соответствующий MSI файл для вашей версии Office.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-140">In the **Details** section at [Microsoft Junk E-mail Reporting Add-In for Microsoft Outlook](https://www.microsoft.com/download/details.aspx?id=18275), download the appropriate .msi file for your version of Office.</span></span>

3. <span data-ttu-id="1d3b5-141">Дважды щелкните файл MSI.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-141">Double-click the .msi file.</span></span>

4. <span data-ttu-id="1d3b5-142">На странице **Добро пожаловать в мастер установки надстройки создания отчетов о нежелательной почте** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-142">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="1d3b5-p105">Ознакомьтесь с условиями лицензионного соглашения и нажмите кнопку **Я принимаю условия лицензионного соглашения**, если вы согласны с условиями установки (это обязательно для продолжения установки). Чтобы продолжить, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-p105">Review the license agreement, and then click **I accept the terms in the License Agreement** if you agree to the terms of installation (required to continue installation). Click **Next** to continue.</span></span>

6. <span data-ttu-id="1d3b5-145">После завершения мастера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-145">When the wizard is complete, click **Finish**.</span></span>

7. <span data-ttu-id="1d3b5-146">Запустите приложение Outlook.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-146">Start Outlook.</span></span>

8. <span data-ttu-id="1d3b5-p106">Найдите кнопку **Нежелательная почта** в ленте Outlook. С ее помощью можно сообщить корпорации Майкрософт о нежелательных сообщениях электронной почты. Выберите эти письма в папке "Входящие" и нажмите кнопку **Сообщить о нежелательной почте**.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-p106">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

9. <span data-ttu-id="1d3b5-p107">Нажмите стрелку вниз рядом с кнопкой **Нежелательная почта**, чтобы открыть дополнительные параметры, например **Фишинговое сообщение**, если вы хотите сообщить корпорации Майкрософт о фишинговых сообщениях. В папке нежелательной почты можно также выбрать параметр **Не является нежелательным**, если сообщение ошибочно помечено как нежелательное.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-p107">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="1d3b5-151">Установка надстройки создания отчетов о нежелательной почте в автоматическом режиме</span><span class="sxs-lookup"><span data-stu-id="1d3b5-151">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="1d3b5-152">Закройте Outlook на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-152">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="1d3b5-153">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-153">Open a command prompt.</span></span>

3. <span data-ttu-id="1d3b5-154">Если вы хотите выполнить простую установку надстройки без дополнительных параметров, введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-154">If you want to perform a straight installation of the add-in, without any optional parameters, specify the following:</span></span>

   - <span data-ttu-id="1d3b5-155">Компьютеры с Outlook x86:`msiexec /qn /i JunkReportingAdd-in.x86-en.msi`</span><span class="sxs-lookup"><span data-stu-id="1d3b5-155">Computers running x86 Outlook: `msiexec /qn /i JunkReportingAdd-in.x86-en.msi`</span></span>

   - <span data-ttu-id="1d3b5-156">Компьютеры с Outlook версии x64:  `msiexec /qn /i JunkReportingAdd-in.x64-en.msi`</span><span class="sxs-lookup"><span data-stu-id="1d3b5-156">Computers running x64 Outlook:  `msiexec /qn /i JunkReportingAdd-in.x64-en.msi`</span></span>

    <span data-ttu-id="1d3b5-157">Также можно указать дополнительные параметры MaxMessageSelection и BccEmailAddress.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-157">You can also specify the optional MaxMessageSelection and BccEmailAddress parameters:</span></span>

   - <span data-ttu-id="1d3b5-p108">Параметр MaxMessageSelection позволяет администратору задать максимальное число сообщений, которые могут быть выбраны пользователями для отправки за один раз. Допускаются значения от 1 до 50; значение по умолчанию  10.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-p108">MaxMessageSelection Allows administrators to define the maximum number of messages that can be selected by users for submission in a single click. The range is 1 to 50 messages, and the default value is 10 messages.</span></span>

     <span data-ttu-id="1d3b5-160">Пример. Чтобы задать значение 16 в качестве максимального числа сообщений, которые пользователи могут выбрать для отправки за один раз, укажите в команде установки следующий параметр.  `MaxMessageSelection=16`</span><span class="sxs-lookup"><span data-stu-id="1d3b5-160">Example: If you want to set the maximum number of messages that can be selected by users for submission in a single click to 16, use the following option as part of the installation command:  `MaxMessageSelection=16`</span></span>

   - <span data-ttu-id="1d3b5-p109">Параметр BccEmailAddress позволяет администратору настроить почтовый ящик для получения копий всех отправок пользователей. Для этого задается адрес в поле «Скрытая копия». После настройки почтового ящика копии всех отправляемых сообщений будут отправляться на адрес, указанный в параметре BccEmailAddress. По умолчанию адрес для отправки скрытой копии не задается.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-p109">BccEmailAddress Allows Administrators to set up a mailbox to receive a copy of all their user submissions by setting a Bcc email address. When the mailbox is set up, a copy of all submitted emails will be sent to the BccEmailAddress. Otherwise, the default setting is no Bcc email address.</span></span>

     <span data-ttu-id="1d3b5-164">Пример. Чтобы использовать для отправки скрытой копии адрес junkReports@contoso.com, введите следующую команду.  `BccEmailAddress="junkReports@contoso.com"`</span><span class="sxs-lookup"><span data-stu-id="1d3b5-164">Example: If you want to use junkReports@contoso.com as the Bcc email address for all submissions, use the following command:  `BccEmailAddress="junkReports@contoso.com"`</span></span>

     > [!NOTE]
     > <span data-ttu-id="1d3b5-p110">Можно задать несколько адресов для отправки скрытой копии, разделив их точкой с запятой. Пример.  `BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"`</span><span class="sxs-lookup"><span data-stu-id="1d3b5-p110">You can set multiple Bcc email addresses by entering them with a semicolon delimiter. Example:  `BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"`</span></span>

     <span data-ttu-id="1d3b5-167">Чтобы добавить оба этих необязательных параметра на основе предыдущих примеров, выполните следующую команду на компьютере, работающем под управлением x86 Outlook:</span><span class="sxs-lookup"><span data-stu-id="1d3b5-167">To add both of these optional parameters based on the previous examples, you would run the following command on a computer running x86 Outlook:</span></span>

     ```
     msiexec /qn /i JunkReportingAdd-in.x86-en.msi. MaxMessageSelection=16 BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"
     ```

4. <span data-ttu-id="1d3b5-168">После завершения установки запустите Outlook.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-168">After the installation is complete, start Outlook.</span></span>

5. <span data-ttu-id="1d3b5-p111">Найдите кнопку **Нежелательная почта** в ленте Outlook. С ее помощью можно сообщить корпорации Майкрософт о нежелательных сообщениях электронной почты. Выберите эти письма в папке "Входящие" и нажмите кнопку **Сообщить о нежелательной почте**.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-p111">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

6. <span data-ttu-id="1d3b5-p112">Нажмите стрелку вниз рядом с кнопкой **Нежелательная почта**, чтобы открыть дополнительные параметры, например **Фишинговое сообщение**, если вы хотите сообщить корпорации Майкрософт о фишинговых сообщениях. В папке нежелательной почты можно также выбрать параметр **Не является нежелательным**, если сообщение ошибочно помечено как нежелательное.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-p112">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="1d3b5-173">Удаление надстройки создания отчетов о нежелательной почте</span><span class="sxs-lookup"><span data-stu-id="1d3b5-173">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="1d3b5-174">Используйте один из параметров, описанных в этой статье, чтобы удалить надстройку создания отчетов о нежелательной почте:</span><span class="sxs-lookup"><span data-stu-id="1d3b5-174">Use one of the options described in this to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="1d3b5-175">Удалите надстройку с помощью панели управления Windows.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-175">Remove the add-in using Windows Control Panel.</span></span>

- <span data-ttu-id="1d3b5-176">Запустите пакет установщика Windows и выберите параметр uninstall.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-176">Run the Windows installer package and select the uninstall option.</span></span>

- <span data-ttu-id="1d3b5-177">Запустите автоматическую установку с помощью параметра удаления.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-177">Run a silent installation using the uninstall option.</span></span>

> [!NOTE]
> <span data-ttu-id="1d3b5-178">Требуются права администратора на компьютере, с которого удаляется надстройка.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-178">You must have administrator privileges on the computer on which you are uninstalling the add-in.</span></span>

### <a name="uninstall-the-junk-email-reporting-add-in-from-control-panel"></a><span data-ttu-id="1d3b5-179">Удаление надстройки создания отчетов о нежелательной почте с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="1d3b5-179">Uninstall the Junk Email Reporting Add-in from Control Panel</span></span>

1. <span data-ttu-id="1d3b5-180">Закройте Outlook на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-180">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="1d3b5-181">На компьютере в меню пуск выберите **Панель управления**.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-181">From the Start menu on your computer, select **Control Panel**.</span></span>

3. <span data-ttu-id="1d3b5-182">Выберите **Программы и компоненты**.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-182">Select **Programs and Features**.</span></span>

4. <span data-ttu-id="1d3b5-183">Выберите **Надстройка создания отчетов о нежелательной почте для Microsoft Office Outlook**.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-183">Select **Microsoft Junk E-mail Reporting Add-In for Microsoft Office Outlook**.</span></span>

5. <span data-ttu-id="1d3b5-184">Выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-184">Select **Uninstall**.</span></span>

6. <span data-ttu-id="1d3b5-185">Снова запустите Outlook, чтобы убедиться, что надстройка больше не отображается в ленте.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-185">Start Outlook again to confirm that the add-in is no longer displayed on your Outlook ribbon.</span></span>

### <a name="uninstall-the-junk-email-reporting-add-in-by-running-the-windows-installer-package"></a><span data-ttu-id="1d3b5-186">Удаление надстройки создания отчетов о нежелательной почте с помощью пакета установщика Windows</span><span class="sxs-lookup"><span data-stu-id="1d3b5-186">Uninstall the Junk Email Reporting Add-in by Running the Windows Installer Package</span></span>

1. <span data-ttu-id="1d3b5-187">Закройте Outlook на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-187">On your computer, close Outlook.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1d3b5-188">Если во время удаления Outlook будет работать, его нужно будет перезапустить, чтобы надстройка была полностью удалена.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-188">If Outlook is running during the uninstall process, it will need to be restarted in order for the add-in to be completely uninstalled.</span></span>

2. <span data-ttu-id="1d3b5-189">Запустите повторно файл MSI, который вы запускали для установки надстройки.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-189">Re-run the .msi file you previously ran to install the add-in.</span></span>

   <span data-ttu-id="1d3b5-190">В разделе **сведения** [надстройки создания отчетов о нежелательной почте для Microsoft Outlook](https://www.microsoft.com/download/details.aspx?id=18275)Скачайте соответствующий MSI-файл для вашей версии Office, а затем дважды щелкните MSI-файл.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-190">(In the **Details** section at [Microsoft Junk E-mail Reporting Add-In for Microsoft Outlook](https://www.microsoft.com/download/details.aspx?id=18275), download the appropriate .msi file for your version of Office, and then double-click the .msi file.)</span></span>

3. <span data-ttu-id="1d3b5-191">Следуйте указаниям для удаления надстройки.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-191">Follow the prompts to uninstall the add-in.</span></span>

4. <span data-ttu-id="1d3b5-192">Снова запустите Outlook, чтобы убедиться, что надстройка больше не отображается в ленте.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-192">Start Outlook again to confirm that the add-in is no longer displayed on your Outlook ribbon.</span></span>

### <a name="uninstall-the-junk-email-reporting-add-in-in-silent-mode"></a><span data-ttu-id="1d3b5-193">Удаление надстройки создания отчетов о нежелательной почте в автоматическом режиме</span><span class="sxs-lookup"><span data-stu-id="1d3b5-193">Uninstall the Junk Email Reporting Add-in in Silent Mode</span></span>

1. <span data-ttu-id="1d3b5-194">Закройте Outlook на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-194">On your computer, close Outlook.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1d3b5-195">Если во время удаления Outlook будет работать, его нужно будет перезапустить, чтобы надстройка была полностью удалена.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-195">If Outlook is running during the uninstall process, it will need to be restarted in order for the add-in to be completely uninstalled.</span></span>

2. <span data-ttu-id="1d3b5-196">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-196">Open a command prompt.</span></span>

3. <span data-ttu-id="1d3b5-197">Укажите следующий параметр командной строки.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-197">Specify the following command line parameter:</span></span>

   <span data-ttu-id="1d3b5-198">Outlook x86:`msiexec /x JunkReportingAdd-in.x86-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`</span><span class="sxs-lookup"><span data-stu-id="1d3b5-198">Outlook x86: `msiexec /x JunkReportingAdd-in.x86-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`</span></span>

   <span data-ttu-id="1d3b5-199">Outlook x64:`msiexec /x JunkReportingAdd-in.x64-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`</span><span class="sxs-lookup"><span data-stu-id="1d3b5-199">Outlook x64: `msiexec /x JunkReportingAdd-in.x64-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`</span></span>

4. <span data-ttu-id="1d3b5-200">Снова запустите Outlook, чтобы убедиться, что надстройка больше не отображается в ленте.</span><span class="sxs-lookup"><span data-stu-id="1d3b5-200">Start Outlook again to confirm that the add-in is no longer displayed on your Outlook ribbon.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="1d3b5-201">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="1d3b5-201">For more information</span></span>

[<span data-ttu-id="1d3b5-202">Отправка отчетов о нежелательных сообщениях в корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1d3b5-202">Report junk email messages to Microsoft</span></span>](report-junk-email-messages-to-microsoft.md)

[<span data-ttu-id="1d3b5-203">Сведения об устранении неполадок и поддержке</span><span class="sxs-lookup"><span data-stu-id="1d3b5-203">Troubleshooting and support information</span></span>](troubleshooting-and-support-information.md)
