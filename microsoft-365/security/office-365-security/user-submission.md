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
ms.openlocfilehash: e9550ce6357ddf19041e752c17e8bd844cba1a11
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726496"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="fe16e-103">Выбор почтового ящика для отправки пользователем сообщений о нежелательной почте и фишинговых сообщениях в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="fe16e-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="fe16e-104">В организациях Microsoft 365 с почтовыми ящиками Exchange Online можно указать почтовый ящик для получения сообщений, которые пользователи сообщают как вредоносные или не являющиеся вредоносными.</span><span class="sxs-lookup"><span data-stu-id="fe16e-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="fe16e-105">Когда пользователи отправляют сообщения с помощью различных параметров отчетов, вы можете использовать этот почтовый ящик для перехвата сообщений (только для личного почтового ящика) или получения копий сообщений (отправить в настраиваемый почтовый ящик и Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="fe16e-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="fe16e-106">Эта функция работает со следующими параметрами отчетов о сообщениях:</span><span class="sxs-lookup"><span data-stu-id="fe16e-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="fe16e-107">Надстройка "сообщение отчета"</span><span class="sxs-lookup"><span data-stu-id="fe16e-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="fe16e-108">[Встроенные отчеты в Outlook в Интернете](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (прежнее название — Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="fe16e-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

  > [!NOTE]
  > <span data-ttu-id="fe16e-109">Если отчетность [отключена в Outlook в Интернете](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), то при включении этой функции переопределяется этот параметр и пользователи могут сообщать о сообщениях в Outlook в Интернете еще раз.</span><span class="sxs-lookup"><span data-stu-id="fe16e-109">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="fe16e-110">Кроме того, можно настроить сторонние средства создания отчетов для пересылки сообщений в указанный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="fe16e-110">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="fe16e-111">Доставка сообщений, отправленных пользователем, в настраиваемый почтовый ящик, а не непосредственно в Майкрософт, позволяет администраторам выборочно и вручную отправлять сообщения в корпорацию Майкрософт с помощью [отправки администратором](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="fe16e-111">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fe16e-112">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="fe16e-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fe16e-113">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="fe16e-113">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="fe16e-114">Чтобы перейти непосредственно на страницу " **отправки пользователя** ", используйте <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="fe16e-114">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="fe16e-115">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="fe16e-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="fe16e-116">Чтобы подключиться к автономному EOP PowerShell, см. раздел [Подключение к PowerShell Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="fe16e-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="fe16e-117">Прежде чем выполнять процедуры, описанные в этом разделе, необходимо назначить разрешения.</span><span class="sxs-lookup"><span data-stu-id="fe16e-117">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="fe16e-118">Чтобы изменить конфигурацию для отправки пользователей, необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="fe16e-118">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="fe16e-119">**Управление организацией** или **администратор безопасности** в [центре безопасности & соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="fe16e-119">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="fe16e-120">**Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="fe16e-120">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="fe16e-121">Для доступа к отправку пользователей только для чтения необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="fe16e-121">For read-only access to User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="fe16e-122">**Средство чтения безопасности** в [центре безопасности & соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="fe16e-122">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="fe16e-123">**Управление организацией только с просмотром** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="fe16e-123">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="fe16e-124">Использование центра безопасности & соответствия требованиям для настройки почтового ящика отправки пользователя</span><span class="sxs-lookup"><span data-stu-id="fe16e-124">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="fe16e-125">В центре безопасности & соответствия требованиям перейдите к разделу пользователь политики **управления угрозами** \> **Policy** \> **User submissions**.</span><span class="sxs-lookup"><span data-stu-id="fe16e-125">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="fe16e-126">На появившейся странице " **отправки пользователей** " выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="fe16e-126">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="fe16e-127">а.</span><span class="sxs-lookup"><span data-stu-id="fe16e-127">a.</span></span> <span data-ttu-id="fe16e-128">**Включить функцию сообщений отчетов для Outlook (рекомендуется)**: Выберите этот параметр, если вы используете надстройку Report Message или встроенную отчетность в Outlook в Интернете, а затем настроили следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fe16e-128">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="fe16e-129">**Настройте сообщение для подтверждения пользователя**. Щелкните эту ссылку.</span><span class="sxs-lookup"><span data-stu-id="fe16e-129">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="fe16e-130">В появившемся всплывающем окне **Настройка предупреждающего сообщения** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fe16e-130">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="fe16e-131">**Перед отправкой**: в полях **название** и **сообщение подтверждения** введите описательный текст, который пользователи видят перед отчетом о сообщении с помощью надстройки Report Message.</span><span class="sxs-lookup"><span data-stu-id="fe16e-131">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="fe16e-132">Вы можете использовать переменную% типа%, чтобы включить тип отправки (нежелательный, нежелательный, фишинг и т. д.).</span><span class="sxs-lookup"><span data-stu-id="fe16e-132">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="fe16e-133">Как отмечалось, при выборе варианта отправки сообщений, отправленных в корпорацию Майкрософт, в уведомление добавляется следующий текст:</span><span class="sxs-lookup"><span data-stu-id="fe16e-133">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="fe16e-134">Ваша электронная почта будет отправлена в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="fe16e-134">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="fe16e-135">Некоторые сообщения электронной почты могут содержать персональные или конфиденциальные сведения.</span><span class="sxs-lookup"><span data-stu-id="fe16e-135">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="fe16e-136">**После отправки**: нажмите ![ развернуть значок ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="fe16e-136">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="fe16e-137">В поля **имя** и **Подтверждение** введите описательный текст, который пользователи видят после того, как отчитываться о сообщении с помощью надстройки Report Message.</span><span class="sxs-lookup"><span data-stu-id="fe16e-137">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="fe16e-138">Вы можете использовать переменную% типа%, чтобы включить тип отправки.</span><span class="sxs-lookup"><span data-stu-id="fe16e-138">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="fe16e-139">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fe16e-139">When you're finished, click **Save**.</span></span> <span data-ttu-id="fe16e-140">Чтобы очистить эти значения, нажмите кнопку **восстановить** обратно на странице " **Отправка пользователя** ".</span><span class="sxs-lookup"><span data-stu-id="fe16e-140">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="fe16e-141">**Отправить сообщения, отправленные в**: сделайте один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="fe16e-141">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="fe16e-142">**Майкрософт (рекомендуется)**: почтовый ящик отправки пользователя не используется (все сообщения, о которых сообщалось в корпорацию Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="fe16e-142">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="fe16e-143">**Майкрософт и настраиваемый почтовый ящик**: в появившемся поле введите адрес электронной почты существующего почтового ящика Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fe16e-143">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="fe16e-144">Группы рассылки не разрешены.</span><span class="sxs-lookup"><span data-stu-id="fe16e-144">Distribution groups are not allowed.</span></span> <span data-ttu-id="fe16e-145">Пользовательские отправки отправляются в корпорацию Майкрософт для анализа и в настраиваемый почтовый ящик для анализа администратором или группой действий по обеспечению безопасности.</span><span class="sxs-lookup"><span data-stu-id="fe16e-145">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="fe16e-146">**Настраиваемый почтовый ящик**: в появившемся поле введите адрес электронной почты существующего почтового ящика Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fe16e-146">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="fe16e-147">Группы рассылки не разрешены.</span><span class="sxs-lookup"><span data-stu-id="fe16e-147">Distribution groups are not allowed.</span></span> <span data-ttu-id="fe16e-148">Используйте этот параметр, если вы хотите, чтобы сообщение сначала заходило только на администрирование или в группу "операции по обеспечению безопасности" для анализа.</span><span class="sxs-lookup"><span data-stu-id="fe16e-148">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="fe16e-149">Сообщения не будут передаваться в корпорацию Майкрософт, если администратор не переадресует себя.</span><span class="sxs-lookup"><span data-stu-id="fe16e-149">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="fe16e-150">В организациях правительства США (GCC, GCC-H и DoD) можно настраивать только **личный почтовый ящик**.</span><span class="sxs-lookup"><span data-stu-id="fe16e-150">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="fe16e-151">Два других параметра отключены.</span><span class="sxs-lookup"><span data-stu-id="fe16e-151">The other two options are disabled.</span></span> 

      <span data-ttu-id="fe16e-152">Когда все будет готово, нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="fe16e-152">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="fe16e-153">Если вы [отключили отчеты о нежелательной почте в Outlook в Интернете](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) с помощью Outlook в веб-политиках почтовых ящиков, но настроили любой из предыдущих параметров для отправки отчетов в корпорацию Майкрософт, пользователи смогут отправлять отчеты в корпорацию Майкрософт в Outlook в Интернете с помощью надстройки Report Message.</span><span class="sxs-lookup"><span data-stu-id="fe16e-153">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="fe16e-154">**Отключить функцию сообщений отчетов для Outlook**: Выберите этот параметр, если вы используете сторонние средства создания отчетов вместо надстройки сообщений отчетов или встроенных отчетов в Outlook в Интернете, а затем настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fe16e-154">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="fe16e-155">Выберите **использовать этот настраиваемый почтовый ящик для получения данных о отправленных пользователем сообщениях**.</span><span class="sxs-lookup"><span data-stu-id="fe16e-155">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="fe16e-156">В появившемся поле введите адрес электронной почты существующего почтового ящика, который уже находится в Office 365.</span><span class="sxs-lookup"><span data-stu-id="fe16e-156">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="fe16e-157">Это должен быть существующий почтовый ящик в Exchange Online, который может получать электронную почту.</span><span class="sxs-lookup"><span data-stu-id="fe16e-157">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="fe16e-158">Когда все будет готово, нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="fe16e-158">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="fe16e-159">Формат отправки сообщений</span><span class="sxs-lookup"><span data-stu-id="fe16e-159">Message submission format</span></span>

<span data-ttu-id="fe16e-160">Сообщения, отправляемые в пользовательские почтовые ящики, должны соответствовать определенному почтовому формату отправки.</span><span class="sxs-lookup"><span data-stu-id="fe16e-160">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="fe16e-161">Тема (название конверта) отправки должна иметь следующий формат:</span><span class="sxs-lookup"><span data-stu-id="fe16e-161">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessgeId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="fe16e-162">Сафетяпиактион — одно из следующих целых значений:</span><span class="sxs-lookup"><span data-stu-id="fe16e-162">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="fe16e-163">1: Нежелательная почта</span><span class="sxs-lookup"><span data-stu-id="fe16e-163">1: Junk</span></span>
- <span data-ttu-id="fe16e-164">2: Нотжунк</span><span class="sxs-lookup"><span data-stu-id="fe16e-164">2: NotJunk</span></span>
- <span data-ttu-id="fe16e-165">3: Фишинг</span><span class="sxs-lookup"><span data-stu-id="fe16e-165">3: Phish</span></span>

<span data-ttu-id="fe16e-166">В следующем примере:</span><span class="sxs-lookup"><span data-stu-id="fe16e-166">In the following example:</span></span>

- <span data-ttu-id="fe16e-167">Сообщение сообщается как "фишинг".</span><span class="sxs-lookup"><span data-stu-id="fe16e-167">The message is being reported as Phish.</span></span>
- <span data-ttu-id="fe16e-168">ИДЕНТИФИКАТОР сетевого сообщения — 49871234-6dc6-43e8-ABCD-08d797f20abe.</span><span class="sxs-lookup"><span data-stu-id="fe16e-168">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="fe16e-169">IP-адрес отправителя — 167.220.232.101.</span><span class="sxs-lookup"><span data-stu-id="fe16e-169">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="fe16e-170">Адрес отправителя — test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="fe16e-170">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="fe16e-171">Строка темы сообщения: "проверка передачи фишинга"</span><span class="sxs-lookup"><span data-stu-id="fe16e-171">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="fe16e-172">Сообщения, которые не соответствуют этому формату, не будут правильно отображаться на портале отправки.</span><span class="sxs-lookup"><span data-stu-id="fe16e-172">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
