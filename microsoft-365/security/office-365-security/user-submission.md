---
title: Выбор почтового ящика для отправки пользователям сообщений о нежелательной почте и фишинговых сообщениях
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
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как настроить почтовый ящик для сбора нежелательных сообщений и фишинговых сообщений, сообщаемых пользователями.
ms.openlocfilehash: 6aa343b337139c4d81f35f78a227634d3b6a8781
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262527"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="a7ea4-103">Выбор почтового ящика для отправки пользователем сообщений о нежелательной почте и фишинговых сообщениях в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a7ea4-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="a7ea4-104">В организациях Microsoft 365 с почтовыми ящиками Exchange Online можно указать почтовый ящик для получения сообщений, которые пользователи сообщают как вредоносные или не являющиеся вредоносными.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="a7ea4-105">Когда пользователи отправляют сообщения с помощью различных параметров отчетов, вы можете использовать этот почтовый ящик для перехвата сообщений (только для личного почтового ящика) или получения копий сообщений (отправить в настраиваемый почтовый ящик и Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="a7ea4-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="a7ea4-106">Эта функция работает со следующими параметрами отчетов о сообщениях:</span><span class="sxs-lookup"><span data-stu-id="a7ea4-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="a7ea4-107">Надстройка "сообщение отчета"</span><span class="sxs-lookup"><span data-stu-id="a7ea4-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="a7ea4-108">[Встроенные отчеты в Outlook в Интернете](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (прежнее название — Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="a7ea4-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

  > [!NOTE]
  > <span data-ttu-id="a7ea4-109">Если отчетность [отключена в Outlook в Интернете](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), то при включении этой функции переопределяется этот параметр и пользователи могут сообщать о сообщениях в Outlook в Интернете еще раз.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-109">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="a7ea4-110">Кроме того, можно настроить сторонние средства создания отчетов для пересылки сообщений в указанный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-110">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="a7ea4-111">Доставка сообщений, отправленных пользователем, в настраиваемый почтовый ящик, а не непосредственно в Майкрософт, позволяет администраторам выборочно и вручную отправлять сообщения в корпорацию Майкрософт с помощью [отправки администратором](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="a7ea4-111">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a7ea4-112">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="a7ea4-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a7ea4-113">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-113">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a7ea4-114">Чтобы перейти непосредственно на страницу " **отправки пользователя** ", используйте <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="a7ea4-114">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="a7ea4-115">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a7ea4-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a7ea4-116">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="a7ea4-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a7ea4-117">Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-117">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="a7ea4-118">Чтобы настроить почтовый ящик для отправки пользователей, необходимо быть участником группы ролей " **Управление организацией** " или " **администратор безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="a7ea4-118">To configure the mailbox for user submissions, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="a7ea4-119">Дополнительные сведения о группах ролей в Центре безопасности и соответствия требованиям см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a7ea4-119">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="a7ea4-120">Использование центра безопасности & соответствия требованиям для настройки почтового ящика отправки пользователя</span><span class="sxs-lookup"><span data-stu-id="a7ea4-120">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="a7ea4-121">В центре безопасности & соответствия требованиям перейдите к разделу пользователь политики **управления угрозами** \> **Policy** \> **User submissions**.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-121">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="a7ea4-122">На появившейся странице " **отправки пользователей** " выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="a7ea4-122">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="a7ea4-123">а.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-123">a.</span></span> <span data-ttu-id="a7ea4-124">**Включить функцию сообщений отчетов для Outlook (рекомендуется)**: Выберите этот параметр, если вы используете надстройку Report Message или встроенную отчетность в Outlook в Интернете, а затем настроили следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="a7ea4-124">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="a7ea4-125">**Настройте сообщение для подтверждения пользователя**. Щелкните эту ссылку.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-125">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="a7ea4-126">В появившемся всплывающем окне **Настройка предупреждающего сообщения** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="a7ea4-126">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="a7ea4-127">**Перед отправкой**: в полях **название** и **сообщение подтверждения** введите описательный текст, который пользователи видят перед отчетом о сообщении с помощью надстройки Report Message.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-127">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="a7ea4-128">Вы можете использовать переменную% типа%, чтобы включить тип отправки (нежелательный, нежелательный, фишинг и т. д.).</span><span class="sxs-lookup"><span data-stu-id="a7ea4-128">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="a7ea4-129">Как отмечалось, при выборе варианта отправки сообщений, отправленных в корпорацию Майкрософт, в уведомление добавляется следующий текст:</span><span class="sxs-lookup"><span data-stu-id="a7ea4-129">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="a7ea4-130">Ваша электронная почта будет отправлена в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-130">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="a7ea4-131">Некоторые сообщения электронной почты могут содержать персональные или конфиденциальные сведения.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-131">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="a7ea4-132">**После отправки**: нажмите ![ развернуть значок ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="a7ea4-132">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="a7ea4-133">В поля **имя** и **Подтверждение** введите описательный текст, который пользователи видят после того, как отчитываться о сообщении с помощью надстройки Report Message.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-133">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="a7ea4-134">Вы можете использовать переменную% типа%, чтобы включить тип отправки.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-134">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="a7ea4-135">Когда закончите, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-135">When you're finished, click **Save**.</span></span> <span data-ttu-id="a7ea4-136">Чтобы очистить эти значения, нажмите кнопку **восстановить** обратно на странице " **Отправка пользователя** ".</span><span class="sxs-lookup"><span data-stu-id="a7ea4-136">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="a7ea4-137">**Отправить сообщения, отправленные в**: сделайте один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="a7ea4-137">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="a7ea4-138">**Майкрософт (рекомендуется)**: почтовый ящик отправки пользователя не используется (все сообщения, о которых сообщалось в корпорацию Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="a7ea4-138">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="a7ea4-139">**Майкрософт и настраиваемый почтовый ящик**: в появившемся поле введите адрес электронной почты существующего почтового ящика Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-139">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="a7ea4-140">Группы рассылки не разрешены.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-140">Distribution groups are not allowed.</span></span> <span data-ttu-id="a7ea4-141">Пользовательские отправки отправляются в корпорацию Майкрософт для анализа и в настраиваемый почтовый ящик для анализа администратором или группой действий по обеспечению безопасности.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-141">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="a7ea4-142">**Настраиваемый почтовый ящик**: в появившемся поле введите адрес электронной почты существующего почтового ящика Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-142">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="a7ea4-143">Группы рассылки не разрешены.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-143">Distribution groups are not allowed.</span></span> <span data-ttu-id="a7ea4-144">Используйте этот параметр, если вы хотите, чтобы сообщение сначала заходило только в группе "Администраторы" или "операции безопасности" для анализа.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-144">Use this option if you want the message to only go to the admin or security operations team for analysis first.</span></span> <span data-ttu-id="a7ea4-145">Сообщения не будут передаваться в корпорацию Майкрософт, если администратор не перенаправлял их.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-145">Messages will not go to Microsoft unless the admin forwards it.</span></span>

        <span data-ttu-id="a7ea4-146">Когда все будет готово, нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-146">When you're finished, click **Confirm**.</span></span>

        ![Отправка сообщений, отправленных в корпорацию Майкрософт, и настраиваемого почтового ящика](../../media/user-submission-enable-outlook-report-message.png)

     > [!CAUTION]
     > <span data-ttu-id="a7ea4-148">Если вы [отключили отчеты о нежелательной почте в Outlook в Интернете](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) с помощью Outlook в веб-политиках почтовых ящиков, но настроили любой из предыдущих параметров для отправки отчетов в корпорацию Майкрософт, пользователи смогут отправлять отчеты в корпорацию Майкрософт в Outlook в Интернете с помощью надстройки Report Message.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-148">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="a7ea4-149">**Отключить функцию сообщений отчетов для Outlook**: Выберите этот параметр, если вы используете сторонние средства создания отчетов вместо надстройки сообщений отчетов или встроенных отчетов в Outlook в Интернете, а затем настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="a7ea4-149">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="a7ea4-150">Выберите **использовать этот настраиваемый почтовый ящик для получения данных о отправленных пользователем сообщениях**.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-150">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="a7ea4-151">В появившемся поле введите адрес электронной почты существующего почтового ящика, который уже находится в Office 365.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-151">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="a7ea4-152">Это должен быть существующий почтовый ящик в Exchange Online, который может получать электронную почту.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-152">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="a7ea4-153">Когда все будет готово, нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-153">When you're finished, click **Confirm**.</span></span>

      ![Отправка сообщений, отправленных в настраиваемый почтовый ящик, с помощью сторонних средств](../../media/user-submission-disable-outlook-report-message.png)
     
## <a name="message-submission-format"></a><span data-ttu-id="a7ea4-155">Формат отправки сообщений</span><span class="sxs-lookup"><span data-stu-id="a7ea4-155">Message submission format</span></span>

<span data-ttu-id="a7ea4-156">Сообщения, отправляемые в пользовательские почтовые ящики, должны соответствовать определенному почтовому формату отправки.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-156">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="a7ea4-157">Тема (название конверта) отправки должна иметь следующий формат:</span><span class="sxs-lookup"><span data-stu-id="a7ea4-157">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`{(int)safetyApiAction}|{networkId}|{senderIp}|{fromAddress}|({subject.Substring(0, Math.Min(subjectLen, subject.Length))})`

<span data-ttu-id="a7ea4-158">Сафетяпиактион:</span><span class="sxs-lookup"><span data-stu-id="a7ea4-158">were SafetyApiAction is:</span></span>

- <span data-ttu-id="a7ea4-159">Нежелательная = 1</span><span class="sxs-lookup"><span data-stu-id="a7ea4-159">Junk = 1</span></span>
- <span data-ttu-id="a7ea4-160">Нотжунк = 2</span><span class="sxs-lookup"><span data-stu-id="a7ea4-160">NotJunk = 2</span></span>
- <span data-ttu-id="a7ea4-161">Фишинг = 3</span><span class="sxs-lookup"><span data-stu-id="a7ea4-161">Phish = 3</span></span>

<span data-ttu-id="a7ea4-162">В следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a7ea4-162">In the following example:</span></span>

- <span data-ttu-id="a7ea4-163">Сообщение сообщается как "фишинг".</span><span class="sxs-lookup"><span data-stu-id="a7ea4-163">The message is being reported as Phish.</span></span>
- <span data-ttu-id="a7ea4-164">ИДЕНТИФИКАТОР сетевого сообщения — 49871234-6dc6-43e8-ABCD-08d797f20abe.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-164">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="a7ea4-165">IP-адрес отправителя — 167.220.232.101.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-165">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="a7ea4-166">Адрес отправителя — test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-166">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="a7ea4-167">Тема сообщения: "проверка передачи по поддельному фишингу"</span><span class="sxs-lookup"><span data-stu-id="a7ea4-167">The message's email subject is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="a7ea4-168">Сообщения, которые не соответствуют этому формату, не будут правильно отображаться на портале отправки.</span><span class="sxs-lookup"><span data-stu-id="a7ea4-168">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
