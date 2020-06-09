---
title: Удаление заблокированных пользователей с портала "Пользователи с ограниченным доступом"
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как удалять пользователей с портала "Пользователи с ограниченным доступом" в Office 365. Пользователи попадают на портал "Пользователи с ограниченным доступом" за отправку исходящей нежелательной почты. Обычно это происходит в результате компрометации учетных записей.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b9e28550c67e20466b18b17d8b49fb1b68997cc4
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617366"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a><span data-ttu-id="f1634-104">Удаление заблокированных пользователей с портала "Пользователи с ограниченным доступом" в Office 365</span><span class="sxs-lookup"><span data-stu-id="f1634-104">Remove blocked users from the Restricted Users portal in Office 365</span></span>

<span data-ttu-id="f1634-105">Если пользователь превысит один из лимитов отправки исходящей почты, указанных в разделе [лимитов служб](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) или [политик исходящей нежелательной почты](configure-the-outbound-spam-policy.md), он потеряет возможность отправлять почту, но по-прежнему сможет принимать ее.</span><span class="sxs-lookup"><span data-stu-id="f1634-105">If a user exceeds one of the outbound sending limits as specified in [the service limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="f1634-106">В этом случае пользователь будет добавлен на портал "Пользователи с ограниченным доступом" в Центре безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="f1634-106">The user is added to the Restricted Users portal in the Security & Compliance Center.</span></span> <span data-ttu-id="f1634-107">Если он попытается отправить электронное письмо, оно вернется в отчете о недоставке (также называемом сообщением о недоставке) с кодом ошибки [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) и следующим текстом:</span><span class="sxs-lookup"><span data-stu-id="f1634-107">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="f1634-108">"Не удалось доставить сообщение, так как система не распознала вас как допустимого отправителя.</span><span class="sxs-lookup"><span data-stu-id="f1634-108">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="f1634-109">Причина проблемы чаще всего связана с предположительной рассылкой нежелательной почты с вашего электронного адреса. Поэтому с него не разрешено отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="f1634-109">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="f1634-110">Обратитесь за помощью к администратору электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f1634-110">Contact  your email admin for assistance.</span></span> <span data-ttu-id="f1634-111">Удаленный сервер вернул ошибку "550 5.1.8. Отказано в доступе: недопустимый отправитель".</span><span class="sxs-lookup"><span data-stu-id="f1634-111">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="f1634-112">Администраторы могут удалять пользователей с портала "Пользователи с ограниченным доступом" в Центре безопасности и соответствия требованиям или в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1634-112">Admins can remove users from the Restricted Senders portal in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f1634-113">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="f1634-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f1634-114">Откройте Центр безопасности и соответствия требованиям по ссылке <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f1634-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f1634-115">Перейдите на страницу **Пользователи с ограниченным доступом** по ссылке <https://protection.office.com/restrictedusers>.</span><span class="sxs-lookup"><span data-stu-id="f1634-115">To go directly to the **Restricted Users** page, use <https://protection.office.com/restrictedusers>.</span></span>

- <span data-ttu-id="f1634-116">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f1634-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="f1634-117">Чтобы вы могли выполнить эти процедуры, вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="f1634-117">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="f1634-118">Чтобы удалить каких-либо пользователей с портала "Пользователи с ограниченным доступом", вы должны быть участником групп ролей **Управление организацией** или **Администратор безопасности**.</span><span class="sxs-lookup"><span data-stu-id="f1634-118">To remove users from the Restricted Users portal, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="f1634-119">Чтобы получить доступ к порталу "Пользователи с ограниченным доступом" только для чтения, вы должны быть участником группы ролей **Читатель сведений о безопасности**.</span><span class="sxs-lookup"><span data-stu-id="f1634-119">For read-only access to the Restricted Users portal, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="f1634-120">Дополнительные сведения о группах ролей в Центре безопасности и соответствия требованиям см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f1634-120">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="f1634-121">Если отправитель превысил лимит сообщений исходящей почты, это свидетельствует о возможной компрометации учетной записи.</span><span class="sxs-lookup"><span data-stu-id="f1634-121">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="f1634-122">Прежде чем удалить пользователя с портала "Пользователи с ограниченным доступом", выполните необходимые действия, чтобы восстановить контроль над его учетной записью.</span><span class="sxs-lookup"><span data-stu-id="f1634-122">Before you remove the user from the Restricted Users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="f1634-123">Дополнительные сведения см. в статье [Реагирование на компрометацию учетной записи электронной почты в Office 365](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="f1634-123">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="f1634-124">Удаление пользователя из списка "Пользователи с ограниченным доступом" с помощью Центра безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="f1634-124">Use the Security & Compliance Center to remove a user from the Restricted Users list</span></span>

1. <span data-ttu-id="f1634-125">В Центре безопасности и соответствия требованиям последовательно выберите пункты **Управление угрозами** \> **Просмотр** \> **Пользователи с ограниченным доступом**.</span><span class="sxs-lookup"><span data-stu-id="f1634-125">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Restricted users**.</span></span>

2. <span data-ttu-id="f1634-126">Найдите и выберите пользователя, которого необходимо разблокировать.</span><span class="sxs-lookup"><span data-stu-id="f1634-126">Find and select the user that you want to unblock.</span></span> <span data-ttu-id="f1634-127">В столбце **Действия** щелкните **Разблокировать**.</span><span class="sxs-lookup"><span data-stu-id="f1634-127">In the **Actions** column, click **Unblock**.</span></span>

3. <span data-ttu-id="f1634-128">Откроется всплывающее окно со сведениями об учетной записи, которой запрещено отправлять почту.</span><span class="sxs-lookup"><span data-stu-id="f1634-128">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="f1634-129">Просмотрите рекомендации, чтобы убедиться, что вы принимаете надлежащие меры в случае фактической компрометации учетной записи.</span><span class="sxs-lookup"><span data-stu-id="f1634-129">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="f1634-130">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f1634-130">Click **Next** when done.</span></span>

4. <span data-ttu-id="f1634-131">На следующем экране представлены рекомендации по предотвращению компрометации в будущем.</span><span class="sxs-lookup"><span data-stu-id="f1634-131">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="f1634-132">Включение многофакторной проверки подлинности (MFA) и изменение паролей обеспечивают хорошую защиту.</span><span class="sxs-lookup"><span data-stu-id="f1634-132">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="f1634-133">По завершении нажмите кнопку **Разблокировать пользователя**.</span><span class="sxs-lookup"><span data-stu-id="f1634-133">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="f1634-134">Нажмите кнопку **Да**, чтобы подтвердить изменение.</span><span class="sxs-lookup"><span data-stu-id="f1634-134">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f1634-135">Для снятия ограничений может потребоваться 30 минут или более.</span><span class="sxs-lookup"><span data-stu-id="f1634-135">It may take 30 minutes or more before restrictions are removed.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="f1634-136">Проверка параметров оповещений для пользователей с ограниченным доступом</span><span class="sxs-lookup"><span data-stu-id="f1634-136">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="f1634-137">Используемая по умолчанию политика оповещений **Пользователи, которым запрещено отправлять почту** автоматически уведомляет администраторов о введении запрета на отправку исходящей почты для пользователя.</span><span class="sxs-lookup"><span data-stu-id="f1634-137">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="f1634-138">Вы можете проверить эти параметры и добавить дополнительных пользователей, которым необходимо отправлять уведомления.</span><span class="sxs-lookup"><span data-stu-id="f1634-138">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="f1634-139">Дополнительные сведения о политиках оповещений см. в статье [Политики оповещений в Центре безопасности и соответствия требованиям](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f1634-139">For more information about alert policies, see [Alert policies in the security and compliance center](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1634-140">Чтобы оповещения работали, должен быть включен поиск в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="f1634-140">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="f1634-141">Дополнительные сведения см. в статье [Включение и отключение поиска в журнале аудита](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="f1634-141">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="f1634-142">В Центре безопасности и соответствия требованиям последовательно выберите пункты **Оповещения** \> **Политики оповещений**.</span><span class="sxs-lookup"><span data-stu-id="f1634-142">In the Security & Compliance Center, go to **Alerts** \> **Alert policies**.</span></span>

2. <span data-ttu-id="f1634-143">Найдите и выберите оповещение **Пользователю запрещена отправка электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="f1634-143">Find an select the **User restricted from sending email** alert.</span></span>

3. <span data-ttu-id="f1634-144">В открывшемся окне проверьте или настройте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="f1634-144">In the flyout that appears, verify or configure the following settings:</span></span>

   - <span data-ttu-id="f1634-145">**Состояние**: убедитесь, что оповещение включено ![Переключатель включен](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span><span class="sxs-lookup"><span data-stu-id="f1634-145">**Status**: Verify the alert is turned on ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="f1634-146">**Получатели электронной почты**: щелкните **Изменить** и в открывшемся окне **Изменение получателей** проверьте или настройте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="f1634-146">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>

     - <span data-ttu-id="f1634-147">**Отправлять уведомления по электронной почте**: убедитесь, что флажок установлен (**Включен**).</span><span class="sxs-lookup"><span data-stu-id="f1634-147">**Send email notifications**: Verify the check box is selected (**On**).</span></span>

     - <span data-ttu-id="f1634-148">**Получатели электронной почты**: по умолчанию используется значение **TenantAdmins** (то есть участники группы **Глобальный администратор**).</span><span class="sxs-lookup"><span data-stu-id="f1634-148">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="f1634-149">Чтобы добавить дополнительных получателей, щелкните пустую область в поле.</span><span class="sxs-lookup"><span data-stu-id="f1634-149">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="f1634-150">Отобразится список получателей, после чего можно начать вводить имя, чтобы отфильтровать список и выбрать нужного получателя.</span><span class="sxs-lookup"><span data-stu-id="f1634-150">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="f1634-151">Чтобы удалить существующего получателя из поля, щелкните значок ![Удалить](../../media/scc-remove-icon.png) рядом с именем этого получателя.</span><span class="sxs-lookup"><span data-stu-id="f1634-151">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/scc-remove-icon.png) next to their name.</span></span>

     - <span data-ttu-id="f1634-152">**Ограничение на ежедневные уведомления**: по умолчанию используется значение **Без ограничений**, но вы можете выбрать ограничение для максимального количества уведомлений в день.</span><span class="sxs-lookup"><span data-stu-id="f1634-152">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="f1634-153">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f1634-153">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="f1634-154">Вернитесь в окно **Пользователю запрещена отправка электронной почты** и щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="f1634-154">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="f1634-155">Просмотр пользователей в списке "Пользователи с ограниченным доступом" и удаление их из этого списка с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1634-155">Use Exchange Online PowerShell to view and remove users from the Restricted Users list</span></span>

<span data-ttu-id="f1634-156">Чтобы отобразить список пользователей, которым запрещено отправлять почту, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f1634-156">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="f1634-157">Чтобы отобразить сведения об определенном пользователе, выполните следующую команду, заменив выражение \<emailaddress\> электронным адресом пользователя:</span><span class="sxs-lookup"><span data-stu-id="f1634-157">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="f1634-158">Подробные сведения о синтаксисе и параметрах см. в статье [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).</span><span class="sxs-lookup"><span data-stu-id="f1634-158">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="f1634-159">Чтобы удалить пользователя из списка "Пользователи с ограниченным доступом", выполните следующую команду, заменив выражение \<emailaddress\> электронным адресом пользователя:</span><span class="sxs-lookup"><span data-stu-id="f1634-159">To remove a user from the Restricted Users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="f1634-160">Подробные сведения о синтаксисе и параметрах см. в статье [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).</span><span class="sxs-lookup"><span data-stu-id="f1634-160">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).</span></span>
