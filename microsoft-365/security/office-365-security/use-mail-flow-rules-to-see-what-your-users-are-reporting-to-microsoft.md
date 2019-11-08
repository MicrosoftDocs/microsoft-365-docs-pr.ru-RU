---
title: Просмотр отчетов, передаваемых пользователями в Майкрософт, с помощью правил для потока обработки почты
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Вы можете создать правило для почтового процесса Exchange, чтобы пользователи не могли отправлять сообщения электронной почты в корпорацию Майкрософт для анализа и использовать их в собственных процессах безопасности.
ms.openlocfilehash: d1b67d60d10ea9ce5d3ed47e20959c85d785e437
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "38030643"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="f6d3a-103">Просмотр отчетов, передаваемых пользователями в Майкрософт, с помощью правил для потока обработки почты</span><span class="sxs-lookup"><span data-stu-id="f6d3a-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="f6d3a-104">Сообщения о ложном срабатывании и пропуске спама можно отправлять в Майкрософт для анализа несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="f6d3a-104">There are multiple ways you can send false positive and false negative messages to Microsoft for analysis.</span></span> <span data-ttu-id="f6d3a-105">Администратор может использовать правила для потока обработки почты, чтобы просматривать отчеты о спаме, не спаме и фишинговых сообщениях, отправляемые пользователями в Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f6d3a-105">As an administrator, you can use mail flow rules to see what your users are reporting to Microsoft as spam, non-spam, and phishing scams.</span></span> <span data-ttu-id="f6d3a-106">Дополнительные сведения о том, [как отправлять сообщения о нежелательной почте и мошеннических сообщениях в корпорацию Майкрософт для анализа](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="f6d3a-106">For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span> <span data-ttu-id="f6d3a-107">Кроме того, вы можете создать правило для поток почты Exchange (также называемое правилом транспорта), чтобы запретить пользователям отправлять сообщения электронной почты в корпорацию Майкрософт для анализа и использовать их в собственных процессах безопасности.</span><span class="sxs-lookup"><span data-stu-id="f6d3a-107">Conversely, you can create an Exchange mail flow rule (also known as a transport rule) to prevent your users from sending email messages to Microsoft for analysis and use them in your own security processes.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f6d3a-108">Что нужно знать перед началом работы?</span><span class="sxs-lookup"><span data-stu-id="f6d3a-108">What do you need to know before you begin?</span></span>

<span data-ttu-id="f6d3a-109">Предполагаемое время для завершения: 5 минут.</span><span class="sxs-lookup"><span data-stu-id="f6d3a-109">Estimated time to complete: 5 minutes</span></span>

<span data-ttu-id="f6d3a-110">Для выполнения этой процедуры (процедур) необходимы соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="f6d3a-110">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="f6d3a-111">Чтобы просмотреть необходимые разрешения, обратитесь к разделу "правила обработки почтового ящика" в разделе "правила обработки сообщений" в разделе " [Политика обмена сообщениями и соответствие требованиям](https://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) " и записи "Outlook в веб-почтовых ящиках" в разделе " [Клиенты и мобильные устройства](https://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) ".</span><span class="sxs-lookup"><span data-stu-id="f6d3a-111">To see what permissions you need, see the "Mail flow rules" entry in the [Messaging policy and compliance permissions](https://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic and the "Outlook on the web mailbox policies" entry in the [Clients and mobile devices permissions](https://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) topic.</span></span>

<span data-ttu-id="f6d3a-112">Дополнительные сведения о сочетаниях клавиш, которые могут применяться к процедурам, описанным в этой статье, приведены в статье [сочетания клавиш для центра администрирования Exchange в Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="f6d3a-112">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a><span data-ttu-id="f6d3a-113">Создание правила для потока обработки почты для просмотра отправляемых пользователями отчетов о спаме, фишинге и не спаме в Центре администрирования Exchange</span><span class="sxs-lookup"><span data-stu-id="f6d3a-113">Use the EAC to create a mail flow rule to view users' manual junk, phishing, and not junk reports</span></span>

1. <span data-ttu-id="f6d3a-114">В Центре администрирования Exchange последовательно выберите пункты **Поток обработки почты** \> **Правила**.</span><span class="sxs-lookup"><span data-stu-id="f6d3a-114">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="f6d3a-115">Щелкните ![Значок добавления](../media/ITPro-EAC-AddIcon.gif) и выберите **Создать новое правило**.</span><span class="sxs-lookup"><span data-stu-id="f6d3a-115">Click ![Add Icon](../media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="f6d3a-116">Присвойте правилу имя и нажмите **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="f6d3a-116">Give the rule a name and then click **More options**.</span></span>

4. <span data-ttu-id="f6d3a-117">В области **Применить это правило, если** выберите **Получатель**, а затем  **Адрес содержит любое из этих слов**.</span><span class="sxs-lookup"><span data-stu-id="f6d3a-117">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span></span>

5. <span data-ttu-id="f6d3a-118">В поле **Укажите слова или фразы** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f6d3a-118">In the **specify words or phrases** box, do the following steps:</span></span>

   - <span data-ttu-id="f6d3a-119">Введите `abuse@messaging.microsoft.com`, щелкните **Добавить** ![значок](../media/ITPro-EAC-AddIcon.gif)добавить, введите `junk@office365.microsoft.com` , а затем нажмите **Добавить** ![значок](../media/ITPro-EAC-AddIcon.gif)добавить.</span><span class="sxs-lookup"><span data-stu-id="f6d3a-119">Type `abuse@messaging.microsoft.com`, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif), type `junk@office365.microsoft.com` and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="f6d3a-120">Эти адреса электронной почты используются для отправки ошибочно отрицательных сообщений в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f6d3a-120">These email addresses are used to submit false negative messages to Microsoft.</span></span>

   - <span data-ttu-id="f6d3a-121">Введите `phish@office365.microsoft.com` команду и нажмите **кнопку** ![добавить значок](../media/ITPro-EAC-AddIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="f6d3a-121">Type `phish@office365.microsoft.com` and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="f6d3a-122">Этот адрес электронной почты используется для отправки пропущенных фишинговых сообщений в Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f6d3a-122">This email address is used to submit missed phishing messages to Microsoft.</span></span>

   - <span data-ttu-id="f6d3a-123">Введите `false_positive@messaging.microsoft.com`, щелкните **Добавить** ![значок](../media/ITPro-EAC-AddIcon.gif)добавить, введите `not_junk@office365.microsoft.com`, а затем нажмите **Добавить** ![значок](../media/ITPro-EAC-AddIcon.gif)добавить.</span><span class="sxs-lookup"><span data-stu-id="f6d3a-123">Type `false_positive@messaging.microsoft.com`, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif), type `not_junk@office365.microsoft.com`, and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="f6d3a-124">Эти адреса электронной почты используются для отправки ошибочно положительных сообщений в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f6d3a-124">These email addresses are used to submit false positive messages to Microsoft.</span></span>

   - <span data-ttu-id="f6d3a-125">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6d3a-125">Click **OK**.</span></span>

6. <span data-ttu-id="f6d3a-126">В разделе **Выполнить следующие действия** выберите **Отправить скрытую копию сообщения (СК)...** и выберите нужные почтовые ящики.</span><span class="sxs-lookup"><span data-stu-id="f6d3a-126">Under **Do the following**, select **Bcc the message to...** and then and then select the mailboxes where you'd like to receive the messages.</span></span>

7. <span data-ttu-id="f6d3a-127">При необходимости можно выбрать нужные параметры для аудита и проверки правила, его активации в течение определенного периода, а также выбрать другие настройки.</span><span class="sxs-lookup"><span data-stu-id="f6d3a-127">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="f6d3a-128">Мы рекомендуем протестировать правило в течение определенного времени перед его применением.</span><span class="sxs-lookup"><span data-stu-id="f6d3a-128">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="f6d3a-129">[В разделе процедуры для правил для почтового процесса](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span><span class="sxs-lookup"><span data-stu-id="f6d3a-129">See [Procedures for mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span></span>

8. <span data-ttu-id="f6d3a-p107">Нажмите кнопку **Сохранить**, чтобы сохранить правило. Оно отобразится в вашем списке правил.</span><span class="sxs-lookup"><span data-stu-id="f6d3a-p107">Click the **save** button to save the rule. It appears in your list of rules.</span></span>

<span data-ttu-id="f6d3a-132">После создания и применения правила все сообщения, отправляемые из вашей организации на указанные адреса электронной почты, будут копироваться в указанный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="f6d3a-132">After you create and enforce the rule, any messages that are sent from your organization to specified email addresses will be copied to the specified mailbox.</span></span>
