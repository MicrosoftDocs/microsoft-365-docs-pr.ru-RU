---
title: Соединителет потока ATP Защитника Майкрософт
ms.reviewer: ''
description: Чтобы автоматизировать безопасность и создать поток, который будет активироваться в любое время, когда на клиенте будет возникать новое оповещение, используйте соединители потока ATP Защитника Майкрософт.
keywords: поток, поддерживаемые api, api, поток Майкрософт, запрос, автоматизация
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6fd210ddfb8e3ab6e4f1f4ffc0635c8b813e3a07
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163391"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a><span data-ttu-id="00618-104">Microsoft Power Automate (ранее Microsoft Flow) и Azure Functions</span><span class="sxs-lookup"><span data-stu-id="00618-104">Microsoft Power Automate (formerly Microsoft Flow), and Azure Functions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="00618-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="00618-105">**Applies to:**</span></span>
- [<span data-ttu-id="00618-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="00618-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="00618-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="00618-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="00618-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="00618-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="00618-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="00618-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="00618-110">Автоматизация процедур безопасности является стандартным требованием для каждого современного центра операций безопасности.</span><span class="sxs-lookup"><span data-stu-id="00618-110">Automating security procedures is a standard requirement for every modern Security Operations Center.</span></span> <span data-ttu-id="00618-111">Отсутствие профессиональных киберзащит заставляет SOC работать наиболее эффективно, а автоматизация является обязательным.</span><span class="sxs-lookup"><span data-stu-id="00618-111">The lack of professional cyber defenders forces SOC to work in the most efficient way and automation is a must.</span></span> <span data-ttu-id="00618-112">Microsoft Power Automate поддерживает различные соединители, которые были построены именно для этого.</span><span class="sxs-lookup"><span data-stu-id="00618-112">Microsoft Power Automate supports different connectors that were built exactly for that.</span></span> <span data-ttu-id="00618-113">Вы можете создать автоматизацию процедуры в течение нескольких минут.</span><span class="sxs-lookup"><span data-stu-id="00618-113">You can build an end-to-end procedure automation within a few minutes.</span></span>

<span data-ttu-id="00618-114">API Защитника Майкрософт имеет официальный соединителет потока с большим количеством возможностей.</span><span class="sxs-lookup"><span data-stu-id="00618-114">Microsoft Defender API has an official Flow Connector with many capabilities.</span></span>

![Изображение учетных данных для редактирования1](images/api-flow-0.png)

> [!NOTE]
> <span data-ttu-id="00618-116">Дополнительные сведения о предварительных условия лицензирования соединителов премиум-класса см. в материале [Licensing for premium connectors.](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors)</span><span class="sxs-lookup"><span data-stu-id="00618-116">For more details about premium connectors licensing prerequisites, see [Licensing for premium connectors](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors).</span></span>


## <a name="usage-example"></a><span data-ttu-id="00618-117">Пример использования</span><span class="sxs-lookup"><span data-stu-id="00618-117">Usage example</span></span>

<span data-ttu-id="00618-118">В следующем примере показано, как создать поток, который запускается в любое время, когда на клиенте возникает новое оповещение.</span><span class="sxs-lookup"><span data-stu-id="00618-118">The following example demonstrates how to create a Flow that is triggered any time a new Alert occurs on your tenant.</span></span>

1. <span data-ttu-id="00618-119">Войдите в [Microsoft Power Automate](https://flow.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="00618-119">Log in to [Microsoft Power Automate](https://flow.microsoft.com).</span></span>

2. <span data-ttu-id="00618-120">Перейдите к **потоку**  >  **My New**  >  **Automated-from blank**.</span><span class="sxs-lookup"><span data-stu-id="00618-120">Go to **My flows** > **New** > **Automated-from blank**.</span></span>

    ![Изображение редактирования учетных данных2](images/api-flow-1.png)

3. <span data-ttu-id="00618-122">Выберите имя потока, в качестве триггера выберите триггер "Триггеры ATP Защитника Майкрософт", а затем выберите новый триггер оповещения.</span><span class="sxs-lookup"><span data-stu-id="00618-122">Choose a name for your Flow, search for "Microsoft Defender ATP Triggers" as the trigger, and then select the new Alerts trigger.</span></span>

    ![Изображение учетных данных для редактирования3](images/api-flow-2.png)

<span data-ttu-id="00618-124">Теперь у вас есть поток, который запускается каждый раз, когда происходит новое оповещение.</span><span class="sxs-lookup"><span data-stu-id="00618-124">Now you have a Flow that is triggered every time a new Alert occurs.</span></span>

![Изображение редактирования учетных данных4](images/api-flow-3.png)

<span data-ttu-id="00618-126">Все, что вам нужно сделать, это выбрать следующие действия.</span><span class="sxs-lookup"><span data-stu-id="00618-126">All you need to do now is choose your next steps.</span></span>
<span data-ttu-id="00618-127">Например, вы можете изолировать устройство, если уровень серьезности оповещений является высоким, и отправить сообщение об этом.</span><span class="sxs-lookup"><span data-stu-id="00618-127">For example, you can isolate the device if the Severity of the Alert is High and send an email about it.</span></span>
<span data-ttu-id="00618-128">Спусковой крючок Alert предоставляет только оповещение и машинный ID.</span><span class="sxs-lookup"><span data-stu-id="00618-128">The Alert trigger provides only the Alert ID and the Machine ID.</span></span> <span data-ttu-id="00618-129">Этот соединитатель можно использовать для расширения этих сущностями.</span><span class="sxs-lookup"><span data-stu-id="00618-129">You can use the connector to expand these entities.</span></span>

### <a name="get-the-alert-entity-using-the-connector"></a><span data-ttu-id="00618-130">Получить объект Alert с помощью соединиттеля</span><span class="sxs-lookup"><span data-stu-id="00618-130">Get the Alert entity using the connector</span></span>

1. <span data-ttu-id="00618-131">Выберите **ATP Защитника Майкрософт** для нового шага.</span><span class="sxs-lookup"><span data-stu-id="00618-131">Choose **Microsoft Defender ATP** for the new step.</span></span>

2. <span data-ttu-id="00618-132">Выбор **оповещений . Получить API единого оповещения**.</span><span class="sxs-lookup"><span data-stu-id="00618-132">Choose **Alerts - Get single alert API**.</span></span>

3. <span data-ttu-id="00618-133">Установите **ID оповещения на** последнем шаге в качестве **ввода.**</span><span class="sxs-lookup"><span data-stu-id="00618-133">Set the **Alert ID** from the last step as **Input**.</span></span>

    ![Изображение учетных данных для редактирования5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a><span data-ttu-id="00618-135">Изолировать устройство, если степень серьезности оповещений высока</span><span class="sxs-lookup"><span data-stu-id="00618-135">Isolate the device if the Alert's severity is High</span></span>

1. <span data-ttu-id="00618-136">Добавьте **Условие** в качестве нового шага.</span><span class="sxs-lookup"><span data-stu-id="00618-136">Add **Condition** as a new step.</span></span>

2. <span data-ttu-id="00618-137">Проверьте, равна ли серьезность оповещения **высокой.**</span><span class="sxs-lookup"><span data-stu-id="00618-137">Check if the Alert severity **is equal to** High.</span></span>

   <span data-ttu-id="00618-138">Если да, добавьте **atP Защитника Microsoft — изолировать** действие машины с машинным ИД и комментарием.</span><span class="sxs-lookup"><span data-stu-id="00618-138">If yes, add the **Microsoft Defender ATP - Isolate machine** action with the Machine ID and a comment.</span></span>

    ![Изображение редактировать учетные данные6](images/api-flow-5.png)

3. <span data-ttu-id="00618-140">Добавьте новый шаг для отправки сообщений по электронной почте об оповещении и изоляции.</span><span class="sxs-lookup"><span data-stu-id="00618-140">Add a new step for emailing about the Alert and the Isolation.</span></span> <span data-ttu-id="00618-141">Существует несколько соединителов электронной почты, которые очень просты в использовании, например Outlook или Gmail.</span><span class="sxs-lookup"><span data-stu-id="00618-141">There are multiple email connectors that are very easy to use, such as Outlook or Gmail.</span></span>

4. <span data-ttu-id="00618-142">Сохраните поток.</span><span class="sxs-lookup"><span data-stu-id="00618-142">Save your flow.</span></span>

<span data-ttu-id="00618-143">Вы также можете создать **запланированный** поток, который запускает расширенные запросы на охоту и многое другое!</span><span class="sxs-lookup"><span data-stu-id="00618-143">You can also create a **scheduled** flow that runs Advanced Hunting queries and much more!</span></span>

## <a name="related-topic"></a><span data-ttu-id="00618-144">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="00618-144">Related topic</span></span>
- [<span data-ttu-id="00618-145">Microsoft Defender для API конечных точек</span><span class="sxs-lookup"><span data-stu-id="00618-145">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
