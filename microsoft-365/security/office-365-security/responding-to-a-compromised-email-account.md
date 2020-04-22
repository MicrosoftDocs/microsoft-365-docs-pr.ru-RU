---
title: Реагирование на компрометацию учетной записи электронной почты
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.custom: TopSMBIssues
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Как распознать компрометацию учетной записи электронной почты в Microsoft 365 и какие принять меры
ms.openlocfilehash: 65e3827b578eec2f851c45d9acc69fb7132d01b8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634344"
---
# <a name="responding-to-a-compromised-email-account"></a><span data-ttu-id="1382e-103">Реагирование на компрометацию учетной записи электронной почты</span><span class="sxs-lookup"><span data-stu-id="1382e-103">Responding to a Compromised Email Account</span></span>

<span data-ttu-id="1382e-104">**Сводка** Как распознать компрометацию учетной записи электронной почты в Microsoft 365 и какие принять меры.</span><span class="sxs-lookup"><span data-stu-id="1382e-104">**Summary** Learn how to recognize and respond to a compromised email account in Microsoft 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a><span data-ttu-id="1382e-105">Что такое компрометация учетной записи электронной почты в Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="1382e-105">What is a Compromised Email Account in Microsoft 365?</span></span>

<span data-ttu-id="1382e-106">Доступ к почтовым ящикам, данным и другим службам Microsoft 365 контролируется с помощью учетных данных, например имени пользователя и пароля или ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="1382e-106">Access to Microsoft 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN.</span></span> <span data-ttu-id="1382e-107">Если кто-то посторонний украдет эти учетные данные, они будут считаться скомпрометированными.</span><span class="sxs-lookup"><span data-stu-id="1382e-107">When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised.</span></span> <span data-ttu-id="1382e-108">Имея их, злоумышленник может войти в почтовый ящик или службу как настоящий пользователь и совершить незаконные действия.</span><span class="sxs-lookup"><span data-stu-id="1382e-108">With them the attacker can sign in as the original user and perform illicit actions.</span></span>
<span data-ttu-id="1382e-109">Используя украденные учетные данные, злоумышленник может получить доступ к почтовому ящику Microsoft 365, папкам SharePoint или файлам OneDrive.</span><span class="sxs-lookup"><span data-stu-id="1382e-109">Using the stolen credentials, the attacker can access the user's Microsoft 365 mailbox, SharePoint folders, or files in the user's OneDrive.</span></span> <span data-ttu-id="1382e-110">Часто деятельность злоумышленника проявляется в виде отправки электронных писем от имени настоящего пользователя получателям в организации и за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="1382e-110">One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization.</span></span> <span data-ttu-id="1382e-111">Когда злоумышленник отправляет данные по электронной почте внешним получателям, имеет место утечка данных.</span><span class="sxs-lookup"><span data-stu-id="1382e-111">When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a><span data-ttu-id="1382e-112">Признаки компрометации учетной записи электронной почты Майкрософт</span><span class="sxs-lookup"><span data-stu-id="1382e-112">Symptoms of a Compromised Microsoft Email Account</span></span>

<span data-ttu-id="1382e-113">Пользователи могут заметить подозрительные действия в своих почтовых ящиках Microsoft 365 и сообщить об этих действиях.</span><span class="sxs-lookup"><span data-stu-id="1382e-113">Users might notice and report unusual activity in their Microsoft 365 mailboxes.</span></span> <span data-ttu-id="1382e-114">Некоторые типичные признаки приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="1382e-114">Here are some common symptoms:</span></span>

- <span data-ttu-id="1382e-115">Подозрительные действия, например отсутствие или удаление сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1382e-115">Suspicious activity, such as missing or deleted emails.</span></span>

- <span data-ttu-id="1382e-116">Другие пользователи могут получать из скомпрометированной учетной записи электронные письма, которых нет в папке **Отправленные** у отправителя.</span><span class="sxs-lookup"><span data-stu-id="1382e-116">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>

- <span data-ttu-id="1382e-117">Наличие в почтовом ящике правил, которые не были созданы пользователем или администратором.</span><span class="sxs-lookup"><span data-stu-id="1382e-117">The presence of inbox rules that weren't created by the intended user or the administrator.</span></span> <span data-ttu-id="1382e-118">Эти правила могут автоматически пересылать письма на неизвестные адреса или перемещать их в папки **Заметки**, **Нежелательная почта** или **RSS-подписки**.</span><span class="sxs-lookup"><span data-stu-id="1382e-118">These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>

- <span data-ttu-id="1382e-119">Изменение краткого имени пользователя в глобальном списке адресов.</span><span class="sxs-lookup"><span data-stu-id="1382e-119">The user's display name might be changed in the Global Address List.</span></span>

- <span data-ttu-id="1382e-120">Почтовый ящик пользователя не может отправлять почту.</span><span class="sxs-lookup"><span data-stu-id="1382e-120">The user's mailbox is blocked from sending email.</span></span>

- <span data-ttu-id="1382e-121">Папки "Отправленные и "Удаленные" в Microsoft Outlook или Outlook в Интернете (прежнее название – Outlook Web App) содержат типичные для взломанного почтового ящика сообщения, например "Я в Лондоне, отправь деньги".</span><span class="sxs-lookup"><span data-stu-id="1382e-121">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>

- <span data-ttu-id="1382e-122">Необычные изменения профиля, например изменение имени, номера телефона или почтового индекса.</span><span class="sxs-lookup"><span data-stu-id="1382e-122">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>

- <span data-ttu-id="1382e-123">Необычные изменения учетных данных, например многократное изменение пароля.</span><span class="sxs-lookup"><span data-stu-id="1382e-123">Unusual credential changes, such as multiple password changes are required.</span></span>

- <span data-ttu-id="1382e-124">Недавнее добавление переадресации почты.</span><span class="sxs-lookup"><span data-stu-id="1382e-124">Mail forwarding was recently added.</span></span>

- <span data-ttu-id="1382e-125">Недавнее появление необычной подписи, например на банковском документе или рецепте на лекарство.</span><span class="sxs-lookup"><span data-stu-id="1382e-125">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="1382e-126">Если пользователь сообщает о любом из указанных признаков, необходимо провести дальнейшее расследование.</span><span class="sxs-lookup"><span data-stu-id="1382e-126">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="1382e-127">Центр безопасности и соответствия требованиям Microsoft 365 и портал Azure предлагает инструменты для расследования активности учетной записи пользователя, которая, как вы подозреваете, может быть скомпрометирована.</span><span class="sxs-lookup"><span data-stu-id="1382e-127">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="1382e-128">**Единые журналы аудита в Центре безопасности и соответствия требованиям**. Просмотрите все действия в подозреваемой учетной записи, отфильтруйте результаты по диапазону дат: с момента сразу перед подозрительным действием до текущей даты.</span><span class="sxs-lookup"><span data-stu-id="1382e-128">**Unified Audit Logs in the Security & Compliance Center**: Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date.</span></span> <span data-ttu-id="1382e-129">Не фильтруйте действия во время поиска.</span><span class="sxs-lookup"><span data-stu-id="1382e-129">Do not filter on the activities during the search.</span></span>

- <span data-ttu-id="1382e-130">**Журналы аудита действий администратора в Центре администрирования Exchange**. В Exchange Online можно использовать Центр администрирования Exchange (EAC) для поиска и просмотра записей в журнале аудита действий администратора.</span><span class="sxs-lookup"><span data-stu-id="1382e-130">**Admin Audit logs in the EAC**: In Exchange Online, you can use the Exchange admin center (EAC) to search for and view entries in the administrator audit log.</span></span> <span data-ttu-id="1382e-131">В журнал аудита действий администратора записываются определенные действия на основе командлетов PowerShell Exchange Online, выполняемых администраторами и пользователями с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="1382e-131">The administrator audit log records specific actions, based on Exchange Online PowerShell cmdlets, performed by administrators and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="1382e-132">В записях журнала уточняется, какой командлет выполнен, какие параметры использованы, кто выполнял командлет, а также какие объекты задействованы.</span><span class="sxs-lookup"><span data-stu-id="1382e-132">Entries in the administrator audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

- <span data-ttu-id="1382e-133">**Журналы входа в Azure AD и другие отчеты о рисках, доступные в портале Azure AD**. Проверьте значения в следующих столбцах:</span><span class="sxs-lookup"><span data-stu-id="1382e-133">**Azure AD Sign-in logs and other risk reports in the Azure AD portal**: Examine the values in these columns:</span></span>

  - <span data-ttu-id="1382e-134">IP-адрес;</span><span class="sxs-lookup"><span data-stu-id="1382e-134">Review IP address</span></span>

  - <span data-ttu-id="1382e-135">место входа;</span><span class="sxs-lookup"><span data-stu-id="1382e-135">sign-in locations</span></span>

  - <span data-ttu-id="1382e-136">время входа;</span><span class="sxs-lookup"><span data-stu-id="1382e-136">sign-in times</span></span>

  - <span data-ttu-id="1382e-137">успешный или неудачный вход.</span><span class="sxs-lookup"><span data-stu-id="1382e-137">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a><span data-ttu-id="1382e-138">Защита и восстановление функции электронной почты в подозрительной с точки зрения компрометации учетной записи Microsoft 365 и почтовом ящике</span><span class="sxs-lookup"><span data-stu-id="1382e-138">How to secure and restore email function to a suspected compromised Microsoft 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="1382e-139">Даже если вы вновь получили доступ к своей учетной записи, возможно, злоумышленник встроил в нее лазейки, которые позволят ему вновь перехватить управление учетной записью.</span><span class="sxs-lookup"><span data-stu-id="1382e-139">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="1382e-140">Обязательно выполните все указанные ниже действия, чтобы восстановить доступ к своей учетной записи, и чем раньше, тем лучше, чтобы взломщик не успел вернуть себе управление учетной записью.</span><span class="sxs-lookup"><span data-stu-id="1382e-140">You must perform all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account.</span></span> <span data-ttu-id="1382e-141">Эти действия помогут вам удалить все лазейки, которые взломщик мог встроить в вашу учетную запись.</span><span class="sxs-lookup"><span data-stu-id="1382e-141">These steps help you remove any back-door entries that the hijacker may have added to your account.</span></span> <span data-ttu-id="1382e-142">После выполнения этих действий рекомендуется проверку на вирусы, чтобы убедиться в том, что компьютер не заражен.</span><span class="sxs-lookup"><span data-stu-id="1382e-142">After you perform these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="1382e-143">Шаг 1. Смените пароль пользователя</span><span class="sxs-lookup"><span data-stu-id="1382e-143">Step 1 Reset the user's password</span></span>

> [!WARNING]
> <span data-ttu-id="1382e-144">Не отправляйте пользователю новый пароль по электронной почте, так как у злоумышленника пока есть доступ к почтовому ящику.</span><span class="sxs-lookup"><span data-stu-id="1382e-144">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>

1. <span data-ttu-id="1382e-145">Выполните процедуры, указанные в разделе "Сброс пароля другого пользователя в приложениях Microsoft 365 для бизнеса" статьи [Сброс паролей в приложениях Microsoft 365 для бизнеса](https://docs.microsoft.com/office365/admin/add-users/reset-passwords)</span><span class="sxs-lookup"><span data-stu-id="1382e-145">Follow the Reset a Microsoft 365 Apps for business password for someone else procedures in [Reset Microsoft 365 Apps for business passwords](https://docs.microsoft.com/office365/admin/add-users/reset-passwords)</span></span>

<span data-ttu-id="1382e-146">**Примечания**:</span><span class="sxs-lookup"><span data-stu-id="1382e-146">**Notes**:</span></span>

- <span data-ttu-id="1382e-147">Пароль должен быть надежным и содержать буквы верхнего и нижнего регистра, хотя бы одну цифру и хотя бы один специальный символ.</span><span class="sxs-lookup"><span data-stu-id="1382e-147">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span>

- <span data-ttu-id="1382e-148">Не используйте пять последних паролей, использованных раньше.</span><span class="sxs-lookup"><span data-stu-id="1382e-148">Don't reuse any of your last five passwords.</span></span> <span data-ttu-id="1382e-149">Хотя требования к журналу паролей разрешают использовать старые пароли, следует выбрать такой пароль, который злоумышленник не мог бы угадать.</span><span class="sxs-lookup"><span data-stu-id="1382e-149">Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>

- <span data-ttu-id="1382e-150">Если ваше локальное удостоверение связано федеративным доступом с Microsoft 365, необходимо сменить локальный пароль, а затем оповестить администратора о компрометации.</span><span class="sxs-lookup"><span data-stu-id="1382e-150">If your on-premises identity is federated with Microsoft 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>

> [!TIP]
> <span data-ttu-id="1382e-151">Настоятельно рекомендуется включить многофакторную проверку подлинности (MFA), чтобы предотвратить компрометацию, особенно для учетных записей с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="1382e-151">We highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.</span></span>  <span data-ttu-id="1382e-152">Дополнительные сведения о MFA см. [здесь](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="1382e-152">You can learn more about MFA [here](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="1382e-153">Шаг 2. Удалите подозрительные адреса перенаправления почты</span><span class="sxs-lookup"><span data-stu-id="1382e-153">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="1382e-154">Откройте Центр администрирования Microsoft 365 и выберите **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="1382e-154">Open the **Microsoft 365 admin center > Active Users**.</span></span>

2. <span data-ttu-id="1382e-155">Найдите подозреваемую учетную запись пользователя и разверните **Параметры почты**.</span><span class="sxs-lookup"><span data-stu-id="1382e-155">Find the user account in question and expand **Mail Settings**.</span></span>

3. <span data-ttu-id="1382e-156">В разделе **Переадресация почты** нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="1382e-156">For **Email forwarding**, click **Edit**.</span></span>

4. <span data-ttu-id="1382e-157">Удалите все подозрительные адреса перенаправления.</span><span class="sxs-lookup"><span data-stu-id="1382e-157">Remove any suspicious forwarding addresses.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="1382e-158">Шаг 3. Отключите все подозрительные правила для папки "Входящие"</span><span class="sxs-lookup"><span data-stu-id="1382e-158">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="1382e-159">Войдите в почтовый ящик пользователя с помощью Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="1382e-159">Sign in to the user's mailbox using Outlook on the web.</span></span>

2. <span data-ttu-id="1382e-160">Щелкните значок шестеренки и выберите пункт **Почта**.</span><span class="sxs-lookup"><span data-stu-id="1382e-160">Click on the gear icon and click **Mail**.</span></span>

3. <span data-ttu-id="1382e-161">Нажмите **Правила для папки "Входящие" и правила очистки** и проверьте правила.</span><span class="sxs-lookup"><span data-stu-id="1382e-161">Click **Inbox and sweep rules** and review the rules.</span></span>

4. <span data-ttu-id="1382e-162">Отключите или удалите подозрительные правила.</span><span class="sxs-lookup"><span data-stu-id="1382e-162">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="1382e-163">Шаг 4. Разблокируйте отправку почты для пользователя</span><span class="sxs-lookup"><span data-stu-id="1382e-163">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="1382e-164">Если подозрительный на компрометацию почтовый ящик незаконно использовался для отправки нежелательной почты, скорее всего, отправка почты из него запрещена.</span><span class="sxs-lookup"><span data-stu-id="1382e-164">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>

<span data-ttu-id="1382e-165">Чтобы разблокировать отправку почты из почтового ящика, выполните действия в статье [Удаление пользователя с портала "Пользователи с ограниченным доступом" после отправки нежелательной почты](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="1382e-165">To unblock a mailbox from sending mail, follow the procedures in [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="1382e-166">Шаг 5 (необязательно). Запретите вход в учетную запись пользователя</span><span class="sxs-lookup"><span data-stu-id="1382e-166">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1382e-167">Можно запретить вход в подозрительную на компрометацию учетную запись, пока вы не убедитесь, что она безопасна.</span><span class="sxs-lookup"><span data-stu-id="1382e-167">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="1382e-168">Перейдите в Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1382e-168">Go to the Microsoft 365 admin center.</span></span>

2. <span data-ttu-id="1382e-169">В Центре администрирования Microsoft 365 выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="1382e-169">In the Microsoft 365 admin center, select **Users**.</span></span>

3. <span data-ttu-id="1382e-170">Выберите сотрудника, которого вы хотите заблокировать, и выберите **Изменить** рядом со строкой **Состояние при входе в систему** на панели пользователя.</span><span class="sxs-lookup"><span data-stu-id="1382e-170">Select the employee that you want to block, and then choose **Edit** next to **Sign-in status** in the user pane.</span></span>

4. <span data-ttu-id="1382e-171">В области **Состояние при входе в систему** выберите **Вход в систему заблокирован** и нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1382e-171">On the **Sign-in status** pane, choose **Sign-in blocked** and then **Save**.</span></span>

5. <span data-ttu-id="1382e-172">В Центре администрирования в нижней части области навигации, расположенной слева, разверните элемент **Центры администрирования** и выберите **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="1382e-172">In the Admin center, in the lower-left navigation pane, expand **Admin Centers** and select **Exchange**.</span></span>

6. <span data-ttu-id="1382e-173">В Центре администрирования Exchange перейдите к разделу **Получатели > Почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="1382e-173">In the Exchange admin center, navigate to **Recipients > Mailboxes**.</span></span>

7. <span data-ttu-id="1382e-174">Выберите пользователя, а затем на странице его свойств в разделе **Мобильные устройства** выберите параметры **Отключить Exchange ActiveSync** и **Отключить Outlook Web App для устройств** и ответьте **Да** на оба вопроса.</span><span class="sxs-lookup"><span data-stu-id="1382e-174">Select the user, and on the user properties page, under **Mobile Devices**, click **Disable Exchange ActivcSync** and **Disable OWA for Devices** and answer **yes** to both.</span></span>

8. <span data-ttu-id="1382e-175">В разделе **Возможность подключения электронной почты** щелкните **Отключить** и нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="1382e-175">Under **Email Connectivity**, **Disable** and answer **yes**.</span></span>

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="1382e-176">Необязательный шаг 6. Удалите подозрительную на компрометацию учетную запись из всех групп административных ролей</span><span class="sxs-lookup"><span data-stu-id="1382e-176">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="1382e-177">Членство в группе административных ролей можно восстановить, когда учетная запись будет защищена.</span><span class="sxs-lookup"><span data-stu-id="1382e-177">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="1382e-178">Войдите в Центр администрирования Microsoft 365 с учетной записью глобального администратора и откройте страницу **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="1382e-178">Sign in to the Microsoft 365 admin center with a global administrator account and open **Active Users**.</span></span>

2. <span data-ttu-id="1382e-179">Найдите подозрительную на компрометацию учетную запись и вручную проверьте, назначены ли ей какие-либо административные роли.</span><span class="sxs-lookup"><span data-stu-id="1382e-179">Find the suspected compromised account and manually check to see if there are any administrative roles assigned to the account.</span></span>

3. <span data-ttu-id="1382e-180">Откройте **Центр безопасности и соответствия требованиям**.</span><span class="sxs-lookup"><span data-stu-id="1382e-180">Open the **Security & Compliance Center**.</span></span>

4. <span data-ttu-id="1382e-181">Выберите пункт **Разрешения**.</span><span class="sxs-lookup"><span data-stu-id="1382e-181">Click **Permissions**.</span></span>

5. <span data-ttu-id="1382e-182">Вручную просмотрите группы ролей и проверьте, не входит ли в какую-то из них подозрительная на компрометацию учетная запись.</span><span class="sxs-lookup"><span data-stu-id="1382e-182">Manually review the role groups to see if the suspected compromised account is a member of any of them.</span></span>  <span data-ttu-id="1382e-183">Если для него выбрано значение</span><span class="sxs-lookup"><span data-stu-id="1382e-183">If it is:</span></span>

   <span data-ttu-id="1382e-184">а)</span><span class="sxs-lookup"><span data-stu-id="1382e-184">a.</span></span> <span data-ttu-id="1382e-185">Щелкните эту группу ролей и нажмите кнопку **Изменить группу ролей**.</span><span class="sxs-lookup"><span data-stu-id="1382e-185">Click the role group and click **Edit Role Group**.</span></span>

   <span data-ttu-id="1382e-186">б)</span><span class="sxs-lookup"><span data-stu-id="1382e-186">b.</span></span> <span data-ttu-id="1382e-187">Нажмите **Выбрать участников** и **Изменить**, а затем удалите пользователя из группы ролей.</span><span class="sxs-lookup"><span data-stu-id="1382e-187">Click **Chose Members** and **Edit** to remove the user from the role group.</span></span>

6. <span data-ttu-id="1382e-188">Откройте **Центр администрирования Exchange**</span><span class="sxs-lookup"><span data-stu-id="1382e-188">Open the **Exchange admin center**.</span></span>

7. <span data-ttu-id="1382e-189">Выберите пункт **Разрешения**.</span><span class="sxs-lookup"><span data-stu-id="1382e-189">Click **Permissions**.</span></span>

8. <span data-ttu-id="1382e-190">Вручную просмотрите группы ролей и проверьте, не входит ли в какую-то из них подозрительная на компрометацию учетная запись.</span><span class="sxs-lookup"><span data-stu-id="1382e-190">Manually review the role groups to see if the suspected compromised account is a member of any of them.</span></span> <span data-ttu-id="1382e-191">Если для него выбрано значение</span><span class="sxs-lookup"><span data-stu-id="1382e-191">If it is:</span></span>

   <span data-ttu-id="1382e-192">а)</span><span class="sxs-lookup"><span data-stu-id="1382e-192">a.</span></span> <span data-ttu-id="1382e-193">Щелкните эту группу ролей и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="1382e-193">Click the role group and click **Edit**.</span></span>

   <span data-ttu-id="1382e-194">б)</span><span class="sxs-lookup"><span data-stu-id="1382e-194">b.</span></span> <span data-ttu-id="1382e-195">В разделе **Участники** удалите пользователя из группы ролей.</span><span class="sxs-lookup"><span data-stu-id="1382e-195">Use the **members** section to remove the user from the role group.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="1382e-196">Шаг 7 (необязательно). Дополнительные меры предосторожности</span><span class="sxs-lookup"><span data-stu-id="1382e-196">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="1382e-197">Еще раз проверьте папку "Отправленные".</span><span class="sxs-lookup"><span data-stu-id="1382e-197">Make sure that you verify your sent items.</span></span> <span data-ttu-id="1382e-198">Возможно, следует сообщить пользователям из вашего списка контактов о том, что ваша учетная запись скомпрометирована.</span><span class="sxs-lookup"><span data-stu-id="1382e-198">You may have to inform people on your contacts list that your account was compromised.</span></span> <span data-ttu-id="1382e-199">Злоумышленник может просить у них денег от вашего имени или отправлять им вирусы для взлома их компьютеров.</span><span class="sxs-lookup"><span data-stu-id="1382e-199">The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>

2. <span data-ttu-id="1382e-200">Любые другие службы, использующие эту учетную запись Exchange как альтернативную для электронной почты, также могут быть скомпрометированы.</span><span class="sxs-lookup"><span data-stu-id="1382e-200">Any other service that used this Exchange account as its alternative email account may have been compromised.</span></span> <span data-ttu-id="1382e-201">Сначала выполните эти действия для вашей подписки Microsoft 365, затем выполните эти действия для других ваших учетных записей.</span><span class="sxs-lookup"><span data-stu-id="1382e-201">First, perform these steps for your Microsoft 365 subscription, and then perform these steps for your other accounts.</span></span>

3. <span data-ttu-id="1382e-202">Убедитесь, что ваши контактные данные, таких как телефонные номера и адреса, указаны правильно.</span><span class="sxs-lookup"><span data-stu-id="1382e-202">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="1382e-203">Защитите Microsoft 365 на профессиональном уровне</span><span class="sxs-lookup"><span data-stu-id="1382e-203">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="1382e-204">Для вашей подписки Microsoft 365 предусмотрен целый ряд полезных функций безопасности, которые можно использовать для защиты ваших данных и пользователей.</span><span class="sxs-lookup"><span data-stu-id="1382e-204">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="1382e-205">Используйте статью к [Стратегия развития безопасности Microsoft 365: приоритеты на первые 30 дней, 90 дней и далее](security-roadmap.md), чтобы применить лучшие методики, рекомендованные корпорацией Майкрософт, для защиты вашего клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1382e-205">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="1382e-206">Задачи для выполнения в первые 30 дней.</span><span class="sxs-lookup"><span data-stu-id="1382e-206">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="1382e-207">Они дают немедленный эффект и не создают помех вашим пользователям.</span><span class="sxs-lookup"><span data-stu-id="1382e-207">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="1382e-208">Задачи для выполнения в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="1382e-208">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="1382e-209">Эти задачи требуют немного больше времени на планирование и реализацию, но значительно укрепляют вашу безопасность.</span><span class="sxs-lookup"><span data-stu-id="1382e-209">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="1382e-210">Более 90 дней.</span><span class="sxs-lookup"><span data-stu-id="1382e-210">Beyond 90 days.</span></span> <span data-ttu-id="1382e-211">Эти меры дополняют ваши действия в течение первых 90 дней.</span><span class="sxs-lookup"><span data-stu-id="1382e-211">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="1382e-212">См. также</span><span class="sxs-lookup"><span data-stu-id="1382e-212">See also</span></span>

- [<span data-ttu-id="1382e-213">Обнаружение атак с внедрением правил и пользовательских форм Outlook и устранение их последствий в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1382e-213">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Microsoft 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

- [<span data-ttu-id="1382e-214">Центр жалоб на Интернет-преступления</span><span class="sxs-lookup"><span data-stu-id="1382e-214">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/preventiontips.aspx)

- [<span data-ttu-id="1382e-215">Комиссия по ценным бумагам и биржам – "фишинговое" мошенничество</span><span class="sxs-lookup"><span data-stu-id="1382e-215">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)

- <span data-ttu-id="1382e-216">Чтобы сообщить о нежелательной почте непосредственно в Майкрософт и своему администратору, [воспользуйтесь надстройкой Report Message](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="1382e-216">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>
