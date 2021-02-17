---
title: Удаление заблокированных пользователей с портала "Пользователи с ограниченным доступом"
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать, как удалять пользователей с портала "Пользователи с ограниченным доступом" в Office 365. Пользователи попадают на портал "Пользователи с ограниченным доступом" за отправку исходящей нежелательной почты. Обычно это происходит в результате компрометации учетных записей.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1ba5334689ad58c8a50864a3618c0972b61dfd7f
ms.sourcegitcommit: a9ac702c9efc9defded3bfa65618b94bac00c237
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/16/2021
ms.locfileid: "50261553"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a><span data-ttu-id="ba835-104">Удаление заблокированных пользователей с портала "Пользователи с ограниченным доступом" в Office 365</span><span class="sxs-lookup"><span data-stu-id="ba835-104">Remove blocked users from the Restricted Users portal in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ba835-105">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="ba835-105">**Applies to**</span></span>
- [<span data-ttu-id="ba835-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ba835-106">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="ba835-107">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="ba835-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="ba835-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ba835-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="ba835-109">Если пользователь превысит один из лимитов отправки исходящей почты, указанных в разделе [лимитов служб](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) или [политик исходящей нежелательной почты](configure-the-outbound-spam-policy.md), он потеряет возможность отправлять почту, но по-прежнему сможет принимать ее.</span><span class="sxs-lookup"><span data-stu-id="ba835-109">If a user exceeds one of the outbound sending limits as specified in [the service limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="ba835-110">В этом случае пользователь будет добавлен на портал "Пользователи с ограниченным доступом" в Центре безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="ba835-110">The user is added to the Restricted Users portal in the Security & Compliance Center.</span></span> <span data-ttu-id="ba835-111">Если он попытается отправить электронное письмо, оно вернется в отчете о недоставке (также называемом сообщением о недоставке) с кодом ошибки [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) и следующим текстом:</span><span class="sxs-lookup"><span data-stu-id="ba835-111">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="ba835-112">"Не удалось доставить сообщение, так как система не распознала вас как допустимого отправителя.</span><span class="sxs-lookup"><span data-stu-id="ba835-112">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="ba835-113">Причина проблемы чаще всего связана с предположительной рассылкой нежелательной почты с вашего электронного адреса. Поэтому с него не разрешено отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="ba835-113">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="ba835-114">Обратитесь за помощью к администратору электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ba835-114">Contact  your email admin for assistance.</span></span> <span data-ttu-id="ba835-115">Удаленный сервер вернул ошибку "550 5.1.8. Отказано в доступе: недопустимый отправитель".</span><span class="sxs-lookup"><span data-stu-id="ba835-115">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="ba835-116">Администраторы могут удалять пользователей с портала "Пользователи с ограниченным доступом" в Центре безопасности и соответствия требованиям или в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba835-116">Admins can remove users from the Restricted Senders portal in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ba835-117">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="ba835-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ba835-118">Откройте Центр безопасности и соответствия требованиям по ссылке <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ba835-118">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ba835-119">Перейдите на страницу **Пользователи с ограниченным доступом** по ссылке <https://protection.office.com/restrictedusers>.</span><span class="sxs-lookup"><span data-stu-id="ba835-119">To go directly to the **Restricted Users** page, use <https://protection.office.com/restrictedusers>.</span></span>

- <span data-ttu-id="ba835-120">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ba835-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="ba835-121">Для выполнения процедур, описанных в этой статье, вам должны быть назначены разрешения в Центре безопасности и соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="ba835-121">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ba835-122">Чтобы удалить каких-либо пользователей с портала "Пользователи с ограниченным доступом", вы должны быть участником групп ролей **Управление организацией** или **Администратор безопасности**.</span><span class="sxs-lookup"><span data-stu-id="ba835-122">To remove users from the Restricted Users portal, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="ba835-123">Чтобы получить доступ к порталу "Пользователи с ограниченным доступом" только для чтения, вы должны быть участником групп ролей **Глобальный читатель** или **Читатель сведений о безопасности**.</span><span class="sxs-lookup"><span data-stu-id="ba835-123">For read-only access to the Restricted Users portal, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="ba835-124">Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ba835-124">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="ba835-125">Добавление пользователей в соответствующую роль Azure Active Directory в Центре безопасности Microsoft 365 предоставляет пользователям необходимые разрешения в Центре безопасности и соответствия требованиям _и_ разрешения для других функций в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ba835-125">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ba835-126">Дополнительные сведения см. в статье [О ролях администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="ba835-126">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  >
  > - <span data-ttu-id="ba835-127">Группа ролей **Управление организацией с правами только на просмотр** в [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) также предоставляет доступ только для чтения к этой функции.</span><span class="sxs-lookup"><span data-stu-id="ba835-127">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="ba835-128">Если отправитель превысил лимит сообщений исходящей почты, это свидетельствует о возможной компрометации учетной записи.</span><span class="sxs-lookup"><span data-stu-id="ba835-128">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="ba835-129">Прежде чем удалить пользователя с портала "Пользователи с ограниченным доступом", выполните необходимые действия, чтобы восстановить контроль над его учетной записью.</span><span class="sxs-lookup"><span data-stu-id="ba835-129">Before you remove the user from the Restricted Users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="ba835-130">Дополнительные сведения см. в статье [Реагирование на компрометацию учетной записи электронной почты в Office 365](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="ba835-130">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="ba835-131">Удаление пользователя из списка "Пользователи с ограниченным доступом" с помощью Центра безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="ba835-131">Use the Security & Compliance Center to remove a user from the Restricted Users list</span></span>

1. <span data-ttu-id="ba835-132">В Центре безопасности и соответствия требованиям последовательно выберите пункты **Управление угрозами** \> **Просмотр** \> **Пользователи с ограниченным доступом**.</span><span class="sxs-lookup"><span data-stu-id="ba835-132">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Restricted users**.</span></span>

2. <span data-ttu-id="ba835-133">Найдите и выберите пользователя, которого необходимо разблокировать.</span><span class="sxs-lookup"><span data-stu-id="ba835-133">Find and select the user that you want to unblock.</span></span> <span data-ttu-id="ba835-134">В столбце **Действия** щелкните **Разблокировать**.</span><span class="sxs-lookup"><span data-stu-id="ba835-134">In the **Actions** column, click **Unblock**.</span></span>

3. <span data-ttu-id="ba835-135">Откроется всплывающее окно со сведениями об учетной записи, которой запрещено отправлять почту.</span><span class="sxs-lookup"><span data-stu-id="ba835-135">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="ba835-136">Просмотрите рекомендации, чтобы убедиться, что вы принимаете надлежащие меры в случае фактической компрометации учетной записи.</span><span class="sxs-lookup"><span data-stu-id="ba835-136">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="ba835-137">По завершении нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ba835-137">Click **Next** when done.</span></span>

4. <span data-ttu-id="ba835-138">На следующем экране представлены рекомендации по предотвращению компрометации в будущем.</span><span class="sxs-lookup"><span data-stu-id="ba835-138">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="ba835-139">Включение многофакторной проверки подлинности (MFA) и изменение паролей обеспечивают хорошую защиту.</span><span class="sxs-lookup"><span data-stu-id="ba835-139">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="ba835-140">По завершении нажмите кнопку **Разблокировать пользователя**.</span><span class="sxs-lookup"><span data-stu-id="ba835-140">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="ba835-141">Нажмите кнопку **Да**, чтобы подтвердить изменение.</span><span class="sxs-lookup"><span data-stu-id="ba835-141">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ba835-142">Для удаления всех ограничений пользователя может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="ba835-142">It might take up to 24 hours for all restrictions to be removed from the user.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="ba835-143">Проверка параметров оповещений для пользователей с ограниченным доступом</span><span class="sxs-lookup"><span data-stu-id="ba835-143">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="ba835-144">Используемая по умолчанию политика оповещений **Пользователи, которым запрещено отправлять почту** автоматически уведомляет администраторов о введении запрета на отправку исходящей почты для пользователя.</span><span class="sxs-lookup"><span data-stu-id="ba835-144">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="ba835-145">Вы можете проверить эти параметры и добавить дополнительных пользователей, которым необходимо отправлять уведомления.</span><span class="sxs-lookup"><span data-stu-id="ba835-145">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="ba835-146">Дополнительные сведения о политиках оповещений см. в статье [Политики оповещений в Центре безопасности и соответствия требованиям](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ba835-146">For more information about alert policies, see [Alert policies in the security and compliance center](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba835-147">Чтобы оповещения работали, должен быть включен поиск в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="ba835-147">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="ba835-148">Дополнительные сведения см. в статье [Включение и отключение поиска в журнале аудита](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="ba835-148">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="ba835-149">В Центре безопасности и соответствия требованиям последовательно выберите пункты **Оповещения** \> **Политики оповещений**.</span><span class="sxs-lookup"><span data-stu-id="ba835-149">In the Security & Compliance Center, go to **Alerts** \> **Alert policies**.</span></span>

2. <span data-ttu-id="ba835-150">Найдите и выберите оповещение **Пользователю запрещена отправка электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="ba835-150">Find and select the **User restricted from sending email** alert.</span></span>

3. <span data-ttu-id="ba835-151">В открывшемся окне проверьте или настройте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="ba835-151">In the flyout that appears, verify or configure the following settings:</span></span>

   - <span data-ttu-id="ba835-152">**Состояние**: убедитесь, что оповещение включено ![Переключатель включен](../../media/scc-toggle-on.png).</span><span class="sxs-lookup"><span data-stu-id="ba835-152">**Status**: Verify the alert is turned on ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="ba835-153">**Получатели электронной почты**: щелкните **Изменить** и в открывшемся окне **Изменение получателей** проверьте или настройте указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="ba835-153">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>

     - <span data-ttu-id="ba835-154">**Отправлять уведомления по электронной почте**: убедитесь, что флажок установлен (**Включен**).</span><span class="sxs-lookup"><span data-stu-id="ba835-154">**Send email notifications**: Verify the check box is selected (**On**).</span></span>

     - <span data-ttu-id="ba835-155">**Получатели электронной почты**: по умолчанию используется значение **TenantAdmins** (то есть участники группы **Глобальный администратор**).</span><span class="sxs-lookup"><span data-stu-id="ba835-155">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="ba835-156">Чтобы добавить дополнительных получателей, щелкните пустую область в поле.</span><span class="sxs-lookup"><span data-stu-id="ba835-156">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="ba835-157">Отобразится список получателей, после чего можно начать вводить имя, чтобы отфильтровать список и выбрать нужного получателя.</span><span class="sxs-lookup"><span data-stu-id="ba835-157">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="ba835-158">Чтобы удалить существующего получателя из поля, щелкните значок ![Удалить](../../media/scc-remove-icon.png) рядом с именем этого получателя.</span><span class="sxs-lookup"><span data-stu-id="ba835-158">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/scc-remove-icon.png) next to their name.</span></span>

     - <span data-ttu-id="ba835-159">**Ограничение на ежедневные уведомления**: по умолчанию используется значение **Без ограничений**, но вы можете выбрать ограничение для максимального количества уведомлений в день.</span><span class="sxs-lookup"><span data-stu-id="ba835-159">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="ba835-160">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ba835-160">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="ba835-161">Вернитесь в окно **Пользователю запрещена отправка электронной почты** и щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="ba835-161">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="ba835-162">Просмотр пользователей в списке "Пользователи с ограниченным доступом" и удаление их из этого списка с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba835-162">Use Exchange Online PowerShell to view and remove users from the Restricted Users list</span></span>

<span data-ttu-id="ba835-163">Чтобы отобразить список пользователей, которым запрещено отправлять почту, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ba835-163">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="ba835-164">Чтобы отобразить сведения об определенном пользователе, выполните следующую команду, заменив выражение \<emailaddress\> электронным адресом пользователя:</span><span class="sxs-lookup"><span data-stu-id="ba835-164">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="ba835-165">Подробные сведения о синтаксисе и параметрах см. в статье [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).</span><span class="sxs-lookup"><span data-stu-id="ba835-165">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="ba835-166">Чтобы удалить пользователя из списка "Пользователи с ограниченным доступом", выполните следующую команду, заменив выражение \<emailaddress\> электронным адресом пользователя:</span><span class="sxs-lookup"><span data-stu-id="ba835-166">To remove a user from the Restricted Users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="ba835-167">Подробные сведения о синтаксисе и параметрах см. в статье [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).</span><span class="sxs-lookup"><span data-stu-id="ba835-167">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).</span></span>
