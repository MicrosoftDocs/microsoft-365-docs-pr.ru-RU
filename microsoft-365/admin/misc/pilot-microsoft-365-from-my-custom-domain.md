---
title: Тестирование Microsoft 365 с личного домена
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom: ''
search.appverid:
- BCS160
- MET150
- MOE150
description: Узнайте, как протестировать пересылку электронной почты из личного домена в почтовый ящик Microsoft 365, используя всего две тестовые учетные записи.
ms.openlocfilehash: bfcb2bda4d560ab629ddebed88ac1d55e6224c05
ms.sourcegitcommit: 5f980a9eb5aca61cf3662ef0bc65dec215e21656
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "45186051"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="a5b38-103">Тестирование Microsoft 365 с личного домена</span><span class="sxs-lookup"><span data-stu-id="a5b38-103">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="a5b38-104">Вы можете протестировать Microsoft 365 со следующими требованиями и ограничениями:</span><span class="sxs-lookup"><span data-stu-id="a5b38-104">You can pilot Microsoft 365 with these requirements and limitations:</span></span>

- <span data-ttu-id="a5b38-105">Ваш текущий поставщик услуг электронной почты должен предоставлять услугу переадресации электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a5b38-105">Your current email provider must provide email forwarding.</span></span>

- <span data-ttu-id="a5b38-106">Вы должны управлять записями DNS Microsoft 365 у своего поставщика услуг размещения DNS. Microsoft 365 не будет управлять этими записями вместо вас.</span><span class="sxs-lookup"><span data-stu-id="a5b38-106">You must manage your Microsoft 365 DNS records at your DNS hosting provider, rather than have Microsoft 365 manage these records for you.</span></span>

    <span data-ttu-id="a5b38-107">Дополнительные сведения см. в статье [Добавление записей DNS для подключения своего домена](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span><span class="sxs-lookup"><span data-stu-id="a5b38-107">To learn more, see [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

- <span data-ttu-id="a5b38-108">Сведения о занятости для пользователей на другом почтовом сервере недоступны.</span><span class="sxs-lookup"><span data-stu-id="a5b38-108">Free/busy information for users on the other email server is not available.</span></span>

- <span data-ttu-id="a5b38-109">Администраторы не могут управлять всеми учетными записями пользователей из одного расположения.</span><span class="sxs-lookup"><span data-stu-id="a5b38-109">Admins can't administer all user accounts from a single location.</span></span>

- <span data-ttu-id="a5b38-110">Возможно, пользователи не смогут использовать фильтрацию нежелательной почты Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5b38-110">Users might not be able to use Microsoft 365 spam filtering.</span></span>

## <a name="set-up-a-microsoft-365-pilot"></a><span data-ttu-id="a5b38-111">Подготовка к тестированию Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a5b38-111">Set up a Microsoft 365 pilot</span></span>

<span data-ttu-id="a5b38-112">Чтобы подготовиться к тестированию Microsoft 365, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a5b38-112">Follow these steps to set up a Microsoft 365 pilot:</span></span>

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a><span data-ttu-id="a5b38-113">Шаг 1. Войдите в Центр администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a5b38-113">Step 1: Sign in to the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="a5b38-114">Войдите в [Центр администрирования Microsoft 365](https://admin.microsoft.com) со своей рабочей или учебной учетной записью.</span><span class="sxs-lookup"><span data-stu-id="a5b38-114">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your work or school account.</span></span>

2. <span data-ttu-id="a5b38-115">В области навигации слева выберите **Параметры** > **Домены**.</span><span class="sxs-lookup"><span data-stu-id="a5b38-115">Select **Settings** > **Domains** in the left navigation pane.</span></span>

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a><span data-ttu-id="a5b38-116">Шаг 2. Подтвердите, что вы являетесь владельцем домена</span><span class="sxs-lookup"><span data-stu-id="a5b38-116">Step 2: Verify that you own the domain you want to use</span></span>

1. <span data-ttu-id="a5b38-117">На странице **Домены** выберите **Добавить домен**.</span><span class="sxs-lookup"><span data-stu-id="a5b38-117">On the **Domains** page, select **Add domain**.</span></span>

2. <span data-ttu-id="a5b38-118">Введите доменное имя в поле, выберите **Использовать этот домен** > **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="a5b38-118">Type the domain name in the box, select **Use this domain**, and then select **Continue**.</span></span>

3. <span data-ttu-id="a5b38-119">Выберите службы, которые нужно протестировать с вашим доменом, например электронную почту и обмен мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="a5b38-119">Select the services you want to test with your domain, like email and instant messaging.</span></span>

5. <span data-ttu-id="a5b38-120">На странице домена **Проверка** выполните пошаговые инструкции, а затем выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="a5b38-120">On the **Verify** domain page, follow the step-by-step instructions, amd then select **Verify**.</span></span>

    <span data-ttu-id="a5b38-121">Чтобы изменения DNS вступили в силу, требуется от нескольких минут до 72 часов.</span><span class="sxs-lookup"><span data-stu-id="a5b38-121">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span>

    <span data-ttu-id="a5b38-122">Если проверка пройдет успешно, вас попросят изменить записи DNS.</span><span class="sxs-lookup"><span data-stu-id="a5b38-122">When verification is successful, you are asked to modify your DNS records.</span></span>

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a><span data-ttu-id="a5b38-123">Шаг 3. Пометьте домен как общий в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a5b38-123">Step 3: Mark the domain as shared in Exchange Online</span></span>

1. <span data-ttu-id="a5b38-124">В Центре администрирования Exchange, в разделе **Поток обработки почты**, выберите **Обслуживаемые домены**, а затем выберите нужный домен.</span><span class="sxs-lookup"><span data-stu-id="a5b38-124">In the Exchange admin center, in the **Mail flow** section, select **Accepted domains**, and then select the domain you want to modify.</span></span>

2. <span data-ttu-id="a5b38-125">Дважды щелкните, чтобы открыть окно, а затем выберите **Внутренняя ретрансляция**.</span><span class="sxs-lookup"><span data-stu-id="a5b38-125">Double-click to open the window, and then select **Internal Relay**.</span></span> 

3. <span data-ttu-id="a5b38-126">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a5b38-126">Select **Save**.</span></span>

    <span data-ttu-id="a5b38-127">Чтобы это изменение вступило в силу, может потребоваться несколько минут.</span><span class="sxs-lookup"><span data-stu-id="a5b38-127">This setting might require a few minutes to take effect.</span></span>

### <a name="step-4-unblock-the-existing-email-server-optional"></a><span data-ttu-id="a5b38-128">Шаг 4. Разблокируйте существующий почтовый сервер (необязательно)</span><span class="sxs-lookup"><span data-stu-id="a5b38-128">Step 4: Unblock the existing email server (optional)</span></span>

<span data-ttu-id="a5b38-129">В Microsoft 365 для защиты от нежелательной почты используется служба Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="a5b38-129">Microsoft 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="a5b38-130">EOP может заблокировать ваш почтовый сервер, если обнаружит, что он пересылает большой объем нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="a5b38-130">EOP might block your existing mail server if it detects a high volume of spam being forwarded by your current mail server.</span></span> <span data-ttu-id="a5b38-131">Если вы доверяете защите от нежелательной почты, которую обеспечивает ваш сторонний поставщик услуг электронной почты, вы можете разблокировать сервер в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5b38-131">If you trust the spam protection for your other email provider, you can unblock the server in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="a5b38-132">После разблокировки существующего почтового сервера любые нежелательные сообщения с вашего исходного сервера будут поступать в почтовые ящики Microsoft 365, и вы не сможете оценить, насколько эффективно работает защита от нежелательной почты Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5b38-132">Unblocking your existing email server allows any spam that arrives through your original server to come to the Microsoft 365 mailboxes, and you can’t evaluate how well Microsoft 365 prevents spam.</span></span>

1. <span data-ttu-id="a5b38-133">В области навигации Центра администрирования Exchange выберите **Защита** > **Фильтр подключений**.</span><span class="sxs-lookup"><span data-stu-id="a5b38-133">In the Exchange admin center navigation pane, select **Protection**, and then select **Connection filter**.</span></span>

2. <span data-ttu-id="a5b38-134">В поле **Список разрешенных IP-адресов** нажмите знак **+** и добавьте IP-адрес почтового сервера текущего поставщика услуг электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a5b38-134">In the **IP Allow list**, select **+**, and add the mail server IP address for your current email provider.</span></span> 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a><span data-ttu-id="a5b38-135">Шаг 5. Создайте учетные записи пользователей и установите основной адрес для ответов</span><span class="sxs-lookup"><span data-stu-id="a5b38-135">Step 5: Create user accounts and set the primary reply-to address</span></span>

1. <span data-ttu-id="a5b38-136">В Центре администрирования Microsoft 365, в области навигации слева, выберите **Пользователи** > **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="a5b38-136">In the Microsoft 365 admin center left navigation, select **Users** > **Active Users**.</span></span>

2. <span data-ttu-id="a5b38-137">Создайте две тестовые учетные записи, добавив двух существующих пользователей.</span><span class="sxs-lookup"><span data-stu-id="a5b38-137">Create two test accounts by adding two existing users.</span></span>

    <span data-ttu-id="a5b38-138">Для каждой учетной записи выберите **+ Добавить пользователя** и введите необходимые сведения, в том числе метод парольной защиты, который вы хотите протестировать.</span><span class="sxs-lookup"><span data-stu-id="a5b38-138">For each account, select **+ Add a user**, and fill out the required information, including the password method you want to test.</span></span>

    <span data-ttu-id="a5b38-139">Чтобы адрес электронной почты пользователя не менялся, содержимое поля **Имя пользователя** должно соответствовать текущему адресу электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="a5b38-139">To ensure a user’s email stays the same, the **User name** field must match the user’s current email address.</span></span>

3. <span data-ttu-id="a5b38-140">Выберите соответствующую лицензию и нажмите **Далее** > **Завершить добавление**.</span><span class="sxs-lookup"><span data-stu-id="a5b38-140">Choose the appropriate license, click **Next**, and then click **Finish adding**.</span></span> 

4. <span data-ttu-id="a5b38-141">Рядом с полем **Имя пользователя** выберите имя личного домена в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="a5b38-141">Next to **User name**, select your custom domain name from the drop-down list.</span></span> 

5. <span data-ttu-id="a5b38-142">Выберите **Создать** > **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="a5b38-142">Select **Create** > **Close**.</span></span>

### <a name="step-6-update-dns-records-at-your-dns-hosting-provider"></a><span data-ttu-id="a5b38-143">Шаг 6. Обновите записи DNS в системе поставщика услуг размещения DNS</span><span class="sxs-lookup"><span data-stu-id="a5b38-143">Step 6: Update DNS records at your DNS hosting provider</span></span>

<span data-ttu-id="a5b38-144">Войдите на сайт поставщика услуг размещения DNS и следуйте инструкциям, приведенным в статье [Добавление записей DNS для подключения своего домена](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span><span class="sxs-lookup"><span data-stu-id="a5b38-144">Sign in to your DNS hosting provider's website, and follow the instructions at [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

<span data-ttu-id="a5b38-145">**Добавьте следующие исключения:**</span><span class="sxs-lookup"><span data-stu-id="a5b38-145">**Make the following two exceptions:**</span></span>

- <span data-ttu-id="a5b38-146">Не создавайте новую и не изменяйте существующую MX-запись.</span><span class="sxs-lookup"><span data-stu-id="a5b38-146">Do not create a new MX record or change your existing MX record.</span></span>

- <span data-ttu-id="a5b38-147">Если у вас уже есть запись SPF для предыдущего поставщика услуг электронной почты, не создавайте запись SPF (TXT) для Exchange Online, а добавьте параметр "include:spf.protection.outlook.com" в текущую запись TXT.</span><span class="sxs-lookup"><span data-stu-id="a5b38-147">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, add "include:spf.protection.outlook.com" to the current TXT record.</span></span>

    <span data-ttu-id="a5b38-148">Пример: "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span><span class="sxs-lookup"><span data-stu-id="a5b38-148">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>

    <span data-ttu-id="a5b38-149">Если у вас еще нет записи SPF, измените запись, рекомендованную Microsoft 365, включив в нее домен текущего поставщика услуг электронной почты, и добавьте spf.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="a5b38-149">If you don't have an SPF record, modify the one recommended by Microsoft 365 to include the domain for your current email provider, and add spf.protection.outlook.com.</span></span> <span data-ttu-id="a5b38-150">В результате будет разрешена отправка исходящих сообщений из обеих почтовых систем.</span><span class="sxs-lookup"><span data-stu-id="a5b38-150">This authorizes outgoing messages from both email systems.</span></span>

### <a name="step-7-set-up-email-forwarding-at-your-current-provider"></a><span data-ttu-id="a5b38-151">Шаг 7. Настройте пересылку электронной почты в системе текущего поставщика</span><span class="sxs-lookup"><span data-stu-id="a5b38-151">Step 7: Set up email forwarding at your current provider</span></span>

<span data-ttu-id="a5b38-152">В системе текущего поставщика услуг электронной почты настройте для учетных записей пользователей пересылку в ваш домен onmicrosoft.com:</span><span class="sxs-lookup"><span data-stu-id="a5b38-152">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>

- <span data-ttu-id="a5b38-153">Пересылка с почтового ящика пользователя A на адрес usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="a5b38-153">Forward User A mailbox to usera@yourcompany.onmicrosoft.com</span></span>

- <span data-ttu-id="a5b38-154">Пересылка с почтового ящика пользователя B на адрес usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="a5b38-154">Forward User B mailbox to userb@yourcompany.onmicrosoft.com</span></span>

<span data-ttu-id="a5b38-155">После выполнения этого действия все сообщения, отправленные на адреса usera@yourcompany.com и userb@yourcompany.com, будут доступны в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5b38-155">When you complete this step, all email sent to usera@yourcompany.com and userb@yourcompany.com is available in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="a5b38-156">За точными инструкциями по настройке пересылки обратитесь к текущему поставщику услуг электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a5b38-156">Contact your current email provider for the exact steps to set up email forwarding.</span></span><br/>
> <span data-ttu-id="a5b38-157">Сохранять копии сообщений на сервере текущего поставщика не нужно.</span><span class="sxs-lookup"><span data-stu-id="a5b38-157">You don't need to keep a copy of messages at the current email provider.</span></span><br/>
> <span data-ttu-id="a5b38-158">Большинство поставщиков при пересылке электронной почты оставляют адрес для ответа без изменений, чтобы ответы направлялись исходному отправителю.</span><span class="sxs-lookup"><span data-stu-id="a5b38-158">Most providers forward email by leaving the Reply-to address of the sender intact so that replies go to the original sender.</span></span>

### <a name="step-8-test-mail-flow"></a><span data-ttu-id="a5b38-159">Шаг 8. Проверьте поток обработки почты</span><span class="sxs-lookup"><span data-stu-id="a5b38-159">Step 8: Test mail flow</span></span>

1. <span data-ttu-id="a5b38-160">Войдите в Outlook Web App, используя учетные данные пользователя A.</span><span class="sxs-lookup"><span data-stu-id="a5b38-160">Sign in to Outlook Web App using the credentials for User A.</span></span>

2. <span data-ttu-id="a5b38-161">Выполните указанные ниже проверки.</span><span class="sxs-lookup"><span data-stu-id="a5b38-161">Perform these tests:</span></span>

    - <span data-ttu-id="a5b38-162">Протестируйте локальную электронную почту Microsoft, отправив сообщение, например пользователю B. Электронная почта доставляется мгновенно.</span><span class="sxs-lookup"><span data-stu-id="a5b38-162">Test local Microsoft email by sending an email, for example, to User B. The email is delivered immediately.</span></span> <span data-ttu-id="a5b38-163">В этом случае сообщение не направляется в почтовый ящик пользователя B на исходном сервере, поскольку почтовый ящик Microsoft 365 является локальным.</span><span class="sxs-lookup"><span data-stu-id="a5b38-163">In this scenario, the message is not routed to the mailbox for User B on your original server because the Microsoft 365 mailbox is local.</span></span>

    - <span data-ttu-id="a5b38-164">Протестируйте электронную почту пользователя в существующей почтовой системе, отправив сообщение, например, пользователю C. Электронная почта доставляется в почтовый ящик пользователя C на исходном почтовом сервере.</span><span class="sxs-lookup"><span data-stu-id="a5b38-164">Test email to a user on the existing email system by sending an email, for example, to User C. The email is delivered to the mailbox for User C on your original mail server.</span></span>

    - <span data-ttu-id="a5b38-165">Убедитесь, что пересылка настроена правильно, с помощью сторонней учетной записи или учетной записи сотрудника в существующей почтовой системе.</span><span class="sxs-lookup"><span data-stu-id="a5b38-165">Verify that forwarding is set up properly from an outside account, or from an employee email account on the existing email system.</span></span> <span data-ttu-id="a5b38-166">Например, из учетной записи пользователя C на исходном сервере или учетной записи Hotmail отправьте пользователю A сообщение и убедитесь, что оно поступило в почтовый ящик пользователя A в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a5b38-166">For example, from the original server account for User C or a Hotmail account, send User A an email and verify that it arrives in the Microsoft 365 mailbox for User A.</span></span>

### <a name="step-9-move-mailbox-contents"></a><span data-ttu-id="a5b38-167">Шаг 9. Переместите содержимое почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="a5b38-167">Step 9: Move mailbox contents</span></span>

<span data-ttu-id="a5b38-168">Так как вы переносите только двух тестовых пользователей, и оба пользователя (A и B) используют Outlook, вы можете переместить почту, открыв старый PST-файл в новом профиле Outlook и скопировав сообщения, элементы календаря, контакты и т. д.</span><span class="sxs-lookup"><span data-stu-id="a5b38-168">Because you are moving only two test users, and User A and User B are both using Outlook, you can move the email by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, and so on.</span></span> <span data-ttu-id="a5b38-169">Подробные сведения см. в статье [Импорт писем, контактов и календаря Outlook из PST-файла](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span><span class="sxs-lookup"><span data-stu-id="a5b38-169">For more information, see [Import email, contacts, and calendar from an Outlook .pst file](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span></span>

<span data-ttu-id="a5b38-170">После импорта в почтовый ящик Microsoft 365 к элементам можно будет получить доступ с любого устройства.</span><span class="sxs-lookup"><span data-stu-id="a5b38-170">After they’re imported to the appropriate locations in the Microsoft 365 mailbox, the items can be accessed from any device, anywhere.</span></span>

<span data-ttu-id="a5b38-171">При наличии дополнительных почтовых ящиков или если сотрудники не используют Outlook, можно воспользоваться инструментами миграции, доступными в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="a5b38-171">When more mailboxes are involved, or if employees are not using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="a5b38-172">Для этого перейдите в Центр администрирования Exchange и следуйте указаниям в статье [Перенос электронной почты с сервера IMAP в почтовые ящики Exchange Online — необходим новый ресурс со статьей].</span><span class="sxs-lookup"><span data-stu-id="a5b38-172">To get started, go to Exchange admin center, and follow the directions in [Migrate Email from an IMAP Server to Exchange Online Mailboxes – we need a new article resource].</span></span>