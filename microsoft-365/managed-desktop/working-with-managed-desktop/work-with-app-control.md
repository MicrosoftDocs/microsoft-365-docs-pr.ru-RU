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
ms.openlocfilehash: 31cc897fe28f557a65cba9c99e5dcecbf7c2b0e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917644"
---
# <a name="work-with-app-control"></a><span data-ttu-id="3fb78-103">Работа с элементом управления приложениями</span><span class="sxs-lookup"><span data-stu-id="3fb78-103">Work with app control</span></span>

<span data-ttu-id="3fb78-104">После развертывания управления приложениями в вашей среде вы и компьютеры, управляемые Майкрософт операции несут постоянные обязанности.</span><span class="sxs-lookup"><span data-stu-id="3fb78-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="3fb78-105">Например, может потребоваться добавить новое приложение в среду или добавить (или удалить) доверенный подписатель.</span><span class="sxs-lookup"><span data-stu-id="3fb78-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="3fb78-106">Чтобы повысить безопасность, все приложения должны быть подписаны кодом перед выпуском их пользователям.</span><span class="sxs-lookup"><span data-stu-id="3fb78-106">To improve security, all apps should be code-signed before you release them to users.</span></span> <span data-ttu-id="3fb78-107">Сведения о издателе приложения включают сведения о подписывателье.</span><span class="sxs-lookup"><span data-stu-id="3fb78-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="3fb78-108">Добавление нового приложения</span><span class="sxs-lookup"><span data-stu-id="3fb78-108">Add a new app</span></span>

<span data-ttu-id="3fb78-109">Чтобы добавить новое приложение, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3fb78-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="3fb78-110">Добавьте приложение в [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).</span><span class="sxs-lookup"><span data-stu-id="3fb78-110">Add the app to [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="3fb78-111">Развертывание приложения на любом устройстве в тестовом кольце.</span><span class="sxs-lookup"><span data-stu-id="3fb78-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="3fb78-112">Проверьте приложение в соответствии со стандартными бизнес-процессами.</span><span class="sxs-lookup"><span data-stu-id="3fb78-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="3fb78-113">Проверка просмотра событий в журналах приложений и **служб\Microsoft\Windows\AppLocker**, ищите события **8003** или **8006.**</span><span class="sxs-lookup"><span data-stu-id="3fb78-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="3fb78-114">Эти события указывают на то, что приложение будет заблокировано.</span><span class="sxs-lookup"><span data-stu-id="3fb78-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="3fb78-115">Дополнительные сведения обо всех событиях App Locker и их значениях см. в приложении [Using Event Viewer with AppLocker.](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)</span><span class="sxs-lookup"><span data-stu-id="3fb78-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="3fb78-116">Если вы найдете любое из этих событий, откройте запрос подписавщика с компьютеры, управляемые Майкрософт Operations.</span><span class="sxs-lookup"><span data-stu-id="3fb78-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="3fb78-117">Добавление (или удаление) доверенного подписаного знака</span><span class="sxs-lookup"><span data-stu-id="3fb78-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="3fb78-118">Когда вы откроете запрос подписавщика, сначала необходимо предоставить некоторые важные сведения издателя.</span><span class="sxs-lookup"><span data-stu-id="3fb78-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="3fb78-119">Затем выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3fb78-119">Then follow these steps:</span></span>

1. <span data-ttu-id="3fb78-120">[Сбор сведений о издателе.](#gather-publisher-details)</span><span class="sxs-lookup"><span data-stu-id="3fb78-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="3fb78-121">Откройте билет с компьютеры, управляемые Майкрософт операций, чтобы запросить правило подписавщика и включив следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="3fb78-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="3fb78-122">Имя приложения</span><span class="sxs-lookup"><span data-stu-id="3fb78-122">Application name</span></span> 
    - <span data-ttu-id="3fb78-123">Версия приложения</span><span class="sxs-lookup"><span data-stu-id="3fb78-123">Application version</span></span> 
    - <span data-ttu-id="3fb78-124">Описание</span><span class="sxs-lookup"><span data-stu-id="3fb78-124">Description</span></span> 
    - <span data-ttu-id="3fb78-125">Изменение типа ("добавить" или "удалить")</span><span class="sxs-lookup"><span data-stu-id="3fb78-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="3fb78-126">Publisher (например: "O= <publisher name> ,L= <location> ,S=State,C=Country")</span><span class="sxs-lookup"><span data-stu-id="3fb78-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="3fb78-127">Чтобы удалить доверие для приложения, выполните те же действия, но установите тип **Изменения,** чтобы *удалить*.</span><span class="sxs-lookup"><span data-stu-id="3fb78-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="3fb78-128">Операции будут постепенно развертывать политики в группах развертывания по следующему расписанию:</span><span class="sxs-lookup"><span data-stu-id="3fb78-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="3fb78-129">Группа развертывания</span><span class="sxs-lookup"><span data-stu-id="3fb78-129">Deployment group</span></span>  |<span data-ttu-id="3fb78-130">Тип политики</span><span class="sxs-lookup"><span data-stu-id="3fb78-130">Policy type</span></span>  |<span data-ttu-id="3fb78-131">Время</span><span class="sxs-lookup"><span data-stu-id="3fb78-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="3fb78-132">Тест</span><span class="sxs-lookup"><span data-stu-id="3fb78-132">Test</span></span>     |  <span data-ttu-id="3fb78-133">Аудит</span><span class="sxs-lookup"><span data-stu-id="3fb78-133">Audit</span></span>       |  <span data-ttu-id="3fb78-134">День 0</span><span class="sxs-lookup"><span data-stu-id="3fb78-134">Day 0</span></span>       |
|<span data-ttu-id="3fb78-135">Первый</span><span class="sxs-lookup"><span data-stu-id="3fb78-135">First</span></span>     | <span data-ttu-id="3fb78-136">Enforced</span><span class="sxs-lookup"><span data-stu-id="3fb78-136">Enforced</span></span>        | <span data-ttu-id="3fb78-137">День 1</span><span class="sxs-lookup"><span data-stu-id="3fb78-137">Day 1</span></span>        |
|<span data-ttu-id="3fb78-138">Быстро</span><span class="sxs-lookup"><span data-stu-id="3fb78-138">Fast</span></span>     | <span data-ttu-id="3fb78-139">Enforced</span><span class="sxs-lookup"><span data-stu-id="3fb78-139">Enforced</span></span>        |  <span data-ttu-id="3fb78-140">День 2</span><span class="sxs-lookup"><span data-stu-id="3fb78-140">Day 2</span></span>       |
|<span data-ttu-id="3fb78-141">Общие</span><span class="sxs-lookup"><span data-stu-id="3fb78-141">Broad</span></span>     | <span data-ttu-id="3fb78-142">Enforced</span><span class="sxs-lookup"><span data-stu-id="3fb78-142">Enforced</span></span>        |  <span data-ttu-id="3fb78-143">День 3</span><span class="sxs-lookup"><span data-stu-id="3fb78-143">Day 3</span></span>       |


<span data-ttu-id="3fb78-144">Развертывание можно приостановить или откатать в любое время во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="3fb78-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="3fb78-145">Для этого откройте еще один запрос службы в Operations.</span><span class="sxs-lookup"><span data-stu-id="3fb78-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="3fb78-146">Если приостановить выпуск правила подписаного знака, это правило необходимо либо откатить, либо завершить до начала очередного выката.</span><span class="sxs-lookup"><span data-stu-id="3fb78-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="3fb78-147">Сбор сведений об издателе</span><span class="sxs-lookup"><span data-stu-id="3fb78-147">Gather publisher details</span></span>

<span data-ttu-id="3fb78-148">Чтобы получить доступ к данным издателя для приложения, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3fb78-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="3fb78-149">Найдите компьютеры, управляемые Майкрософт в тестовом ринге с примененной политикой режима аудита.</span><span class="sxs-lookup"><span data-stu-id="3fb78-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="3fb78-150">Попытка установки приложения на устройстве.</span><span class="sxs-lookup"><span data-stu-id="3fb78-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="3fb78-151">Откройте viewer события на этом устройстве.</span><span class="sxs-lookup"><span data-stu-id="3fb78-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="3fb78-152">В viewer событий перейдите в журналы приложений и **служб\Microsoft\Windows,** а затем выберите **AppLocker**.</span><span class="sxs-lookup"><span data-stu-id="3fb78-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="3fb78-153">Найдите любое **событие 8003** или **8006,** а затем скопируйте сведения из события:</span><span class="sxs-lookup"><span data-stu-id="3fb78-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="3fb78-154">Имя приложения</span><span class="sxs-lookup"><span data-stu-id="3fb78-154">Application name</span></span> 
    - <span data-ttu-id="3fb78-155">Версия приложения</span><span class="sxs-lookup"><span data-stu-id="3fb78-155">Application version</span></span> 
    - <span data-ttu-id="3fb78-156">Описание</span><span class="sxs-lookup"><span data-stu-id="3fb78-156">Description</span></span> 
    - <span data-ttu-id="3fb78-157">Publisher (например: "O= <publisher name> , L= <location> , S=State, C=Country")</span><span class="sxs-lookup"><span data-stu-id="3fb78-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span>