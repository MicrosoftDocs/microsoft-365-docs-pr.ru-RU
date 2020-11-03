---
title: Переход в центр уведомлений для просмотра и утверждения автоматического исследования и задач по исправлению
description: Используйте центр уведомлений для просмотра сведений об автоматическом исследовании и утверждения ожидающих действий
keywords: Центр уведомлений, защита от угроз, исследование, оповещение, ожидание, автоматически, обнаружение
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: 3ec17204903f3e83f3fbfd126d57d0b9ca5d56f7
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843796"
---
# <a name="the-action-center"></a><span data-ttu-id="a05bb-104">Центр уведомлений</span><span class="sxs-lookup"><span data-stu-id="a05bb-104">The Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a05bb-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a05bb-105">**Applies to:**</span></span>
- <span data-ttu-id="a05bb-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a05bb-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a05bb-107">Используйте центр уведомлений для просмотра результатов текущего и прошлых исследований в почтовых ящиках и устройствах вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a05bb-107">Use the Action center to see the results of current and past investigations across your organization's devices and mailboxes.</span></span> <span data-ttu-id="a05bb-108">В зависимости от типа угрозы и результата вредоносности [действия по исправлению](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) происходят автоматически или при утверждении группой операций безопасности Организации.</span><span class="sxs-lookup"><span data-stu-id="a05bb-108">Depending on the type of threat and resulting verdict, [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="a05bb-109">Все действия по исправлению (как ожидающие утверждения, так и утвержденные) объединяются в центре уведомлений.</span><span class="sxs-lookup"><span data-stu-id="a05bb-109">All remediation actions, whether they are pending approval or were already approved, are consolidated in the Action center.</span></span> 

![Центр уведомлений](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a><span data-ttu-id="a05bb-111">Интерфейс "единой области представления"</span><span class="sxs-lookup"><span data-stu-id="a05bb-111">A "single pane of glass" experience</span></span>

<span data-ttu-id="a05bb-112">В центре уведомлений доступен интерфейс "единой области представления" для задач, таких как:</span><span class="sxs-lookup"><span data-stu-id="a05bb-112">The Action center provides a "single pane of glass" experience for tasks, such as:</span></span>
- <span data-ttu-id="a05bb-113">утверждение ожидающих действий по исправлению;</span><span class="sxs-lookup"><span data-stu-id="a05bb-113">Approving pending remediation actions;</span></span>
- <span data-ttu-id="a05bb-114">просмотр журнала аудита утвержденных действий по исправлению; и</span><span class="sxs-lookup"><span data-stu-id="a05bb-114">Viewing an audit log of already approved remediation actions; and</span></span>
- <span data-ttu-id="a05bb-115">проверка выполненных действий по исправлению.</span><span class="sxs-lookup"><span data-stu-id="a05bb-115">Reviewing completed remediation actions.</span></span>

<span data-ttu-id="a05bb-116">Команда по обеспечению безопасности может эффективно работать эффективнее и эффективно, так как центр уведомлений предоставляет исчерпывающее представление о работе защитника Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a05bb-116">Your security operations team can operate more effectively and efficiently, because the Action center provides a comprehensive view of Microsoft 365 Defender at work.</span></span>

## <a name="go-to-the-action-center"></a><span data-ttu-id="a05bb-117">Переход в центр уведомлений</span><span class="sxs-lookup"><span data-stu-id="a05bb-117">Go to the Action center</span></span>

1. <span data-ttu-id="a05bb-118">Перейдите на страницу [https://security.microsoft.com](https://security.microsoft.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="a05bb-118">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="a05bb-119">В панели навигации щелкните **Центр уведомлений**.</span><span class="sxs-lookup"><span data-stu-id="a05bb-119">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="a05bb-120">В центре уведомлений вы увидите две вкладки: **ожидающие** и **журналу**.</span><span class="sxs-lookup"><span data-stu-id="a05bb-120">In the Action center, you'll see two tabs: **Pending** and **History**.</span></span>

    - <span data-ttu-id="a05bb-121">На вкладке **Ожидание** перечислены исследования, требующие проверки и утверждения участником группы операций по безопасности для продолжения процесса.</span><span class="sxs-lookup"><span data-stu-id="a05bb-121">The **Pending** tab lists investigations that require review and approval by someone in your security operations team to continue.</span></span> <span data-ttu-id="a05bb-122">Обязательно просмотрите ожидающие элементы, представленные здесь, и выполните соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="a05bb-122">Make sure to review and take action on pending items you see here.</span></span>

    - <span data-ttu-id="a05bb-123">На вкладке **Журнал** перечислены прошлые исследования и действия по исправлению, выполненные автоматически.</span><span class="sxs-lookup"><span data-stu-id="a05bb-123">The **History** tab lists past investigations and remediation actions that were taken automatically.</span></span> <span data-ttu-id="a05bb-124">Вы можете просматривать данные за последний день, неделю, месяц или шесть месяцев.</span><span class="sxs-lookup"><span data-stu-id="a05bb-124">You can view data for the past day, week, month, or six months.</span></span>

4. <span data-ttu-id="a05bb-125">Чтобы отобразить только нужные столбцы, выберите команду **Настроить столбцы**.</span><span class="sxs-lookup"><span data-stu-id="a05bb-125">To show only the columns you want to see, select **Customize columns**.</span></span><br/><span data-ttu-id="a05bb-126">![Центр уведомлений в защитнике Microsoft 365](../../media/mtp-action-center.png)</span><span class="sxs-lookup"><span data-stu-id="a05bb-126">![Action Center in Microsoft 365 Defender](../../media/mtp-action-center.png)</span></span>

5. <span data-ttu-id="a05bb-127">Выберите элемент в списке, чтобы просмотреть дополнительные сведения об исследовании.</span><span class="sxs-lookup"><span data-stu-id="a05bb-127">Select an item in the list to view more details about an investigation.</span></span> <span data-ttu-id="a05bb-128">Откроется представление со сведениями об исследовании.</span><span class="sxs-lookup"><span data-stu-id="a05bb-128">The investigation details view opens.</span></span><br/>![Сведения об исследовании](../../media/mtp-air-investdetails.png)

    - <span data-ttu-id="a05bb-130">Если исследование относится к содержимому электронной почты (например, объект является почтовым ящиком), сведения об исследовании открываются в центре безопасности & соответствия требованиям ( [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) ).</span><span class="sxs-lookup"><span data-stu-id="a05bb-130">If the investigation pertains to email content (such as, the entity is a mailbox), investigation details open in the Security & Compliance Center ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)).</span></span> 

    - <span data-ttu-id="a05bb-131">Если исследование затрагивает устройство, сведения об исследовании откроются в Центре безопасности ([https://security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="a05bb-131">If the investigation involves a device, investigation details open in the security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span> 

> [!TIP]
> <span data-ttu-id="a05bb-132">Если вы считаете, что что-то пошло не так или неправильно, с помощью функции автоматического исследования и ответа в защитнике Microsoft 365, дайте нам знать!</span><span class="sxs-lookup"><span data-stu-id="a05bb-132">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="a05bb-133">Сведения о [том, как сообщить о ложных срабатываниях и негативах в возможностях автоматического исследования и реагирования (AIR) в защитнике Microsoft 365](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="a05bb-133">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="available-actions"></a><span data-ttu-id="a05bb-134">Доступные действия</span><span class="sxs-lookup"><span data-stu-id="a05bb-134">Available actions</span></span>

<span data-ttu-id="a05bb-135">По мере выполнения действий по исправлению они отображаются на вкладке "журнал" в центре уведомлений.</span><span class="sxs-lookup"><span data-stu-id="a05bb-135">As remediation actions are taken, they're listed on the History tab in the Action center.</span></span> <span data-ttu-id="a05bb-136">К таким действиям относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="a05bb-136">Such actions include the following:</span></span>

- <span data-ttu-id="a05bb-137">Сбор пакетов для расследования</span><span class="sxs-lookup"><span data-stu-id="a05bb-137">Collect investigation package</span></span> 
- <span data-ttu-id="a05bb-138">Изолировать устройство (это действие можно отменить)</span><span class="sxs-lookup"><span data-stu-id="a05bb-138">Isolate device (this action can be undone)</span></span> 
- <span data-ttu-id="a05bb-139">Компьютер переносе</span><span class="sxs-lookup"><span data-stu-id="a05bb-139">Offboard machine</span></span> 
- <span data-ttu-id="a05bb-140">Запуск кода</span><span class="sxs-lookup"><span data-stu-id="a05bb-140">Release code execution</span></span> 
- <span data-ttu-id="a05bb-141">Выпуск из карантина</span><span class="sxs-lookup"><span data-stu-id="a05bb-141">Release from quarantine</span></span> 
- <span data-ttu-id="a05bb-142">Пример запроса</span><span class="sxs-lookup"><span data-stu-id="a05bb-142">Request sample</span></span> 
- <span data-ttu-id="a05bb-143">Ограничение выполнения кода (это действие можно отменить)</span><span class="sxs-lookup"><span data-stu-id="a05bb-143">Restrict code execution (this action can be undone)</span></span> 
- <span data-ttu-id="a05bb-144">Запуск антивирусной проверки</span><span class="sxs-lookup"><span data-stu-id="a05bb-144">Run antivirus scan</span></span> 
- <span data-ttu-id="a05bb-145">Остановка и карантин</span><span class="sxs-lookup"><span data-stu-id="a05bb-145">Stop and quarantine</span></span> 

## <a name="required-permissions-for-action-center-tasks"></a><span data-ttu-id="a05bb-146">Обязательные разрешения для задач центра уведомлений</span><span class="sxs-lookup"><span data-stu-id="a05bb-146">Required permissions for Action center tasks</span></span>

<span data-ttu-id="a05bb-147">Чтобы утвердить или отклонить ожидающие действия в центре уведомлений, вам должны быть назначены разрешения, указанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a05bb-147">To approve or reject pending actions in the Action center, you must have permissions assigned as listed in the following table:</span></span>

|<span data-ttu-id="a05bb-148">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="a05bb-148">Remediation action</span></span> |<span data-ttu-id="a05bb-149">Обязательные роли и разрешения</span><span class="sxs-lookup"><span data-stu-id="a05bb-149">Required roles and permissions</span></span> |
|--|----|
|<span data-ttu-id="a05bb-150">Защитник Майкрософт для исправления конечных точек (устройства)</span><span class="sxs-lookup"><span data-stu-id="a05bb-150">Microsoft Defender for Endpoint remediation (devices)</span></span> |<span data-ttu-id="a05bb-151">Роль администратора безопасности, назначенная в Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) или Центре администрирования Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))</span><span class="sxs-lookup"><span data-stu-id="a05bb-151">Security Administrator role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="a05bb-152">--- или ---</span><span class="sxs-lookup"><span data-stu-id="a05bb-152">--- or ---</span></span><br/><span data-ttu-id="a05bb-153">Роль "активные действия при исправлении", назначенная в защитнике Майкрософт для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a05bb-153">Active remediation actions role assigned in Microsoft Defender for Endpoint</span></span> <br/> <br/> <span data-ttu-id="a05bb-154">Для получения дополнительных сведений ознакомьтесь с приведенными ниже ресурсами.</span><span class="sxs-lookup"><span data-stu-id="a05bb-154">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="a05bb-155">- [Разрешения роли администратора в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="a05bb-155">- [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span></span><br/><span data-ttu-id="a05bb-156">- [Создание и управление ролями для управления доступом на основе ролей (защитник Майкрософт для конечной точки)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span><span class="sxs-lookup"><span data-stu-id="a05bb-156">- [Create and manage roles for role-based access control (Microsoft Defender for Endpoint)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span></span>  |
|<span data-ttu-id="a05bb-157">Защитник Майкрософт для Office 365 об исправлении (контент и электронная почта Office)</span><span class="sxs-lookup"><span data-stu-id="a05bb-157">Microsoft Defender for Office 365 remediation (Office content and email)</span></span>  |<span data-ttu-id="a05bb-158">Роль администратора безопасности, назначенная в Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) или Центре администрирования Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))</span><span class="sxs-lookup"><span data-stu-id="a05bb-158">Security Administrator role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com))</span></span><br/><span data-ttu-id="a05bb-159">--- и ---</span><span class="sxs-lookup"><span data-stu-id="a05bb-159">--- and ---</span></span> <br/><span data-ttu-id="a05bb-160">Роль поиска и очистки, которой назначен центр безопасности & соответствия требованиям ( [https://protection.office.com](https://protection.office.com) ).</span><span class="sxs-lookup"><span data-stu-id="a05bb-160">Search and Purge role assigned the Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span> <br/><br/><span data-ttu-id="a05bb-161">**Важно!** если у вас есть роль администратора безопасности, назначенная только в центре безопасности & соответствия требованиям, доступ к центру уведомлений и возможностям защитника Microsoft 365 будет невозможен.</span><span class="sxs-lookup"><span data-stu-id="a05bb-161">**IMPORTANT** : If you have the Security Administrator role assigned only in the Security & Compliance Center, you will not be able to access the Action center or Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="a05bb-162">У вас должна быть роль администратора безопасности, назначенная в Azure Active Directory или Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a05bb-162">You must have the Security Administrator role assigned in Azure Active Directory or the Microsoft 365 admin center.</span></span> <br/><br/><span data-ttu-id="a05bb-163">Для получения дополнительных сведений ознакомьтесь с приведенными ниже ресурсами.</span><span class="sxs-lookup"><span data-stu-id="a05bb-163">To learn more, see the following resources:</span></span> <br/><span data-ttu-id="a05bb-164">- [Разрешения роли администратора в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="a05bb-164">- [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span></span><br/><span data-ttu-id="a05bb-165">- [Разрешения в центре безопасности & соответствия требованиям](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span><span class="sxs-lookup"><span data-stu-id="a05bb-165">- [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)</span></span> |

> [!NOTE]
> <span data-ttu-id="a05bb-166">Пользователи, которым назначена роль Глобальный администратор в Azure Active Directory, могут утвердить или отклонить любые ожидающие действия в центре уведомлений.</span><span class="sxs-lookup"><span data-stu-id="a05bb-166">Users who have the Global Administrator role assigned in Azure Active Directory can approve or reject any pending action in the Action center.</span></span> <span data-ttu-id="a05bb-167">Однако рекомендуется ограничить в организации число пользователей, которым назначена роль глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="a05bb-167">However, as a best practice, your organization should limit the number of people who have the Global Administrator role assigned.</span></span> <span data-ttu-id="a05bb-168">Рекомендуем использовать роли Администратор безопасности, Активные действия по исправлению, и Поиск и очистка, указанные выше, в качестве разрешений центра уведомлений.</span><span class="sxs-lookup"><span data-stu-id="a05bb-168">We recommend using the Security Administrator, Active remediation actions, and Search and Purge roles listed above for Action center permissions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a05bb-169">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="a05bb-169">Next steps</span></span> 

- [<span data-ttu-id="a05bb-170">Утверждение или отклонение ожидающих действий за автоматическим исследованием</span><span class="sxs-lookup"><span data-stu-id="a05bb-170">Approve or reject pending actions following an automated investigation</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="a05bb-171">Просмотр результатов автоматического исследования</span><span class="sxs-lookup"><span data-stu-id="a05bb-171">View the results of an automated investigation</span></span>](mtp-autoir-results.md)

