---
title: Соединитетор Microsoft Defender для Flow конечных точек
ms.reviewer: ''
description: Используйте соединители Microsoft Defender для Flow конечной точки, чтобы автоматизировать безопасность и создать поток, который будет активироваться в любое время, когда на клиенте будет возникать новое оповещение.
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: a0718f8e3aba27e6fbfc92a4308278f4c629275f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843798"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a><span data-ttu-id="77e18-104">Microsoft Power Automate (ранее Microsoft Flow) и Azure Functions</span><span class="sxs-lookup"><span data-stu-id="77e18-104">Microsoft Power Automate (formerly Microsoft Flow), and Azure Functions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="77e18-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="77e18-105">**Applies to:**</span></span>
- [<span data-ttu-id="77e18-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="77e18-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="77e18-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="77e18-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="77e18-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="77e18-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="77e18-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="77e18-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="77e18-110">Автоматизация процедур безопасности является стандартным требованием для каждого современного центра операций безопасности.</span><span class="sxs-lookup"><span data-stu-id="77e18-110">Automating security procedures is a standard requirement for every modern Security Operations Center.</span></span> <span data-ttu-id="77e18-111">Отсутствие профессиональных киберзащит заставляет SOC работать наиболее эффективно, а автоматизация является обязательным.</span><span class="sxs-lookup"><span data-stu-id="77e18-111">The lack of professional cyber defenders forces SOC to work in the most efficient way and automation is a must.</span></span> <span data-ttu-id="77e18-112">Microsoft Power Automate поддерживает различные соединители, которые были построены именно для этого.</span><span class="sxs-lookup"><span data-stu-id="77e18-112">Microsoft Power Automate supports different connectors that were built exactly for that.</span></span> <span data-ttu-id="77e18-113">Вы можете создать автоматизацию процедуры в течение нескольких минут.</span><span class="sxs-lookup"><span data-stu-id="77e18-113">You can build an end-to-end procedure automation within a few minutes.</span></span>

<span data-ttu-id="77e18-114">API Защитника Майкрософт имеет официальный Flow со многими возможностями.</span><span class="sxs-lookup"><span data-stu-id="77e18-114">Microsoft Defender API has an official Flow Connector with many capabilities.</span></span>

![Изображение учетных данных для редактирования1](images/api-flow-0.png)

> [!NOTE]
> <span data-ttu-id="77e18-116">Дополнительные сведения о предварительных условия лицензирования соединителов премиум-класса см. в материале [Licensing for premium connectors.](/power-automate/triggers-introduction#licensing-for-premium-connectors)</span><span class="sxs-lookup"><span data-stu-id="77e18-116">For more details about premium connectors licensing prerequisites, see [Licensing for premium connectors](/power-automate/triggers-introduction#licensing-for-premium-connectors).</span></span>


## <a name="usage-example"></a><span data-ttu-id="77e18-117">Пример использования</span><span class="sxs-lookup"><span data-stu-id="77e18-117">Usage example</span></span>

<span data-ttu-id="77e18-118">В следующем примере показано, как создать Flow, который запускается в любое время, когда на клиенте возникает новое оповещение.</span><span class="sxs-lookup"><span data-stu-id="77e18-118">The following example demonstrates how to create a Flow that is triggered any time a new Alert occurs on your tenant.</span></span>

1. <span data-ttu-id="77e18-119">Войдите в [Microsoft Power Automate.](https://flow.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="77e18-119">Log in to [Microsoft Power Automate](https://flow.microsoft.com).</span></span>

2. <span data-ttu-id="77e18-120">Перейдите к **потоку**  >  **My New**  >  **Automated-from blank**.</span><span class="sxs-lookup"><span data-stu-id="77e18-120">Go to **My flows** > **New** > **Automated-from blank**.</span></span>

    ![Изображение редактирования учетных данных2](images/api-flow-1.png)

3. <span data-ttu-id="77e18-122">Выберите имя для Flow, найди в качестве триггера ATP в Защитнике Microsoft триггер, а затем выберите новый триггер оповещения.</span><span class="sxs-lookup"><span data-stu-id="77e18-122">Choose a name for your Flow, search for "Microsoft Defender ATP Triggers" as the trigger, and then select the new Alerts trigger.</span></span>

    ![Изображение учетных данных для редактирования3](images/api-flow-2.png)

<span data-ttu-id="77e18-124">Теперь у вас есть Flow, который запускается каждый раз при новом оповещении.</span><span class="sxs-lookup"><span data-stu-id="77e18-124">Now you have a Flow that is triggered every time a new Alert occurs.</span></span>

![Изображение редактирования учетных данных4](images/api-flow-3.png)

<span data-ttu-id="77e18-126">Все, что вам нужно сделать, это выбрать следующие действия.</span><span class="sxs-lookup"><span data-stu-id="77e18-126">All you need to do now is choose your next steps.</span></span>
<span data-ttu-id="77e18-127">Например, вы можете изолировать устройство, если уровень серьезности оповещений является высоким, и отправить сообщение об этом.</span><span class="sxs-lookup"><span data-stu-id="77e18-127">For example, you can isolate the device if the Severity of the Alert is High and send an email about it.</span></span>
<span data-ttu-id="77e18-128">Спусковой крючок Alert предоставляет только оповещение и машинный ID.</span><span class="sxs-lookup"><span data-stu-id="77e18-128">The Alert trigger provides only the Alert ID and the Machine ID.</span></span> <span data-ttu-id="77e18-129">Этот соединитатель можно использовать для расширения этих сущностями.</span><span class="sxs-lookup"><span data-stu-id="77e18-129">You can use the connector to expand these entities.</span></span>

### <a name="get-the-alert-entity-using-the-connector"></a><span data-ttu-id="77e18-130">Получить объект Alert с помощью соединиттеля</span><span class="sxs-lookup"><span data-stu-id="77e18-130">Get the Alert entity using the connector</span></span>

1. <span data-ttu-id="77e18-131">Выберите **ATP в Защитнике Microsoft** для нового шага.</span><span class="sxs-lookup"><span data-stu-id="77e18-131">Choose **Microsoft Defender ATP** for the new step.</span></span>

2. <span data-ttu-id="77e18-132">Выбор **оповещений . Получить API единого оповещения**.</span><span class="sxs-lookup"><span data-stu-id="77e18-132">Choose **Alerts - Get single alert API**.</span></span>

3. <span data-ttu-id="77e18-133">Установите **ID оповещения на** последнем шаге в качестве **ввода.**</span><span class="sxs-lookup"><span data-stu-id="77e18-133">Set the **Alert ID** from the last step as **Input**.</span></span>

    ![Изображение учетных данных для редактирования5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a><span data-ttu-id="77e18-135">Изолировать устройство, если степень серьезности оповещений высока</span><span class="sxs-lookup"><span data-stu-id="77e18-135">Isolate the device if the Alert's severity is High</span></span>

1. <span data-ttu-id="77e18-136">Добавьте **Условие** в качестве нового шага.</span><span class="sxs-lookup"><span data-stu-id="77e18-136">Add **Condition** as a new step.</span></span>

2. <span data-ttu-id="77e18-137">Проверьте, равна ли серьезность оповещения **высокой.**</span><span class="sxs-lookup"><span data-stu-id="77e18-137">Check if the Alert severity **is equal to** High.</span></span>

   <span data-ttu-id="77e18-138">Если да, добавьте **ATP в Защитнике Microsoft — изолировать** действие машины с машинным ИД и комментарием.</span><span class="sxs-lookup"><span data-stu-id="77e18-138">If yes, add the **Microsoft Defender ATP - Isolate machine** action with the Machine ID and a comment.</span></span>

    ![Изображение редактировать учетные данные6](images/api-flow-5.png)

3. <span data-ttu-id="77e18-140">Добавьте новый шаг для отправки сообщений по электронной почте об оповещении и изоляции.</span><span class="sxs-lookup"><span data-stu-id="77e18-140">Add a new step for emailing about the Alert and the Isolation.</span></span> <span data-ttu-id="77e18-141">Существует несколько соединителов электронной почты, которые очень просты в использовании, например Outlook или Gmail.</span><span class="sxs-lookup"><span data-stu-id="77e18-141">There are multiple email connectors that are very easy to use, such as Outlook or Gmail.</span></span>

4. <span data-ttu-id="77e18-142">Сохраните поток.</span><span class="sxs-lookup"><span data-stu-id="77e18-142">Save your flow.</span></span>

<span data-ttu-id="77e18-143">Вы также можете создать **запланированный** поток, который запускает расширенные запросы на охоту и многое другое!</span><span class="sxs-lookup"><span data-stu-id="77e18-143">You can also create a **scheduled** flow that runs Advanced Hunting queries and much more!</span></span>

## <a name="related-topic"></a><span data-ttu-id="77e18-144">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="77e18-144">Related topic</span></span>
- [<span data-ttu-id="77e18-145">Microsoft Defender для API конечных точек</span><span class="sxs-lookup"><span data-stu-id="77e18-145">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
