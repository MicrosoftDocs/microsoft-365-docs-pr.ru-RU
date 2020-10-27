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
ms.openlocfilehash: 8992efdd79295b6b56b8f033bd97b10f59a7a4d5
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769679"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a><span data-ttu-id="e2ea7-104">Создание и отслеживание билетов для ServiceNow в центре безопасности Майкрософт 365</span><span class="sxs-lookup"><span data-stu-id="e2ea7-104">Create and track ServiceNow tickets in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
><span data-ttu-id="e2ea7-105">**Завершен период предварительной версии для соединителя ServiceNow**</span><span class="sxs-lookup"><span data-stu-id="e2ea7-105">**The preview period for the ServiceNow connector is ending**</span></span><br>
><span data-ttu-id="e2ea7-106">Эта возможность больше не будет доступна в конце ноября 2020.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-106">This capability will no longer available by the end of November 2020.</span></span> <span data-ttu-id="e2ea7-107">Благодарим вас за отзыв и продолжение поддержки, пока мы определим дальнейшие действия.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-107">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="e2ea7-108">[Центр безопасности Microsoft 365](overview-security-center.md) был усовершенствован благодаря возможности создавать и отслеживать билеты в ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-108">The [Microsoft 365 security center](overview-security-center.md) has been enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> [<span data-ttu-id="e2ea7-109">Дополнительные сведения о ServiceNow</span><span class="sxs-lookup"><span data-stu-id="e2ea7-109">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="e2ea7-110">В центре безопасности Администраторы безопасности могут отправить действие улучшения [оценки безопасности Майкрософт](microsoft-secure-score.md) непосредственно в ServiceNow и создать билет.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-110">In the security center, security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="e2ea7-111">Могут быть созданы как управление инцидентами, так и билеты управления изменениями.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-111">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="e2ea7-112">Отслеживайте билеты на домашней странице центра безопасности и ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-112">Track tickets in the security center home page and ServiceNow.</span></span>

- [<span data-ttu-id="e2ea7-113">**Сведения о предварительных требованиях, обмене данными и устранению неполадок**</span><span class="sxs-lookup"><span data-stu-id="e2ea7-113">**Learn about prerequisites, data exchange, and troubleshooting**</span></span>](tickets.md)
- <span data-ttu-id="e2ea7-114">**Управление билетами ServiceNow в центре соответствия требованиям** (недоступно)</span><span class="sxs-lookup"><span data-stu-id="e2ea7-114">**Manage ServiceNow tickets in the compliance center** (not available)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="e2ea7-115">Подключение центра безопасности Microsoft 365 к ServiceNow</span><span class="sxs-lookup"><span data-stu-id="e2ea7-115">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="e2ea7-116">Перейдите на домашнюю страницу центра безопасности Microsoft 365, чтобы просмотреть карточку подключения ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-116">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![Использование ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="e2ea7-118">Выберите "подключиться к ServiceNow", чтобы перейти на страницу установки ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-118">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="e2ea7-119">Следуйте инструкциям для авторизации приложения Microsoft 365 Connector.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-119">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="e2ea7-120">Прежде чем выполнять авторизацию подключения между центром безопасности Microsoft 365 и ServiceNow, убедитесь, что вы используете имя входа и пароль пользователя интеграции, которые вы создали в шагах установки.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-120">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="e2ea7-121">Не используйте свои личные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-121">Do not use your personal credentials.</span></span>

<span data-ttu-id="e2ea7-122">После выполнения инструкций и авторизации подключения просмотрите состояние подключения на странице Подключение к центру безопасности Microsoft 365 и в интерфейсе приложения ServiceNow Microsoft 365 с помощью соединителя.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-122">After you've followed the directions and authorized the connection, view the connection status in the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="e2ea7-123">Теперь все готово для начала создания задач.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-123">Now you're all set to start creating tasks!</span></span>

### <a name="troubleshooting"></a><span data-ttu-id="e2ea7-124">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="e2ea7-124">Troubleshooting</span></span>

<span data-ttu-id="e2ea7-125">Сведения об общих ошибках, которые могут возникать в процессе подключения, а также о том, как их можно устранить в [разделе Устранение неполадок](tickets.md#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="e2ea7-125">Learn common errors you may come across in the connection process, and how to mitigate them, in the [troubleshooting section](tickets.md#troubleshooting).</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="e2ea7-126">Создание задачи и общий доступ к ней в ServiceNow</span><span class="sxs-lookup"><span data-stu-id="e2ea7-126">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="e2ea7-127">После настройки интеграции Создайте задачи ServiceNow на основе определенных действий по улучшению [оценки безопасности Майкрософт](microsoft-secure-score.md) .</span><span class="sxs-lookup"><span data-stu-id="e2ea7-127">Once the integration is set up, create ServiceNow tasks based on specific [Microsoft Secure Score](microsoft-secure-score.md) improvement actions.</span></span> <span data-ttu-id="e2ea7-128">Перейдите к любому действию по улучшению оценки безопасности в центре безопасности Microsoft 365 и выберите пункт **общий доступ** .</span><span class="sxs-lookup"><span data-stu-id="e2ea7-128">Go to any Secure Score improvement action in the Microsoft 365 security center, and select **Share** .</span></span> <span data-ttu-id="e2ea7-129">Один из вариантов раскрывающегося списка — ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-129">One of the dropdown options is ServiceNow.</span></span>

<span data-ttu-id="e2ea7-130">Создается задача, в которой можно задать приоритет и изменить имя, описание или срок выполнения.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-130">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="e2ea7-131">После заполнения всех обязательных полей отправьте задачу в ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-131">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="e2ea7-132">Эта задача отображается в ServiceNow как запрос на изменение безопасности и конфигурации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-132">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="e2ea7-133">Отслеживание билетов</span><span class="sxs-lookup"><span data-stu-id="e2ea7-133">Track tickets</span></span>

<span data-ttu-id="e2ea7-134">После создания билетов управления изменениями и управления инцидентами, они отображаются на карточках на домашней странице центра безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-134">Once ServiceNow change management and incident management tickets have been created, they're displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="e2ea7-135">Из этих карточек вы можете создать билет, просмотреть все билеты или управлять конфигурацией ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-135">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![Билеты управления изменениями ServiceNow](../../media/change-management-375.png)  ![Билеты управления инцидентами ServiceNow](../../media/incident-management-375.png)

<span data-ttu-id="e2ea7-138">Для повторной подготовки или управления интеграцией ServiceNow в центре безопасности Майкрософт 365 выберите **Управление конфигурацией servicenow** на любой из карточек.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-138">To reprovision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="e2ea7-139">После этого удалите текущие подключения ServiceNow и настройте имена состояний билетов.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-139">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="e2ea7-140">С билетами ServiceNow, которые отображаются в центре безопасности Майкрософт 365, ваши задачи находятся в том месте, где они могут отслеживаться и обрабатываться вместе с другими элементами панели мониторинга безопасности.</span><span class="sxs-lookup"><span data-stu-id="e2ea7-140">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="resources"></a><span data-ttu-id="e2ea7-141">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="e2ea7-141">Resources</span></span>

- [<span data-ttu-id="e2ea7-142">Сведения о предварительных требованиях, обмене данными и устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="e2ea7-142">Learn about prerequisites, data exchange, and troubleshooting</span></span>](tickets.md)
- [<span data-ttu-id="e2ea7-143">Оценка безопасности (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="e2ea7-143">Microsoft Secure Score</span></span>](microsoft-secure-score.md)
