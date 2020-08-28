---
title: Выбор почтового ящика для отправки пользователям сообщений о нежелательной почте и фишинговых сообщениях
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
description: Администраторы могут узнать, как настроить почтовый ящик для сбора нежелательных сообщений и фишинговых сообщений, сообщаемых пользователями.
ms.openlocfilehash: 458938105d03cb82dfa4e9a7824f8b026fddec5d
ms.sourcegitcommit: 89b2ad0793c68415f178b8792a9757b9448345a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2020
ms.locfileid: "47294757"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="27187-103">Выбор почтового ящика для отправки пользователем сообщений о нежелательной почте и фишинговых сообщениях в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="27187-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="27187-104">В организациях Microsoft 365 с почтовыми ящиками Exchange Online можно указать почтовый ящик для получения сообщений, которые пользователи сообщают как вредоносные или не являющиеся вредоносными.</span><span class="sxs-lookup"><span data-stu-id="27187-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="27187-105">Когда пользователи отправляют сообщения с помощью различных параметров отчетов, вы можете использовать этот почтовый ящик для перехвата сообщений (только для личного почтового ящика) или получения копий сообщений (отправить в настраиваемый почтовый ящик и Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="27187-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="27187-106">Эта функция работает со следующими параметрами отчетов о сообщениях:</span><span class="sxs-lookup"><span data-stu-id="27187-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="27187-107">Надстройка "сообщение отчета"</span><span class="sxs-lookup"><span data-stu-id="27187-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="27187-108">[Встроенные отчеты в Outlook в Интернете](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (прежнее название — Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="27187-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- [<span data-ttu-id="27187-109">Встроенные отчеты в Outlook для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="27187-109">Built-in reporting in Outlook for iOS and Android</span></span>](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > <span data-ttu-id="27187-110">Если отчетность [отключена в Outlook в Интернете](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), то при включении этой функции переопределяется этот параметр и пользователи могут сообщать о сообщениях в Outlook в Интернете еще раз.</span><span class="sxs-lookup"><span data-stu-id="27187-110">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="27187-111">Кроме того, можно настроить сторонние средства создания отчетов для пересылки сообщений в указанный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="27187-111">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="27187-112">Доставка сообщений, отправленных пользователем, в настраиваемый почтовый ящик, а не непосредственно в Майкрософт, позволяет администраторам выборочно и вручную отправлять сообщения в корпорацию Майкрософт с помощью [отправки администратором](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="27187-112">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="27187-113">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="27187-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="27187-114">Откройте Центр безопасности и соответствия требованиям на сайте <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="27187-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="27187-115">Чтобы перейти непосредственно на страницу " **отправки пользователя** ", используйте <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="27187-115">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="27187-116">Чтобы вы могли выполнить процедуры, упомянутые в этой теме, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="27187-116">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="27187-117">Чтобы изменить конфигурацию для отправки пользователей, необходимо быть участником одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="27187-117">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="27187-118">**[Администратор Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** в Azure AD и **Управление организацией** или **администратор безопасности** , а также в [центре безопасности & соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="27187-118">**[Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** in Azure AD and **Organization Management** or **Security Administrator** and in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="27187-119">**Управление организацией** или **Управление санацией** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="27187-119">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="27187-120">Для доступа к отправку пользователей только для чтения необходимо быть членом обеих следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="27187-120">For read-only access to User submissions, you need to be a member of both of the following role groups:</span></span>

    - <span data-ttu-id="27187-121">**Средство считывания сведений о безопасности** в [Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="27187-121">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="27187-122">**Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="27187-122">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="27187-123">Использование центра безопасности & соответствия требованиям для настройки почтового ящика отправки пользователя</span><span class="sxs-lookup"><span data-stu-id="27187-123">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="27187-124">В центре безопасности & соответствия требованиям перейдите к разделу пользователь политики **управления угрозами** \> **Policy** \> **User submissions**.</span><span class="sxs-lookup"><span data-stu-id="27187-124">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="27187-125">На появившейся странице " **отправки пользователей** " выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="27187-125">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="27187-126">а)</span><span class="sxs-lookup"><span data-stu-id="27187-126">a.</span></span> <span data-ttu-id="27187-127">**Включить функцию сообщений отчетов для Outlook (рекомендуется)**: Выберите этот параметр, если вы используете надстройку Report Message или встроенную отчетность в Outlook в Интернете, а затем настроили следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="27187-127">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="27187-128">**Настройте сообщение для подтверждения пользователя**. Щелкните эту ссылку.</span><span class="sxs-lookup"><span data-stu-id="27187-128">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="27187-129">В появившемся всплывающем окне **Настройка предупреждающего сообщения** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="27187-129">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="27187-130">**Перед отправкой**: в полях **название** и **сообщение подтверждения** введите описательный текст, который пользователи видят перед отчетом о сообщении с помощью надстройки Report Message.</span><span class="sxs-lookup"><span data-stu-id="27187-130">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="27187-131">Вы можете использовать переменную% типа%, чтобы включить тип отправки (нежелательный, нежелательный, фишинг и т. д.).</span><span class="sxs-lookup"><span data-stu-id="27187-131">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="27187-132">Как отмечалось, при выборе варианта отправки сообщений, отправленных в корпорацию Майкрософт, в уведомление добавляется следующий текст:</span><span class="sxs-lookup"><span data-stu-id="27187-132">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="27187-133">Ваша электронная почта будет отправлена в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="27187-133">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="27187-134">Некоторые сообщения электронной почты могут содержать персональные или конфиденциальные сведения.</span><span class="sxs-lookup"><span data-stu-id="27187-134">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="27187-135">**После отправки**: нажмите ![ развернуть значок ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="27187-135">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="27187-136">В поля **имя** и **Подтверждение** введите описательный текст, который пользователи видят после того, как отчитываться о сообщении с помощью надстройки Report Message.</span><span class="sxs-lookup"><span data-stu-id="27187-136">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="27187-137">Вы можете использовать переменную% типа%, чтобы включить тип отправки.</span><span class="sxs-lookup"><span data-stu-id="27187-137">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="27187-138">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="27187-138">When you're finished, click **Save**.</span></span> <span data-ttu-id="27187-139">Чтобы очистить эти значения, нажмите кнопку **восстановить** обратно на странице " **Отправка пользователя** ".</span><span class="sxs-lookup"><span data-stu-id="27187-139">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="27187-140">**Отправить сообщения, отправленные в**: сделайте один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="27187-140">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="27187-141">**Майкрософт (рекомендуется)**: почтовый ящик отправки пользователя не используется (все сообщения, о которых сообщалось в корпорацию Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="27187-141">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="27187-142">**Майкрософт и настраиваемый почтовый ящик**: в появившемся поле введите адрес электронной почты существующего почтового ящика Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="27187-142">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="27187-143">Группы рассылки не разрешены.</span><span class="sxs-lookup"><span data-stu-id="27187-143">Distribution groups are not allowed.</span></span> <span data-ttu-id="27187-144">Пользовательские отправки отправляются в корпорацию Майкрософт для анализа и в настраиваемый почтовый ящик для анализа администратором или группой действий по обеспечению безопасности.</span><span class="sxs-lookup"><span data-stu-id="27187-144">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="27187-145">**Настраиваемый почтовый ящик**: в появившемся поле введите адрес электронной почты существующего почтового ящика Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="27187-145">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="27187-146">Группы рассылки не разрешены.</span><span class="sxs-lookup"><span data-stu-id="27187-146">Distribution groups are not allowed.</span></span> <span data-ttu-id="27187-147">Используйте этот параметр, если вы хотите, чтобы сообщение сначала заходило только на администрирование или в группу "операции по обеспечению безопасности" для анализа.</span><span class="sxs-lookup"><span data-stu-id="27187-147">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="27187-148">Сообщения не будут передаваться в корпорацию Майкрософт, если администратор не переадресует себя.</span><span class="sxs-lookup"><span data-stu-id="27187-148">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="27187-149">В организациях правительства США (GCC, GCC-H и DoD) можно настраивать только **личный почтовый ящик**.</span><span class="sxs-lookup"><span data-stu-id="27187-149">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="27187-150">Два других параметра отключены.</span><span class="sxs-lookup"><span data-stu-id="27187-150">The other two options are disabled.</span></span> 

      <span data-ttu-id="27187-151">Когда все будет готово, нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="27187-151">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="27187-152">Если вы [отключили отчеты о нежелательной почте в Outlook в Интернете](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) с помощью Outlook в веб-политиках почтовых ящиков, но настроили любой из предыдущих параметров для отправки отчетов в корпорацию Майкрософт, пользователи смогут отправлять отчеты в корпорацию Майкрософт в Outlook в Интернете с помощью надстройки Report Message.</span><span class="sxs-lookup"><span data-stu-id="27187-152">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="27187-153">**Отключить функцию сообщений отчетов для Outlook**: Выберите этот параметр, если вы используете сторонние средства создания отчетов вместо надстройки сообщений отчетов или встроенных отчетов в Outlook в Интернете, а затем настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="27187-153">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="27187-154">Выберите **использовать этот настраиваемый почтовый ящик для получения данных о отправленных пользователем сообщениях**.</span><span class="sxs-lookup"><span data-stu-id="27187-154">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="27187-155">В появившемся поле введите адрес электронной почты существующего почтового ящика, который уже находится в Office 365.</span><span class="sxs-lookup"><span data-stu-id="27187-155">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="27187-156">Это должен быть существующий почтовый ящик в Exchange Online, который может получать электронную почту.</span><span class="sxs-lookup"><span data-stu-id="27187-156">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="27187-157">Когда все будет готово, нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="27187-157">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="27187-158">Формат отправки сообщений</span><span class="sxs-lookup"><span data-stu-id="27187-158">Message submission format</span></span>

<span data-ttu-id="27187-159">Сообщения, отправляемые в пользовательские почтовые ящики, должны соответствовать определенному почтовому формату отправки.</span><span class="sxs-lookup"><span data-stu-id="27187-159">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="27187-160">Тема (название конверта) отправки должна иметь следующий формат:</span><span class="sxs-lookup"><span data-stu-id="27187-160">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="27187-161">Сафетяпиактион — одно из следующих целых значений:</span><span class="sxs-lookup"><span data-stu-id="27187-161">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="27187-162">1: Нежелательная почта</span><span class="sxs-lookup"><span data-stu-id="27187-162">1: Junk</span></span>
- <span data-ttu-id="27187-163">2: Нотжунк</span><span class="sxs-lookup"><span data-stu-id="27187-163">2: NotJunk</span></span>
- <span data-ttu-id="27187-164">3: Фишинг</span><span class="sxs-lookup"><span data-stu-id="27187-164">3: Phish</span></span>

<span data-ttu-id="27187-165">В следующем примере:</span><span class="sxs-lookup"><span data-stu-id="27187-165">In the following example:</span></span>

- <span data-ttu-id="27187-166">Сообщение сообщается как "фишинг".</span><span class="sxs-lookup"><span data-stu-id="27187-166">The message is being reported as Phish.</span></span>
- <span data-ttu-id="27187-167">ИДЕНТИФИКАТОР сетевого сообщения — 49871234-6dc6-43e8-ABCD-08d797f20abe.</span><span class="sxs-lookup"><span data-stu-id="27187-167">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="27187-168">IP-адрес отправителя — 167.220.232.101.</span><span class="sxs-lookup"><span data-stu-id="27187-168">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="27187-169">Адрес отправителя — test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="27187-169">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="27187-170">Строка темы сообщения: "проверка передачи фишинга"</span><span class="sxs-lookup"><span data-stu-id="27187-170">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="27187-171">Сообщения, которые не соответствуют этому формату, не будут правильно отображаться на портале отправки.</span><span class="sxs-lookup"><span data-stu-id="27187-171">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
