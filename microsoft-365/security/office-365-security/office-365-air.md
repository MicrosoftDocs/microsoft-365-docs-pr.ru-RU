---
title: Автоматическое изучение угроз и реагирование на них в Office 365
keywords: ВОЗДУШный, Аутоир, ATP, автоматизированный, исследование, ответ, исправление, угрозы, усовершенствованный, угроза, защита
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Приступите к работе с автоматизированным исследованием и возможностями реагирования в Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 9c17d7219e5dd15404b171fbd6707d00fd788f19
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598766"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a><span data-ttu-id="cb2ba-104">Автоматическое изучение угроз и реагирование на них в Office 365</span><span class="sxs-lookup"><span data-stu-id="cb2ba-104">Automatically investigate and respond to threats in Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="cb2ba-105">Обзор</span><span class="sxs-lookup"><span data-stu-id="cb2ba-105">Overview</span></span>

<span data-ttu-id="cb2ba-106">В зависимости от вашей подписки [Office 365 Advanced Threat protection](office-365-atp.md) может включать возможности автоматизированного расследования и реагирования (AIR), которые могут сэкономить время и усилия группы управления безопасностью при работе с оповещениями и угрозами.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-106">Depending on your subscription, [Office 365 Advanced Threat Protection](office-365-atp.md) can include automated investigation and response (AIR) capabilities that can save your security operations team time and effort in dealing with alerts and threats.</span></span>

- <span data-ttu-id="cb2ba-107">Чтобы приступить к работе с автоматизированным исследованием и функциями реагирования в Office 365, используйте эту статью.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-107">To get started using automated investigation and response capabilities in Office 365, use this article.</span></span> 
- <span data-ttu-id="cb2ba-108">Чтобы узнать, как это работает, обратитесь к разделу [Автоматическое исследование и ответ в Office 365](automated-investigation-response-office.md).</span><span class="sxs-lookup"><span data-stu-id="cb2ba-108">To get an overview of how it works, see [Automated investigation and response in Office 365](automated-investigation-response-office.md).</span></span>

> [!TIP]
> <span data-ttu-id="cb2ba-109">У вас есть Microsoft 365 E5 или Microsoft 365 E3 с управлением учетными записями и защитой от угроз?</span><span class="sxs-lookup"><span data-stu-id="cb2ba-109">Do you have Microsoft 365 E5 or Microsoft 365 E3 together with Identity & Threat Protection?</span></span> <span data-ttu-id="cb2ba-110">Рекомендуется использовать [Автоматическое исследование и реагирование (AIR) в Microsoft Threat protection](../mtp/mtp-autoir.md).</span><span class="sxs-lookup"><span data-stu-id="cb2ba-110">Consider trying [Automated investigation and response (AIR) in Microsoft Threat Protection](../mtp/mtp-autoir.md).</span></span>

<span data-ttu-id="cb2ba-111">При автоматическом расследовании и возможностях реагирования, когда инициируются определенные оповещения, инициируется один или несколько "Playbooks" безопасности, и начинается процесс автоматического исследования.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-111">With automated investigation and response capabilities, when certain alerts are triggered, one or more security playbooks initiate, and the automated investigation process begins.</span></span> <span data-ttu-id="cb2ba-112">Во время и после автоматического исследования группа безопасности может выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="cb2ba-112">During and after an automated investigation process, your security team can do the following:</span></span>

- [<span data-ttu-id="cb2ba-113">Просмотр сведений о расследовании</span><span class="sxs-lookup"><span data-stu-id="cb2ba-113">View the details of an investigation</span></span>](#view-details-of-an-investigation)
- [<span data-ttu-id="cb2ba-114">Просмотр и утверждение действий в результате расследования</span><span class="sxs-lookup"><span data-stu-id="cb2ba-114">Review and approve actions as a result of an investigation</span></span>](#review-and-approve-actions) 
- [<span data-ttu-id="cb2ba-115">Просмотр сведений о предупреждении, связанных с исследованием</span><span class="sxs-lookup"><span data-stu-id="cb2ba-115">View details about an alert related to an investigation</span></span>](#view-details-about-an-alert-related-to-an-investigation)

> [!IMPORTANT]
> <span data-ttu-id="cb2ba-116">Для выполнения задач, описанных в этой статье, необходимы соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-116">To perform the tasks described in this article, you must have appropriate permissions assigned.</span></span> <span data-ttu-id="cb2ba-117">Ознакомьтесь [с разрешениями, необходимыми для использования возможностей Air](automated-investigation-response-office.md#required-permissions-to-use-air-capabilities).</span><span class="sxs-lookup"><span data-stu-id="cb2ba-117">See [required permissions to use AIR capabilities](automated-investigation-response-office.md#required-permissions-to-use-air-capabilities).</span></span>

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="cb2ba-118">Просмотр сведений о расследовании</span><span class="sxs-lookup"><span data-stu-id="cb2ba-118">View details of an investigation</span></span>

1. <span data-ttu-id="cb2ba-119">Перейдите на страницу [https://protection.office.com](https://protection.office.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-119">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="cb2ba-120">Откроется Центр безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-120">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="cb2ba-121">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-121">Do one of the following:</span></span>

    - <span data-ttu-id="cb2ba-122">Перейдите на > **панель мониторинга** **управления угрозами**.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-122">Go to **Threat management** > **Dashboard**.</span></span> <span data-ttu-id="cb2ba-123">Откроется [панель мониторинга безопасности](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="cb2ba-123">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="cb2ba-124">Мини – приложение AIR отображается в верхней части [панели мониторинга безопасности](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="cb2ba-124">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="cb2ba-125">Выберите мини-приложение, например " **Сводка по расследованию**".</span><span class="sxs-lookup"><span data-stu-id="cb2ba-125">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="cb2ba-126">Перейдите на страницу > **расследования**по **управлению угрозами**.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-126">Go to **Threat management** > **Investigations**.</span></span> 

    <span data-ttu-id="cb2ba-127">Любой из способов переводит вас в список расследования.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-127">Either method takes you to a list of investigations.</span></span>

    ![Страница основного исследования для воздуха](../media/air-maininvestigationpage.png) 

3. <span data-ttu-id="cb2ba-129">В списке исследований выберите элемент в столбце **идентификатор** .</span><span class="sxs-lookup"><span data-stu-id="cb2ba-129">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="cb2ba-130">Откроется страница "сведения о расследовании", начиная с диаграммы "исследование" в представлении.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-130">This opens investigation details page, starting with the investigation graph in view.</span></span>

    ![Страница графа расследования воздуха](../media/air-investigationgraphpage.png)

4. <span data-ttu-id="cb2ba-132">Используйте различные вкладки, чтобы узнать больше о расследовании.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-132">Use the various tabs to learn more about the investigation.</span></span>

## <a name="review-and-approve-actions"></a><span data-ttu-id="cb2ba-133">Просмотр и утверждение действий</span><span class="sxs-lookup"><span data-stu-id="cb2ba-133">Review and approve actions</span></span>

<span data-ttu-id="cb2ba-134">В Office 365 автоматизированное расследования обычно приводит к одному или нескольким рекомендуемым действиям.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-134">In Office 365, automated investigations typically result in one or more recommended actions.</span></span> <span data-ttu-id="cb2ba-135">Тем не менее никакие действия не выполняются до тех пор, пока не будут утверждены Группой действий по обеспечению безопасности.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-135">However, no actions are taken until they are approved by your security operations team.</span></span> <span data-ttu-id="cb2ba-136">Используйте следующую процедуру для просмотра и утверждения действий.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-136">Use the following procedure to review and approve actions.</span></span>

1. <span data-ttu-id="cb2ba-137">Перейдите на страницу [https://protection.office.com](https://protection.office.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-137">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> 

2. <span data-ttu-id="cb2ba-138">Перейдите на страницу > **расследования**по **управлению угрозами**.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-138">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="cb2ba-139">В списке исследований выберите элемент в столбце **идентификатор** .</span><span class="sxs-lookup"><span data-stu-id="cb2ba-139">In the list of investigations, select an item in the **ID** column.</span></span> 

3. <span data-ttu-id="cb2ba-140">В представлении сведения об расследовании перейдите на вкладку **действия** . Здесь перечислены все действия, ожидающие утверждения.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-140">On the investigation details view, select the **Actions** tab. Any actions that are pending approval are listed here.</span></span>

4. <span data-ttu-id="cb2ba-141">Выберите элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-141">Select an item in the list.</span></span>

5. <span data-ttu-id="cb2ba-142">Выберите **утвердить** , чтобы выполнить рекомендуемое действие (или **отклонить** , чтобы закрыть исследование без принятия действия).</span><span class="sxs-lookup"><span data-stu-id="cb2ba-142">Select **Approve** to take the recommended action (or **Reject** to close the investigation without taking action).</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="cb2ba-143">Просмотр сведений о предупреждении, связанных с исследованием</span><span class="sxs-lookup"><span data-stu-id="cb2ba-143">View details about an alert related to an investigation</span></span>

<span data-ttu-id="cb2ba-144">Определенные виды оповещений инициируют автоматическое исследование в Office 365.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-144">Certain kinds of alerts trigger automated investigation in Office 365.</span></span> <span data-ttu-id="cb2ba-145">Чтобы узнать больше, ознакомьтесь со статьей [оповещения](automated-investigation-response-office.md#alerts).</span><span class="sxs-lookup"><span data-stu-id="cb2ba-145">To learn more, see [Alerts](automated-investigation-response-office.md#alerts).</span></span> <span data-ttu-id="cb2ba-146">Используйте следующую процедуру для просмотра подробных сведений об оповещении, связанных с автоматическим исследованием.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-146">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="cb2ba-147">Перейдите на страницу [https://protection.office.com](https://protection.office.com) и войдите.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-147">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="cb2ba-148">Откроется Центр безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-148">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="cb2ba-149">Перейдите на страницу > **расследования**по **управлению угрозами**.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-149">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="cb2ba-150">В списке исследований выберите элемент в столбце **идентификатор** .</span><span class="sxs-lookup"><span data-stu-id="cb2ba-150">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="cb2ba-151">С подробностями открытого исследования перейдите на вкладку **оповещения** . Здесь перечислены все оповещения, которые запускаются в ходе расследования.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-151">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="cb2ba-152">Выберите элемент в списке.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-152">Select an item in the list.</span></span> <span data-ttu-id="cb2ba-153">Откроется раскрывающееся меню со сведениями об оповещении и ссылками на дополнительные сведения и действия.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-153">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="cb2ba-154">Просмотрите сведения в всплывающем меню и, в зависимости от конкретного оповещения, выполните действие, например " **Разрешить**", " **запретить**" или " **уведомить пользователей**".</span><span class="sxs-lookup"><span data-stu-id="cb2ba-154">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span> 

    - <span data-ttu-id="cb2ba-155">**Устранение проблемы** эквивалентно закрытию оповещения</span><span class="sxs-lookup"><span data-stu-id="cb2ba-155">**Resolve** is equivalent to closing an alert</span></span>
    
    - <span data-ttu-id="cb2ba-156">**Подавлять** указывает, что политика не запускает оповещения в течение указанного периода времени.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-156">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>
    
    - <span data-ttu-id="cb2ba-157">**Уведомлять пользователи** запускают электронное письмо с уже введенными адресами электронной почты пользователей, а также позволяет группе "Управление операциями безопасности" ввести сообщение для этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-157">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="cb2ba-158">(Это похоже на отправку сообщения получателям с помощью [обозревателя угроз](threat-explorer.md).)</span><span class="sxs-lookup"><span data-stu-id="cb2ba-158">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="cb2ba-159">Использование API действий управления Office 365 для настраиваемых и сторонних решений для создания отчетов</span><span class="sxs-lookup"><span data-stu-id="cb2ba-159">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="cb2ba-160">Если в организации используется пользовательское или стороннее решение для создания отчетов, можно просмотреть сведения об автоматическом расследовании в этом решении с помощью API действий управления Office 365.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-160">If your organization is using a custom or third-party reporting solution, you can view information about automated investigations in that solution by using the Office 365 Management Activity API.</span></span>

<span data-ttu-id="cb2ba-161">Используйте следующие ресурсы для настройки:</span><span class="sxs-lookup"><span data-stu-id="cb2ba-161">Use the following resources to set this up:</span></span>

|<span data-ttu-id="cb2ba-162">Resource</span><span class="sxs-lookup"><span data-stu-id="cb2ba-162">Resource</span></span>  |<span data-ttu-id="cb2ba-163">Описание</span><span class="sxs-lookup"><span data-stu-id="cb2ba-163">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="cb2ba-164">Обзор API управления Office 365</span><span class="sxs-lookup"><span data-stu-id="cb2ba-164">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="cb2ba-165">API действий управления Office 365 обеспечивает получение информации о различных действиях и событиях, касающихся пользователей, администраторов, систем и политик, из отчетов о действиях касательно Office 365 и Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-165">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="cb2ba-166">Начало работы с API управления Office 365</span><span class="sxs-lookup"><span data-stu-id="cb2ba-166">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="cb2ba-167">API управления Office 365 использует Azure AD для предоставления служб проверки подлинности приложениям доступа к данным Office 365.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-167">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="cb2ba-168">Выполните действия, описанные в этой статье, чтобы настроить ее.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-168">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="cb2ba-169">Справочник по API действий управления Office 365</span><span class="sxs-lookup"><span data-stu-id="cb2ba-169">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="cb2ba-170">Вы можете использовать API действий управления Office 365, чтобы получить сведения о действиях пользователя, администратора, системы, а также о событиях и политиках из журналов активности Office 365 и Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-170">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="cb2ba-171">Прочтите эту статью, чтобы узнать больше о том, как это работает.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-171">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="cb2ba-172">Схема API действий управления Office 365</span><span class="sxs-lookup"><span data-stu-id="cb2ba-172">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="cb2ba-173">В этой статье представлены общие сведения о конкретных типах данных, доступных через API действий управления Office 365, а также сведения о том, как ознакомиться с [общими схемами](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) и сведениями об [анализе и ответе на Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) .</span><span class="sxs-lookup"><span data-stu-id="cb2ba-173">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="next-steps"></a><span data-ttu-id="cb2ba-174">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="cb2ba-174">Next steps</span></span>

- [<span data-ttu-id="cb2ba-175">Сведения о получении воздуха и просмотре необходимых разрешений</span><span class="sxs-lookup"><span data-stu-id="cb2ba-175">Find out how to get AIR and see required permissions</span></span>](automated-investigation-response-office.md#how-to-get-air)
- [<span data-ttu-id="cb2ba-176">Дополнительные сведения об оповещениях</span><span class="sxs-lookup"><span data-stu-id="cb2ba-176">Learn more about alerts</span></span>](../../compliance/alert-policies.md)
- [<span data-ttu-id="cb2ba-177">Поиск и исследование вредоносных сообщений электронной почты, доставляемых в Office 365, вручную</span><span class="sxs-lookup"><span data-stu-id="cb2ba-177">Manually find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="cb2ba-178">Сведения о воздухе воздуха в защитнике Майкрософт для ATP</span><span class="sxs-lookup"><span data-stu-id="cb2ba-178">Learn about AIR in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [<span data-ttu-id="cb2ba-179">Посетите план Microsoft 365, чтобы узнать, что скоро ожидается и как выполняется развертывание.</span><span class="sxs-lookup"><span data-stu-id="cb2ba-179">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)