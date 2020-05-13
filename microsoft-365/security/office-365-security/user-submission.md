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
ms.openlocfilehash: 7b4b913a29c3eb16286d5a2874fe48bbc1c121fe
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208505"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="8fbbf-103">Выбор почтового ящика для отправки пользователем сообщений о нежелательной почте и фишинговых сообщениях в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8fbbf-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="8fbbf-104">В организациях Microsoft 365 с почтовыми ящиками Exchange Online можно указать почтовый ящик для получения сообщений, которые пользователи сообщают как вредоносные или не являющиеся вредоносными.</span><span class="sxs-lookup"><span data-stu-id="8fbbf-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="8fbbf-105">Когда пользователи отправляют сообщения с помощью различных параметров отчетов, вы можете использовать этот почтовый ящик для перехвата сообщений (только для личного почтового ящика) или получения копий сообщений (отправить в настраиваемый почтовый ящик и Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="8fbbf-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="8fbbf-106">Эта функция работает со следующими параметрами отчетов о сообщениях:</span><span class="sxs-lookup"><span data-stu-id="8fbbf-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="8fbbf-107">Надстройка "сообщение отчета"</span><span class="sxs-lookup"><span data-stu-id="8fbbf-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="8fbbf-108">[Встроенные отчеты в Outlook в Интернете](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (прежнее название — Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="8fbbf-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

<span data-ttu-id="8fbbf-109">Кроме того, можно настроить сторонние средства создания отчетов для пересылки сообщений в указанный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="8fbbf-109">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="8fbbf-110">Доставка сообщений, отправленных пользователем, в настраиваемый почтовый ящик, а не непосредственно в Майкрософт, позволяет администраторам выборочно и вручную отправлять сообщения в корпорацию Майкрософт с помощью [отправки администратором](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="8fbbf-110">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8fbbf-111">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="8fbbf-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8fbbf-112">Откройте Центр безопасности и соответствия требованиям по ссылке <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="8fbbf-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8fbbf-113">Чтобы перейти непосредственно на страницу " **отправки пользователя** ", используйте <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="8fbbf-113">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="8fbbf-114">Сведения о подключении к Exchange Online PowerShell см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="8fbbf-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="8fbbf-115">Сведения о подключении к автономной службе Exchange Online Protection PowerShell см. в статье [Подключение к PowerShell для Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="8fbbf-115">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="8fbbf-116">Для выполнения этих процедур необходимы соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="8fbbf-116">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="8fbbf-117">Чтобы настроить почтовый ящик для отправки пользователей, необходимо быть участником группы ролей " **Управление организацией** " или " **администратор безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="8fbbf-117">To configure the mailbox for user submissions, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="8fbbf-118">Дополнительные сведения о группах ролей в Центре безопасности и соответствия требованиям см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="8fbbf-118">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="8fbbf-119">Использование центра безопасности & соответствия требованиям для настройки почтового ящика отправки пользователя</span><span class="sxs-lookup"><span data-stu-id="8fbbf-119">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="8fbbf-120">В центре безопасности & соответствия требованиям перейдите к разделу пользователь политики **управления угрозами** \> **Policy** \> **User submissions**.</span><span class="sxs-lookup"><span data-stu-id="8fbbf-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="8fbbf-121">На появившейся странице " **отправки пользователей** " выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="8fbbf-121">In the **User submissions** page that appears, select one of the following options:</span></span>

   - <span data-ttu-id="8fbbf-122">**Включить функцию сообщений отчетов для Outlook (рекомендуется)**: Выберите этот параметр, если вы используете надстройку Report Message или встроенную отчетность в Outlook в Интернете, а затем настроили следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="8fbbf-122">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     - <span data-ttu-id="8fbbf-123">**Настройте сообщение для подтверждения пользователя**. Щелкните эту ссылку.</span><span class="sxs-lookup"><span data-stu-id="8fbbf-123">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="8fbbf-124">В появившемся всплывающем окне **Настройка предупреждающего сообщения** настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="8fbbf-124">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

       - <span data-ttu-id="8fbbf-125">**Перед отправкой**: в полях **название** и **сообщение подтверждения** введите описательный текст, который пользователи видят перед отчетом о сообщении с помощью надстройки Report Message.</span><span class="sxs-lookup"><span data-stu-id="8fbbf-125">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="8fbbf-126">Вы можете использовать переменную% типа%, чтобы включить тип отправки (нежелательный, нежелательный, фишинг и т. д.).</span><span class="sxs-lookup"><span data-stu-id="8fbbf-126">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

         <span data-ttu-id="8fbbf-127">Как отмечалось, в уведомление также добавляется следующий текст:</span><span class="sxs-lookup"><span data-stu-id="8fbbf-127">As noted, the following text is also added to the notification:</span></span>

         > <span data-ttu-id="8fbbf-128">Ваша электронная почта будет отправлена в корпорацию Майкрософт для анализа.</span><span class="sxs-lookup"><span data-stu-id="8fbbf-128">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="8fbbf-129">Некоторые сообщения электронной почты могут содержать персональные или конфиденциальные сведения.</span><span class="sxs-lookup"><span data-stu-id="8fbbf-129">Some emails might contain personal or sensitive information.</span></span>

       - <span data-ttu-id="8fbbf-130">**После отправки**: нажмите ![ развернуть значок ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="8fbbf-130">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="8fbbf-131">В поля **имя** и **Подтверждение** введите описательный текст, который пользователи видят после того, как отчитываться о сообщении с помощью надстройки Report Message.</span><span class="sxs-lookup"><span data-stu-id="8fbbf-131">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="8fbbf-132">Вы можете использовать переменную% типа%, чтобы включить тип отправки.</span><span class="sxs-lookup"><span data-stu-id="8fbbf-132">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="8fbbf-133">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8fbbf-133">When you're finished, click **Save**.</span></span> <span data-ttu-id="8fbbf-134">Чтобы очистить эти значения, нажмите кнопку **восстановить** обратно на странице " **Отправка пользователя** ".</span><span class="sxs-lookup"><span data-stu-id="8fbbf-134">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

   - <span data-ttu-id="8fbbf-135">**Отправить сообщения, отправленные в**: сделайте один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="8fbbf-135">**Send the reported messages to**: Make one of the following selections:</span></span>

     - <span data-ttu-id="8fbbf-136">**Майкрософт (рекомендуется)**: почтовый ящик отправки пользователя не используется (все сообщения, о которых сообщалось в корпорацию Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="8fbbf-136">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

     - <span data-ttu-id="8fbbf-137">**Майкрософт и настраиваемый почтовый ящик**: в появившемся поле введите адрес электронной почты существующего почтового ящика Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8fbbf-137">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="8fbbf-138">Группы рассылки не разрешены.</span><span class="sxs-lookup"><span data-stu-id="8fbbf-138">Distribution groups are not allowed.</span></span>

     - <span data-ttu-id="8fbbf-139">**Настраиваемый почтовый ящик**: в появившемся поле введите адрес электронной почты существующего почтового ящика Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8fbbf-139">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="8fbbf-140">Группы рассылки не разрешены.</span><span class="sxs-lookup"><span data-stu-id="8fbbf-140">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="8fbbf-141">Когда все будет готово, нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="8fbbf-141">When you're finished, click **Confirm**.</span></span>

     ![Отправка сообщений, отправленных в корпорацию Майкрософт, и настраиваемого почтового ящика](../../media/user-submission-enable-outlook-report-message.png)

   - <span data-ttu-id="8fbbf-143">**Отключить функцию сообщений отчетов для Outlook**: Выберите этот параметр, если вы используете сторонние средства создания отчетов вместо надстройки сообщений отчетов или встроенных отчетов в Outlook в Интернете, а затем настройте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="8fbbf-143">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     <span data-ttu-id="8fbbf-144">Выберите **использовать этот настраиваемый почтовый ящик для получения данных о отправленных пользователем сообщениях**.</span><span class="sxs-lookup"><span data-stu-id="8fbbf-144">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="8fbbf-145">В появившемся поле введите адрес электронной почты существующего почтового ящика или электронный адрес почтового ящика, который вы хотите создать.</span><span class="sxs-lookup"><span data-stu-id="8fbbf-145">In the box that appears, enter the email address of an existing mailbox, or the email address of the mailbox that you want to create.</span></span>

     <span data-ttu-id="8fbbf-146">Когда все будет готово, нажмите кнопку **подтвердить**.</span><span class="sxs-lookup"><span data-stu-id="8fbbf-146">When you're finished, click **Confirm**.</span></span>

     ![Отправка сообщений, отправленных в настраиваемый почтовый ящик, с помощью сторонних средств](../../media/user-submission-disable-outlook-report-message.png)
