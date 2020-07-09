---
title: Создание и отслеживание билетов для ServiceNow в центре безопасности Майкрософт 365
description: Узнайте, как создавать и отслеживать билеты в ServiceNow из центра безопасности Майкрософт 365.
keywords: безопасность, Microsoft 365, M365, Оценка безопасности, центр безопасности, ServiceNow, билеты, задачи
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 48512cf2fff802509ebaa14ca69d3ca02908902e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "45087937"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a><span data-ttu-id="ca37b-104">Создание и отслеживание билетов для ServiceNow в центре безопасности Майкрософт 365</span><span class="sxs-lookup"><span data-stu-id="ca37b-104">Create and track ServiceNow tickets in the Microsoft 365 security center</span></span>

<span data-ttu-id="ca37b-105">[Центр безопасности Microsoft 365](overview-security-center.md) был усовершенствован благодаря возможности создавать и отслеживать билеты в ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="ca37b-105">The [Microsoft 365 security center](overview-security-center.md) has been enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> [<span data-ttu-id="ca37b-106">Дополнительные сведения о ServiceNow</span><span class="sxs-lookup"><span data-stu-id="ca37b-106">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="ca37b-107">В центре безопасности Администраторы безопасности могут отправить действие улучшения [оценки безопасности Майкрософт](microsoft-secure-score.md) непосредственно в ServiceNow и создать билет.</span><span class="sxs-lookup"><span data-stu-id="ca37b-107">In the security center, security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="ca37b-108">Могут быть созданы как управление инцидентами, так и билеты управления изменениями.</span><span class="sxs-lookup"><span data-stu-id="ca37b-108">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="ca37b-109">Затем они могут быть записаны на домашней странице центра безопасности и ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="ca37b-109">They can then be tracked in the security center home page, and ServiceNow.</span></span>

- [<span data-ttu-id="ca37b-110">**Сведения о предварительных требованиях, обмене данными и устранению неполадок**</span><span class="sxs-lookup"><span data-stu-id="ca37b-110">**Learn about prerequisites, data exchange, and troubleshooting**</span></span>](tickets.md)
- <span data-ttu-id="ca37b-111">**Управление билетами ServiceNow в центре соответствия требованиям** (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="ca37b-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="ca37b-112">Подключение центра безопасности Microsoft 365 к ServiceNow</span><span class="sxs-lookup"><span data-stu-id="ca37b-112">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="ca37b-113">Перейдите на домашнюю страницу центра безопасности Microsoft 365, чтобы просмотреть карточку подключения ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="ca37b-113">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![Использование ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="ca37b-115">Выберите "подключиться к ServiceNow", чтобы перейти на страницу установки ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="ca37b-115">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="ca37b-116">Следуйте инструкциям для авторизации приложения Microsoft 365 Connector.</span><span class="sxs-lookup"><span data-stu-id="ca37b-116">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="ca37b-117">Прежде чем выполнять авторизацию подключения между центром безопасности Microsoft 365 и ServiceNow, убедитесь, что вы используете имя входа и пароль пользователя интеграции, которые вы создали в шагах установки.</span><span class="sxs-lookup"><span data-stu-id="ca37b-117">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="ca37b-118">Не используйте свои личные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="ca37b-118">Do not use your personal credentials.</span></span>

<span data-ttu-id="ca37b-119">После выполнения инструкций и авторизации подключения просмотрите состояние подключения на странице Подключение к центру безопасности Microsoft 365 и в интерфейсе приложения ServiceNow Microsoft 365 с помощью соединителя.</span><span class="sxs-lookup"><span data-stu-id="ca37b-119">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="ca37b-120">Теперь все готово для начала создания задач.</span><span class="sxs-lookup"><span data-stu-id="ca37b-120">Now you are all set to start creating tasks!</span></span>

### <a name="troubleshooting"></a><span data-ttu-id="ca37b-121">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="ca37b-121">Troubleshooting</span></span>

<span data-ttu-id="ca37b-122">Узнайте о распространенных ошибках, которые могут возникнуть в процессе подключения, и о том, как их устранить в [разделе Устранение неполадок](tickets.md#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="ca37b-122">Learn common errors you may encounter in the connection process, and how to mitigate them, in the [troubleshooting section](tickets.md#troubleshooting).</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="ca37b-123">Создание задачи и общий доступ к ней в ServiceNow</span><span class="sxs-lookup"><span data-stu-id="ca37b-123">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="ca37b-124">После настройки интеграции Создайте задачи ServiceNow на основе определенных действий по улучшению оценки безопасности Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ca37b-124">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="ca37b-125">Перейдите к любому действию улучшения в поле Оценка безопасности на портале Центра безопасности Microsoft 365 и выберите значок "общий доступ".</span><span class="sxs-lookup"><span data-stu-id="ca37b-125">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the "share" icon.</span></span> <span data-ttu-id="ca37b-126">Один из вариантов раскрывающегося списка — ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="ca37b-126">One of the dropdown options is ServiceNow.</span></span>

![Общий доступ к файлам ServiceNow в безопасной оценке](../../media/servicenow-share.png)

<span data-ttu-id="ca37b-128">Создается задача, в которой можно задать приоритет и изменить имя, описание или срок выполнения.</span><span class="sxs-lookup"><span data-stu-id="ca37b-128">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="ca37b-129">После заполнения всех обязательных полей отправьте задачу в ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="ca37b-129">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="ca37b-130">Эта задача отображается в ServiceNow как запрос на изменение безопасности и конфигурации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ca37b-130">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="ca37b-131">Отслеживание билетов</span><span class="sxs-lookup"><span data-stu-id="ca37b-131">Track tickets</span></span>

<span data-ttu-id="ca37b-132">После создания билетов управления изменениями и управления инцидентами, они отображаются в карточках на домашней странице центра безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ca37b-132">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="ca37b-133">Из этих карточек вы можете создать билет, просмотреть все билеты или управлять конфигурацией ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="ca37b-133">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![Билеты управления изменениями ServiceNow](../../media/change-management-375.png)  ![Билеты управления инцидентами ServiceNow](../../media/incident-management-375.png)

<span data-ttu-id="ca37b-136">Чтобы повторно подготовить или управлять интеграцией ServiceNow в центре безопасности Майкрософт 365, выберите **Управление конфигурацией servicenow** на любой из карточек.</span><span class="sxs-lookup"><span data-stu-id="ca37b-136">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="ca37b-137">После этого удалите текущие подключения ServiceNow и настройте имена состояний билетов.</span><span class="sxs-lookup"><span data-stu-id="ca37b-137">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="ca37b-138">С билетами ServiceNow, которые отображаются в центре безопасности Майкрософт 365, ваши задачи находятся в том месте, где они могут отслеживаться и обрабатываться вместе с другими элементами панели мониторинга безопасности.</span><span class="sxs-lookup"><span data-stu-id="ca37b-138">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="resources"></a><span data-ttu-id="ca37b-139">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="ca37b-139">Resources</span></span>

- [<span data-ttu-id="ca37b-140">Сведения о предварительных требованиях, обмене данными и устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="ca37b-140">Learn about prerequisites, data exchange, and troubleshooting</span></span>](tickets.md)
- [<span data-ttu-id="ca37b-141">Оценка безопасности (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="ca37b-141">Microsoft Secure Score</span></span>](microsoft-secure-score.md)