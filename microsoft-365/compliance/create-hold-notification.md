---
title: Создание юридического уведомления о удержании
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
description: Используйте средство Communications в деле Advanced eDiscovery для отправки, сбора и отслеживания уведомлений об удержании по юридическим основаниям.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: df1b2d962e83110c62ccac871f669bbc0d3bfe02
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840564"
---
# <a name="create-a-legal-hold-notice"></a><span data-ttu-id="cf4a3-103">Создание юридического уведомления о удержании</span><span class="sxs-lookup"><span data-stu-id="cf4a3-103">Create a legal hold notice</span></span>

<span data-ttu-id="cf4a3-104">Используя коммуникации хранителя Advanced eDiscovery, организации могут управлять своим процессом взаимодействия с хранителями.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-104">Using Advanced eDiscovery custodian communications, organizations can manage their workflow around communicating with custodians.</span></span> <span data-ttu-id="cf4a3-105">С помощью средства "Связь" юридические группы могут систематически отправлять, собирать и отслеживать уведомления об удержании по юридическим основаниям.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-105">Through the Communications tool, legal teams can systematically send, collect, and track legal hold notifications.</span></span> <span data-ttu-id="cf4a3-106">Гибкий процесс создания также позволяет группам настраивать рабочий процесс уведомлений об удержании и содержимое уведомлений, отправленных хранителям.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-106">The flexible creation process also allows teams to customize the hold notification workflow and the content in the notices sent to custodians.</span></span>

![Страница "Связь"](../media/CommunicationPage.PNG)

<span data-ttu-id="cf4a3-108">В статье описаны действия в рабочий процесс уведомления об удержании.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-108">The article outlines the steps in the hold notification workflow.</span></span>

## <a name="step-1-specify-communication-details"></a><span data-ttu-id="cf4a3-109">Шаг 1. Указание сведений о связи</span><span class="sxs-lookup"><span data-stu-id="cf4a3-109">Step 1: Specify communication details</span></span>

<span data-ttu-id="cf4a3-110">Первый шаг — указать соответствующие сведения для уведомлений об удержании по юридическим и другим данным хранителя.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-110">The first step is to specify the appropriate details for legal hold notices or other custodian communications.</span></span>

![Страница "Связь с именем"](../media/NameCommunication.PNG)

1. <span data-ttu-id="cf4a3-112">В Центре безопасности & соответствия требованиям перейдите в > **Advanced eDiscovery,** чтобы отобразить список дел в организации.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-112">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery** to display the list of cases in your organization.</span></span>

2. <span data-ttu-id="cf4a3-113">Выберите дело, щелкните **вкладку "Связь"** и выберите "Новое **взаимодействие".**</span><span class="sxs-lookup"><span data-stu-id="cf4a3-113">Select a case, click the **Communications** tab, and then click **New communication**.</span></span>

3. <span data-ttu-id="cf4a3-114">На странице **"Связь с именем"** укажите следующие (необходимые) сведения о связи.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-114">On the **Name communication** page, specify the following (required) communication details.</span></span>

    - <span data-ttu-id="cf4a3-115">**Name**: this is the name for the communication.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-115">**Name**: This is the name for the communication.</span></span>

    - <span data-ttu-id="cf4a3-116">**Выдача** сотрудника: в выпадаемом списке отображается список участников дела.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-116">**Issuing officer**: The dropdown list displays a list of case members.</span></span> <span data-ttu-id="cf4a3-117">Дополнительные сведения о добавлении новых участников в дело см. в примере создания дела [Advanced eDiscovery.](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case)</span><span class="sxs-lookup"><span data-stu-id="cf4a3-117">For more information on how to add new members to a case, see [Create an Advanced eDiscovery case](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case).</span></span> <span data-ttu-id="cf4a3-118">Каждое уведомление, отправленные хранителям, будет отправлено от имени указанного выдавляемого сотрудника.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-118">Each notice sent to custodians will be sent on behalf of the specified issuing officer.</span></span>

> [!NOTE]
> <span data-ttu-id="cf4a3-119">У выдавляемой должности должен быть **активный** почтовый ящик, чтобы он мог демонстрироваться в выпадаемом списке "Сотрудник по выдаче".</span><span class="sxs-lookup"><span data-stu-id="cf4a3-119">The issuing officer must have an **active mailbox** to show up in the Issuing Officer dropdown</span></span>


4. <span data-ttu-id="cf4a3-120">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-120">Click **Next**.</span></span>

## <a name="step-2-define-the-portal-content"></a><span data-ttu-id="cf4a3-121">Шаг 2. Определение содержимого портала</span><span class="sxs-lookup"><span data-stu-id="cf4a3-121">Step 2: Define the portal content</span></span>

<span data-ttu-id="cf4a3-122">Затем можно создать и добавить содержимое уведомления об удержании.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-122">Next, you can create and add the content of the hold notice.</span></span> <span data-ttu-id="cf4a3-123">На странице **"Определение содержимого портала"** в **мастере** создания взаимодействия укажите содержимое уведомления об удержании.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-123">On the **Define portal content** page in the **Create communication** wizard, specify the contents of the hold notice.</span></span> <span data-ttu-id="cf4a3-124">Это содержимое будет автоматически примещение к уведомлениям о выдаче, повторной выдаче, напоминании и эскалации.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-124">This content will be automatically appended to the Issuance, Re-Issue, Reminder, and Escalation notices.</span></span> <span data-ttu-id="cf4a3-125">Кроме того, этот контент будет отображаться на портале соответствия требованиям хранителя.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-125">Additionally, this content will appear in the custodian's Compliance Portal.</span></span> 

![Страница содержимого портала](../media/PortalContent.PNG)

<span data-ttu-id="cf4a3-127">Чтобы создать контент портала:</span><span class="sxs-lookup"><span data-stu-id="cf4a3-127">To create the portal content:</span></span>

1. <span data-ttu-id="cf4a3-128">Введите (или вырезание и ветвь из другого документа) уведомление о удержании в текстовом ящике для содержимого портала.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-128">Type (or cut and paste from another document) your hold notice in the textbox for the portal content.</span></span> 

2. <span data-ttu-id="cf4a3-129">Вставьте переменные объединения в уведомление, чтобы настроить уведомление и поделиться порталом соответствия требованиям custodian.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-129">Insert merge variables into your notice to customize the notice and share the Custodian Compliance Portal.</span></span>

3. <span data-ttu-id="cf4a3-130">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-130">Click **Next**.</span></span>

  >[!Tip]
  ><span data-ttu-id="cf4a3-131">Чтобы узнать больше о том, как настроить контент и формат содержимого портала, см. статью ["Использование редактора коммуникаций".](using-communications-editor.md)</span><span class="sxs-lookup"><span data-stu-id="cf4a3-131">To learn more about how to can customize the content and format of the portal content, see [Use the Communications Editor](using-communications-editor.md).</span></span>

## <a name="step-3-set-the-required-notifications"></a><span data-ttu-id="cf4a3-132">Шаг 3. Настройка необходимых уведомлений</span><span class="sxs-lookup"><span data-stu-id="cf4a3-132">Step 3: Set the required notifications</span></span>

<span data-ttu-id="cf4a3-133">После определения содержимого уведомления об удержании можно настроить рабочий процесс отправки и управления процессом уведомления.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-133">After you've defined the contents of the hold notice, you can set up the workflows around sending and managing the notification process.</span></span> <span data-ttu-id="cf4a3-134">Уведомления — это сообщения электронной почты, которые отправляются для уведомления и последующего уведомления хранителям.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-134">Notifications are email messages that are sent to notify and follow up with custodians.</span></span> <span data-ttu-id="cf4a3-135">Все хранители, добавленные в связь, получат одинаковое уведомление.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-135">Every custodian added to the communication will receive the same notification.</span></span> 

<span data-ttu-id="cf4a3-136">Чтобы настроить и отправить уведомление об удержании, необходимо включить уведомления о выдаче, повторной выдаче и выпуске.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-136">To set up and send a hold notice, you must include Issuance, Re-Issuance, and Release notifications.</span></span>

### <a name="issuance-notification"></a><span data-ttu-id="cf4a3-137">Уведомление о выдаче</span><span class="sxs-lookup"><span data-stu-id="cf4a3-137">Issuance notification</span></span> 

<span data-ttu-id="cf4a3-138">После создания сообщения уведомление  о выдаче инициалось указанным сотрудником по выдаче.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-138">After the communication is created, the **Issuance Notification** is initiated by the specified Issuing Officer.</span></span> <span data-ttu-id="cf4a3-139">Уведомление о выдаче — это первое сообщение, от отправленное хранителям, чтобы уведомить его об их обязательствах по сохранению.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-139">The Issuance notification is the first communication sent to the custodian to inform them about their preservation obligations.</span></span> 

<span data-ttu-id="cf4a3-140">Чтобы создать уведомление о выдаче:</span><span class="sxs-lookup"><span data-stu-id="cf4a3-140">To create an issuance notification:</span></span>

1. <span data-ttu-id="cf4a3-141">На **плитке** "Выдача" нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="cf4a3-141">In the **Issuance** tile, click **Edit**.</span></span>

2. <span data-ttu-id="cf4a3-142">При необходимости добавьте в поля "Ск" и "СК" дополнительных участников дела или **сотрудников.** </span><span class="sxs-lookup"><span data-stu-id="cf4a3-142">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="cf4a3-143">Чтобы добавить в эти поля нескольких пользователей, разделяйте адреса электронной почты за двоеточием.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-143">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>

3. <span data-ttu-id="cf4a3-144">Укажите **тему** уведомления (обязательно).</span><span class="sxs-lookup"><span data-stu-id="cf4a3-144">Specify the **Subject** for the notice (required).</span></span>

4. <span data-ttu-id="cf4a3-145">Укажите содержимое или дополнительные инструкции, которые вы хотите предоставить хранителям (обязательно).</span><span class="sxs-lookup"><span data-stu-id="cf4a3-145">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="cf4a3-146">Содержимое портала, определенное в шаге 2, добавляется в конец уведомления о выдаче.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-146">The portal content you defined in Step 2 is added to the end of the issuance notice.</span></span> 

5. <span data-ttu-id="cf4a3-147">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-147">Click **Save**.</span></span>

### <a name="re-issuance-notification"></a><span data-ttu-id="cf4a3-148">Re-Issuance уведомления</span><span class="sxs-lookup"><span data-stu-id="cf4a3-148">Re-Issuance notification</span></span>

<span data-ttu-id="cf4a3-149">По мере выполнения дела хранителям может потребоваться сохранить дополнительные или меньшие данные, чем было подано ранее.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-149">As the case progresses, custodians may be required to preserve additional or less data than was previously instructed.</span></span> <span data-ttu-id="cf4a3-150">После обновления содержимого портала отправляется уведомление о повторной выдаче, которое оповещает хранителей о любых изменениях в их обязательствах по сохранению.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-150">After you update the portal content, the re-issuance notification is sent and alerts custodians about any changes to their preservation obligations.</span></span>

<span data-ttu-id="cf4a3-151">Чтобы создать уведомление о повторной выдаче:</span><span class="sxs-lookup"><span data-stu-id="cf4a3-151">To create a re-issuance notification:</span></span>

1. <span data-ttu-id="cf4a3-152">На **плитке "Повторное** редактирование" нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="cf4a3-152">In the **Reissue** tile, click **Edit**.</span></span>

2. <span data-ttu-id="cf4a3-153">При необходимости добавьте в поля "Ск" и "Ск" дополнительных участников дела или **сотрудников.** </span><span class="sxs-lookup"><span data-stu-id="cf4a3-153">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="cf4a3-154">Чтобы добавить в эти поля нескольких пользователей, разделяйте адреса электронной почты за двоеточием.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-154">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>

3. <span data-ttu-id="cf4a3-155">Укажите **тему** уведомления (обязательно).</span><span class="sxs-lookup"><span data-stu-id="cf4a3-155">Specify the **Subject** for the notice (required).</span></span>

4. <span data-ttu-id="cf4a3-156">Укажите содержимое или дополнительные инструкции, которые вы хотите предоставить хранителям (обязательно).</span><span class="sxs-lookup"><span data-stu-id="cf4a3-156">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="cf4a3-157">Содержимое портала, определенное в шаге 2, добавляется в конец уведомления о повторной выдаче.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-157">The portal content you defined in Step 2 is added to the end of the re-issuance notice.</span></span>

5. <span data-ttu-id="cf4a3-158">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-158">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="cf4a3-159">Если содержимое портала изменено  (на странице  "Определение содержимого портала" в мастере редактирования связи), уведомление о повторной выдаче будет автоматически отправлено всем хранителям, которые назначены уведомлению.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-159">If the portal content is modified (on the **Define Portal Content** page in the **Edit communication** wizard), the re-issuance notification will be automatically sent to all custodians assigned to the notice.</span></span> <span data-ttu-id="cf4a3-160">После того как уведомление будет отправлено, хранителям будет предложено повторно подтвердить свое уведомление о удержании.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-160">After the notification is sent, custodians will be asked to re-acknowledge their hold notice.</span></span> <span data-ttu-id="cf4a3-161">Если вы настроили какие-либо процессы напоминания или эскалации, они также будут повторно запускаться.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-161">If you have set up any reminder or escalation workflows, these will also re-start.</span></span> <span data-ttu-id="cf4a3-162">Дополнительные сведения о том, какие другие события управления случаями инициирует связь, см. в сведениях о событиях, [которые запускают уведомления.](#events-that-trigger-notifications)</span><span class="sxs-lookup"><span data-stu-id="cf4a3-162">For more information about what other case management events trigger communications, see [Events that trigger notifications](#events-that-trigger-notifications).</span></span>

### <a name="release-notification"></a><span data-ttu-id="cf4a3-163">Уведомление о выпуске</span><span class="sxs-lookup"><span data-stu-id="cf4a3-163">Release notification</span></span>

<span data-ttu-id="cf4a3-164">После разрешения вопроса или если хранители больше не подлежат сохранению содержимого, вы можете освободить хранителя из дела.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-164">After a matter is resolved or if a custodian is no longer subject to preserve content, you can release the custodian from a case.</span></span> <span data-ttu-id="cf4a3-165">Если хранителям ранее было выдано уведомление о удержании, уведомление о выпуске можно использовать для оповещения хранителей о том, что они освобождены от своих обязательств.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-165">If the custodian was previously issued a hold notice, the release notification can be used to alert custodians that they have been released from their obligation.</span></span>

<span data-ttu-id="cf4a3-166">Чтобы создать уведомление о выпуске:</span><span class="sxs-lookup"><span data-stu-id="cf4a3-166">To create a release notification:</span></span> 

1. <span data-ttu-id="cf4a3-167">На **плитке "Выпуск"** нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="cf4a3-167">In the **Release** tile, click **Edit**.</span></span>

2. <span data-ttu-id="cf4a3-168">При необходимости добавьте в поля "Ск" и "СК" дополнительных участников дела или **сотрудников.** </span><span class="sxs-lookup"><span data-stu-id="cf4a3-168">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="cf4a3-169">Чтобы добавить в эти поля нескольких пользователей, разделяйте адреса электронной почты за двоеточием.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-169">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>

3. <span data-ttu-id="cf4a3-170">Укажите **тему** уведомления (обязательно).</span><span class="sxs-lookup"><span data-stu-id="cf4a3-170">Specify the **Subject** for the notice (required).</span></span>

4. <span data-ttu-id="cf4a3-171">Укажите содержимое или дополнительные инструкции, которые вы хотите предоставить хранителям (обязательно).</span><span class="sxs-lookup"><span data-stu-id="cf4a3-171">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span>

5. <span data-ttu-id="cf4a3-172">Нажмите **кнопку** "Сохранить" и перейдите к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-172">Click **Save** and go to the next step.</span></span>

## <a name="optional-step-4-set-the-optional-notifications"></a><span data-ttu-id="cf4a3-173">(Необязательно) Шаг 4. Настройка необязательных уведомлений</span><span class="sxs-lookup"><span data-stu-id="cf4a3-173">(Optional) Step 4: Set the optional notifications</span></span>

<span data-ttu-id="cf4a3-174">При желании можно упростить рабочий процесс для дальнейшего с неотвещения хранителями, создав и запланируя автоматические напоминания и уведомления об эскалации.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-174">Optionally, you can simplify the workflow for following up with unresponsive custodians by creating and scheduling automated reminder and escalation notifications.</span></span>

![Страница напоминания/эскалации](../media/ReminderEscalations.PNG)

### <a name="reminders"></a><span data-ttu-id="cf4a3-176">Reminders</span><span class="sxs-lookup"><span data-stu-id="cf4a3-176">Reminders</span></span>

<span data-ttu-id="cf4a3-177">После того как вы отправили уведомление об удержании, вы можете следить за неотвеживающими хранителями, определив рабочий процесс напоминания.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-177">After you have sent a hold notification, you can follow up with unresponsive custodians by defining a reminder workflow.</span></span>

<span data-ttu-id="cf4a3-178">Чтобы запланировать напоминания:</span><span class="sxs-lookup"><span data-stu-id="cf4a3-178">To schedule reminders:</span></span>

1. <span data-ttu-id="cf4a3-179">На **плитке "Напоминание"** нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="cf4a3-179">In the **Reminder** tile, click **Edit**.</span></span>

2. <span data-ttu-id="cf4a3-180">**Включит** рабочий процесс напоминания, включив **переключель состояния** (обязательно).</span><span class="sxs-lookup"><span data-stu-id="cf4a3-180">Enable the **Reminder** workflow by turning on the **Status** toggle (required).</span></span>

3. <span data-ttu-id="cf4a3-181">Укажите интервал **напоминания (в днях)** (обязательно).</span><span class="sxs-lookup"><span data-stu-id="cf4a3-181">Specify the **Reminder interval (in days)** (required).</span></span> <span data-ttu-id="cf4a3-182">Это количество дней до отправки первых и последующих уведомлений с напоминанием.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-182">This is the number of days to wait before sending the first and follow-up reminder notifications.</span></span> <span data-ttu-id="cf4a3-183">Например, если для интервала напоминания установлено семь дней, то первое напоминание будет отправлено через семь дней после первоначальной выдачи уведомления об удержании.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-183">For example, if you set the reminder interval to seven days, then the first reminder would be sent seven days after the hold notification was initially issued.</span></span> <span data-ttu-id="cf4a3-184">Все последующие напоминания также отправляются каждые семь дней.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-184">All subsequent reminders would also be sent every seven days.</span></span>

4. <span data-ttu-id="cf4a3-185">Укажите **количество напоминаний** (обязательно).</span><span class="sxs-lookup"><span data-stu-id="cf4a3-185">Specify the **Number of reminders** (required).</span></span> <span data-ttu-id="cf4a3-186">В этом поле указывается количество напоминаний, отправляемых неотвечивым хранителям.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-186">This field specifies how many reminders to send to unresponsive custodians.</span></span> <span data-ttu-id="cf4a3-187">Например, если установить для количества напоминаний значение 3, хранители получат не более трех напоминаний.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-187">For example, if you set the number of reminders to 3, then a custodian would receive a maximum of three reminders.</span></span> <span data-ttu-id="cf4a3-188">После того как хранител подтвердит уведомление об удержании, напоминания больше не будут отправлены этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-188">After a custodian acknowledges the hold notification, reminders will no longer be sent to that user.</span></span>

5. <span data-ttu-id="cf4a3-189">Укажите **тему** уведомления (обязательно).</span><span class="sxs-lookup"><span data-stu-id="cf4a3-189">Specify the **Subject** for the notice (required).</span></span> 

6. <span data-ttu-id="cf4a3-190">Укажите содержимое или дополнительные инструкции, которые вы хотите предоставить хранителям (обязательно).</span><span class="sxs-lookup"><span data-stu-id="cf4a3-190">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="cf4a3-191">Содержимое портала, определенное в шаге 2, добавляется в конец уведомления с напоминанием.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-191">The portal content you defined in Step 2 is added to the end of the reminder notice.</span></span>

7. <span data-ttu-id="cf4a3-192">Нажмите **кнопку "Сохранить"** и перейдите к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-192">Click **Save** and go the next step.</span></span>

### <a name="escalations"></a><span data-ttu-id="cf4a3-193">Эскалации</span><span class="sxs-lookup"><span data-stu-id="cf4a3-193">Escalations</span></span>

<span data-ttu-id="cf4a3-194">В некоторых ситуациях могут потребоваться дополнительные способы данной меры с неотвечивой хранителями.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-194">In some situations, you may need additional ways to follow up with unresponsive custodians.</span></span> <span data-ttu-id="cf4a3-195">Если хранител не подтверждает уведомление об удержании после получения указанного количества напоминаний, группа юристов может указать рабочий процесс для автоматической отправки уведомления об эскалации хранителю и его руководителю.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-195">If a custodian doesn't acknowledge a hold notification after receiving the specified number of reminders, the legal team can specify a workflow to automatically send an escalation notice to the custodian and their manager.</span></span>

<span data-ttu-id="cf4a3-196">Чтобы запланировать эскалацию, спланировать:</span><span class="sxs-lookup"><span data-stu-id="cf4a3-196">To schedule escalations:</span></span>

1. <span data-ttu-id="cf4a3-197">На **плитке "Эскалация"** нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="cf4a3-197">In the **Escalation** tile, click **Edit**.</span></span>

2. <span data-ttu-id="cf4a3-198">**Включите** рабочий процесс эскалации, включив **переключель состояния.**</span><span class="sxs-lookup"><span data-stu-id="cf4a3-198">Enable the **Escalation** workflow by turning on the **Status** toggle.</span></span>

3. <span data-ttu-id="cf4a3-199">Укажите **интервал эскалации (в днях)** (обязательно).</span><span class="sxs-lookup"><span data-stu-id="cf4a3-199">Specify the **Escalation interval (in days)** (required).</span></span>

4. <span data-ttu-id="cf4a3-200">Укажите **количество эскалаций** (обязательно).</span><span class="sxs-lookup"><span data-stu-id="cf4a3-200">Specify the **Number of escalations** (required).</span></span> <span data-ttu-id="cf4a3-201">В этом поле указывается количество эскалаций для отправки неотвечивым хранителям.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-201">This field specifies how many escalations to send to unresponsive custodians.</span></span> <span data-ttu-id="cf4a3-202">Например, если вы установите для количества эскалаций значение 3, уведомление об эскалации будет отправлено хранителям и их руководителю не более трех раз.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-202">For example, if you set the number of escalations to 3, then an escalation notice would be sent to the custodian and their manager a maximum of three times.</span></span> <span data-ttu-id="cf4a3-203">После того как хранител подтвердит уведомление об удержании, эскалации больше не будут отправлены.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-203">After a custodian acknowledges the hold notification, escalations will no longer be sent.</span></span>

5. <span data-ttu-id="cf4a3-204">Укажите **тему** уведомления (обязательно).</span><span class="sxs-lookup"><span data-stu-id="cf4a3-204">Specify the **Subject** for the notice (required).</span></span> 

6. <span data-ttu-id="cf4a3-205">Укажите содержимое или дополнительные инструкции, которые вы хотите предоставить хранителям (обязательно).</span><span class="sxs-lookup"><span data-stu-id="cf4a3-205">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="cf4a3-206">Содержимое портала, определенное на шаге 2, добавляется в конец уведомления об эскалации.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-206">The portal content you defined in Step 2 is added to the end of the escalation notice.</span></span>

7. <span data-ttu-id="cf4a3-207">Нажмите **кнопку "Сохранить"** и перейдите к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-207">Click **Save** and go the next step.</span></span>

## <a name="step-5-assign-custodians-to-receive-notifications"></a><span data-ttu-id="cf4a3-208">Шаг 5. Назначение хранителей для получения уведомлений</span><span class="sxs-lookup"><span data-stu-id="cf4a3-208">Step 5: Assign custodians to receive notifications</span></span>

<span data-ttu-id="cf4a3-209">Завершив отправку содержимого для уведомлений, выберите хранителей, в которые вы хотите отправлять уведомления.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-209">After you have finalized the content for notifications, select the custodians that you would like to send notifications to.</span></span> 

![Страница "Выбор хранителей"](../media/SelectCustodians.PNG)

<span data-ttu-id="cf4a3-211">Чтобы добавить хранителей:</span><span class="sxs-lookup"><span data-stu-id="cf4a3-211">To add custodians:</span></span>

1. <span data-ttu-id="cf4a3-212">Назначьте хранителей сообщению, щелкнув рядом с их именем контрольный ящик.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-212">Assign custodians to the communication by clicking the checkbox next to their name.</span></span>

    <span data-ttu-id="cf4a3-213">После создания сообщения рабочий процесс уведомления автоматически применяется к выбранным хранителям.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-213">After the communication is created, the notification workflow will automatically apply to the selected custodians.</span></span>

2. <span data-ttu-id="cf4a3-214">Нажмите **кнопку** "Далее", чтобы просмотреть параметры связи и сведения.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-214">Click **Next** to review the communication settings and details.</span></span>

>[!NOTE]
><span data-ttu-id="cf4a3-215">Вы можете добавлять только хранителей, которые были добавлены в дело и не были отправлены в рамках дела еще одно уведомление.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-215">You can only add custodians who have been added to the case and haven't been sent another notification within the case.</span></span>

## <a name="step-6-review-settings"></a><span data-ttu-id="cf4a3-216">Шаг 6. Просмотр параметров</span><span class="sxs-lookup"><span data-stu-id="cf4a3-216">Step 6: Review settings</span></span>

<span data-ttu-id="cf4a3-217">После просмотра параметров и нажатия кнопки **"Отправить"** для завершения связи система автоматически запустит рабочий процесс связи, отправив уведомление о выдаче.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-217">After you review the settings and click **Send** to complete the communication, the system will automatically start the communication workflow by sending the issuance notice.</span></span>

## <a name="events-that-trigger-notifications"></a><span data-ttu-id="cf4a3-218">События, которые запускают уведомления</span><span class="sxs-lookup"><span data-stu-id="cf4a3-218">Events that trigger notifications</span></span>

<span data-ttu-id="cf4a3-219">В следующей таблице описываются события в процессе управления делами, которые запускаются при отправлении хранителям различных типов уведомлений.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-219">The following table describes events in the case management process that trigger when the different types of notifications are sent to custodians.</span></span>

|<span data-ttu-id="cf4a3-220">Тип связи</span><span class="sxs-lookup"><span data-stu-id="cf4a3-220">Type of communication</span></span>|<span data-ttu-id="cf4a3-221">Триггер</span><span class="sxs-lookup"><span data-stu-id="cf4a3-221">Trigger</span></span> |
|:---------|:---------|
|<span data-ttu-id="cf4a3-222">Уведомления о выдаче</span><span class="sxs-lookup"><span data-stu-id="cf4a3-222">Issuance notices</span></span>|<span data-ttu-id="cf4a3-223">Начальное создание уведомления.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-223">The initial creation of the notification.</span></span> <span data-ttu-id="cf4a3-224">Вы также можете вручную повторно уведомить об удержании.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-224">You can also manually resend a hold notification.</span></span> |
|<span data-ttu-id="cf4a3-225">Уведомления о повторной выдаче</span><span class="sxs-lookup"><span data-stu-id="cf4a3-225">Re-issuance notices</span></span>|<span data-ttu-id="cf4a3-226">Обновление содержимого портала на странице **"Определение содержимого портала"** в **мастере редактирования связи.**</span><span class="sxs-lookup"><span data-stu-id="cf4a3-226">Updating the portal content on the **Define Portal Content** page in the **Edit communication** wizard.</span></span>|
|<span data-ttu-id="cf4a3-227">Уведомления о выпуске</span><span class="sxs-lookup"><span data-stu-id="cf4a3-227">Release notices</span></span>|<span data-ttu-id="cf4a3-228">Хранители освобождены из дела.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-228">The custodian is released from the case.</span></span>|
|<span data-ttu-id="cf4a3-229">Reminders</span><span class="sxs-lookup"><span data-stu-id="cf4a3-229">Reminders</span></span>|<span data-ttu-id="cf4a3-230">Интервал и количество напоминаний, настроенных для напоминания.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-230">The interval and number of reminders configured for the reminder.</span></span>|
|<span data-ttu-id="cf4a3-231">Эскалации</span><span class="sxs-lookup"><span data-stu-id="cf4a3-231">Escalations</span></span>|<span data-ttu-id="cf4a3-232">Интервал и количество напоминаний, настроенных для эскалации.</span><span class="sxs-lookup"><span data-stu-id="cf4a3-232">The interval and number of reminders configured for the escalation.</span></span>|
|||
