---
title: Реагирование на компрометацию учетной записи электронной почты
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection:
- o365_security_incident_response
- M365-security-compliance
- m365solution-smb
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
localization_priority: Priority
search.appverid:
- MET150
description: Узнайте, как распознать компрометацию учетной записи электронной почты с помощью средств Microsoft 365 и какие принять меры.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a1bf2a5dbc7e1fdd447baf76fd051abff88b4b30
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205717"
---
# <a name="responding-to-a-compromised-email-account"></a><span data-ttu-id="7e3e1-103">Реагирование на компрометацию учетной записи электронной почты</span><span class="sxs-lookup"><span data-stu-id="7e3e1-103">Responding to a Compromised Email Account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7e3e1-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="7e3e1-104">**Applies to**</span></span>
- [<span data-ttu-id="7e3e1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7e3e1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7e3e1-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="7e3e1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7e3e1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7e3e1-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="7e3e1-108">**Сводка** Как распознать компрометацию учетной записи электронной почты в Microsoft 365 и какие принять меры.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-108">**Summary** Learn how to recognize and respond to a compromised email account in Microsoft 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a><span data-ttu-id="7e3e1-109">Что такое компрометация учетной записи электронной почты в Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="7e3e1-109">What is a Compromised Email Account in Microsoft 365?</span></span>

<span data-ttu-id="7e3e1-110">Доступ к почтовым ящикам, данным и другим службам Microsoft 365 контролируется с помощью учетных данных, например имени пользователя и пароля или ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-110">Access to Microsoft 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN.</span></span> <span data-ttu-id="7e3e1-111">Если кто-то посторонний украдет эти учетные данные, они будут считаться скомпрометированными.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-111">When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised.</span></span> <span data-ttu-id="7e3e1-112">Имея их, злоумышленник может войти в почтовый ящик или службу как настоящий пользователь и совершить незаконные действия.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-112">With them the attacker can sign in as the original user and perform illicit actions.</span></span>
<span data-ttu-id="7e3e1-113">Используя украденные учетные данные, злоумышленник может получить доступ к почтовому ящику Microsoft 365, папкам SharePoint или файлам OneDrive.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-113">Using the stolen credentials, the attacker can access the user's Microsoft 365 mailbox, SharePoint folders, or files in the user's OneDrive.</span></span> <span data-ttu-id="7e3e1-114">Часто деятельность злоумышленника проявляется в виде отправки электронных писем от имени настоящего пользователя получателям в организации и за ее пределами.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-114">One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization.</span></span> <span data-ttu-id="7e3e1-115">Когда злоумышленник отправляет данные по электронной почте внешним получателям, имеет место утечка данных.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-115">When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a><span data-ttu-id="7e3e1-116">Признаки компрометации учетной записи электронной почты Майкрософт</span><span class="sxs-lookup"><span data-stu-id="7e3e1-116">Symptoms of a Compromised Microsoft Email Account</span></span>

<span data-ttu-id="7e3e1-117">Пользователи могут заметить подозрительные действия в своих почтовых ящиках Microsoft 365 и сообщить об этих действиях.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-117">Users might notice and report unusual activity in their Microsoft 365 mailboxes.</span></span> <span data-ttu-id="7e3e1-118">Некоторые типичные признаки приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-118">Here are some common symptoms:</span></span>

- <span data-ttu-id="7e3e1-119">Подозрительные действия, например отсутствие или удаление сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-119">Suspicious activity, such as missing or deleted emails.</span></span>

- <span data-ttu-id="7e3e1-120">Другие пользователи могут получать из скомпрометированной учетной записи электронные письма, которых нет в папке **Отправленные** у отправителя.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-120">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>

- <span data-ttu-id="7e3e1-121">Наличие в почтовом ящике правил, которые не были созданы пользователем или администратором.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-121">The presence of inbox rules that weren't created by the intended user or the administrator.</span></span> <span data-ttu-id="7e3e1-122">Эти правила могут автоматически пересылать письма на неизвестные адреса или перемещать их в папки **Заметки**, **Нежелательная почта** или **RSS-подписки**.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-122">These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>

- <span data-ttu-id="7e3e1-123">Изменение краткого имени пользователя в глобальном списке адресов.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-123">The user's display name might be changed in the Global Address List.</span></span>

- <span data-ttu-id="7e3e1-124">Почтовый ящик пользователя не может отправлять почту.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-124">The user's mailbox is blocked from sending email.</span></span>

- <span data-ttu-id="7e3e1-125">Папки "Отправленные и "Удаленные" в Microsoft Outlook или Outlook в Интернете (прежнее название – Outlook Web App) содержат типичные для взломанного почтового ящика сообщения, например "Я в Лондоне, отправь деньги".</span><span class="sxs-lookup"><span data-stu-id="7e3e1-125">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>

- <span data-ttu-id="7e3e1-126">Необычные изменения профиля, например изменение имени, номера телефона или почтового индекса.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-126">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>

- <span data-ttu-id="7e3e1-127">Необычные изменения учетных данных, например многократное изменение пароля.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-127">Unusual credential changes, such as multiple password changes are required.</span></span>

- <span data-ttu-id="7e3e1-128">Недавнее добавление переадресации почты.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-128">Mail forwarding was recently added.</span></span>

- <span data-ttu-id="7e3e1-129">Недавнее появление необычной подписи, например на банковском документе или рецепте на лекарство.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-129">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="7e3e1-130">Если пользователь сообщает о любом из указанных признаков, необходимо провести дальнейшее расследование.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-130">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="7e3e1-131">Центр безопасности и соответствия требованиям Microsoft 365 и портал Azure предлагает инструменты для расследования активности учетной записи пользователя, которая, как вы подозреваете, может быть скомпрометирована.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-131">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="7e3e1-132">**Единые журналы аудита в Центре безопасности и соответствия требованиям**. Просмотрите все действия в подозреваемой учетной записи, отфильтруйте результаты по диапазону дат: с момента сразу перед подозрительным действием до текущей даты.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-132">**Unified Audit Logs in the Security & Compliance Center**: Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date.</span></span> <span data-ttu-id="7e3e1-133">Не фильтруйте действия во время поиска.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-133">Do not filter on the activities during the search.</span></span>

- <span data-ttu-id="7e3e1-134">**Журналы аудита действий администратора в Центре администрирования Exchange**. В Exchange Online можно использовать Центр администрирования Exchange (EAC) для поиска и просмотра записей в журнале аудита действий администратора.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-134">**Admin Audit logs in the EAC**: In Exchange Online, you can use the Exchange admin center (EAC) to search for and view entries in the administrator audit log.</span></span> <span data-ttu-id="7e3e1-135">В журнал аудита действий администратора записываются определенные действия на основе командлетов PowerShell Exchange Online, выполняемых администраторами и пользователями с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-135">The administrator audit log records specific actions, based on Exchange Online PowerShell cmdlets, performed by administrators and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="7e3e1-136">В записях журнала уточняется, какой командлет выполнен, какие параметры использованы, кто выполнял командлет, а также какие объекты задействованы.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-136">Entries in the administrator audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

- <span data-ttu-id="7e3e1-137">**Журналы входа в Azure AD и другие отчеты о рисках, доступные в портале Azure AD**. Проверьте значения в следующих столбцах:</span><span class="sxs-lookup"><span data-stu-id="7e3e1-137">**Azure AD Sign-in logs and other risk reports in the Azure AD portal**: Examine the values in these columns:</span></span>

  - <span data-ttu-id="7e3e1-138">IP-адрес;</span><span class="sxs-lookup"><span data-stu-id="7e3e1-138">Review IP address</span></span>
  - <span data-ttu-id="7e3e1-139">место входа;</span><span class="sxs-lookup"><span data-stu-id="7e3e1-139">sign-in locations</span></span>
  - <span data-ttu-id="7e3e1-140">время входа;</span><span class="sxs-lookup"><span data-stu-id="7e3e1-140">sign-in times</span></span>
  - <span data-ttu-id="7e3e1-141">успешный или неудачный вход.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-141">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a><span data-ttu-id="7e3e1-142">Защита и восстановление функции электронной почты в подозрительной с точки зрения компрометации учетной записи Microsoft 365 и почтовом ящике</span><span class="sxs-lookup"><span data-stu-id="7e3e1-142">How to secure and restore email function to a suspected compromised Microsoft 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="7e3e1-143">Даже если вы вновь получили доступ к своей учетной записи, возможно, злоумышленник встроил в нее лазейки, которые позволят ему вновь перехватить управление учетной записью.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-143">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="7e3e1-144">Обязательно выполните все указанные ниже действия, чтобы восстановить доступ к своей учетной записи, и чем раньше, тем лучше, чтобы взломщик не успел вернуть себе управление учетной записью.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-144">You must do all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account.</span></span> <span data-ttu-id="7e3e1-145">Эти действия помогут вам удалить все лазейки, которые взломщик мог встроить в вашу учетную запись.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-145">These steps help you remove any back-door entries that the hijacker may have added to your account.</span></span> <span data-ttu-id="7e3e1-146">После выполнения этих действий рекомендуется запустить проверку на вирусы, чтобы убедиться в том, что компьютер не скомпрометирован.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-146">After you do these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="7e3e1-147">Шаг 1. Смените пароль пользователя</span><span class="sxs-lookup"><span data-stu-id="7e3e1-147">Step 1 Reset the user's password</span></span>

<span data-ttu-id="7e3e1-148">Выполните процедуры из раздела [Сброс бизнес-пароля для другого пользователя](../../admin/add-users/reset-passwords.md#reset-my-admin-password).</span><span class="sxs-lookup"><span data-stu-id="7e3e1-148">Follow the procedures in [Reset a business password for someone](../../admin/add-users/reset-passwords.md#reset-my-admin-password).</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="7e3e1-149">Не отправляйте пользователю новый пароль по электронной почте, так как у злоумышленника пока есть доступ к почтовому ящику.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-149">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>
>
> - <span data-ttu-id="7e3e1-150">Пароль должен быть надежным и содержать буквы верхнего и нижнего регистра, хотя бы одну цифру и хотя бы один специальный символ.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-150">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span>
>
> - <span data-ttu-id="7e3e1-151">Не используйте пять последних паролей, использованных раньше.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-151">Don't reuse any of your last five passwords.</span></span> <span data-ttu-id="7e3e1-152">Хотя требования к журналу паролей разрешают использовать старые пароли, следует выбрать такой пароль, который злоумышленник не мог бы угадать.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-152">Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>
>
> - <span data-ttu-id="7e3e1-153">Если ваше локальное удостоверение связано федеративным доступом с Microsoft 365, необходимо сменить локальный пароль, а затем оповестить администратора о компрометации.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-153">If your on-premises identity is federated with Microsoft 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>
>
> - <span data-ttu-id="7e3e1-154">Не забудьте обновить пароли приложений.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-154">Be sure to update app passwords.</span></span> <span data-ttu-id="7e3e1-155">Пароли приложения не отзываются автоматически при сбросе пароля учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-155">App passwords aren't automatically revoked when a user account password reset.</span></span> <span data-ttu-id="7e3e1-156">Пользователь должен удалить существующие пароли приложений и создать новые.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-156">The user should delete existing app passwords and create new ones.</span></span> <span data-ttu-id="7e3e1-157">Инструкции см. в разделе [Создание и удаление паролей приложений на странице дополнительной проверки безопасности](/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).</span><span class="sxs-lookup"><span data-stu-id="7e3e1-157">For instructions, see [Create and delete app passwords from the Additional security verification page](/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).</span></span>
>
> - <span data-ttu-id="7e3e1-158">Настоятельно рекомендуется включить многофакторную проверку подлинности (MFA), чтобы предотвратить компрометацию, особенно для учетных записей с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-158">We highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.</span></span> <span data-ttu-id="7e3e1-159">Дополнительные сведения о MFA см. в статье [Настройка многофакторной проверки подлинности](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="7e3e1-159">To learn more about MFA, go to [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="7e3e1-160">Шаг 2. Удалите подозрительные адреса перенаправления почты</span><span class="sxs-lookup"><span data-stu-id="7e3e1-160">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="7e3e1-161">Откройте Центр администрирования Microsoft 365 на странице <https://admin.microsoft.com></span><span class="sxs-lookup"><span data-stu-id="7e3e1-161">Open the Microsoft 365 admin center at <https://admin.microsoft.com></span></span>

2. <span data-ttu-id="7e3e1-162">Перейдите в раздел **Пользователи** \> **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-162">Go to **Users** \> **Active users**.</span></span> <span data-ttu-id="7e3e1-163">Найдите подозрительную учетную запись пользователя и выберите пользователя (строку), не устанавливая флажок.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-163">Find the user account in question, and select the user (row) without selecting the checkbox.</span></span>

3. <span data-ttu-id="7e3e1-164">В открывшейся панели сведений выберите вкладку **Почта**.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-164">In the details flyout that appears, select the **Mail** tab.</span></span>

4. <span data-ttu-id="7e3e1-165">Если в разделе **Переадресация почты** установлено значение **Применяется**, щелкните **Управление переадресацией электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-165">If the value in the **Email forwarding** section is **Applied**, click **Manage email forwarding**.</span></span> <span data-ttu-id="7e3e1-166">В открывшейся панели **Управление переадресацией электронной почты** снимите флажок **Пересылать всю почту, поступающую в этот почтовый ящик** и нажмите **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-166">In the **Manage email forwarding** flyout that appears, clear **Forward all email sent to this mailbox**, and then click **Save changes**.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="7e3e1-167">Шаг 3. Отключите все подозрительные правила для папки "Входящие"</span><span class="sxs-lookup"><span data-stu-id="7e3e1-167">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="7e3e1-168">Войдите в почтовый ящик пользователя с помощью Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-168">Sign in to the user's mailbox using Outlook on the web.</span></span>

2. <span data-ttu-id="7e3e1-169">Щелкните значок шестеренки и выберите пункт **Почта**.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-169">Click on the gear icon and click **Mail**.</span></span>

3. <span data-ttu-id="7e3e1-170">Нажмите **Правила для папки "Входящие" и правила очистки** и проверьте правила.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-170">Click **Inbox and sweep rules** and review the rules.</span></span>

4. <span data-ttu-id="7e3e1-171">Отключите или удалите подозрительные правила.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-171">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="7e3e1-172">Шаг 4. Разблокируйте отправку почты для пользователя</span><span class="sxs-lookup"><span data-stu-id="7e3e1-172">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="7e3e1-173">Если подозрительный на компрометацию почтовый ящик незаконно использовался для отправки нежелательной почты, скорее всего, отправка почты из него запрещена.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-173">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>

<span data-ttu-id="7e3e1-174">Чтобы разблокировать отправку почты из почтового ящика, выполните действия в статье [Удаление пользователя с портала "Пользователи с ограниченным доступом" после отправки нежелательной почты](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="7e3e1-174">To unblock a mailbox from sending mail, follow the procedures in [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="7e3e1-175">Шаг 5 (необязательно). Запретите вход в учетную запись пользователя</span><span class="sxs-lookup"><span data-stu-id="7e3e1-175">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7e3e1-176">Можно запретить вход в подозрительную на компрометацию учетную запись, пока вы не убедитесь, что она безопасна.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-176">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="7e3e1-177">Откройте Центр администрирования Microsoft 365 и перейдите к разделу **Пользователи** \> **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-177">Open the Microsoft 365 admin center and go to **Users** \> **Active users**.</span></span>

2. <span data-ttu-id="7e3e1-178">Найдите и выберите учетную запись пользователя, щелкните значок ![Другие действия](../../media/ITPro-EAC-MoreOptionsIcon.png) и выберите **Изменение состояния входа**.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-178">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Edit sign-in status**.</span></span>

3. <span data-ttu-id="7e3e1-179">В появившейся панели **Заблокировать вход** щелкните **Запретить этому пользователю вход** и нажмите **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-179">On the **Block sign-in** pane that appears, select **Block this user from signing in**, and then click **Save changes**.</span></span>

4. <span data-ttu-id="7e3e1-180">Откройте Центр администрирования Exchange (EAC) на странице <admin.protection.outlook.com/ecp/> и перейдите к разделу **Получатели > Почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-180">Open the Exchange admin center (EAC) at <admin.protection.outlook.com/ecp/>, and go to **Recipients > Mailboxes**.</span></span>

5. <span data-ttu-id="7e3e1-181">Найдите и выберите пользователя.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-181">Find and select the select the user.</span></span> <span data-ttu-id="7e3e1-182">В области сведений выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7e3e1-182">In the details pane, do the following steps:</span></span>

   - <span data-ttu-id="7e3e1-183">В разделе **Функции телефона и голосовой почты** раздела выполните указанные ниже шаги.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-183">In the **Phone and voice features** section, do the following steps:</span></span>

     - <span data-ttu-id="7e3e1-184">Щелкните **Отключить Exchange ActiveSync** и нажмите **Да** в появившемся предупреждении.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-184">Select **Disable Exchange ActiveSync** and then click **Yes** in the warning that appears.</span></span>
     - <span data-ttu-id="7e3e1-185">Щелкните **Отключить Outlook Web App для устройств** и нажмите **Да** в появившемся предупреждении.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-185">Select **Disable OWA for Devices** and then click **Yes** in the warning that appears.</span></span>

   - <span data-ttu-id="7e3e1-186">В разделе **Возможность подключения электронной почты** для Outlook в Интернете щелкните **Отключить** и нажмите **Да** в появившемся предупреждении.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-186">In the **Email Connectivity** section for Outlook on the web, click **Disable** and then click **Yes** in the warning that appears.</span></span>

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="7e3e1-187">Необязательный шаг 6. Удалите подозрительную на компрометацию учетную запись из всех групп административных ролей</span><span class="sxs-lookup"><span data-stu-id="7e3e1-187">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="7e3e1-188">Членство в группе административных ролей можно восстановить, когда учетная запись будет защищена.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-188">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="7e3e1-189">Войдите с учетной записью глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-189">Sign in with a global administrator account:</span></span>

2. <span data-ttu-id="7e3e1-190">В Центре администрирования Microsoft 365 выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7e3e1-190">In the Microsoft 365 admin center, do the following steps:</span></span>

   1. <span data-ttu-id="7e3e1-191">Перейдите в раздел **Пользователи** \> **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-191">Go to **Users** \> **Active users**.</span></span>
   2. <span data-ttu-id="7e3e1-192">Найдите и выберите учетную запись пользователя, щелкните значок ![Другие действия](../../media/ITPro-EAC-MoreOptionsIcon.png) и выберите **Управление ролями**.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-192">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Manage roles**.</span></span>
   3. <span data-ttu-id="7e3e1-193">Удалите все роли администратора, назначенные учетной записи.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-193">Remove any administrative roles that are assigned to the account.</span></span> <span data-ttu-id="7e3e1-194">После завершения нажмите кнопку **Сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-194">When you're finished, click **Save changes**.</span></span>

3. <span data-ttu-id="7e3e1-195">В Центре безопасности и соответствия требованиям на странице <https://protection.office.com> выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7e3e1-195">In the Security & Compliance Center at <https://protection.office.com>, do the following steps:</span></span>

   <span data-ttu-id="7e3e1-196">Щелкните **Разрешения**, выберите каждую группу ролей в списке и найдите учетную запись пользователя в разделе **Участники** появившейся области сведений.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-196">Select **Permissions**, select each role group in the list and look for the user account in the **Members** section of the details flyout that appears.</span></span> <span data-ttu-id="7e3e1-197">Если группа ролей содержит учетную запись пользователя, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7e3e1-197">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="7e3e1-198">а.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-198">a.</span></span> <span data-ttu-id="7e3e1-199">Щелкните **Изменить** рядом с пунктом **Участники**.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-199">Click **Edit** next to **Members**.</span></span>
   <span data-ttu-id="7e3e1-200">b.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-200">b.</span></span> <span data-ttu-id="7e3e1-201">В появившейся области **Изменение свойства "Выбор участников"** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-201">On the **Editing Choose members** flyout that appears, click **Edit**.</span></span>
   <span data-ttu-id="7e3e1-202">c.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-202">c.</span></span> <span data-ttu-id="7e3e1-203">В появившейся области **Выбор участников** выберите учетную запись пользователя и нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-203">In the **Choose members** flyout that appears, select the user account, and then click **Remove**.</span></span> <span data-ttu-id="7e3e1-204">После завершения нажмите **Готово**, **Сохранить** и **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-204">When you're finished, click **Done**, **Save**, and then **Close**.</span></span>

4. <span data-ttu-id="7e3e1-205">В Центре администрирования Exchange на странице <admin.protection.outlook.com/ecp/> выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7e3e1-205">In the EAC at <admin.protection.outlook.com/ecp/>, do the following steps:</span></span>

   <span data-ttu-id="7e3e1-206">Щелкните **Разрешения** и вручную выберите каждую группу ролей. В области сведений проверьте учетные записи пользователей в разделе **Участники**.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-206">Select **Permissions**, manually select each role group, and in the details pane, verify the user accounts in the **Members** section.</span></span>  <span data-ttu-id="7e3e1-207">Если группа ролей содержит учетную запись пользователя, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7e3e1-207">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="7e3e1-208">а.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-208">a.</span></span> <span data-ttu-id="7e3e1-209">Выберите группу ролей и щелкните **Изменить** ![значок "Изменить"](../../media/ITPro-EAC-EditIcon.png).</span><span class="sxs-lookup"><span data-stu-id="7e3e1-209">Select the role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>
   <span data-ttu-id="7e3e1-210">b.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-210">b.</span></span> <span data-ttu-id="7e3e1-211">В разделе **Участник** выберите учетную запись и щелкните **Удалить** ![значок "Удалить"](../../media/ITPro-EAC-RemoveIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="7e3e1-211">In the **Member** section, select the user account, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span> <span data-ttu-id="7e3e1-212">По завершении нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-212">When you're finished, click **Save**.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="7e3e1-213">Шаг 7 (необязательно). Дополнительные меры предосторожности</span><span class="sxs-lookup"><span data-stu-id="7e3e1-213">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="7e3e1-214">Еще раз проверьте папку "Отправленные".</span><span class="sxs-lookup"><span data-stu-id="7e3e1-214">Make sure that you verify your sent items.</span></span> <span data-ttu-id="7e3e1-215">Возможно, следует сообщить пользователям из вашего списка контактов о том, что ваша учетная запись скомпрометирована.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-215">You may have to inform people on your contacts list that your account was compromised.</span></span> <span data-ttu-id="7e3e1-216">Злоумышленник может просить у них денег от вашего имени или отправлять им вирусы для взлома их компьютеров.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-216">The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>

2. <span data-ttu-id="7e3e1-217">Любые другие службы, использующие эту учетную запись Exchange как альтернативную для электронной почты, также могут быть скомпрометированы.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-217">Any other service that used this Exchange account as its alternative email account may have been compromised.</span></span> <span data-ttu-id="7e3e1-218">Сначала выполните эти действия для вашей подписки Microsoft 365, а затем для других ваших учетных записей.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-218">First, do these steps for your Microsoft 365 subscription, and then do these steps for your other accounts.</span></span>

3. <span data-ttu-id="7e3e1-219">Убедитесь, что ваши контактные данные, таких как телефонные номера и адреса, указаны правильно.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-219">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="7e3e1-220">Защитите Microsoft 365 на профессиональном уровне</span><span class="sxs-lookup"><span data-stu-id="7e3e1-220">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="7e3e1-221">Для вашей подписки Microsoft 365 предусмотрен целый ряд полезных функций безопасности, которые можно использовать для защиты ваших данных и пользователей.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-221">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="7e3e1-222">Используйте статью к [Стратегия развития безопасности Microsoft 365: приоритеты на первые 30 дней, 90 дней и далее](security-roadmap.md), чтобы применить лучшие методики, рекомендованные корпорацией Майкрософт, для защиты вашего клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-222">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="7e3e1-223">Задачи для выполнения в первые 30 дней.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-223">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="7e3e1-224">Они дают немедленный эффект и не создают помех вашим пользователям.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-224">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="7e3e1-225">Задачи для выполнения в течение 90 дней.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-225">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="7e3e1-226">Эти задачи требуют немного больше времени на планирование и реализацию, но значительно укрепляют вашу безопасность.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-226">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="7e3e1-227">Более 90 дней.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-227">Beyond 90 days.</span></span> <span data-ttu-id="7e3e1-228">Эти меры дополняют ваши действия в течение первых 90 дней.</span><span class="sxs-lookup"><span data-stu-id="7e3e1-228">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e3e1-229">См. также</span><span class="sxs-lookup"><span data-stu-id="7e3e1-229">See also</span></span>

- [<span data-ttu-id="7e3e1-230">Обнаружение атак с внедрением правил и пользовательских форм Outlook и устранение их последствий в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7e3e1-230">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Microsoft 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

- [<span data-ttu-id="7e3e1-231">Центр жалоб на Интернет-преступления</span><span class="sxs-lookup"><span data-stu-id="7e3e1-231">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/Home/Ransomware)

- [<span data-ttu-id="7e3e1-232">Комиссия по ценным бумагам и биржам – "фишинговое" мошенничество</span><span class="sxs-lookup"><span data-stu-id="7e3e1-232">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)

- <span data-ttu-id="7e3e1-233">Чтобы сообщить о нежелательной почте непосредственно в Майкрософт и своему администратору, [воспользуйтесь надстройкой Report Message](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="7e3e1-233">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>