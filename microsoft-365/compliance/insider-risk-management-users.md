---
title: Пользователи по управлению рисками для участников (Предварительная версия)
description: Сведения о пользователях по управлению рисками в Microsoft 365
keywords: Microsoft 365, управление рисками для оценки, управление рисками, соответствие требованиям
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: f79fcebf220f1aee98ba97c537ff80b65b6e3881
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41582858"
---
# <a name="insider-risk-management-users-preview"></a><span data-ttu-id="24388-104">Пользователи по управлению рисками для участников (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="24388-104">Insider risk management users (preview)</span></span>

<span data-ttu-id="24388-105">Пользователи, участвующие в управлении рисками для участников вашей организации, входят в одну или несколько политик управления рисками.</span><span class="sxs-lookup"><span data-stu-id="24388-105">Insider risk management users are employees in your organization that are included in one or more insider risk management policies.</span></span> <span data-ttu-id="24388-106">Используйте **панель мониторинга "Пользователи"** , чтобы быстро просмотреть сведения о рисках для сотрудников и добавить сотрудника в существующую политику управления рисками для оценки.</span><span class="sxs-lookup"><span data-stu-id="24388-106">Use the **Users dashboard** to quickly review risk information about employees and to add an employee to an existing insider risk management policy.</span></span> <span data-ttu-id="24388-107">Для каждого пользователя, включенного в политику управления рисками для предварительной оценки, отображаются следующие сведения на **панели мониторинга "Пользователи"**:</span><span class="sxs-lookup"><span data-stu-id="24388-107">Each user included in an insider risk management policy has the following information displayed on the **Users dashboard**:</span></span>

- <span data-ttu-id="24388-108">**Пользователи**: имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="24388-108">**Users**: The user name for a user.</span></span>
- <span data-ttu-id="24388-109">**Уровень риска**:</span><span class="sxs-lookup"><span data-stu-id="24388-109">**Risk level**:</span></span> 
- <span data-ttu-id="24388-110">**Активные оповещения**: количество активных оповещений для всех политик.</span><span class="sxs-lookup"><span data-stu-id="24388-110">**Active alerts**: The number of active alerts for all policies.</span></span>
- <span data-ttu-id="24388-111">**Подтвержденные нарушения**: количество вариантов, разрешенных как *подтвержденное нарушение политики* для пользователя.</span><span class="sxs-lookup"><span data-stu-id="24388-111">**Confirmed violations**: The number of cases resolved as *confirmed policy violation* for the user.</span></span>
- <span data-ttu-id="24388-112">**Регистр**: текущее активное обращение для пользователя.</span><span class="sxs-lookup"><span data-stu-id="24388-112">**Case**: The current active case for the user.</span></span>

![Панель мониторинга пользователей управления рисками для участников](media/insider-risk-users-dashboard.png)

## <a name="view-user-details"></a><span data-ttu-id="24388-114">Просмотр сведений о пользователях</span><span class="sxs-lookup"><span data-stu-id="24388-114">View user details</span></span>

<span data-ttu-id="24388-115">Чтобы просмотреть дополнительные сведения о действиях с рисками для пользователя, откройте область сведений о пользователях, дважды щелкнув пользователя на **панели мониторинга "Пользователи"**.</span><span class="sxs-lookup"><span data-stu-id="24388-115">To view more details about risk activity for a user, open the user details pane by double-clicking a user in the **Users dashboard**.</span></span> <span data-ttu-id="24388-116">В области сведений можно просмотреть следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="24388-116">On the details pane, you can view the following information:</span></span>

- <span data-ttu-id="24388-117">Вкладка " **профиль пользователя** "</span><span class="sxs-lookup"><span data-stu-id="24388-117">**User profile** tab</span></span>
    - <span data-ttu-id="24388-118">**Имя и должность**: имя и должность пользователя.</span><span class="sxs-lookup"><span data-stu-id="24388-118">**Name and title**: The name and position title for the user.</span></span>
    - <span data-ttu-id="24388-119">**Электронная почта пользователя**: адрес электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="24388-119">**User email**: The email address for the user.</span></span>
    - <span data-ttu-id="24388-120">**Псевдоним**: псевдоним сети для пользователя.</span><span class="sxs-lookup"><span data-stu-id="24388-120">**Alias**: The network alias for the user.</span></span>
    - <span data-ttu-id="24388-121">**Организация или отдел**: организация или отдел для пользователя.</span><span class="sxs-lookup"><span data-stu-id="24388-121">**Organization or department**: The organization or department for the user.</span></span>

- <span data-ttu-id="24388-122">Вкладка " **действия пользователя** "</span><span class="sxs-lookup"><span data-stu-id="24388-122">**User activity** tab</span></span>
    - <span data-ttu-id="24388-123">**Журнал недавних действий пользователя**: перечисляет события триггера политики и индикаторы риска для действий пользователей.</span><span class="sxs-lookup"><span data-stu-id="24388-123">**History of recent user activity**: Lists both policy triggering events and risk indicators for user activities.</span></span> <span data-ttu-id="24388-124">Событие триггера может быть приемом ресигнатион даты или последней запланированной даты трудозатрат для сотрудника.</span><span class="sxs-lookup"><span data-stu-id="24388-124">A triggering event may be the acceptance of a resignation date or the last scheduled date of work for the employee.</span></span> <span data-ttu-id="24388-125">Индикаторы риска — это действия, которые определяют наличие элемента риска и совпадают с политиками, в которых он включен.</span><span class="sxs-lookup"><span data-stu-id="24388-125">Risk indicators are activities that are determined to have an element of risk and that are matched to policies that the user is included in.</span></span> <span data-ttu-id="24388-126">События и действия с рисками перечислены в списке последних элементов.</span><span class="sxs-lookup"><span data-stu-id="24388-126">Events and risk activities are listed with the most recent item listed first.</span></span>

## <a name="add-a-user-to-a-policy"></a><span data-ttu-id="24388-127">Добавление пользователя к политике</span><span class="sxs-lookup"><span data-stu-id="24388-127">Add a user to a policy</span></span>

<span data-ttu-id="24388-128">Чтобы добавить пользователя в политику управления рисками для оценки, воспользуйтесь мастером создания политики или вкладкой **Пользователи** в решении " **Управление рисками** " в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="24388-128">To add a user to an insider risk management policy, you'll either use the new policy wizard or the **Users** tab in the **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="24388-129">Выполните указанные ниже действия, чтобы добавить пользователя к существующей политике риска предварительной оценки.</span><span class="sxs-lookup"><span data-stu-id="24388-129">Complete the following steps to add a user to an existing insider risk policy:</span></span>

1. <span data-ttu-id="24388-130">В [центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com)перейдите к разделу **Управление рисками для оценки** и выберите вкладку **Пользователи** .</span><span class="sxs-lookup"><span data-stu-id="24388-130">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Users** tab.</span></span>
2. <span data-ttu-id="24388-131">Выберите **Добавить пользователя в политику** на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="24388-131">Select **Add a user to a policy** on the toolbar.</span></span>
3. <span data-ttu-id="24388-132">В диалоговом окне **Добавление нового пользователя** начните ввод имени пользователя в поле **пользователь** .</span><span class="sxs-lookup"><span data-stu-id="24388-132">On the **Add a new user** dialog, start typing a user name in the **User** field.</span></span> <span data-ttu-id="24388-133">Выберите пользователя, которого вы хотите добавить в политику.</span><span class="sxs-lookup"><span data-stu-id="24388-133">Select the user you want to add to a policy.</span></span>
4. <span data-ttu-id="24388-134">Нажмите стрелку раскрывающегося списка для поля **Политика** , чтобы отобразить настроенные политики управления рисками для участников программы оценки.</span><span class="sxs-lookup"><span data-stu-id="24388-134">Select the dropdown arrow for the **Policy** field to display configured insider risk management policies.</span></span> <span data-ttu-id="24388-135">Выберите политику, в которую нужно добавить пользователя.</span><span class="sxs-lookup"><span data-stu-id="24388-135">Select the policy to add the user to.</span></span>
5. <span data-ttu-id="24388-136">Используйте ползунок **окна мониторинга** , чтобы определить...... Диапазон для окна мониторинга составляет от 5 до 30 дней.</span><span class="sxs-lookup"><span data-stu-id="24388-136">Use the **Monitoring window** slider control to define the...... The range for the monitoring window is 5 to 30 days.</span></span>
6. <span data-ttu-id="24388-137">Нажмите кнопку **Добавить** , а затем **Подтвердите** , чтобы добавить пользователя в политику.</span><span class="sxs-lookup"><span data-stu-id="24388-137">Select **Add** and then **Confirm** to add the user to the policy.</span></span>
