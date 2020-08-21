---
title: Настройка почтового ящика для отправки нежелательной почты и фишинговых сообщений пользователем
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
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как настроить почтовый ящик для сбора спама и фишинговых сообщений, о которых сообщают пользователи.
ms.openlocfilehash: 76264801820b6a41ee744a8adcc3b3b48a8e9479
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826745"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="d0863-103">Настройка почтового ящика для отправки нежелательной и фишинговых сообщений в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d0863-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="d0863-104">В организациях Microsoft 365 с почтовыми ящиками Exchange Online можно указать почтовый ящик, который будет получать сообщения, которые будут отправлять сообщения, которые пользователи делятся как вредоносные или не вредоносные.</span><span class="sxs-lookup"><span data-stu-id="d0863-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="d0863-105">Этот почтовый ящик позволяет перехватывать сообщения (отправку только в пользовательский почтовый ящик) и получать их копии (отправку в пользовательский почтовый ящик и майкрософт).</span><span class="sxs-lookup"><span data-stu-id="d0863-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="d0863-106">Эта функция работает со следующими возможностями создания отчетов в сообщении:</span><span class="sxs-lookup"><span data-stu-id="d0863-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="d0863-107">Надстройка Report Message</span><span class="sxs-lookup"><span data-stu-id="d0863-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="d0863-108">[Встроенные отчеты в Outlook в Интернете](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (ранее Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="d0863-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- <span data-ttu-id="d0863-109">Встроенные отчеты в Outlook для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="d0863-109">Built-in reporting in Outlook for iOS and Android</span></span>

  > [!NOTE]
  > <span data-ttu-id="d0863-110">Если отчеты были [отключены в Outlook в Интернете,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)включение отправки пользователями для этих сообщений переозадает эту настройку и позволит пользователям снова сообщать о сообщениях в Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="d0863-110">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="d0863-111">Вы также можете настроить средства создания сторонних сообщений на пересылку сообщений в указанный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="d0863-111">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="d0863-112">Доставка сообщения пользователя, отправленных в пользовательский почтовый ящик, а не в корпорацию Майкрософт позволяет администраторам выборочно и вручную отправлять корпорации Майкрософт отчеты о сообщениях в корпорацию [Майкрософт с помощью отправки администратором.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="d0863-112">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d0863-113">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="d0863-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d0863-114">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="d0863-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d0863-115">Чтобы перейти непосредственно на страницу **отправки** пользователей, используйте <https://protection.office.com/userSubmissionsReportMessage> этот параметр.</span><span class="sxs-lookup"><span data-stu-id="d0863-115">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="d0863-116">Чтобы вы могли выполнить процедуры, упомянутые в этой теме, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="d0863-116">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="d0863-117">Чтобы изменить конфигурацию отправленных пользователей, вы должны быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="d0863-117">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="d0863-118">**Управление организацией** или **Администратор безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d0863-118">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="d0863-119">**Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="d0863-119">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="d0863-120">Для доступа пользователей только для чтения вы должны быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="d0863-120">For read-only access to User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="d0863-121">**Средство считывания сведений о безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d0863-121">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="d0863-122">**Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="d0863-122">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="d0863-123">Использование Центра безопасности & Security Для настройки почтового ящика отправленных приложений</span><span class="sxs-lookup"><span data-stu-id="d0863-123">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="d0863-124">В Центре безопасности & соответствия требованиям перейдите в раздел **Отправку** \> **пользовательских ресурсов** \> **политики управления угрозами.**</span><span class="sxs-lookup"><span data-stu-id="d0863-124">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="d0863-125">На **появившейся** странице отправки пользователей выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="d0863-125">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="d0863-126">а)</span><span class="sxs-lookup"><span data-stu-id="d0863-126">a.</span></span> <span data-ttu-id="d0863-127">**Включите функцию Report Message для Outlook (рекомендуется). Выберите**этот параметр, если используется надстройка Report Message или встроенные отчеты в Outlook в Интернете, а затем настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="d0863-127">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="d0863-128">**Настройте сообщение подтверждения пользователя: щелкните**эту ссылку.</span><span class="sxs-lookup"><span data-stu-id="d0863-128">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="d0863-129">В **появившейся окне** "Настройка" настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="d0863-129">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="d0863-130">**До отправки:** в **окнах заголовка** и подтверждения введите текст с описанием, который будет отображаться для пользователей, прежде чем сообщать о сообщении с помощью надстройки Report Message. **Confirmation message**</span><span class="sxs-lookup"><span data-stu-id="d0863-130">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="d0863-131">Переменная %type% позволяет включить тип отправки ("нежелательное", "не нежелательное", "фишинг" и т. д.).</span><span class="sxs-lookup"><span data-stu-id="d0863-131">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="d0863-132">Как было отмечено ранее, если вы выбираете вариант, который отправляет отчетные сообщения в корпорацию Майкрософт, в уведомление также будет добавлен следующий текст:</span><span class="sxs-lookup"><span data-stu-id="d0863-132">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="d0863-133">Ваши сообщения будут отправлены в корпорацию Майкрософт для анализа в качестве образца.</span><span class="sxs-lookup"><span data-stu-id="d0863-133">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="d0863-134">Некоторые сообщения могут содержать личные или конфиденциальные данные.</span><span class="sxs-lookup"><span data-stu-id="d0863-134">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="d0863-135">**After submission**: Click ![ Expand ](../../media/scc-expand-icon.png) icon.</span><span class="sxs-lookup"><span data-stu-id="d0863-135">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="d0863-136">В **окнах сообщений** **"Заголовок" и** "Подтверждение" введите текст с описанием, который будет отображаться для пользователей после сообщения с помощью надстройки Report Message.</span><span class="sxs-lookup"><span data-stu-id="d0863-136">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="d0863-137">Чтобы включить тип отправки, можно использовать переменную %type%.</span><span class="sxs-lookup"><span data-stu-id="d0863-137">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="d0863-138">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d0863-138">When you're finished, click **Save**.</span></span> <span data-ttu-id="d0863-139">Чтобы очистить эти значения, нажмите **кнопку "Восстановить"** на **странице "Отправки пользователей".**</span><span class="sxs-lookup"><span data-stu-id="d0863-139">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="d0863-140">**Отправьте переданные сообщения: выберите**один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="d0863-140">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="d0863-141">**Microsoft (рекомендуется).** Почтовый ящик отправки пользователей не используется (все отправленные сообщения об ошибках корпорации Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="d0863-141">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="d0863-142">**Майкрософт и пользовательский почтовый**ящик: в появившемся поле введите адрес электронной почты существующего почтового ящика Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d0863-142">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="d0863-143">Группы рассылки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="d0863-143">Distribution groups are not allowed.</span></span> <span data-ttu-id="d0863-144">Пользовательские надстройки поступат в корпорацию Майкрософт анализ и в пользовательский почтовый ящик для анализа администратором или группой операций безопасности.</span><span class="sxs-lookup"><span data-stu-id="d0863-144">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="d0863-145">**Настраиваемый**почтовый ящик: в поле, в котором отобразится сообщение, введите адрес электронной почты существующего почтового ящика Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d0863-145">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="d0863-146">Группы рассылки не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="d0863-146">Distribution groups are not allowed.</span></span> <span data-ttu-id="d0863-147">Используйте этот вариант, если сообщение сначала попало только администратору или группе операций безопасности.</span><span class="sxs-lookup"><span data-stu-id="d0863-147">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="d0863-148">Сообщения не будут отправляться в корпорацию Майкрософт, пока администратор не пересылает его самим.</span><span class="sxs-lookup"><span data-stu-id="d0863-148">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="d0863-149">Государственные организации США (GCC, GCC-H и DoD) могут настраивать только **настраиваемые почтовые ящики.**</span><span class="sxs-lookup"><span data-stu-id="d0863-149">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="d0863-150">Другие два параметра отключены.</span><span class="sxs-lookup"><span data-stu-id="d0863-150">The other two options are disabled.</span></span> 

      <span data-ttu-id="d0863-151">По завершении нажмите кнопку Confirm **.**</span><span class="sxs-lookup"><span data-stu-id="d0863-151">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="d0863-152">Если вы [отключили создание отчетов о нежелательной почте в Outlook в Интернете](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) с помощью политик почтовых ящиков Outlook в Интернете, но вы настроили любой из вышеуказанных параметров для отправки отчетов о сообщениях корпорации Майкрософт, пользователи смогут сообщать о них в Майкрософт в Outlook в Интернете с помощью надстройки Report Message.</span><span class="sxs-lookup"><span data-stu-id="d0863-152">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="d0863-153">**Отключение функции Report Message для Outlook:** выберите этот параметр, если вы используете сторонние средства создания отчетов вместо надстройки Report Message или встроенные отчеты в Outlook в Интернете, а затем настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="d0863-153">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="d0863-154">Выберите **использовать этот настраиваемый почтовый ящик для получения уведомлений о пользователях.**</span><span class="sxs-lookup"><span data-stu-id="d0863-154">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="d0863-155">В появившемся поле введите адрес электронной почты существующего почтового ящика, уже существующего в Office 365.</span><span class="sxs-lookup"><span data-stu-id="d0863-155">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="d0863-156">Это должен быть существующий почтовый ящик в Exchange Online, который может принимать электронную почту.</span><span class="sxs-lookup"><span data-stu-id="d0863-156">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="d0863-157">По завершении нажмите кнопку Confirm **.**</span><span class="sxs-lookup"><span data-stu-id="d0863-157">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="d0863-158">Формат отправки сообщений</span><span class="sxs-lookup"><span data-stu-id="d0863-158">Message submission format</span></span>

<span data-ttu-id="d0863-159">Для сообщений, отправляемых в настраиваемые почтовые ящики, необходимо следовать определенному формату отправленных сообщений.</span><span class="sxs-lookup"><span data-stu-id="d0863-159">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="d0863-160">Субъект (название конверта) отправки должен быть в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="d0863-160">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="d0863-161">В отличие от SafetyAPIAction, можно использовать одно из следующих целых значений:</span><span class="sxs-lookup"><span data-stu-id="d0863-161">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="d0863-162">1. Нежелательная почта</span><span class="sxs-lookup"><span data-stu-id="d0863-162">1: Junk</span></span>
- <span data-ttu-id="d0863-163">2. NotJunk</span><span class="sxs-lookup"><span data-stu-id="d0863-163">2: NotJunk</span></span>
- <span data-ttu-id="d0863-164">3: Фишинг</span><span class="sxs-lookup"><span data-stu-id="d0863-164">3: Phish</span></span>

<span data-ttu-id="d0863-165">В следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d0863-165">In the following example:</span></span>

- <span data-ttu-id="d0863-166">Сообщение сообщается как фишинговое сообщение.</span><span class="sxs-lookup"><span data-stu-id="d0863-166">The message is being reported as Phish.</span></span>
- <span data-ttu-id="d0863-167">Идентификатор сетевого сообщения 49871234-6dc6-43e8-abcd-08d797f20abe.</span><span class="sxs-lookup"><span data-stu-id="d0863-167">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="d0863-168">IP-адрес отправителя: 167.220.232.101.</span><span class="sxs-lookup"><span data-stu-id="d0863-168">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="d0863-169">Адрес отправителя является test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d0863-169">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="d0863-170">В теме сообщения указана проверка тестовой отправки фишинга.</span><span class="sxs-lookup"><span data-stu-id="d0863-170">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="d0863-171">Сообщения, которые не следуют этому формату, будут отображаться неправильно на портале отправки.</span><span class="sxs-lookup"><span data-stu-id="d0863-171">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
