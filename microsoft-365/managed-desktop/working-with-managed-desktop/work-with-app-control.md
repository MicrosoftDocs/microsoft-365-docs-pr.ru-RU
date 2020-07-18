---
title: Работать с элементом управления App
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
ms.openlocfilehash: 74cd1ec93058ed733e7d79da2d6932f04acfa5da
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170716"
---
# <a name="work-with-app-control"></a><span data-ttu-id="a8635-103">Работать с элементом управления App</span><span class="sxs-lookup"><span data-stu-id="a8635-103">Work with app control</span></span>

<span data-ttu-id="a8635-104">После развертывания элемента управления приложением в вашей среде операции с рабочими столами и управляемыми рабочими столами будут иметь текущие обязанности.</span><span class="sxs-lookup"><span data-stu-id="a8635-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="a8635-105">Например, вы можете добавить новое приложение в среду или добавить (или удалить) доверенного лица.</span><span class="sxs-lookup"><span data-stu-id="a8635-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="a8635-106">Для обеспечения безопасности все приложения должны подписываться кодом, прежде чем отпустить их конечным пользователям.</span><span class="sxs-lookup"><span data-stu-id="a8635-106">To improve security, all apps should be code-signed before you release them to end users.</span></span> <span data-ttu-id="a8635-107">Сведения об издателе приложения включают сведения о подписавшем.</span><span class="sxs-lookup"><span data-stu-id="a8635-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="a8635-108">Добавление нового приложения</span><span class="sxs-lookup"><span data-stu-id="a8635-108">Add a new app</span></span>

<span data-ttu-id="a8635-109">Чтобы добавить новое приложение, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a8635-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="a8635-110">Добавьте приложение в [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span><span class="sxs-lookup"><span data-stu-id="a8635-110">Add the app to [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="a8635-111">Разверните приложение на любом устройстве в тестовом круге.</span><span class="sxs-lookup"><span data-stu-id="a8635-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="a8635-112">Протестируйте приложение в соответствии со стандартными бизнес-процессами.</span><span class="sxs-lookup"><span data-stu-id="a8635-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="a8635-113">Просмотрите окно просмотра событий в разделе **Application and Services логс\микрософт\виндовс\апплоккер**, в котором нужно найти события **8003** или **8006** .</span><span class="sxs-lookup"><span data-stu-id="a8635-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="a8635-114">Эти события указывают на то, что приложение будет заблокировано.</span><span class="sxs-lookup"><span data-stu-id="a8635-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="a8635-115">Для получения дополнительных сведений о всех событиях и их значениях в разделе [Использование средства просмотра событий с помощью AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span><span class="sxs-lookup"><span data-stu-id="a8635-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="a8635-116">Если вы обнаружите какие – либо из этих событий, откройте запрос подписавшего с настольными операциями, управляемыми Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a8635-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="a8635-117">Добавление или удаление доверенного лица</span><span class="sxs-lookup"><span data-stu-id="a8635-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="a8635-118">Когда вы открываете запрос подписавшего, сначала необходимо предоставить некоторые важные сведения об издателе.</span><span class="sxs-lookup"><span data-stu-id="a8635-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="a8635-119">Затем выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a8635-119">Then follow these steps:</span></span>

1. <span data-ttu-id="a8635-120">[Сбор сведений об издателе](#gather-publisher-details).</span><span class="sxs-lookup"><span data-stu-id="a8635-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="a8635-121">Откройте билет с управляемыми операциями на рабочем столе Майкрософт, чтобы запросить правило подписавшего и включить следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="a8635-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="a8635-122">Имя приложения</span><span class="sxs-lookup"><span data-stu-id="a8635-122">Application name</span></span> 
    - <span data-ttu-id="a8635-123">Версия приложения</span><span class="sxs-lookup"><span data-stu-id="a8635-123">Application version</span></span> 
    - <span data-ttu-id="a8635-124">Описание</span><span class="sxs-lookup"><span data-stu-id="a8635-124">Description</span></span> 
    - <span data-ttu-id="a8635-125">Тип изменения ("Add" или "Remove")</span><span class="sxs-lookup"><span data-stu-id="a8635-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="a8635-126">Сведения об издателе (например, "O = <publisher name> , L = <location> , S = штат, C = Country").</span><span class="sxs-lookup"><span data-stu-id="a8635-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="a8635-127">Чтобы удалить отношение доверия для приложения, выполните те же действия, но присвойте **типу изменений** значение *Remove (удалить*).</span><span class="sxs-lookup"><span data-stu-id="a8635-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="a8635-128">Операции будут последовательно развертывать политики в группах развертывания, следующих за этим расписанием:</span><span class="sxs-lookup"><span data-stu-id="a8635-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="a8635-129">Группа развертывания</span><span class="sxs-lookup"><span data-stu-id="a8635-129">Deployment group</span></span>  |<span data-ttu-id="a8635-130">Тип политики</span><span class="sxs-lookup"><span data-stu-id="a8635-130">Policy type</span></span>  |<span data-ttu-id="a8635-131">Время</span><span class="sxs-lookup"><span data-stu-id="a8635-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a8635-132">Тест</span><span class="sxs-lookup"><span data-stu-id="a8635-132">Test</span></span>     |  <span data-ttu-id="a8635-133">Аудит</span><span class="sxs-lookup"><span data-stu-id="a8635-133">Audit</span></span>       |  <span data-ttu-id="a8635-134">День 0</span><span class="sxs-lookup"><span data-stu-id="a8635-134">Day 0</span></span>       |
|<span data-ttu-id="a8635-135">Первый</span><span class="sxs-lookup"><span data-stu-id="a8635-135">First</span></span>     | <span data-ttu-id="a8635-136">Enforced</span><span class="sxs-lookup"><span data-stu-id="a8635-136">Enforced</span></span>        | <span data-ttu-id="a8635-137">День 1</span><span class="sxs-lookup"><span data-stu-id="a8635-137">Day 1</span></span>        |
|<span data-ttu-id="a8635-138">Быстро</span><span class="sxs-lookup"><span data-stu-id="a8635-138">Fast</span></span>     | <span data-ttu-id="a8635-139">Enforced</span><span class="sxs-lookup"><span data-stu-id="a8635-139">Enforced</span></span>        |  <span data-ttu-id="a8635-140">День 3</span><span class="sxs-lookup"><span data-stu-id="a8635-140">Day 3</span></span>       |
|<span data-ttu-id="a8635-141">Общие</span><span class="sxs-lookup"><span data-stu-id="a8635-141">Broad</span></span>     | <span data-ttu-id="a8635-142">Enforced</span><span class="sxs-lookup"><span data-stu-id="a8635-142">Enforced</span></span>        |  <span data-ttu-id="a8635-143">День 7</span><span class="sxs-lookup"><span data-stu-id="a8635-143">Day 7</span></span>       |


<span data-ttu-id="a8635-144">Вы можете приостановить или откатить развертывание в любой момент в процессе развертывания.</span><span class="sxs-lookup"><span data-stu-id="a8635-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="a8635-145">Для этого откройте другой запрос службы с операциями.</span><span class="sxs-lookup"><span data-stu-id="a8635-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="a8635-146">Если приостановить выпуск правила подписавшего, то оно должно быть откатом или завершено до того, как может быть запущено другое развертывание.</span><span class="sxs-lookup"><span data-stu-id="a8635-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="a8635-147">Сбор сведений о приложении Publisher</span><span class="sxs-lookup"><span data-stu-id="a8635-147">Gather publisher details</span></span>

<span data-ttu-id="a8635-148">Чтобы получить доступ к данным издателя для приложения, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a8635-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="a8635-149">Найдите устройство, управляемое Майкрософт, в тестовом кольце, к которому применена политика режима аудита.</span><span class="sxs-lookup"><span data-stu-id="a8635-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="a8635-150">Попытка установить приложение на устройстве.</span><span class="sxs-lookup"><span data-stu-id="a8635-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="a8635-151">Откройте средство просмотра событий на этом устройстве.</span><span class="sxs-lookup"><span data-stu-id="a8635-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="a8635-152">В средстве просмотра событий перейдите в раздел **Application and Services логс\микрософт\виндовс**и выберите **AppLocker**.</span><span class="sxs-lookup"><span data-stu-id="a8635-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="a8635-153">Найдите любое событие **8003** или **8006** , а затем скопируйте информацию из события:</span><span class="sxs-lookup"><span data-stu-id="a8635-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="a8635-154">Имя приложения</span><span class="sxs-lookup"><span data-stu-id="a8635-154">Application name</span></span> 
    - <span data-ttu-id="a8635-155">Версия приложения</span><span class="sxs-lookup"><span data-stu-id="a8635-155">Application version</span></span> 
    - <span data-ttu-id="a8635-156">Описание</span><span class="sxs-lookup"><span data-stu-id="a8635-156">Description</span></span> 
    - <span data-ttu-id="a8635-157">Сведения об издателе (например, "O = <publisher name> , L = <location> , S = штат, C = Country").</span><span class="sxs-lookup"><span data-stu-id="a8635-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span> 