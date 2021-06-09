---
title: Создание уведомления о легальном удержании
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Используйте средство связи в случае Advanced eDiscovery для отправки, сбора и отслеживания уведомлений о удержании.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: df1b2d962e83110c62ccac871f669bbc0d3bfe02
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840564"
---
# <a name="create-a-legal-hold-notice"></a><span data-ttu-id="5f7da-103">Создание уведомления о легальном удержании</span><span class="sxs-lookup"><span data-stu-id="5f7da-103">Create a legal hold notice</span></span>

<span data-ttu-id="5f7da-104">С Advanced eDiscovery связи с хранителями организации могут управлять своим процессом взаимодействия с хранителями.</span><span class="sxs-lookup"><span data-stu-id="5f7da-104">Using Advanced eDiscovery custodian communications, organizations can manage their workflow around communicating with custodians.</span></span> <span data-ttu-id="5f7da-105">С помощью средства связи юридические группы могут систематически отправлять, собирать и отслеживать уведомления о удержании.</span><span class="sxs-lookup"><span data-stu-id="5f7da-105">Through the Communications tool, legal teams can systematically send, collect, and track legal hold notifications.</span></span> <span data-ttu-id="5f7da-106">Гибкий процесс создания также позволяет группам настраивать рабочий процесс уведомления о удержании и содержимое уведомлений, отправленных хранителям.</span><span class="sxs-lookup"><span data-stu-id="5f7da-106">The flexible creation process also allows teams to customize the hold notification workflow and the content in the notices sent to custodians.</span></span>

![Страница "Связь"](../media/CommunicationPage.PNG)

<span data-ttu-id="5f7da-108">В статье описаны действия в рабочего процесса уведомления о удержании.</span><span class="sxs-lookup"><span data-stu-id="5f7da-108">The article outlines the steps in the hold notification workflow.</span></span>

## <a name="step-1-specify-communication-details"></a><span data-ttu-id="5f7da-109">Шаг 1. Указание сведений о связи</span><span class="sxs-lookup"><span data-stu-id="5f7da-109">Step 1: Specify communication details</span></span>

<span data-ttu-id="5f7da-110">Первый шаг — указать соответствующие сведения для юридических уведомлений о удержании или других сообщений хранителя.</span><span class="sxs-lookup"><span data-stu-id="5f7da-110">The first step is to specify the appropriate details for legal hold notices or other custodian communications.</span></span>

![Страница связи name](../media/NameCommunication.PNG)

1. <span data-ttu-id="5f7da-112">В Центре & безопасности перейдите в **службу** > Advanced eDiscovery, чтобы отобразить список случаев в организации.</span><span class="sxs-lookup"><span data-stu-id="5f7da-112">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery** to display the list of cases in your organization.</span></span>

2. <span data-ttu-id="5f7da-113">Выберите случай, щелкните вкладку **Communications** и нажмите кнопку **Новое сообщение**.</span><span class="sxs-lookup"><span data-stu-id="5f7da-113">Select a case, click the **Communications** tab, and then click **New communication**.</span></span>

3. <span data-ttu-id="5f7da-114">На странице **Связи Имя** укажите следующие (необходимые) сведения о связи.</span><span class="sxs-lookup"><span data-stu-id="5f7da-114">On the **Name communication** page, specify the following (required) communication details.</span></span>

    - <span data-ttu-id="5f7da-115">**Имя.** Это имя для связи.</span><span class="sxs-lookup"><span data-stu-id="5f7da-115">**Name**: This is the name for the communication.</span></span>

    - <span data-ttu-id="5f7da-116">**Сотрудник по выдаче.** В списке выпаданий отображается список участников дела.</span><span class="sxs-lookup"><span data-stu-id="5f7da-116">**Issuing officer**: The dropdown list displays a list of case members.</span></span> <span data-ttu-id="5f7da-117">Дополнительные сведения о добавлении новых членов в дело см. в Advanced eDiscovery [примере.](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case)</span><span class="sxs-lookup"><span data-stu-id="5f7da-117">For more information on how to add new members to a case, see [Create an Advanced eDiscovery case](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case).</span></span> <span data-ttu-id="5f7da-118">Каждое уведомление, отправленные хранителям, будет отправлено от имени указанного сотрудника по выдаче.</span><span class="sxs-lookup"><span data-stu-id="5f7da-118">Each notice sent to custodians will be sent on behalf of the specified issuing officer.</span></span>

> [!NOTE]
> <span data-ttu-id="5f7da-119">Сотрудник по выдаче должен иметь **активный почтовый ящик** для показа в отсеве сотрудника по выдаче</span><span class="sxs-lookup"><span data-stu-id="5f7da-119">The issuing officer must have an **active mailbox** to show up in the Issuing Officer dropdown</span></span>


4. <span data-ttu-id="5f7da-120">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5f7da-120">Click **Next**.</span></span>

## <a name="step-2-define-the-portal-content"></a><span data-ttu-id="5f7da-121">Шаг 2. Определение контента портала</span><span class="sxs-lookup"><span data-stu-id="5f7da-121">Step 2: Define the portal content</span></span>

<span data-ttu-id="5f7da-122">Далее можно создать и добавить содержимое уведомления о удержании.</span><span class="sxs-lookup"><span data-stu-id="5f7da-122">Next, you can create and add the content of the hold notice.</span></span> <span data-ttu-id="5f7da-123">На странице **"Определение контента портала"** в **мастере создания** связи укажите содержимое уведомления о удержании.</span><span class="sxs-lookup"><span data-stu-id="5f7da-123">On the **Define portal content** page in the **Create communication** wizard, specify the contents of the hold notice.</span></span> <span data-ttu-id="5f7da-124">Это содержимое автоматически будет примеся к уведомлениям о выпуске, повторном выпуске, напоминании и эскалации.</span><span class="sxs-lookup"><span data-stu-id="5f7da-124">This content will be automatically appended to the Issuance, Re-Issue, Reminder, and Escalation notices.</span></span> <span data-ttu-id="5f7da-125">Кроме того, этот контент появится на портале соответствия требованиям хранителя.</span><span class="sxs-lookup"><span data-stu-id="5f7da-125">Additionally, this content will appear in the custodian's Compliance Portal.</span></span> 

![Страница контента портала](../media/PortalContent.PNG)

<span data-ttu-id="5f7da-127">Для создания контента портала:</span><span class="sxs-lookup"><span data-stu-id="5f7da-127">To create the portal content:</span></span>

1. <span data-ttu-id="5f7da-128">Введите (или вырезать и введите из другого документа) уведомление о удержании в текстовом ящике для контента портала.</span><span class="sxs-lookup"><span data-stu-id="5f7da-128">Type (or cut and paste from another document) your hold notice in the textbox for the portal content.</span></span> 

2. <span data-ttu-id="5f7da-129">Вставьте переменные слияния в уведомление, чтобы настроить уведомление и поделиться порталом соответствия требованиям хранителя.</span><span class="sxs-lookup"><span data-stu-id="5f7da-129">Insert merge variables into your notice to customize the notice and share the Custodian Compliance Portal.</span></span>

3. <span data-ttu-id="5f7da-130">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5f7da-130">Click **Next**.</span></span>

  >[!Tip]
  ><span data-ttu-id="5f7da-131">Дополнительные материалы о том, как настроить контент и формат контента портала, см. в статью [Использование редактора сообщений.](using-communications-editor.md)</span><span class="sxs-lookup"><span data-stu-id="5f7da-131">To learn more about how to can customize the content and format of the portal content, see [Use the Communications Editor](using-communications-editor.md).</span></span>

## <a name="step-3-set-the-required-notifications"></a><span data-ttu-id="5f7da-132">Шаг 3. Настройка необходимых уведомлений</span><span class="sxs-lookup"><span data-stu-id="5f7da-132">Step 3: Set the required notifications</span></span>

<span data-ttu-id="5f7da-133">После определения содержимого уведомления о удержании можно настроить рабочий процесс отправки и управления процессом уведомления.</span><span class="sxs-lookup"><span data-stu-id="5f7da-133">After you've defined the contents of the hold notice, you can set up the workflows around sending and managing the notification process.</span></span> <span data-ttu-id="5f7da-134">Уведомления — это сообщения электронной почты, которые отправляются для уведомления и последующей связи с хранителями.</span><span class="sxs-lookup"><span data-stu-id="5f7da-134">Notifications are email messages that are sent to notify and follow up with custodians.</span></span> <span data-ttu-id="5f7da-135">Каждый хранитель, добавленный в сообщение, получит одно и то же уведомление.</span><span class="sxs-lookup"><span data-stu-id="5f7da-135">Every custodian added to the communication will receive the same notification.</span></span> 

<span data-ttu-id="5f7da-136">Чтобы настроить и отправить уведомление о удержании, необходимо включить уведомления о выпуске, повторной выдаче и выпуске.</span><span class="sxs-lookup"><span data-stu-id="5f7da-136">To set up and send a hold notice, you must include Issuance, Re-Issuance, and Release notifications.</span></span>

### <a name="issuance-notification"></a><span data-ttu-id="5f7da-137">Уведомление о выдаче</span><span class="sxs-lookup"><span data-stu-id="5f7da-137">Issuance notification</span></span> 

<span data-ttu-id="5f7da-138">После создания сообщения уведомление  о выдаче инициировал указанный сотрудник по выдаче.</span><span class="sxs-lookup"><span data-stu-id="5f7da-138">After the communication is created, the **Issuance Notification** is initiated by the specified Issuing Officer.</span></span> <span data-ttu-id="5f7da-139">Уведомление о выдаче — это первое сообщение, отправленное хранителям для информирования о своих обязательствах по сохранению.</span><span class="sxs-lookup"><span data-stu-id="5f7da-139">The Issuance notification is the first communication sent to the custodian to inform them about their preservation obligations.</span></span> 

<span data-ttu-id="5f7da-140">Чтобы создать уведомление о выдаче:</span><span class="sxs-lookup"><span data-stu-id="5f7da-140">To create an issuance notification:</span></span>

1. <span data-ttu-id="5f7da-141">В **плитке выдачи** нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="5f7da-141">In the **Issuance** tile, click **Edit**.</span></span>

2. <span data-ttu-id="5f7da-142">При необходимости добавьте дополнительных членов или сотрудников в **поля Cc** и **Bcc.**</span><span class="sxs-lookup"><span data-stu-id="5f7da-142">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="5f7da-143">Чтобы добавить несколько пользователей в эти поля, разделяйте адреса электронной почты с полу-двоеточием.</span><span class="sxs-lookup"><span data-stu-id="5f7da-143">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>

3. <span data-ttu-id="5f7da-144">Укажите **субъект** для уведомления (обязательно).</span><span class="sxs-lookup"><span data-stu-id="5f7da-144">Specify the **Subject** for the notice (required).</span></span>

4. <span data-ttu-id="5f7da-145">Укажите содержимое или дополнительные инструкции, которые необходимо предоставить хранителям.</span><span class="sxs-lookup"><span data-stu-id="5f7da-145">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="5f7da-146">Содержимое портала, определенное в шаге 2, добавляется в конец уведомления о выдаче.</span><span class="sxs-lookup"><span data-stu-id="5f7da-146">The portal content you defined in Step 2 is added to the end of the issuance notice.</span></span> 

5. <span data-ttu-id="5f7da-147">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5f7da-147">Click **Save**.</span></span>

### <a name="re-issuance-notification"></a><span data-ttu-id="5f7da-148">Re-Issuance уведомления</span><span class="sxs-lookup"><span data-stu-id="5f7da-148">Re-Issuance notification</span></span>

<span data-ttu-id="5f7da-149">По мере развития дела хранителям может потребоваться сохранить дополнительные или менее данные, чем было поручено ранее.</span><span class="sxs-lookup"><span data-stu-id="5f7da-149">As the case progresses, custodians may be required to preserve additional or less data than was previously instructed.</span></span> <span data-ttu-id="5f7da-150">После обновления контента портала отправляется уведомление о повторной выдаче и оповещает хранителей о любых изменениях в их обязательствах по сохранению.</span><span class="sxs-lookup"><span data-stu-id="5f7da-150">After you update the portal content, the re-issuance notification is sent and alerts custodians about any changes to their preservation obligations.</span></span>

<span data-ttu-id="5f7da-151">Чтобы создать уведомление о повторной выдаче:</span><span class="sxs-lookup"><span data-stu-id="5f7da-151">To create a re-issuance notification:</span></span>

1. <span data-ttu-id="5f7da-152">В **плитке Reissue** нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="5f7da-152">In the **Reissue** tile, click **Edit**.</span></span>

2. <span data-ttu-id="5f7da-153">При необходимости добавьте дополнительных членов или сотрудников в **поля Cc** и **Bcc.**</span><span class="sxs-lookup"><span data-stu-id="5f7da-153">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="5f7da-154">Чтобы добавить несколько пользователей в эти поля, разделяйте адреса электронной почты с полу-двоеточием.</span><span class="sxs-lookup"><span data-stu-id="5f7da-154">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>

3. <span data-ttu-id="5f7da-155">Укажите **субъект** для уведомления (обязательно).</span><span class="sxs-lookup"><span data-stu-id="5f7da-155">Specify the **Subject** for the notice (required).</span></span>

4. <span data-ttu-id="5f7da-156">Укажите содержимое или дополнительные инструкции, которые необходимо предоставить хранителям.</span><span class="sxs-lookup"><span data-stu-id="5f7da-156">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="5f7da-157">Содержимое портала, определенное в шаге 2, добавляется в конец уведомления о повторной выдаче.</span><span class="sxs-lookup"><span data-stu-id="5f7da-157">The portal content you defined in Step 2 is added to the end of the re-issuance notice.</span></span>

5. <span data-ttu-id="5f7da-158">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5f7da-158">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="5f7da-159">Если содержимое портала изменено  (на странице Определение контента портала в мастере связи **Редактирование),** уведомление о повторной выдаче будет автоматически отправлено всем хранителям, назначенным к уведомлению.</span><span class="sxs-lookup"><span data-stu-id="5f7da-159">If the portal content is modified (on the **Define Portal Content** page in the **Edit communication** wizard), the re-issuance notification will be automatically sent to all custodians assigned to the notice.</span></span> <span data-ttu-id="5f7da-160">После того как уведомление будет отправлено, хранителям будет предложено повторно подтвердить уведомление о удержании.</span><span class="sxs-lookup"><span data-stu-id="5f7da-160">After the notification is sent, custodians will be asked to re-acknowledge their hold notice.</span></span> <span data-ttu-id="5f7da-161">Если вы настроили какие-либо процессы напоминания или эскалации, они также будут повторно запускаться.</span><span class="sxs-lookup"><span data-stu-id="5f7da-161">If you have set up any reminder or escalation workflows, these will also re-start.</span></span> <span data-ttu-id="5f7da-162">Дополнительные сведения о том, какие другие события управления случаем вызывают связь, см. в примере [События, которые вызывают уведомления.](#events-that-trigger-notifications)</span><span class="sxs-lookup"><span data-stu-id="5f7da-162">For more information about what other case management events trigger communications, see [Events that trigger notifications](#events-that-trigger-notifications).</span></span>

### <a name="release-notification"></a><span data-ttu-id="5f7da-163">Уведомление о выпуске</span><span class="sxs-lookup"><span data-stu-id="5f7da-163">Release notification</span></span>

<span data-ttu-id="5f7da-164">После решения вопроса или если хранитель больше не подлежит сохранению контента, вы можете освободить хранителя из дела.</span><span class="sxs-lookup"><span data-stu-id="5f7da-164">After a matter is resolved or if a custodian is no longer subject to preserve content, you can release the custodian from a case.</span></span> <span data-ttu-id="5f7da-165">Если хранителям ранее было выдано уведомление о удержании, уведомление об освобождении может использоваться для оповещения хранителей о том, что они освобождены от своих обязательств.</span><span class="sxs-lookup"><span data-stu-id="5f7da-165">If the custodian was previously issued a hold notice, the release notification can be used to alert custodians that they have been released from their obligation.</span></span>

<span data-ttu-id="5f7da-166">Чтобы создать уведомление о выпуске:</span><span class="sxs-lookup"><span data-stu-id="5f7da-166">To create a release notification:</span></span> 

1. <span data-ttu-id="5f7da-167">В **плитке выпуска** нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="5f7da-167">In the **Release** tile, click **Edit**.</span></span>

2. <span data-ttu-id="5f7da-168">При необходимости добавьте дополнительных членов или сотрудников в **поля Cc** и **Bcc.**</span><span class="sxs-lookup"><span data-stu-id="5f7da-168">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="5f7da-169">Чтобы добавить несколько пользователей в эти поля, разделяйте адреса электронной почты с полу-двоеточием.</span><span class="sxs-lookup"><span data-stu-id="5f7da-169">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>

3. <span data-ttu-id="5f7da-170">Укажите **субъект** для уведомления (обязательно).</span><span class="sxs-lookup"><span data-stu-id="5f7da-170">Specify the **Subject** for the notice (required).</span></span>

4. <span data-ttu-id="5f7da-171">Укажите содержимое или дополнительные инструкции, которые необходимо предоставить хранителям.</span><span class="sxs-lookup"><span data-stu-id="5f7da-171">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span>

5. <span data-ttu-id="5f7da-172">Щелкните **Сохранить** и перейти к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="5f7da-172">Click **Save** and go to the next step.</span></span>

## <a name="optional-step-4-set-the-optional-notifications"></a><span data-ttu-id="5f7da-173">(Необязательный) Шаг 4. Настройка необязательных уведомлений</span><span class="sxs-lookup"><span data-stu-id="5f7da-173">(Optional) Step 4: Set the optional notifications</span></span>

<span data-ttu-id="5f7da-174">Дополнительно можно упростить рабочий процесс для работы с неопровержимыми хранителями, создав и запланируя автоматические уведомления о напоминаниях и эскалации.</span><span class="sxs-lookup"><span data-stu-id="5f7da-174">Optionally, you can simplify the workflow for following up with unresponsive custodians by creating and scheduling automated reminder and escalation notifications.</span></span>

![Страница Reminder/Escalation](../media/ReminderEscalations.PNG)

### <a name="reminders"></a><span data-ttu-id="5f7da-176">Reminders</span><span class="sxs-lookup"><span data-stu-id="5f7da-176">Reminders</span></span>

<span data-ttu-id="5f7da-177">После того как вы отправили уведомление о удержании, вы можете следить за неответствовающими хранителями, определяя рабочий процесс напоминания.</span><span class="sxs-lookup"><span data-stu-id="5f7da-177">After you have sent a hold notification, you can follow up with unresponsive custodians by defining a reminder workflow.</span></span>

<span data-ttu-id="5f7da-178">Чтобы запланировать напоминания:</span><span class="sxs-lookup"><span data-stu-id="5f7da-178">To schedule reminders:</span></span>

1. <span data-ttu-id="5f7da-179">В **плитке Напоминания** нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="5f7da-179">In the **Reminder** tile, click **Edit**.</span></span>

2. <span data-ttu-id="5f7da-180">**Включим** рабочий процесс Reminder, включив очки **Status** (необходимые).</span><span class="sxs-lookup"><span data-stu-id="5f7da-180">Enable the **Reminder** workflow by turning on the **Status** toggle (required).</span></span>

3. <span data-ttu-id="5f7da-181">Укажите интервал **Напоминания (в днях)** (обязательно).</span><span class="sxs-lookup"><span data-stu-id="5f7da-181">Specify the **Reminder interval (in days)** (required).</span></span> <span data-ttu-id="5f7da-182">Это число дней, которые необходимо подождать перед отправкой первых и последующих уведомлений о напоминаниях.</span><span class="sxs-lookup"><span data-stu-id="5f7da-182">This is the number of days to wait before sending the first and follow-up reminder notifications.</span></span> <span data-ttu-id="5f7da-183">Например, если интервал напоминаний установлен до семи дней, первое напоминание будет отправлено через семь дней после первоначального выпуска уведомления о удержании.</span><span class="sxs-lookup"><span data-stu-id="5f7da-183">For example, if you set the reminder interval to seven days, then the first reminder would be sent seven days after the hold notification was initially issued.</span></span> <span data-ttu-id="5f7da-184">Все последующие напоминания также будут отправлены каждые семь дней.</span><span class="sxs-lookup"><span data-stu-id="5f7da-184">All subsequent reminders would also be sent every seven days.</span></span>

4. <span data-ttu-id="5f7da-185">Укажите **количество напоминаний** (необходимых).</span><span class="sxs-lookup"><span data-stu-id="5f7da-185">Specify the **Number of reminders** (required).</span></span> <span data-ttu-id="5f7da-186">В этом поле указывается количество напоминаний для отправки неоправданным хранителям.</span><span class="sxs-lookup"><span data-stu-id="5f7da-186">This field specifies how many reminders to send to unresponsive custodians.</span></span> <span data-ttu-id="5f7da-187">Например, если вы установите число напоминаний до 3, то хранитель получит не более трех напоминаний.</span><span class="sxs-lookup"><span data-stu-id="5f7da-187">For example, if you set the number of reminders to 3, then a custodian would receive a maximum of three reminders.</span></span> <span data-ttu-id="5f7da-188">После того как хранитель признает уведомление о удержании, напоминания больше не будут отправлены этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="5f7da-188">After a custodian acknowledges the hold notification, reminders will no longer be sent to that user.</span></span>

5. <span data-ttu-id="5f7da-189">Укажите **субъект** для уведомления (обязательно).</span><span class="sxs-lookup"><span data-stu-id="5f7da-189">Specify the **Subject** for the notice (required).</span></span> 

6. <span data-ttu-id="5f7da-190">Укажите содержимое или дополнительные инструкции, которые необходимо предоставить хранителям.</span><span class="sxs-lookup"><span data-stu-id="5f7da-190">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="5f7da-191">Содержимое портала, определенное в шаге 2, добавляется в конец уведомления о напоминаниях.</span><span class="sxs-lookup"><span data-stu-id="5f7da-191">The portal content you defined in Step 2 is added to the end of the reminder notice.</span></span>

7. <span data-ttu-id="5f7da-192">Щелкните **Сохранить** и перейти на следующий шаг.</span><span class="sxs-lookup"><span data-stu-id="5f7da-192">Click **Save** and go the next step.</span></span>

### <a name="escalations"></a><span data-ttu-id="5f7da-193">Эскалации</span><span class="sxs-lookup"><span data-stu-id="5f7da-193">Escalations</span></span>

<span data-ttu-id="5f7da-194">В некоторых ситуациях вам могут потребоваться дополнительные способы для последующей проверки с неотвеживательными хранителями.</span><span class="sxs-lookup"><span data-stu-id="5f7da-194">In some situations, you may need additional ways to follow up with unresponsive custodians.</span></span> <span data-ttu-id="5f7da-195">Если хранитель не признает уведомление о удержании после получения указанного количества напоминаний, группа юристов может указать рабочий процесс, чтобы автоматически отправить уведомление об эскалации хранителю и его руководителю.</span><span class="sxs-lookup"><span data-stu-id="5f7da-195">If a custodian doesn't acknowledge a hold notification after receiving the specified number of reminders, the legal team can specify a workflow to automatically send an escalation notice to the custodian and their manager.</span></span>

<span data-ttu-id="5f7da-196">Чтобы запланировать эскалации:</span><span class="sxs-lookup"><span data-stu-id="5f7da-196">To schedule escalations:</span></span>

1. <span data-ttu-id="5f7da-197">В **плитке эскалации** нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="5f7da-197">In the **Escalation** tile, click **Edit**.</span></span>

2. <span data-ttu-id="5f7da-198">Включить рабочий **процесс эскалации,** включив **переключить очки Status.**</span><span class="sxs-lookup"><span data-stu-id="5f7da-198">Enable the **Escalation** workflow by turning on the **Status** toggle.</span></span>

3. <span data-ttu-id="5f7da-199">Укажите **интервал эскалации (в днях)** (обязательно).</span><span class="sxs-lookup"><span data-stu-id="5f7da-199">Specify the **Escalation interval (in days)** (required).</span></span>

4. <span data-ttu-id="5f7da-200">Укажите **количество эскалаций** (необходимых).</span><span class="sxs-lookup"><span data-stu-id="5f7da-200">Specify the **Number of escalations** (required).</span></span> <span data-ttu-id="5f7da-201">В этом поле указывается количество эскалаций для отправки неоправданным хранителям.</span><span class="sxs-lookup"><span data-stu-id="5f7da-201">This field specifies how many escalations to send to unresponsive custodians.</span></span> <span data-ttu-id="5f7da-202">Например, если вы установите число эскалаций до 3, то уведомление об эскалации будет отправлено хранителям и их руководителю не более трех раз.</span><span class="sxs-lookup"><span data-stu-id="5f7da-202">For example, if you set the number of escalations to 3, then an escalation notice would be sent to the custodian and their manager a maximum of three times.</span></span> <span data-ttu-id="5f7da-203">После того как хранитель признает уведомление о удержании, эскалации больше не будут отправлены.</span><span class="sxs-lookup"><span data-stu-id="5f7da-203">After a custodian acknowledges the hold notification, escalations will no longer be sent.</span></span>

5. <span data-ttu-id="5f7da-204">Укажите **субъект** для уведомления (обязательно).</span><span class="sxs-lookup"><span data-stu-id="5f7da-204">Specify the **Subject** for the notice (required).</span></span> 

6. <span data-ttu-id="5f7da-205">Укажите содержимое или дополнительные инструкции, которые необходимо предоставить хранителям.</span><span class="sxs-lookup"><span data-stu-id="5f7da-205">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="5f7da-206">Содержимое портала, определенное в шаге 2, добавляется в конец уведомления об эскалации.</span><span class="sxs-lookup"><span data-stu-id="5f7da-206">The portal content you defined in Step 2 is added to the end of the escalation notice.</span></span>

7. <span data-ttu-id="5f7da-207">Щелкните **Сохранить** и перейти на следующий шаг.</span><span class="sxs-lookup"><span data-stu-id="5f7da-207">Click **Save** and go the next step.</span></span>

## <a name="step-5-assign-custodians-to-receive-notifications"></a><span data-ttu-id="5f7da-208">Шаг 5. Назначение хранителей для получения уведомлений</span><span class="sxs-lookup"><span data-stu-id="5f7da-208">Step 5: Assign custodians to receive notifications</span></span>

<span data-ttu-id="5f7da-209">После завершения подготовки контента для уведомлений выберите хранителей, в которые вы хотите отправить уведомления.</span><span class="sxs-lookup"><span data-stu-id="5f7da-209">After you have finalized the content for notifications, select the custodians that you would like to send notifications to.</span></span> 

![Выберите страницу Хранители](../media/SelectCustodians.PNG)

<span data-ttu-id="5f7da-211">Добавление хранителей:</span><span class="sxs-lookup"><span data-stu-id="5f7da-211">To add custodians:</span></span>

1. <span data-ttu-id="5f7da-212">Назначьте хранителей связи, щелкнув рядом с их именем почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="5f7da-212">Assign custodians to the communication by clicking the checkbox next to their name.</span></span>

    <span data-ttu-id="5f7da-213">После создания сообщения рабочий процесс уведомления автоматически применяется к выбранным хранителям.</span><span class="sxs-lookup"><span data-stu-id="5f7da-213">After the communication is created, the notification workflow will automatically apply to the selected custodians.</span></span>

2. <span data-ttu-id="5f7da-214">Нажмите **кнопку Далее,** чтобы просмотреть параметры и сведения о связи.</span><span class="sxs-lookup"><span data-stu-id="5f7da-214">Click **Next** to review the communication settings and details.</span></span>

>[!NOTE]
><span data-ttu-id="5f7da-215">Вы можете добавить только хранителей, которые были добавлены в дело и не были отправлены еще одно уведомление в случае.</span><span class="sxs-lookup"><span data-stu-id="5f7da-215">You can only add custodians who have been added to the case and haven't been sent another notification within the case.</span></span>

## <a name="step-6-review-settings"></a><span data-ttu-id="5f7da-216">Шаг 6. Параметры обзора</span><span class="sxs-lookup"><span data-stu-id="5f7da-216">Step 6: Review settings</span></span>

<span data-ttu-id="5f7da-217">После просмотра параметров и нажмите **кнопку Отправить,** чтобы завершить сообщение, система автоматически запустит рабочий процесс связи, отправив уведомление о выдаче.</span><span class="sxs-lookup"><span data-stu-id="5f7da-217">After you review the settings and click **Send** to complete the communication, the system will automatically start the communication workflow by sending the issuance notice.</span></span>

## <a name="events-that-trigger-notifications"></a><span data-ttu-id="5f7da-218">События, запуская уведомления</span><span class="sxs-lookup"><span data-stu-id="5f7da-218">Events that trigger notifications</span></span>

<span data-ttu-id="5f7da-219">В следующей таблице описываются события в процессе управления случаем, которые запускают при отправлении разных типов уведомлений хранителям.</span><span class="sxs-lookup"><span data-stu-id="5f7da-219">The following table describes events in the case management process that trigger when the different types of notifications are sent to custodians.</span></span>

|<span data-ttu-id="5f7da-220">Тип связи</span><span class="sxs-lookup"><span data-stu-id="5f7da-220">Type of communication</span></span>|<span data-ttu-id="5f7da-221">Триггер</span><span class="sxs-lookup"><span data-stu-id="5f7da-221">Trigger</span></span> |
|:---------|:---------|
|<span data-ttu-id="5f7da-222">Уведомления о выдаче</span><span class="sxs-lookup"><span data-stu-id="5f7da-222">Issuance notices</span></span>|<span data-ttu-id="5f7da-223">Начальное создание уведомления.</span><span class="sxs-lookup"><span data-stu-id="5f7da-223">The initial creation of the notification.</span></span> <span data-ttu-id="5f7da-224">Вы также можете вручную повторное уведомление о удержании.</span><span class="sxs-lookup"><span data-stu-id="5f7da-224">You can also manually resend a hold notification.</span></span> |
|<span data-ttu-id="5f7da-225">Уведомления о повторной выдаче</span><span class="sxs-lookup"><span data-stu-id="5f7da-225">Re-issuance notices</span></span>|<span data-ttu-id="5f7da-226">Обновление контента портала на странице **Определение контента портала** в **мастере редактирования коммуникации.**</span><span class="sxs-lookup"><span data-stu-id="5f7da-226">Updating the portal content on the **Define Portal Content** page in the **Edit communication** wizard.</span></span>|
|<span data-ttu-id="5f7da-227">Уведомления о выпуске</span><span class="sxs-lookup"><span data-stu-id="5f7da-227">Release notices</span></span>|<span data-ttu-id="5f7da-228">Хранитель освобожден из дела.</span><span class="sxs-lookup"><span data-stu-id="5f7da-228">The custodian is released from the case.</span></span>|
|<span data-ttu-id="5f7da-229">Reminders</span><span class="sxs-lookup"><span data-stu-id="5f7da-229">Reminders</span></span>|<span data-ttu-id="5f7da-230">Интервал и количество напоминаний, настроенных для напоминания.</span><span class="sxs-lookup"><span data-stu-id="5f7da-230">The interval and number of reminders configured for the reminder.</span></span>|
|<span data-ttu-id="5f7da-231">Эскалации</span><span class="sxs-lookup"><span data-stu-id="5f7da-231">Escalations</span></span>|<span data-ttu-id="5f7da-232">Интервал и количество напоминаний, настроенных для эскалации.</span><span class="sxs-lookup"><span data-stu-id="5f7da-232">The interval and number of reminders configured for the escalation.</span></span>|
|||
