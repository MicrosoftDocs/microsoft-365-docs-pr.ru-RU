---
title: Тестирование Microsoft 365 с личного домена
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
description: Узнайте, как протестировать пересылку электронной почты из личного домена в почтовый ящик Microsoft 365, используя всего две тестовые учетные записи.
ms.openlocfilehash: b2017da30aba3b48b51de26b7907167dc5dd3e6e
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623649"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="bf7f4-103">Тестирование Microsoft 365 с личного домена</span><span class="sxs-lookup"><span data-stu-id="bf7f4-103">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="bf7f4-104">Вы можете протестировать Microsoft 365 со следующими требованиями и ограничениями:</span><span class="sxs-lookup"><span data-stu-id="bf7f4-104">You can pilot Microsoft 365 with these requirements and limitations:</span></span>

- <span data-ttu-id="bf7f4-105">Ваш текущий поставщик услуг электронной почты должен предоставлять услугу переадресации электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-105">Your current email provider must provide email forwarding.</span></span>

- <span data-ttu-id="bf7f4-106">Вы должны управлять записями DNS Microsoft 365 у своего поставщика услуг размещения DNS. Microsoft 365 не будет управлять этими записями вместо вас.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-106">You must manage your Microsoft 365 DNS records at your DNS hosting provider, rather than have Microsoft 365 manage these records for you.</span></span>

    <span data-ttu-id="bf7f4-107">Дополнительные сведения см. в статье [Добавление записей DNS для подключения своего домена](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="bf7f4-107">To learn more, see [Add DNS records to connect your domain](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

- <span data-ttu-id="bf7f4-108">Сведения о занятости для пользователей на другом почтовом сервере недоступны.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-108">Free/busy information for users on the other email server is not available.</span></span>

- <span data-ttu-id="bf7f4-109">Администраторы не могут управлять всеми учетными записями пользователей из одного расположения.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-109">Admins can't administer all user accounts from a single location.</span></span>

- <span data-ttu-id="bf7f4-110">Возможно, пользователи не смогут использовать фильтрацию нежелательной почты Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-110">Users might not be able to use Microsoft 365 spam filtering.</span></span>

- <span data-ttu-id="bf7f4-111">Это рекомендуется для небольшого числа пользователей и относится только к использованию электронной почты для пилотного проекта.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-111">This is recommended for a very small number of users and only applies to the use of email for a pilot.</span></span>

## <a name="set-up-a-microsoft-365-pilot"></a><span data-ttu-id="bf7f4-112">Подготовка к тестированию Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bf7f4-112">Set up a Microsoft 365 pilot</span></span>

<span data-ttu-id="bf7f4-113">Чтобы подготовиться к тестированию Microsoft 365, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="bf7f4-113">Follow these steps to set up a Microsoft 365 pilot:</span></span>

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a><span data-ttu-id="bf7f4-114">Шаг 1. Войдите в Центр администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bf7f4-114">Step 1: Sign in to the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="bf7f4-115">Войдите в [Центр администрирования Microsoft 365](https://admin.microsoft.com) со своей рабочей или учебной учетной записью.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-115">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your work or school account.</span></span>

2. <span data-ttu-id="bf7f4-116">В области навигации слева выберите **Параметры** > **Домены**.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-116">Select **Settings** > **Domains** in the left navigation pane.</span></span>

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a><span data-ttu-id="bf7f4-117">Шаг 2. Подтвердите, что вы являетесь владельцем домена</span><span class="sxs-lookup"><span data-stu-id="bf7f4-117">Step 2: Verify that you own the domain you want to use</span></span>

1. <span data-ttu-id="bf7f4-118">На странице **Домены** выберите **Добавить домен**.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-118">On the **Domains** page, select **Add domain**.</span></span>

2. <span data-ttu-id="bf7f4-119">Введите доменное имя в поле, выберите **Использовать этот домен** > **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-119">Type the domain name in the box, select **Use this domain**, and then select **Continue**.</span></span>

3. <span data-ttu-id="bf7f4-120">Выберите службы, которые нужно протестировать с вашим доменом, например электронную почту и обмен мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-120">Select the services you want to test with your domain, like email and instant messaging.</span></span>

4. <span data-ttu-id="bf7f4-121">На странице домена **Проверка** выполните пошаговые инструкции, а затем выберите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-121">On the **Verify** domain page, follow the step-by-step instructions, amd then select **Verify**.</span></span>

    <span data-ttu-id="bf7f4-122">Чтобы изменения DNS вступили в силу, требуется от нескольких минут до 72 часов.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-122">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span>

    <span data-ttu-id="bf7f4-123">Если проверка пройдет успешно, вас попросят изменить записи DNS.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-123">When verification is successful, you are asked to modify your DNS records.</span></span>

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a><span data-ttu-id="bf7f4-124">Шаг 3. Пометьте домен как общий в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bf7f4-124">Step 3: Mark the domain as shared in Exchange Online</span></span>

1. <span data-ttu-id="bf7f4-125">В Центре администрирования Exchange, в разделе **Поток обработки почты**, выберите **Обслуживаемые домены**, а затем выберите нужный домен.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-125">In the Exchange admin center, in the **Mail flow** section, select **Accepted domains**, and then select the domain you want to modify.</span></span>

2. <span data-ttu-id="bf7f4-126">Дважды щелкните, чтобы открыть окно, а затем выберите **Внутренняя ретрансляция**.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-126">Double-click to open the window, and then select **Internal Relay**.</span></span>

3. <span data-ttu-id="bf7f4-127">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-127">Select **Save**.</span></span>

    <span data-ttu-id="bf7f4-128">Чтобы это изменение вступило в силу, может потребоваться несколько минут.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-128">This setting might require a few minutes to take effect.</span></span>

### <a name="step-4-unblock-the-existing-email-server-optional"></a><span data-ttu-id="bf7f4-129">Шаг 4. Разблокируйте существующий почтовый сервер (необязательно)</span><span class="sxs-lookup"><span data-stu-id="bf7f4-129">Step 4: Unblock the existing email server (optional)</span></span>

<span data-ttu-id="bf7f4-130">В Microsoft 365 для защиты от нежелательной почты используется служба Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="bf7f4-130">Microsoft 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="bf7f4-131">EOP может заблокировать ваш почтовый сервер, если обнаружит, что он пересылает большой объем нежелательной почты.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-131">EOP might block your existing mail server if it detects a high volume of spam being forwarded by your current mail server.</span></span> <span data-ttu-id="bf7f4-132">Если вы доверяете защите от нежелательной почты, которую обеспечивает ваш сторонний поставщик услуг электронной почты, вы можете разблокировать сервер в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-132">If you trust the spam protection for your other email provider, you can unblock the server in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="bf7f4-133">После разблокировки существующего почтового сервера любые нежелательные сообщения с вашего исходного сервера будут поступать в почтовые ящики Microsoft 365, и вы не сможете оценить, насколько эффективно работает защита от нежелательной почты Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-133">Unblocking your existing email server allows any spam that arrives through your original server to come to the Microsoft 365 mailboxes, and you can't evaluate how well Microsoft 365 prevents spam.</span></span>

1. <span data-ttu-id="bf7f4-134">В области навигации Центра администрирования Exchange выберите **Защита** > **Фильтр подключений**.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-134">In the Exchange admin center navigation pane, select **Protection**, and then select **Connection filter**.</span></span>

2. <span data-ttu-id="bf7f4-135">В поле **Список разрешенных IP-адресов** нажмите знак **+** и добавьте IP-адрес почтового сервера текущего поставщика услуг электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-135">In the **IP Allow list**, select **+**, and add the mail server IP address for your current email provider.</span></span>

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a><span data-ttu-id="bf7f4-136">Шаг 5. Создайте учетные записи пользователей и установите основной адрес для ответов</span><span class="sxs-lookup"><span data-stu-id="bf7f4-136">Step 5: Create user accounts and set the primary reply-to address</span></span>

1. <span data-ttu-id="bf7f4-137">В Центре администрирования Microsoft 365, в области навигации слева, выберите **Пользователи** > **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-137">In the Microsoft 365 admin center left navigation, select **Users** > **Active Users**.</span></span>

2. <span data-ttu-id="bf7f4-138">Создайте две тестовые учетные записи, добавив двух существующих пользователей.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-138">Create two test accounts by adding two existing users.</span></span>

    <span data-ttu-id="bf7f4-139">Для каждой учетной записи выберите **+ Добавить пользователя** и введите необходимые сведения, в том числе метод парольной защиты, который вы хотите протестировать.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-139">For each account, select **+ Add a user**, and fill out the required information, including the password method you want to test.</span></span>

    <span data-ttu-id="bf7f4-140">Чтобы адрес электронной почты пользователя не менялся, содержимое поля **Имя пользователя** должно соответствовать текущему адресу электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-140">To ensure a user's email stays the same, the **User name** field must match the user's current email address.</span></span>

3. <span data-ttu-id="bf7f4-141">Выберите соответствующую лицензию и нажмите **Далее** > **Завершить добавление**.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-141">Choose the appropriate license, click **Next**, and then click **Finish adding**.</span></span>

4. <span data-ttu-id="bf7f4-142">Рядом с полем **Имя пользователя** выберите имя личного домена в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-142">Next to **User name**, select your custom domain name from the drop-down list.</span></span>

5. <span data-ttu-id="bf7f4-143">Выберите **Создать** > **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-143">Select **Create** > **Close**.</span></span>

### <a name="step-6-configure-mail-to-flow-from-microsoft-365-or-office-365-to-email-server"></a><span data-ttu-id="bf7f4-144">Шаг 6. \*\*Настройте поток почты из Microsoft 365 или Office 365 на сервер электронной почты</span><span class="sxs-lookup"><span data-stu-id="bf7f4-144">Step 6: \*\*Configure mail to flow from Microsoft 365 or Office 365 to Email server</span></span>

<span data-ttu-id="bf7f4-145">Для этого необходимо выполнить два следующих действия.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-145">There are two steps for this:</span></span>

1. <span data-ttu-id="bf7f4-146">Настройте свою среду Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-146">Configure your Microsoft 365 or Office 365 environment.</span></span>

2. <span data-ttu-id="bf7f4-147">Настройте соединитель от Microsoft 365 или Office 365 к вашему серверу электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-147">Set up a connector from Microsoft 365 or Office 365 to your email server.</span></span>

### <a name="1-configure-your-microsoft-365-or-office-365-environment"></a><span data-ttu-id="bf7f4-148">1. Настройка своей среды Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="bf7f4-148">1. Configure your Microsoft 365 or Office 365 environment</span></span>

<span data-ttu-id="bf7f4-149">Убедитесь, что в Microsoft 365 или Office 365 выполнены следующие действия:</span><span class="sxs-lookup"><span data-stu-id="bf7f4-149">Make sure you have completed the following in Microsoft 365 or Office 365:</span></span>

1. <span data-ttu-id="bf7f4-150">Перед настройкой соединителей должны быть назначены разрешения.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-150">To set up connectors, you need permissions assigned before you can begin.</span></span> <span data-ttu-id="bf7f4-151">Чтобы узнать, какие необходимы разрешения, см. запись о соединителях Microsoft 365 или Office 365 в разделе [Разрешения на функции в Exchange Online](/exchange/permissions-exo/feature-permissions).</span><span class="sxs-lookup"><span data-stu-id="bf7f4-151">To check what permissions you need, see the Microsoft 365 and Office 365 connectors entry in the [Feature permissions in Exchange Online](/exchange/permissions-exo/feature-permissions) topic.</span></span>

2. <span data-ttu-id="bf7f4-152">Чтобы служба EOP или Exchange Online ретранслировала почту с ваших почтовых серверов в Интернет, выполните одно из двух следующих действий:</span><span class="sxs-lookup"><span data-stu-id="bf7f4-152">If you want EOP or Exchange Online to relay email from your email servers to the Internet, either:</span></span>

   - <span data-ttu-id="bf7f4-153">Используйте сертификат, в котором имя субъекта соответствует обслуживаемому домену в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-153">Use a certificate configured with a subject name that matches an accepted domain in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="bf7f4-154">Рекомендуется, чтобы общее имя сертификата или дополнительное имя субъекта соответствовало основному домену SMTP вашей организации.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-154">We recommend that your certificate's common name or subject alternative name matches the primary SMTP domain for your organization.</span></span> <span data-ttu-id="bf7f4-155">Подробнее см. в статье [Необходимые условия для локальной среды электронной почты](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment).</span><span class="sxs-lookup"><span data-stu-id="bf7f4-155">For details, see [Prerequisites for your on-premises email environment](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment).</span></span>

   <span data-ttu-id="bf7f4-156">-ИЛИ-</span><span class="sxs-lookup"><span data-stu-id="bf7f4-156">-OR-</span></span>

   - <span data-ttu-id="bf7f4-157">Убедитесь, что все домены и поддомены отправки почты организации настроены как обслуживаемые домены в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-157">Make sure that all your organization sender domains and subdomains are configured as accepted domains in Microsoft 365 or Office 365.</span></span>

   <span data-ttu-id="bf7f4-158">Подробнее об определении обслуживаемых доменов см. в статьях [Управление обслуживаемыми доменами в Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) и [Включение потока обработки почты для поддоменов в Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span><span class="sxs-lookup"><span data-stu-id="bf7f4-158">For more information about defining accepted domains, see [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) and [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

3. <span data-ttu-id="bf7f4-159">Решите, как будет доставляться почта из Microsoft 365 или Office 365 на ваши почтовые серверы: с помощью правил потока обработки почты (которые называют также правилами транспорта) или доменных имен.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-159">Decide whether you want to use mail flow rules (also known as transport rules) or domain names to deliver mail from Microsoft 365 or Office 365 to your email servers.</span></span> <span data-ttu-id="bf7f4-160">Большинство организаций предпочитают доставку почты для всех обслуживаемых доменов.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-160">Most businesses choose to deliver mail for all accepted domains.</span></span> <span data-ttu-id="bf7f4-161">Подробнее см. в разделе [Сценарий: условная маршрутизация почты в Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).</span><span class="sxs-lookup"><span data-stu-id="bf7f4-161">For more information, see [Scenario: Conditional mail routing in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).</span></span>

> [!NOTE]
> <span data-ttu-id="bf7f4-162">Вы можете настроить правила потока обработки почты, как описано в разделе [Действия, связанные с правилами обработки почты в Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="bf7f4-162">You can set up mail flow rules as described in [Mail flow rule actions in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span> <span data-ttu-id="bf7f4-163">Например, вам может потребоваться использовать правила потока обработки почты с соединителями, если сейчас ваша почта направляется на несколько сайтов через списки рассылки.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-163">For example, you might want to use mail flow rules with connectors if your mail is currently directed via distribution lists to multiple sites.</span></span>

### <a name="2-set-up-a-connector-from-microsoft-365-or-office-365-to-your-email-server"></a><span data-ttu-id="bf7f4-164">2. Настройка соединителя от Microsoft 365 или Office 365 к вашему серверу электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-164">2. Set up a connector from Microsoft 365 or Office 365 to your email server</span></span>

<span data-ttu-id="bf7f4-165">Чтобы создать соединитель в Microsoft 365 или Office 365, выберите пункты **Администратор** и **Exchange** для перехода в Центр администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-165">To create a connector in Microsoft 365 or Office 365, click **Admin**, and then click **Exchange** to go to the Exchange admin center.</span></span> <span data-ttu-id="bf7f4-166">Затем выберите пункт **поток обработки почты** и нажмите кнопку **соединители**.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-166">Next, click **mail flow**, and click **connectors**.</span></span>

<span data-ttu-id="bf7f4-167">Настройка соединителей с помощью мастера.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-167">Set up connectors using the wizard.</span></span>

<span data-ttu-id="bf7f4-168">Чтобы запустить мастер, нажмите знак плюса **+**.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-168">To start the wizard, click the plus symbol **+**.</span></span> <span data-ttu-id="bf7f4-169">На первом экране выберите **Из** Office 365 и **В** почтовый сервер вашей организации.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-169">On the first screen, choose **From** Office 365 and **To** Your Organization Mail server.</span></span>

<span data-ttu-id="bf7f4-170">Нажмите кнопку **Далее** и следуйте указаниям мастера.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-170">Click **Next**, and follow the instructions in the wizard.</span></span> <span data-ttu-id="bf7f4-171">Если вам требуются дополнительные сведения, выберите ссылки **Справка** или **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-171">Click the **Help** or **Learn More** links if you need more information.</span></span> <span data-ttu-id="bf7f4-172">Мастер поможет вам выполнить настройку.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-172">The wizard will guide you through setup.</span></span> <span data-ttu-id="bf7f4-173">В конце убедитесь, что соединитель выполняет проверку.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-173">At the end, make sure your connector validates.</span></span> <span data-ttu-id="bf7f4-174">Если соединитель не выполняет проверку, дважды щелкните на появившемся сообщении, чтобы получить дополнительные сведения, а также ознакомьтесь с разделом [Проверка соединителей](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors), где приведены рекомендации по устранению проблем.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-174">If the connector does not validate, double-click the message displayed to get more information, and see [Validate connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors) for help resolving issues.</span></span>



### <a name="step-7-update-dns-records-at-your-dns-hosting-provider"></a><span data-ttu-id="bf7f4-175">Шаг 7. Обновите записи DNS в системе поставщика услуг размещения DNS</span><span class="sxs-lookup"><span data-stu-id="bf7f4-175">Step 7: Update DNS records at your DNS hosting provider</span></span>

<span data-ttu-id="bf7f4-176">Войдите на сайт поставщика услуг размещения DNS и следуйте инструкциям, приведенным в статье [Добавление записей DNS для подключения своего домена](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="bf7f4-176">Sign in to your DNS hosting provider's website, and follow the instructions at [Add DNS records to connect your domain](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="bf7f4-177">**Добавьте следующие исключения:**</span><span class="sxs-lookup"><span data-stu-id="bf7f4-177">**Make the following two exceptions:**</span></span>

- <span data-ttu-id="bf7f4-178">Не создавайте новую и не изменяйте существующую MX-запись.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-178">Do not create a new MX record or change your existing MX record.</span></span>

- <span data-ttu-id="bf7f4-179">Если у вас уже есть запись SPF для предыдущего поставщика услуг электронной почты, не создавайте запись SPF (TXT) для Exchange Online, а добавьте параметр "include:spf.protection.outlook.com" в текущую запись TXT.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-179">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, add "include:spf.protection.outlook.com" to the current TXT record.</span></span>

    <span data-ttu-id="bf7f4-180">Пример: "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span><span class="sxs-lookup"><span data-stu-id="bf7f4-180">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>

    <span data-ttu-id="bf7f4-p109">Если у вас нет записи SPF, измените запись, рекомендованную Microsoft 365, включив в нее домен текущего поставщика услуг электронной почты, и добавьте spf.protection.outlook.com. В результате будет разрешена отправка исходящих сообщений из обеих почтовых систем.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-p109">If you don't have an SPF record, modify the one recommended by Microsoft 365 to include the domain for your current email provider, and add spf.protection.outlook.com. This authorizes outgoing messages from both email systems.</span></span>

### <a name="step-8-set-up-email-forwarding-at-your-current-provider"></a><span data-ttu-id="bf7f4-183">Шаг 8. Настройте пересылку электронной почты в системе действующего поставщика</span><span class="sxs-lookup"><span data-stu-id="bf7f4-183">Step 8: Set up email forwarding at your current provider</span></span>

<span data-ttu-id="bf7f4-184">В системе текущего поставщика услуг электронной почты настройте для учетных записей пользователей пересылку в ваш домен onmicrosoft.com:</span><span class="sxs-lookup"><span data-stu-id="bf7f4-184">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>

- <span data-ttu-id="bf7f4-185">Пересылка с почтового ящика пользователя A на адрес usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="bf7f4-185">Forward User A mailbox to usera@yourcompany.onmicrosoft.com</span></span>

- <span data-ttu-id="bf7f4-186">Пересылка с почтового ящика пользователя B на адрес usera@yourcompany.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="bf7f4-186">Forward User B mailbox to userb@yourcompany.onmicrosoft.com</span></span>

<span data-ttu-id="bf7f4-187">После выполнения этого действия все сообщения, отправленные на адреса usera@yourcompany.com и userb@yourcompany.com, будут доступны в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-187">When you complete this step, all email sent to usera@yourcompany.com and userb@yourcompany.com is available in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="bf7f4-188">За точными инструкциями по настройке пересылки обратитесь к текущему поставщику услуг электронной почты.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-188">Contact your current email provider for the exact steps to set up email forwarding.</span></span><br/>
> <span data-ttu-id="bf7f4-189">Сохранять копии сообщений на сервере текущего поставщика не нужно.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-189">You don't need to keep a copy of messages at the current email provider.</span></span><br/>
> <span data-ttu-id="bf7f4-190">Большинство поставщиков при пересылке электронной почты оставляют адрес для ответа без изменений, чтобы ответы направлялись исходному отправителю.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-190">Most providers forward email by leaving the Reply-to address of the sender intact so that replies go to the original sender.</span></span>

### <a name="step-9-test-mail-flow"></a><span data-ttu-id="bf7f4-191">Шаг 9. Проверьте поток обработки почты</span><span class="sxs-lookup"><span data-stu-id="bf7f4-191">Step 9: Test mail flow</span></span>

1. <span data-ttu-id="bf7f4-192">Войдите в Outlook Web App, используя учетные данные пользователя A.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-192">Sign in to Outlook Web App using the credentials for User A.</span></span>

2. <span data-ttu-id="bf7f4-193">Выполните указанные ниже проверки.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-193">Perform these tests:</span></span>

    - <span data-ttu-id="bf7f4-194">Протестируйте локальную электронную почту Microsoft, отправив сообщение, например пользователю B. Электронная почта доставляется мгновенно.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-194">Test local Microsoft email by sending an email, for example, to User B. The email is delivered immediately.</span></span> <span data-ttu-id="bf7f4-195">В этом случае сообщение не направляется в почтовый ящик пользователя B на исходном сервере, поскольку почтовый ящик Microsoft 365 является локальным.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-195">In this scenario, the message is not routed to the mailbox for User B on your original server because the Microsoft 365 mailbox is local.</span></span>

    - <span data-ttu-id="bf7f4-196">Протестируйте электронную почту пользователя в существующей почтовой системе, отправив сообщение, например, пользователю C. Электронная почта доставляется в почтовый ящик пользователя C на исходном почтовом сервере.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-196">Test email to a user on the existing email system by sending an email, for example, to User C. The email is delivered to the mailbox for User C on your original mail server.</span></span>

    - <span data-ttu-id="bf7f4-197">Убедитесь, что пересылка настроена правильно, с помощью сторонней учетной записи или учетной записи сотрудника в существующей почтовой системе.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-197">Verify that forwarding is set up properly from an outside account, or from an employee email account on the existing email system.</span></span> <span data-ttu-id="bf7f4-198">Например, из учетной записи пользователя C на исходном сервере или учетной записи Hotmail отправьте пользователю A сообщение и убедитесь, что оно поступило в почтовый ящик пользователя A в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-198">For example, from the original server account for User C or a Hotmail account, send User A an email and verify that it arrives in the Microsoft 365 mailbox for User A.</span></span>

### <a name="step-10-move-mailbox-contents"></a><span data-ttu-id="bf7f4-199">Шаг 10. Переместите содержимое почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="bf7f4-199">Step 10: Move mailbox contents</span></span>

<span data-ttu-id="bf7f4-200">Так как вы переносите только двух тестовых пользователей, и оба пользователя (A и B) используют Outlook, вы можете переместить почту, открыв старый PST-файл в новом профиле Outlook и скопировав сообщения, элементы календаря, контакты и т. д.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-200">Because you are moving only two test users, and User A and User B are both using Outlook, you can move the email by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, and so on.</span></span> <span data-ttu-id="bf7f4-201">Подробные сведения см. в статье [Импорт писем, контактов и календаря Outlook из PST-файла](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span><span class="sxs-lookup"><span data-stu-id="bf7f4-201">For more information, see [Import email, contacts, and calendar from an Outlook .pst file](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span></span>

<span data-ttu-id="bf7f4-202">После импорта в почтовый ящик Microsoft 365 к элементам можно будет получить доступ с любого устройства.</span><span class="sxs-lookup"><span data-stu-id="bf7f4-202">After they're imported to the appropriate locations in the Microsoft 365 mailbox, the items can be accessed from any device, anywhere.</span></span>
