---
title: Соединители потока конечных точек Microsoft Defender для конечных точек
ms.reviewer: ''
description: Используйте соединители Потока конечных точек Microsoft Defender для автоматизации безопасности и создания потока, который будет запускаться в любое время, когда в клиенте будет возникать новое оповещение.
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
ms.openlocfilehash: 33a7c7b1907ac761dfdde43a70bfb8f515235150
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51929303"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a><span data-ttu-id="75448-104">Microsoft Power Automate (ранее Microsoft Flow) и Azure Functions</span><span class="sxs-lookup"><span data-stu-id="75448-104">Microsoft Power Automate (formerly Microsoft Flow), and Azure Functions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="75448-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="75448-105">**Applies to:**</span></span>
- [<span data-ttu-id="75448-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="75448-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="75448-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75448-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="75448-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="75448-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="75448-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="75448-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="75448-110">Автоматизация процедур безопасности является стандартным требованием для каждого современного центра операций безопасности.</span><span class="sxs-lookup"><span data-stu-id="75448-110">Automating security procedures is a standard requirement for every modern Security Operations Center.</span></span> <span data-ttu-id="75448-111">Отсутствие профессиональных киберзащит заставляет SOC работать наиболее эффективно, а автоматизация является обязательным.</span><span class="sxs-lookup"><span data-stu-id="75448-111">The lack of professional cyber defenders forces SOC to work in the most efficient way and automation is a must.</span></span> <span data-ttu-id="75448-112">Microsoft Power Automate поддерживает различные соединители, которые были построены именно для этого.</span><span class="sxs-lookup"><span data-stu-id="75448-112">Microsoft Power Automate supports different connectors that were built exactly for that.</span></span> <span data-ttu-id="75448-113">Вы можете создать автоматизацию процедуры в течение нескольких минут.</span><span class="sxs-lookup"><span data-stu-id="75448-113">You can build an end-to-end procedure automation within a few minutes.</span></span>

<span data-ttu-id="75448-114">API Защитника Майкрософт имеет официальный соединителет потока с большим количеством возможностей.</span><span class="sxs-lookup"><span data-stu-id="75448-114">Microsoft Defender API has an official Flow Connector with many capabilities.</span></span>

![Изображение учетных данных для редактирования1](images/api-flow-0.png)

> [!NOTE]
> <span data-ttu-id="75448-116">Дополнительные сведения о предварительных условия лицензирования соединителов премиум-класса см. в материале [Licensing for premium connectors.](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors)</span><span class="sxs-lookup"><span data-stu-id="75448-116">For more details about premium connectors licensing prerequisites, see [Licensing for premium connectors](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors).</span></span>


## <a name="usage-example"></a><span data-ttu-id="75448-117">Пример использования</span><span class="sxs-lookup"><span data-stu-id="75448-117">Usage example</span></span>

<span data-ttu-id="75448-118">В следующем примере показано, как создать поток, который запускается в любое время, когда на клиенте возникает новое оповещение.</span><span class="sxs-lookup"><span data-stu-id="75448-118">The following example demonstrates how to create a Flow that is triggered any time a new Alert occurs on your tenant.</span></span>

1. <span data-ttu-id="75448-119">Войдите в [Microsoft Power Automate](https://flow.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="75448-119">Log in to [Microsoft Power Automate](https://flow.microsoft.com).</span></span>

2. <span data-ttu-id="75448-120">Перейдите к **потоку**  >  **My New**  >  **Automated-from blank**.</span><span class="sxs-lookup"><span data-stu-id="75448-120">Go to **My flows** > **New** > **Automated-from blank**.</span></span>

    ![Изображение редактирования учетных данных2](images/api-flow-1.png)

3. <span data-ttu-id="75448-122">Выберите имя потока, в качестве триггера выберите триггер "Триггеры ATP Защитника Майкрософт", а затем выберите новый триггер оповещения.</span><span class="sxs-lookup"><span data-stu-id="75448-122">Choose a name for your Flow, search for "Microsoft Defender ATP Triggers" as the trigger, and then select the new Alerts trigger.</span></span>

    ![Изображение учетных данных для редактирования3](images/api-flow-2.png)

<span data-ttu-id="75448-124">Теперь у вас есть поток, который запускается каждый раз, когда происходит новое оповещение.</span><span class="sxs-lookup"><span data-stu-id="75448-124">Now you have a Flow that is triggered every time a new Alert occurs.</span></span>

![Изображение редактирования учетных данных4](images/api-flow-3.png)

<span data-ttu-id="75448-126">Все, что вам нужно сделать, это выбрать следующие действия.</span><span class="sxs-lookup"><span data-stu-id="75448-126">All you need to do now is choose your next steps.</span></span>
<span data-ttu-id="75448-127">Например, вы можете изолировать устройство, если уровень серьезности оповещений является высоким, и отправить сообщение об этом.</span><span class="sxs-lookup"><span data-stu-id="75448-127">For example, you can isolate the device if the Severity of the Alert is High and send an email about it.</span></span>
<span data-ttu-id="75448-128">Спусковой крючок Alert предоставляет только оповещение и машинный ID.</span><span class="sxs-lookup"><span data-stu-id="75448-128">The Alert trigger provides only the Alert ID and the Machine ID.</span></span> <span data-ttu-id="75448-129">Этот соединитатель можно использовать для расширения этих сущностями.</span><span class="sxs-lookup"><span data-stu-id="75448-129">You can use the connector to expand these entities.</span></span>

### <a name="get-the-alert-entity-using-the-connector"></a><span data-ttu-id="75448-130">Получить объект Alert с помощью соединиттеля</span><span class="sxs-lookup"><span data-stu-id="75448-130">Get the Alert entity using the connector</span></span>

1. <span data-ttu-id="75448-131">Выберите **ATP Защитника Майкрософт** для нового шага.</span><span class="sxs-lookup"><span data-stu-id="75448-131">Choose **Microsoft Defender ATP** for the new step.</span></span>

2. <span data-ttu-id="75448-132">Выбор **оповещений . Получить API единого оповещения**.</span><span class="sxs-lookup"><span data-stu-id="75448-132">Choose **Alerts - Get single alert API**.</span></span>

3. <span data-ttu-id="75448-133">Установите **ID оповещения на** последнем шаге в качестве **ввода.**</span><span class="sxs-lookup"><span data-stu-id="75448-133">Set the **Alert ID** from the last step as **Input**.</span></span>

    ![Изображение учетных данных для редактирования5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a><span data-ttu-id="75448-135">Изолировать устройство, если степень серьезности оповещений высока</span><span class="sxs-lookup"><span data-stu-id="75448-135">Isolate the device if the Alert's severity is High</span></span>

1. <span data-ttu-id="75448-136">Добавьте **Условие** в качестве нового шага.</span><span class="sxs-lookup"><span data-stu-id="75448-136">Add **Condition** as a new step.</span></span>

2. <span data-ttu-id="75448-137">Проверьте, равна ли серьезность оповещения **высокой.**</span><span class="sxs-lookup"><span data-stu-id="75448-137">Check if the Alert severity **is equal to** High.</span></span>

   <span data-ttu-id="75448-138">Если да, добавьте **atP Защитника Microsoft — изолировать** действие машины с машинным ИД и комментарием.</span><span class="sxs-lookup"><span data-stu-id="75448-138">If yes, add the **Microsoft Defender ATP - Isolate machine** action with the Machine ID and a comment.</span></span>

    ![Изображение редактировать учетные данные6](images/api-flow-5.png)

3. <span data-ttu-id="75448-140">Добавьте новый шаг для отправки сообщений по электронной почте об оповещении и изоляции.</span><span class="sxs-lookup"><span data-stu-id="75448-140">Add a new step for emailing about the Alert and the Isolation.</span></span> <span data-ttu-id="75448-141">Существует несколько соединителов электронной почты, которые очень просты в использовании, например Outlook или Gmail.</span><span class="sxs-lookup"><span data-stu-id="75448-141">There are multiple email connectors that are very easy to use, such as Outlook or Gmail.</span></span>

4. <span data-ttu-id="75448-142">Сохраните поток.</span><span class="sxs-lookup"><span data-stu-id="75448-142">Save your flow.</span></span>

<span data-ttu-id="75448-143">Вы также можете создать **запланированный** поток, который запускает расширенные запросы на охоту и многое другое!</span><span class="sxs-lookup"><span data-stu-id="75448-143">You can also create a **scheduled** flow that runs Advanced Hunting queries and much more!</span></span>

## <a name="related-topic"></a><span data-ttu-id="75448-144">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="75448-144">Related topic</span></span>
- [<span data-ttu-id="75448-145">Microsoft Defender для API конечных точек</span><span class="sxs-lookup"><span data-stu-id="75448-145">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
