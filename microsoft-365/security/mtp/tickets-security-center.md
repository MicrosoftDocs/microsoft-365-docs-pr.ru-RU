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
ms.openlocfilehash: 16ee37b1c7bf33c902db35af2d29744f42830ea7
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094838"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a><span data-ttu-id="bad23-104">Создание и отслеживание билетов для ServiceNow в центре безопасности Майкрософт 365</span><span class="sxs-lookup"><span data-stu-id="bad23-104">Create and track ServiceNow tickets in the Microsoft 365 security center</span></span>

<span data-ttu-id="bad23-105">[Центр безопасности Microsoft 365](overview-security-center.md) был усовершенствован благодаря возможности создавать и отслеживать билеты в ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="bad23-105">The [Microsoft 365 security center](overview-security-center.md) has been enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> [<span data-ttu-id="bad23-106">Дополнительные сведения о ServiceNow</span><span class="sxs-lookup"><span data-stu-id="bad23-106">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="bad23-107">В центре безопасности Администраторы безопасности могут отправить действие улучшения [оценки безопасности Майкрософт](microsoft-secure-score.md) непосредственно в ServiceNow и создать билет.</span><span class="sxs-lookup"><span data-stu-id="bad23-107">In the security center, security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="bad23-108">Могут быть созданы как управление инцидентами, так и билеты управления изменениями.</span><span class="sxs-lookup"><span data-stu-id="bad23-108">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="bad23-109">Затем они могут быть записаны на домашней странице центра безопасности и ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="bad23-109">They can then be tracked in the security center home page, and ServiceNow.</span></span>

- [<span data-ttu-id="bad23-110">**Сведения о предварительных требованиях, обмене данными и устранению неполадок**</span><span class="sxs-lookup"><span data-stu-id="bad23-110">**Learn about prerequisites, data exchange, and troubleshooting**</span></span>](tickets.md)
- <span data-ttu-id="bad23-111">**Управление билетами ServiceNow в центре соответствия требованиям** (ожидается в ближайшее время)</span><span class="sxs-lookup"><span data-stu-id="bad23-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="bad23-112">Подключение центра безопасности Microsoft 365 к ServiceNow</span><span class="sxs-lookup"><span data-stu-id="bad23-112">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="bad23-113">Перейдите на домашнюю страницу центра безопасности Microsoft 365, чтобы просмотреть карточку подключения ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="bad23-113">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![Использование ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="bad23-115">Выберите "подключиться к ServiceNow", чтобы перейти на страницу установки ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="bad23-115">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="bad23-116">Следуйте инструкциям для авторизации приложения Microsoft 365 Connector.</span><span class="sxs-lookup"><span data-stu-id="bad23-116">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="bad23-117">Прежде чем выполнять авторизацию подключения между центром безопасности Microsoft 365 и ServiceNow, убедитесь, что вы используете имя входа и пароль пользователя интеграции, которые вы создали в шагах установки.</span><span class="sxs-lookup"><span data-stu-id="bad23-117">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="bad23-118">Не используйте свои личные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="bad23-118">Do not use your personal credentials.</span></span>

<span data-ttu-id="bad23-119">После выполнения инструкций и авторизации подключения просмотрите состояние подключения на странице Подключение к центру безопасности Microsoft 365 и в интерфейсе приложения ServiceNow Microsoft 365 с помощью соединителя.</span><span class="sxs-lookup"><span data-stu-id="bad23-119">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="bad23-120">Теперь все готово для начала создания задач.</span><span class="sxs-lookup"><span data-stu-id="bad23-120">Now you are all set to start creating tasks!</span></span>

### <a name="troubleshooting"></a><span data-ttu-id="bad23-121">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="bad23-121">Troubleshooting</span></span>

<span data-ttu-id="bad23-122">Узнайте о распространенных ошибках, которые могут возникнуть в процессе подключения, и о том, как их устранить в [разделе Устранение неполадок](tickets.md#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="bad23-122">Learn common errors you may encounter in the connection process, and how to mitigate them, in the [troubleshooting section](tickets.md#troubleshooting).</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="bad23-123">Создание задачи и общий доступ к ней в ServiceNow</span><span class="sxs-lookup"><span data-stu-id="bad23-123">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="bad23-124">После настройки интеграции Создайте задачи ServiceNow на основе определенных действий по улучшению [оценки безопасности Майкрософт](microsoft-secure-score.md) .</span><span class="sxs-lookup"><span data-stu-id="bad23-124">Once the integration is set up, create ServiceNow tasks based on specific [Microsoft Secure Score](microsoft-secure-score.md) improvement actions.</span></span> <span data-ttu-id="bad23-125">Перейдите к любому действию улучшения в поле Оценка безопасности на портале Центра безопасности Microsoft 365 и выберите **общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="bad23-125">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select **Share**.</span></span> <span data-ttu-id="bad23-126">Один из вариантов раскрывающегося списка — ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="bad23-126">One of the dropdown options is ServiceNow.</span></span>

<span data-ttu-id="bad23-127">Создается задача, в которой можно задать приоритет и изменить имя, описание или срок выполнения.</span><span class="sxs-lookup"><span data-stu-id="bad23-127">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="bad23-128">После заполнения всех обязательных полей отправьте задачу в ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="bad23-128">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="bad23-129">Эта задача отображается в ServiceNow как запрос на изменение безопасности и конфигурации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bad23-129">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="bad23-130">Отслеживание билетов</span><span class="sxs-lookup"><span data-stu-id="bad23-130">Track tickets</span></span>

<span data-ttu-id="bad23-131">После создания билетов управления изменениями и управления инцидентами, они отображаются в карточках на домашней странице центра безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bad23-131">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="bad23-132">Из этих карточек вы можете создать билет, просмотреть все билеты или управлять конфигурацией ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="bad23-132">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![Билеты управления изменениями ServiceNow](../../media/change-management-375.png)  ![Билеты управления инцидентами ServiceNow](../../media/incident-management-375.png)

<span data-ttu-id="bad23-135">Чтобы повторно подготовить или управлять интеграцией ServiceNow в центре безопасности Майкрософт 365, выберите **Управление конфигурацией servicenow** на любой из карточек.</span><span class="sxs-lookup"><span data-stu-id="bad23-135">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="bad23-136">После этого удалите текущие подключения ServiceNow и настройте имена состояний билетов.</span><span class="sxs-lookup"><span data-stu-id="bad23-136">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="bad23-137">С билетами ServiceNow, которые отображаются в центре безопасности Майкрософт 365, ваши задачи находятся в том месте, где они могут отслеживаться и обрабатываться вместе с другими элементами панели мониторинга безопасности.</span><span class="sxs-lookup"><span data-stu-id="bad23-137">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="resources"></a><span data-ttu-id="bad23-138">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="bad23-138">Resources</span></span>

- [<span data-ttu-id="bad23-139">Сведения о предварительных требованиях, обмене данными и устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="bad23-139">Learn about prerequisites, data exchange, and troubleshooting</span></span>](tickets.md)
- [<span data-ttu-id="bad23-140">Оценка безопасности (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="bad23-140">Microsoft Secure Score</span></span>](microsoft-secure-score.md)