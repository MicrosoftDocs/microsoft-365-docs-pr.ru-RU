---
title: Получите поддержку пользователей для компьютеры, управляемые Майкрософт
description: Как пользователи могут получать помощь с помощью службы и устройств
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eea02b0a891f65ccd7e4e993ca719b0f3aa1b8b
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362610"
---
# <a name="getting-help-for-users"></a><span data-ttu-id="90d05-104">Получение справки для пользователей</span><span class="sxs-lookup"><span data-stu-id="90d05-104">Getting help for users</span></span>

<span data-ttu-id="90d05-105">Если вы достигли точки [](../service-description/user-support.md) рабочего процесса, в которой необходимо запросить повышенный доступ к устройству или эскалацию в Корпорацию Майкрософт, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="90d05-105">If you've reached the point in the [workflow](../service-description/user-support.md) where you need to request elevated device access or escalation to Microsoft, follow these steps:</span></span>
 
>[!NOTE]
><span data-ttu-id="90d05-106">Эти параметры поддержки недоступны для устройств в группе Test.</span><span class="sxs-lookup"><span data-stu-id="90d05-106">These support options are not available for devices in the Test group.</span></span>

## <a name="elevation-requests"></a><span data-ttu-id="90d05-107">Запросы на повышение</span><span class="sxs-lookup"><span data-stu-id="90d05-107">Elevation requests</span></span>

<span data-ttu-id="90d05-108">Прежде чем запрашивать повышенный доступ к устройству, лучше всего просмотреть, какие действия наиболее подходят.</span><span class="sxs-lookup"><span data-stu-id="90d05-108">Before you request elevated access to a device, it's best to review which actions are best suited.</span></span>

- <span data-ttu-id="90d05-109">**Типичные** действия — это то, для чего этот процесс предназначен и будет выполняться регулярно при устранении проблем с компьютеры, управляемые Майкрософт устройствами.</span><span class="sxs-lookup"><span data-stu-id="90d05-109">**Typical actions** are what this process is intended for and would be performed routinely while troubleshooting problems with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="90d05-110">Вот некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="90d05-110">Examples include:</span></span>
    - <span data-ttu-id="90d05-111">Повышение уровня устранения неполадок встроенной системы, командной подсказки или Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="90d05-111">Elevating built-in system troubleshooters, the command prompt, or Windows PowerShell</span></span>
    - <span data-ttu-id="90d05-112">Устранение неполадок в бизнес-приложениях</span><span class="sxs-lookup"><span data-stu-id="90d05-112">Troubleshooting line-of-business applications</span></span>
    - <span data-ttu-id="90d05-113">Использование обходного решения для исправления того, что должно функционировать по проекту (например, активация BitLocker или не обновление системного времени)</span><span class="sxs-lookup"><span data-stu-id="90d05-113">Using a workaround to correct something that should function by design (such as BitLocker activation or system time not updating)</span></span>
    - <span data-ttu-id="90d05-114">Повышение уровня диспетчера устройств для таких функций, как обновление драйверов, удалить устройство или сканировать новые изменения</span><span class="sxs-lookup"><span data-stu-id="90d05-114">Elevating Device Manager to do things like update drivers, uninstall a device, or scan for new changes</span></span>

- <span data-ttu-id="90d05-115">**Действия, которые не рекомендуется, включают** следующие действия:</span><span class="sxs-lookup"><span data-stu-id="90d05-115">**Actions that aren't recommended** include the following:</span></span>
    - <span data-ttu-id="90d05-116">Установка программного обеспечения или браузеров</span><span class="sxs-lookup"><span data-stu-id="90d05-116">Installing software or browsers</span></span>
    - <span data-ttu-id="90d05-117">Установка драйверов вне параметров Windows, в том числе для периферийных устройств</span><span class="sxs-lookup"><span data-stu-id="90d05-117">Installing drivers outside of Windows settings, including those for peripherals</span></span>
    - <span data-ttu-id="90d05-118">Установка .msi или .exe файлов</span><span class="sxs-lookup"><span data-stu-id="90d05-118">Installing .msi or .exe files</span></span>
    - <span data-ttu-id="90d05-119">Установка Windows</span><span class="sxs-lookup"><span data-stu-id="90d05-119">Installing Windows features</span></span>

- <span data-ttu-id="90d05-120">**Действия, которые не поддерживаются,** включают следующие действия:</span><span class="sxs-lookup"><span data-stu-id="90d05-120">**Actions that aren't supported** include the following:</span></span>
    - <span data-ttu-id="90d05-121">Установка программного обеспечения или функций, которые компьютеры, управляемые Майкрософт с возможностями безопасности или управления или операциями</span><span class="sxs-lookup"><span data-stu-id="90d05-121">Installing software or features that conflict with Microsoft Managed Desktop security or management capabilities or operations</span></span>
    - <span data-ttu-id="90d05-122">Отключение Windows, необходимого для компьютеры, управляемые Майкрософт, например BitLocker</span><span class="sxs-lookup"><span data-stu-id="90d05-122">Disabling a Windows feature that is required for Microsoft Managed Desktop, such as BitLocker</span></span>
    - <span data-ttu-id="90d05-123">Изменение параметров, управляемых вашей организации</span><span class="sxs-lookup"><span data-stu-id="90d05-123">Modifying settings managed by your org</span></span>

### <a name="to-request-elevation"></a><span data-ttu-id="90d05-124">Запрос высоты</span><span class="sxs-lookup"><span data-stu-id="90d05-124">To request elevation</span></span>

1. <span data-ttu-id="90d05-125">Перейдите на портал и войдите с Azure Active Directory [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) учетными данными.</span><span class="sxs-lookup"><span data-stu-id="90d05-125">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="90d05-126">Выберите **новый запрос на повышение.**</span><span class="sxs-lookup"><span data-stu-id="90d05-126">Select **New elevation request**.</span></span>
3. <span data-ttu-id="90d05-127">Предокав эти сведения:</span><span class="sxs-lookup"><span data-stu-id="90d05-127">Provide these details:</span></span>
    - <span data-ttu-id="90d05-128">**ИД билета поддержки** из собственной системы поддержки.</span><span class="sxs-lookup"><span data-stu-id="90d05-128">**Support ticket ID** from your own support ticketing system.</span></span>
    - <span data-ttu-id="90d05-129">**Имя устройства:** введите серийный номер устройства и выберите устройство из меню.</span><span class="sxs-lookup"><span data-stu-id="90d05-129">**Device name**: enter the device serial number and then select the device from the menu.</span></span>
    - <span data-ttu-id="90d05-130">**Категория.** Выберите категорию, которая наилучшим образом соответствует вашей проблеме.</span><span class="sxs-lookup"><span data-stu-id="90d05-130">**Category**: Select the category that best fits your issue.</span></span> <span data-ttu-id="90d05-131">Если параметр не кажется близким, выберите **Другое** и предоглавь дополнительные сведения в **полях Title** и **Plan of action.**</span><span class="sxs-lookup"><span data-stu-id="90d05-131">If no option seems close, then select **Other** and provide more info in the **Title** and **Plan of action** fields.</span></span> <span data-ttu-id="90d05-132">Лучше всего выбрать категорию, если это вообще возможно.</span><span class="sxs-lookup"><span data-stu-id="90d05-132">It's best to select a category if at all possible.</span></span>
    - <span data-ttu-id="90d05-133">**Subcategory:** Выберите тот, который наилучшим образом соответствует проблеме.</span><span class="sxs-lookup"><span data-stu-id="90d05-133">**Subcategory**: Select the one that best fits the issue.</span></span> <span data-ttu-id="90d05-134">Если параметр не кажется близким, выберите **Другое** и укажи краткое описание в **Заголовке.**</span><span class="sxs-lookup"><span data-stu-id="90d05-134">If no option seems close, then select **Other** and provide a short description in **Title**.</span></span> <span data-ttu-id="90d05-135">В **Плане действий** укайте действия по устранению неполадок, которые планируется предпринять после предоставления высоты.</span><span class="sxs-lookup"><span data-stu-id="90d05-135">In **Plan of action**, provide the troubleshooting steps you plan to take once elevation is granted.</span></span>
4. <span data-ttu-id="90d05-136">Выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="90d05-136">Select **Submit**.</span></span>


## <a name="escalation-requests"></a><span data-ttu-id="90d05-137">Запросы на эскалацию</span><span class="sxs-lookup"><span data-stu-id="90d05-137">Escalation requests</span></span>


<span data-ttu-id="90d05-138">Если требуется [перенастрить проблему](../service-description/user-support.md#escalation-portal) в Корпорацию Майкрософт, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="90d05-138">If you need to [escalate](../service-description/user-support.md#escalation-portal) an issue to Microsoft, follow these steps:</span></span>

1. <span data-ttu-id="90d05-139">Перейдите на портал и войдите с Azure Active Directory [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) учетными данными.</span><span class="sxs-lookup"><span data-stu-id="90d05-139">Go to the portal at [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) and sign in with your Azure Active Directory credentials.</span></span>
2. <span data-ttu-id="90d05-140">Выберите **запросы на эскалацию,** а затем выберите **новый запрос эскалации.**</span><span class="sxs-lookup"><span data-stu-id="90d05-140">Select **Escalation requests**, and then select **New escalation request**.</span></span>
3. <span data-ttu-id="90d05-141">Предокав эти сведения:</span><span class="sxs-lookup"><span data-stu-id="90d05-141">Provide these details:</span></span>
    - <span data-ttu-id="90d05-142">**Категория.** Выберите категорию, которая наилучшим образом соответствует вашей проблеме.</span><span class="sxs-lookup"><span data-stu-id="90d05-142">**Category**: Select the category that best fits your issue.</span></span>
    - <span data-ttu-id="90d05-143">**Заголовок.** Укажи очень краткое описание.</span><span class="sxs-lookup"><span data-stu-id="90d05-143">**Title**: Provide a very brief description.</span></span>
    - <span data-ttu-id="90d05-144">**Описание.** Добавьте дополнительные сведения, которые помогут нашей команде разобраться в проблеме.</span><span class="sxs-lookup"><span data-stu-id="90d05-144">**Description**: Add any additional details that could help our team understand the problem.</span></span> <span data-ttu-id="90d05-145">Если вам нужно прикрепить файлы, вы можете сделать это, возвращаясь к запросу после отправки.</span><span class="sxs-lookup"><span data-stu-id="90d05-145">If you need to attach files, you can do that by coming back to the request after you submit it.</span></span>
    - <span data-ttu-id="90d05-146">**Основные контактные** данные. Сведения о том, как связаться с главным лицом, ответственным за работу с нашей командой.</span><span class="sxs-lookup"><span data-stu-id="90d05-146">**Primary contact information**: Provide info about how to contact the main person responsible for working with our team.</span></span>
4. <span data-ttu-id="90d05-147">Выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="90d05-147">Select **Submit**.</span></span>
5. <span data-ttu-id="90d05-148">Пересмотр билета на том же портале, чтобы взаимодействовать с нашей командой.</span><span class="sxs-lookup"><span data-stu-id="90d05-148">Revisit the ticket in the same portal to interact with our team.</span></span>

> [!NOTE]
> <span data-ttu-id="90d05-149">Только проблемы серьезности C могут быть эскалации с помощью этого пути.</span><span class="sxs-lookup"><span data-stu-id="90d05-149">Only Severity C issues can be escalated through this path.</span></span> <span data-ttu-id="90d05-150">По другим вопросам обратитесь к ИТ-администратору, чтобы подать запрос на портале Admin.</span><span class="sxs-lookup"><span data-stu-id="90d05-150">For other issues, contact your IT admin to file the request through the Admin portal.</span></span>