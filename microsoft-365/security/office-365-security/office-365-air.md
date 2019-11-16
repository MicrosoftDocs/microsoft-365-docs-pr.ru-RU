---
title: Автоматическое изучение угроз и реагирование на них в Office 365
keywords: ВОЗДУШный, Аутоир, ATP, автоматизированный, исследование, ответ, исправление, угрозы, усовершенствованный, угроза, защита
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 11/15/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Приступите к работе с автоматизированными возможностями реагирования на инциденты в Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 13f7e95829b8cf3adf17a40cf7b02c5322b15ea7
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673425"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a><span data-ttu-id="3b04f-104">Автоматическое изучение угроз и реагирование на них в Office 365</span><span class="sxs-lookup"><span data-stu-id="3b04f-104">Automatically investigate and respond to threats in Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="3b04f-105">Обзор</span><span class="sxs-lookup"><span data-stu-id="3b04f-105">Overview</span></span>

<span data-ttu-id="3b04f-106">В зависимости от вашей подписки [Office 365 Advanced Threat protection](office-365-atp.md) может включать автоматизированные возможности реагирования на инциденты, которые могут сэкономить время и усилия группы управления безопасностью при работе с оповещениями и угрозами.</span><span class="sxs-lookup"><span data-stu-id="3b04f-106">Depending on your subscription, [Office 365 Advanced Threat Protection](office-365-atp.md) can include automated incident response (AIR) capabilities that can save your security operations team time and effort in dealing with alerts and threats.</span></span>

- <span data-ttu-id="3b04f-107">Чтобы приступить к работе с возможностями AIR в Office 365, используйте эту статью.</span><span class="sxs-lookup"><span data-stu-id="3b04f-107">To get started using AIR capabilities in Office 365, use this article.</span></span> 
- <span data-ttu-id="3b04f-108">Чтобы узнать, как работает воздух, ознакомьтесь со статьей [автоматизированного реагирования на инциденты (AIR) в Office 365](automated-investigation-response-office.md).</span><span class="sxs-lookup"><span data-stu-id="3b04f-108">To get an overview of how AIR works, see [Automated incident response (AIR) in Office 365](automated-investigation-response-office.md).</span></span>

<span data-ttu-id="3b04f-109">В среде AIR при запуске определенных оповещений запускается один или несколько "Playbooks" безопасности, и начинается автоматическое исследование.</span><span class="sxs-lookup"><span data-stu-id="3b04f-109">With AIR, when certain alerts are triggered, one or more security playbooks initiate, and automated investigation begins.</span></span> <span data-ttu-id="3b04f-110">Во время и после автоматического исследования администраторы и группы управления безопасностью могут выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3b04f-110">During and after an automated investigation process, your administrators and security operations team can:</span></span>

- [<span data-ttu-id="3b04f-111">Просмотр сведений о расследовании</span><span class="sxs-lookup"><span data-stu-id="3b04f-111">View the details of an investigation</span></span>](#view-details-of-an-investigation)
- [<span data-ttu-id="3b04f-112">Просмотр и утверждение действий в результате расследования</span><span class="sxs-lookup"><span data-stu-id="3b04f-112">Review and approve actions as a result of an investigation</span></span>](#review-and-approve-actions) 
- [<span data-ttu-id="3b04f-113">Просмотр сведений о предупреждении, связанных с исследованием</span><span class="sxs-lookup"><span data-stu-id="3b04f-113">View details about an alert related to an investigation</span></span>](#view-details-about-an-alert-related-to-an-investigation)

> [!NOTE]
> <span data-ttu-id="3b04f-114">Для выполнения задач, описанных в этой статье, необходимы соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="3b04f-114">You must have appropriate permissions to perform the tasks described in this article.</span></span> <span data-ttu-id="3b04f-115">Например, вы Мист быть глобальным администратором, администратором безопасности, оператором безопасности или средством чтения безопасности.</span><span class="sxs-lookup"><span data-stu-id="3b04f-115">For example, you myst be a global administrator, security administrator, security operator, or security reader.</span></span> <span data-ttu-id="3b04f-116">[Дополнительные сведения о ролях и разрешениях центра безопасности Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span><span class="sxs-lookup"><span data-stu-id="3b04f-116">[Learn more about Microsoft 365 security center roles and permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

<span data-ttu-id="3b04f-117">ВОЗДУХ включен в следующие подписки:</span><span class="sxs-lookup"><span data-stu-id="3b04f-117">AIR is included in the following subscriptions:</span></span>
- <span data-ttu-id="3b04f-118">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="3b04f-118">Microsoft 365 E5</span></span>
- <span data-ttu-id="3b04f-119">Безопасность Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="3b04f-119">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="3b04f-120">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="3b04f-120">Office 365 E5</span></span>
- <span data-ttu-id="3b04f-121">Office 365 Advanced Threat Protection (план 2)</span><span class="sxs-lookup"><span data-stu-id="3b04f-121">Office 365 Advanced Threat Protection Plan 2</span></span>

<span data-ttu-id="3b04f-122">Если у вас нет одной из этих подписок, [запустите бесплатную пробную версию](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="3b04f-122">If you don't have one of these subscriptions, [start a free trial](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="3b04f-123">Просмотр сведений о расследовании</span><span class="sxs-lookup"><span data-stu-id="3b04f-123">View details of an investigation</span></span>

1. <span data-ttu-id="3b04f-124">Как глобальный администратор Office 365, администратор безопасности или средство чтения безопасности, перейдите на [https://protection.office.com](https://protection.office.com) страницу и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="3b04f-124">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="3b04f-125">Откроется Центр безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="3b04f-125">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="3b04f-126">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="3b04f-126">Do one of the following:</span></span>

    - <span data-ttu-id="3b04f-127">Перейдите на > **панель мониторинга** **управления угрозами**.</span><span class="sxs-lookup"><span data-stu-id="3b04f-127">Go to **Threat management** > **Dashboard**.</span></span> <span data-ttu-id="3b04f-128">Откроется [панель мониторинга безопасности](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="3b04f-128">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="3b04f-129">Мини – приложение AIR отображается в верхней части [панели мониторинга безопасности](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="3b04f-129">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="3b04f-130">Выберите мини-приложение, например " **Сводка по расследованию**".</span><span class="sxs-lookup"><span data-stu-id="3b04f-130">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="3b04f-131">Перейдите на страницу > **расследования**по **управлению угрозами**.</span><span class="sxs-lookup"><span data-stu-id="3b04f-131">Go to **Threat management** > **Investigations**.</span></span> 

    <span data-ttu-id="3b04f-132">Любой из способов переводит вас в список расследования.</span><span class="sxs-lookup"><span data-stu-id="3b04f-132">Either method takes you to a list of investigations.</span></span>

    ![Страница основного исследования для воздуха](../media/air-maininvestigationpage.png) 

3. <span data-ttu-id="3b04f-134">В списке исследований выберите элемент в столбце **идентификатор** .</span><span class="sxs-lookup"><span data-stu-id="3b04f-134">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="3b04f-135">Откроется страница "сведения о расследовании", начиная с диаграммы "исследование" в представлении.</span><span class="sxs-lookup"><span data-stu-id="3b04f-135">This opens investigation details page, starting with the investigation graph in view.</span></span>

    ![Страница графа расследования воздуха](../media/air-investigationgraphpage.png)

4. <span data-ttu-id="3b04f-137">Используйте различные вкладки, чтобы узнать больше о расследовании.</span><span class="sxs-lookup"><span data-stu-id="3b04f-137">Use the various tabs to learn more about the investigation.</span></span>

## <a name="review-and-approve-actions"></a><span data-ttu-id="3b04f-138">Просмотр и утверждение действий</span><span class="sxs-lookup"><span data-stu-id="3b04f-138">Review and approve actions</span></span>

<span data-ttu-id="3b04f-139">В Office 365 автоматизированное расследования обычно приводит к одному или нескольким рекомендуемым действиям.</span><span class="sxs-lookup"><span data-stu-id="3b04f-139">In Office 365, automated investigations typically result in one or more recommended actions.</span></span> <span data-ttu-id="3b04f-140">Тем не менее никакие действия не выполняются до тех пор, пока не будут утверждены Группой действий по обеспечению безопасности.</span><span class="sxs-lookup"><span data-stu-id="3b04f-140">However, no actions are taken until they are approved by your security operations team.</span></span> <span data-ttu-id="3b04f-141">Используйте следующую процедуру для просмотра и утверждения действий.</span><span class="sxs-lookup"><span data-stu-id="3b04f-141">Use the following procedure to review and approve actions.</span></span>

1. <span data-ttu-id="3b04f-142">Как глобальный администратор Office 365, администратор безопасности или средство чтения безопасности, перейдите на [https://protection.office.com](https://protection.office.com) страницу и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="3b04f-142">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> 

2. <span data-ttu-id="3b04f-143">Перейдите на страницу > **расследования**по **управлению угрозами**.</span><span class="sxs-lookup"><span data-stu-id="3b04f-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="3b04f-144">В списке исследований выберите элемент в столбце **идентификатор** .</span><span class="sxs-lookup"><span data-stu-id="3b04f-144">In the list of investigations, select an item in the **ID** column.</span></span> 

3. <span data-ttu-id="3b04f-145">В представлении сведения об расследовании перейдите на вкладку **действия** . Здесь перечислены все действия, ожидающие утверждения.</span><span class="sxs-lookup"><span data-stu-id="3b04f-145">On the investigation details view, select the **Actions** tab. Any actions that are pending approval are listed here.</span></span>

4. <span data-ttu-id="3b04f-146">Выберите элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="3b04f-146">Select an item in the list.</span></span>

5. <span data-ttu-id="3b04f-147">Выберите **утвердить** , чтобы выполнить рекомендуемое действие (или **отклонить** , чтобы закрыть исследование без принятия действия).</span><span class="sxs-lookup"><span data-stu-id="3b04f-147">Select **Approve** to take the recommended action (or **Reject** to close the investigation without taking action).</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="3b04f-148">Просмотр сведений о предупреждении, связанных с исследованием</span><span class="sxs-lookup"><span data-stu-id="3b04f-148">View details about an alert related to an investigation</span></span>

<span data-ttu-id="3b04f-149">Определенные виды оповещений инициируют автоматическое исследование в Office 365.</span><span class="sxs-lookup"><span data-stu-id="3b04f-149">Certain kinds of alerts trigger automated investigation in Office 365.</span></span> <span data-ttu-id="3b04f-150">Чтобы узнать больше, ознакомьтесь со статьей [оповещения](automated-investigation-response-office.md#alerts).</span><span class="sxs-lookup"><span data-stu-id="3b04f-150">To learn more, see [Alerts](automated-investigation-response-office.md#alerts).</span></span> <span data-ttu-id="3b04f-151">Используйте следующую процедуру для просмотра подробных сведений об оповещении, связанных с автоматическим исследованием.</span><span class="sxs-lookup"><span data-stu-id="3b04f-151">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="3b04f-152">Как глобальный администратор Office 365, администратор безопасности или средство чтения безопасности, перейдите на [https://protection.office.com](https://protection.office.com) страницу и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="3b04f-152">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="3b04f-153">Откроется Центр безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="3b04f-153">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="3b04f-154">Перейдите на страницу > **расследования**по **управлению угрозами**.</span><span class="sxs-lookup"><span data-stu-id="3b04f-154">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="3b04f-155">В списке исследований выберите элемент в столбце **идентификатор** .</span><span class="sxs-lookup"><span data-stu-id="3b04f-155">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="3b04f-156">С подробностями открытого исследования перейдите на вкладку **оповещения** . Здесь перечислены все оповещения, которые запускаются в ходе расследования.</span><span class="sxs-lookup"><span data-stu-id="3b04f-156">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="3b04f-157">Выберите элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="3b04f-157">Select an item in the list.</span></span> <span data-ttu-id="3b04f-158">Откроется раскрывающееся меню со сведениями об оповещении и ссылками на дополнительные сведения и действия.</span><span class="sxs-lookup"><span data-stu-id="3b04f-158">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="3b04f-159">Просмотрите сведения в всплывающем меню и, в зависимости от конкретного оповещения, выполните действие, например " **Разрешить**", " **запретить**" или " **уведомить пользователей**".</span><span class="sxs-lookup"><span data-stu-id="3b04f-159">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span> 

    - <span data-ttu-id="3b04f-160">**Устранение проблемы** эквивалентно закрытию оповещения</span><span class="sxs-lookup"><span data-stu-id="3b04f-160">**Resolve** is equivalent to closing an alert</span></span>
    
    - <span data-ttu-id="3b04f-161">**Подавлять** указывает, что политика не запускает оповещения в течение указанного периода времени.</span><span class="sxs-lookup"><span data-stu-id="3b04f-161">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>
    
    - <span data-ttu-id="3b04f-162">**Уведомлять пользователи** запускают электронное письмо с уже введенными адресами электронной почты пользователей, а также позволяет группе "Управление операциями безопасности" ввести сообщение для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="3b04f-162">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="3b04f-163">(Это похоже на отправку сообщения получателям с помощью [обозревателя угроз](threat-explorer.md).)</span><span class="sxs-lookup"><span data-stu-id="3b04f-163">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="3b04f-164">Использование API действий управления Office 365 для настраиваемых и сторонних решений для создания отчетов</span><span class="sxs-lookup"><span data-stu-id="3b04f-164">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="3b04f-165">Если в организации используется пользовательское или стороннее решение для создания отчетов, можно просмотреть сведения об автоматическом расследовании в этом решении с помощью API действий управления Office 365.</span><span class="sxs-lookup"><span data-stu-id="3b04f-165">If your organization is using a custom or third-party reporting solution, you can view information about automated investigations in that solution by using the Office 365 Management Activity API.</span></span>

<span data-ttu-id="3b04f-166">Используйте следующие ресурсы для настройки:</span><span class="sxs-lookup"><span data-stu-id="3b04f-166">Use the following resources to set this up:</span></span>

|<span data-ttu-id="3b04f-167">Ресурс</span><span class="sxs-lookup"><span data-stu-id="3b04f-167">Resource</span></span>  |<span data-ttu-id="3b04f-168">Описание</span><span class="sxs-lookup"><span data-stu-id="3b04f-168">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="3b04f-169">Обзор API управления Office 365</span><span class="sxs-lookup"><span data-stu-id="3b04f-169">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="3b04f-170">API действий управления Office 365 обеспечивает получение информации о различных действиях и событиях, касающихся пользователей, администраторов, систем и политик, из отчетов о действиях касательно Office 365 и Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3b04f-170">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="3b04f-171">Начало работы с API управления Office 365</span><span class="sxs-lookup"><span data-stu-id="3b04f-171">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="3b04f-172">API управления Office 365 использует Azure AD для предоставления служб проверки подлинности приложениям доступа к данным Office 365.</span><span class="sxs-lookup"><span data-stu-id="3b04f-172">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="3b04f-173">Выполните действия, описанные в этой статье, чтобы настроить ее.</span><span class="sxs-lookup"><span data-stu-id="3b04f-173">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="3b04f-174">Справочник по API действий управления Office 365</span><span class="sxs-lookup"><span data-stu-id="3b04f-174">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="3b04f-175">Вы можете использовать API действий управления Office 365, чтобы получить сведения о действиях пользователя, администратора, системы, а также о событиях и политиках из журналов активности Office 365 и Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3b04f-175">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="3b04f-176">Прочтите эту статью, чтобы узнать больше о том, как это работает.</span><span class="sxs-lookup"><span data-stu-id="3b04f-176">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="3b04f-177">Схема API действий управления Office 365</span><span class="sxs-lookup"><span data-stu-id="3b04f-177">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="3b04f-178">В этой статье представлены общие сведения о конкретных типах данных, доступных через API действий управления Office 365, а также сведения о том, как ознакомиться с [общими схемами](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) и сведениями об [анализе и ответе на Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) .</span><span class="sxs-lookup"><span data-stu-id="3b04f-178">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="next-steps"></a><span data-ttu-id="3b04f-179">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="3b04f-179">Next steps</span></span>

[<span data-ttu-id="3b04f-180">Дополнительные сведения об оповещениях</span><span class="sxs-lookup"><span data-stu-id="3b04f-180">Learn more about alerts</span></span>](../../compliance/alert-policies.md)

[<span data-ttu-id="3b04f-181">Поиск и исследование вредоносных сообщений электронной почты, доставляемых в Office 365, вручную</span><span class="sxs-lookup"><span data-stu-id="3b04f-181">Manually find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

[<span data-ttu-id="3b04f-182">Сведения о воздухе воздуха в защитнике Майкрософт для ATP</span><span class="sxs-lookup"><span data-stu-id="3b04f-182">Learn about AIR in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

[<span data-ttu-id="3b04f-183">Посетите план Microsoft 365, чтобы узнать, что скоро ожидается и как выполняется развертывание.</span><span class="sxs-lookup"><span data-stu-id="3b04f-183">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)