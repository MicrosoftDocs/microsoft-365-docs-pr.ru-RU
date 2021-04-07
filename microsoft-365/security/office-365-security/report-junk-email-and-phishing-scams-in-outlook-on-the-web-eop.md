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
ms.openlocfilehash: 933387dd32a6c1ca1e27ee11e4a9384615e8fdec
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615217"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="5ba99-103">Сообщение нежелательной и фишинговой почты в Outlook в Интернете в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5ba99-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5ba99-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="5ba99-104">**Applies to**</span></span>
- [<span data-ttu-id="5ba99-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5ba99-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5ba99-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="5ba99-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5ba99-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ba99-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="5ba99-108">В microsoft 365 организациях с почтовыми ящиками в Exchange [](../../enterprise/hybrid-modern-auth-overview.md)Online или в локальном почтовом ящике с использованием гибридной современной проверки подлинности вы можете отправлять ложные срабатывания (хорошая электронная почта помечена как спам), ложные негативы (разрешена плохая электронная почта) и фишинговые сообщения в Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="5ba99-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5ba99-109">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="5ba99-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5ba99-110">Для наилучшего использования пользовательской отправки рекомендуется использовать надстройки Report Message и Report Phishing. Дополнительные [сведения см.](./enable-the-report-message-add-in.md) в [](./enable-the-report-phish-add-in.md) дополнительных сведениях.</span><span class="sxs-lookup"><span data-stu-id="5ba99-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](./enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](./enable-the-report-phish-add-in.md) for more information.</span></span>

- <span data-ttu-id="5ba99-111">Если вы администратор в организации с почтовыми ящиками Exchange Online, рекомендуем использовать портал Отправки в Центре & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="5ba99-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="5ba99-112">Дополнительные сведения см. в материале Использование отправки администратора для отправки в Корпорацию Майкрософт подозрительных [спама, фишинга, URL-адресов и файлов.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="5ba99-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="5ba99-113">Администраторы могут отключить или включить возможность для пользователей сообщать о сообщениях в Microsoft в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="5ba99-113">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="5ba99-114">Подробные сведения см. в разделе Отключение или включить нежелательные сообщения электронной почты в [Outlook в веб-разделе](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) в этой статье.</span><span class="sxs-lookup"><span data-stu-id="5ba99-114">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="5ba99-115">Вы можете настроить сообщения, которые будут скопированы или перенаправлены в почтовый ящик, который указан.</span><span class="sxs-lookup"><span data-stu-id="5ba99-115">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="5ba99-116">Дополнительные сведения см. [в материале Политики отправки пользователей.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="5ba99-116">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="5ba99-117">Дополнительные сведения об отчетах о сообщениях в Корпорации Майкрософт см. в материалах [Report messages and files to Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="5ba99-117">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="5ba99-118">Отключить или включить нежелательные сообщения электронной почты в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="5ba99-118">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="5ba99-119">По умолчанию пользователи могут сообщать о ложных срабатываниях нежелательной почты, ложных негативах и фишинговых сообщениях в Microsoft для анализа в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="5ba99-119">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="5ba99-120">Администраторы могут настраивать Outlook для политик веб-почтовых ящиков в Exchange Online PowerShell, чтобы пользователи не сообщали о ложных срабатываваемых спама и нежелательных ложных негативах в Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5ba99-120">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="5ba99-121">Нельзя отключить возможность для пользователей сообщать о фишинговых сообщениях в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5ba99-121">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5ba99-122">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="5ba99-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5ba99-123">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="5ba99-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="5ba99-124">Вам необходимо получить разрешения в Exchange Online, прежде чем вы сможете сделать процедуры в этой статье.</span><span class="sxs-lookup"><span data-stu-id="5ba99-124">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="5ba99-125">В частности, вам нужны  роли **политики** получателей или получателей  почты, которые по умолчанию назначены группам ролей управления и управления получателями организации. </span><span class="sxs-lookup"><span data-stu-id="5ba99-125">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="5ba99-126">Дополнительные сведения о группах ролей в Exchange Online см. в рублях [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) и [Modify role groups in Exchange Online.](/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="5ba99-126">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="5ba99-127">Каждая организация имеет политику по умолчанию с именем OwaMailboxPolicy-Default, но можно создавать настраиваемые политики.</span><span class="sxs-lookup"><span data-stu-id="5ba99-127">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="5ba99-128">Пользовательские политики применяются к пользователям с масштабами перед политикой по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5ba99-128">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="5ba99-129">Дополнительные сведения о политиках Outlook для веб-почтовых ящиков см. в странице Outlook в политиках веб-почтовых [ящиков в Exchange Online.](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)</span><span class="sxs-lookup"><span data-stu-id="5ba99-129">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="5ba99-130">Отключение нежелательной отчетности по электронной почте не удаляет возможность пометить сообщение как нежелательное или нежелательное в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="5ba99-130">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="5ba99-131">Выбор сообщения в папке нежелательной почты и нажатие кнопки **Не** нежелательной не нежелательной по-прежнему перемещает сообщение обратно \>  в папку "Входящие".</span><span class="sxs-lookup"><span data-stu-id="5ba99-131">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="5ba99-132">Выбор сообщения в любой другой папке  электронной почты и нажатие нежелательной нежелательной почты по-прежнему перемещает сообщение \>  в папку нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="5ba99-132">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="5ba99-133">Больше нет возможности сообщить об этом сообщении в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5ba99-133">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="5ba99-134">Использование Exchange Online PowerShell для отключения или отключения нежелательной отчетности по электронной почте в Outlook в Интернете</span><span class="sxs-lookup"><span data-stu-id="5ba99-134">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="5ba99-135">Чтобы найти существующий Outlook в политиках веб-почтовых ящиков и состоянии нежелательной отчетности по электронной почте, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5ba99-135">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="5ba99-136">Чтобы отключить или включить нежелательные сообщения электронной почты в Outlook в Интернете, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="5ba99-136">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="5ba99-137">В этом примере отключает нежелательные сообщения электронной почты в политике по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5ba99-137">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="5ba99-138">В этом примере включается нежелательное сообщение электронной почты в настраиваемой политике под названием Contoso Managers.</span><span class="sxs-lookup"><span data-stu-id="5ba99-138">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="5ba99-139">Подробные сведения о синтаксисах и параметрах см. в [сведениях Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) и [Set-OwaMailboxPolicy.](/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="5ba99-139">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="5ba99-140">Как убедиться, что все получилось?</span><span class="sxs-lookup"><span data-stu-id="5ba99-140">How do you know this worked?</span></span>

<span data-ttu-id="5ba99-141">Чтобы убедиться, что вы успешно включили или отключили нежелательные сообщения электронной почты в Outlook в Интернете, используйте следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5ba99-141">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="5ba99-142">В Exchange Online PowerShell запустите следующую команду и проверьте значение **свойства ReportJunkEmailEnabled:**</span><span class="sxs-lookup"><span data-stu-id="5ba99-142">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="5ba99-143">Откройте почтовый ящик пострадавшего пользователя в Outlook в Интернете, выберите  сообщение в почтовом ящике, нажмите нежелательной почты и убедитесь, что сообщение в Корпорацию Майкрософт отображается или не \>  отображается.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5ba99-143">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="5ba99-144">Откройте почтовый ящик пострадавшего пользователя в Outlook в Интернете, выберите сообщение  в папке нежелательной почты, щелкните нежелательной почты и убедитесь, что запрос на сообщение в Корпорацию Майкрософт отображается или не \>  отображается.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5ba99-144">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="5ba99-145"><sup>\*</sup> Пользователи могут скрыть запрос, чтобы сообщить о сообщении, но при этом сообщить о сообщении.</span><span class="sxs-lookup"><span data-stu-id="5ba99-145"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="5ba99-146">Чтобы проверить этот параметр в Outlook в Интернете:</span><span class="sxs-lookup"><span data-stu-id="5ba99-146">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="5ba99-147">Щелкните **Параметры** ![ Outlook на значке веб-параметров Просмотр всех ](../../media/owa-settings-icon.png) \> **параметров Outlook** \> **нежелательной почты**.</span><span class="sxs-lookup"><span data-stu-id="5ba99-147">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="5ba99-148">В разделе **Отчеты** проверьте значение: **Спросите меня перед отправкой отчета**.</span><span class="sxs-lookup"><span data-stu-id="5ba99-148">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Outlook для параметров отчетов о нежелательной почте в Интернете](../../media/owa-junk-email-reporting-options.png)