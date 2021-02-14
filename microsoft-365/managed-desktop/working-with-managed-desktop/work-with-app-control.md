---
title: Работа с элементом управления приложениями
description: ''
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0b76a14a30caeb75cfdcb8acc5715fe6710e0625
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289463"
---
# <a name="work-with-app-control"></a><span data-ttu-id="75680-103">Работа с элементом управления приложениями</span><span class="sxs-lookup"><span data-stu-id="75680-103">Work with app control</span></span>

<span data-ttu-id="75680-104">После развертывания управления приложениями в вашей среде вы и microsoft Managed Desktop Operations будете выполнять текущие обязанности.</span><span class="sxs-lookup"><span data-stu-id="75680-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="75680-105">Например, может потребоваться добавить новое приложение в среду или добавить (или удалить) доверенного подписантов.</span><span class="sxs-lookup"><span data-stu-id="75680-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="75680-106">Для повышения безопасности все приложения должны быть подписаны кодом перед их выпуском для пользователей.</span><span class="sxs-lookup"><span data-stu-id="75680-106">To improve security, all apps should be code-signed before you release them to users.</span></span> <span data-ttu-id="75680-107">Сведения о издателе приложения содержат сведения о подписываемом.</span><span class="sxs-lookup"><span data-stu-id="75680-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="75680-108">Добавление нового приложения</span><span class="sxs-lookup"><span data-stu-id="75680-108">Add a new app</span></span>

<span data-ttu-id="75680-109">Чтобы добавить новое приложение, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="75680-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="75680-110">Добавьте приложение в [Microsoft Intune.](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="75680-110">Add the app to [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="75680-111">Развертывание приложения на любом устройстве в круге "Тестирование".</span><span class="sxs-lookup"><span data-stu-id="75680-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="75680-112">Протестировать приложение в соответствии со стандартными бизнес-процессами.</span><span class="sxs-lookup"><span data-stu-id="75680-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="75680-113">Проверьте окно просмотра событий в журнале приложений и **служб\Microsoft\Windows\AppLocker** и найдите все события **8003** или **8006.**</span><span class="sxs-lookup"><span data-stu-id="75680-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="75680-114">Эти события указывают на то, что приложение будет заблокировано.</span><span class="sxs-lookup"><span data-stu-id="75680-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="75680-115">Дополнительные сведения обо всех событиях и их значениях в app Locker см. в подзаголовке ["Просмотр событий" с AppLocker.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)</span><span class="sxs-lookup"><span data-stu-id="75680-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="75680-116">Если вы нашли любое из этих событий, откройте запрос подписи с помощью microsoft Managed Desktop Operations.</span><span class="sxs-lookup"><span data-stu-id="75680-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="75680-117">Добавление (или удаление) доверенного подписаного</span><span class="sxs-lookup"><span data-stu-id="75680-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="75680-118">Когда вы открываете запрос подписываного знака, сначала необходимо предоставить некоторые важные сведения о издателе.</span><span class="sxs-lookup"><span data-stu-id="75680-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="75680-119">Затем выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="75680-119">Then follow these steps:</span></span>

1. <span data-ttu-id="75680-120">[Сбор сведений о издателе.](#gather-publisher-details)</span><span class="sxs-lookup"><span data-stu-id="75680-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="75680-121">Откройте запрос с помощью microsoft Managed Desktop Operations, чтобы запросить правило для подписываного и включив следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="75680-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="75680-122">Имя приложения</span><span class="sxs-lookup"><span data-stu-id="75680-122">Application name</span></span> 
    - <span data-ttu-id="75680-123">Версия приложения</span><span class="sxs-lookup"><span data-stu-id="75680-123">Application version</span></span> 
    - <span data-ttu-id="75680-124">Description</span><span class="sxs-lookup"><span data-stu-id="75680-124">Description</span></span> 
    - <span data-ttu-id="75680-125">Тип изменения ("добавить" или "удалить")</span><span class="sxs-lookup"><span data-stu-id="75680-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="75680-126">Сведения о издателе (например, "O= <publisher name> ,L= <location> ,S=State,C=Country")</span><span class="sxs-lookup"><span data-stu-id="75680-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="75680-127">Чтобы удалить доверие для приложения, выполните те же действия, но задайте **удаляемый** *тип изменения.*</span><span class="sxs-lookup"><span data-stu-id="75680-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="75680-128">Операции постепенно развертывают политики в группах развертывания по следующему расписанию:</span><span class="sxs-lookup"><span data-stu-id="75680-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="75680-129">Группа развертывания</span><span class="sxs-lookup"><span data-stu-id="75680-129">Deployment group</span></span>  |<span data-ttu-id="75680-130">Тип политики</span><span class="sxs-lookup"><span data-stu-id="75680-130">Policy type</span></span>  |<span data-ttu-id="75680-131">Время</span><span class="sxs-lookup"><span data-stu-id="75680-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="75680-132">Тест</span><span class="sxs-lookup"><span data-stu-id="75680-132">Test</span></span>     |  <span data-ttu-id="75680-133">Аудит</span><span class="sxs-lookup"><span data-stu-id="75680-133">Audit</span></span>       |  <span data-ttu-id="75680-134">День 0</span><span class="sxs-lookup"><span data-stu-id="75680-134">Day 0</span></span>       |
|<span data-ttu-id="75680-135">Первый</span><span class="sxs-lookup"><span data-stu-id="75680-135">First</span></span>     | <span data-ttu-id="75680-136">Enforced</span><span class="sxs-lookup"><span data-stu-id="75680-136">Enforced</span></span>        | <span data-ttu-id="75680-137">День 1</span><span class="sxs-lookup"><span data-stu-id="75680-137">Day 1</span></span>        |
|<span data-ttu-id="75680-138">Быстро</span><span class="sxs-lookup"><span data-stu-id="75680-138">Fast</span></span>     | <span data-ttu-id="75680-139">Enforced</span><span class="sxs-lookup"><span data-stu-id="75680-139">Enforced</span></span>        |  <span data-ttu-id="75680-140">День 2</span><span class="sxs-lookup"><span data-stu-id="75680-140">Day 2</span></span>       |
|<span data-ttu-id="75680-141">Общие</span><span class="sxs-lookup"><span data-stu-id="75680-141">Broad</span></span>     | <span data-ttu-id="75680-142">Enforced</span><span class="sxs-lookup"><span data-stu-id="75680-142">Enforced</span></span>        |  <span data-ttu-id="75680-143">День 3</span><span class="sxs-lookup"><span data-stu-id="75680-143">Day 3</span></span>       |


<span data-ttu-id="75680-144">Вы можете приостановить или откатить развертывание в любое время во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="75680-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="75680-145">Для этого откройте другой запрос на обслуживание с помощью Operations.</span><span class="sxs-lookup"><span data-stu-id="75680-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="75680-146">Если вы приостановите выпуск правила для подписываемого, это правило должно быть откатино или завершено до запуска другого выпуска.</span><span class="sxs-lookup"><span data-stu-id="75680-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="75680-147">Сбор сведений о издателе</span><span class="sxs-lookup"><span data-stu-id="75680-147">Gather publisher details</span></span>

<span data-ttu-id="75680-148">Чтобы получить доступ к данным издателя для приложения, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="75680-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="75680-149">Найдите настольное устройство, управляемое Майкрософт, в круге тестирования, к которым применена политика режима аудита.</span><span class="sxs-lookup"><span data-stu-id="75680-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="75680-150">Попытка установить приложение на устройстве.</span><span class="sxs-lookup"><span data-stu-id="75680-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="75680-151">Откройте "Просмотр событий" на этом устройстве.</span><span class="sxs-lookup"><span data-stu-id="75680-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="75680-152">В окне "Просмотр событий" перейдите к журналу приложений и **служб\Microsoft\Windows** и выберите **AppLocker.**</span><span class="sxs-lookup"><span data-stu-id="75680-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="75680-153">Найдите **любое событие 8003** или **8006,** а затем скопируйте сведения из события:</span><span class="sxs-lookup"><span data-stu-id="75680-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="75680-154">Имя приложения</span><span class="sxs-lookup"><span data-stu-id="75680-154">Application name</span></span> 
    - <span data-ttu-id="75680-155">Версия приложения</span><span class="sxs-lookup"><span data-stu-id="75680-155">Application version</span></span> 
    - <span data-ttu-id="75680-156">Description</span><span class="sxs-lookup"><span data-stu-id="75680-156">Description</span></span> 
    - <span data-ttu-id="75680-157">Сведения о издателе (например, "O= <publisher name> , L= <location> , S=State, C=Country")</span><span class="sxs-lookup"><span data-stu-id="75680-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span> 
