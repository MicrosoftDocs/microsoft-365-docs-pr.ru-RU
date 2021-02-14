---
title: Подготовка к развертыванию клиента Office с помощью Microsoft 365 для бизнеса
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Узнайте, как автоматически устанавливать 32-битные приложения Office на компьютерах с Windows 10 и обновлять их.
ms.openlocfilehash: 2de492914edbde2afe593aac290c4a634b801443
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470954"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a><span data-ttu-id="1eeb2-103">Подготовка к развертыванию клиента Office с помощью Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="1eeb2-103">Prepare for Office client deployment by Microsoft 365 for business</span></span>

<span data-ttu-id="1eeb2-104">Эта статья относится к Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="1eeb2-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="1eeb2-105">Подготовка к автоматической установке приложений Office на клиентские компьютеры</span><span class="sxs-lookup"><span data-stu-id="1eeb2-105">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="1eeb2-106">Microsoft 365 бизнес премиум можно использовать для автоматической установки 32-битных приложений Office на компьютерах с Windows 10 и обновлениями.</span><span class="sxs-lookup"><span data-stu-id="1eeb2-106">You can use Microsoft 365 Business Premium to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="1eeb2-107">Автоматическая установка лучше всего работает, если компьютер пользователя находится в Windows 10 бизнес и:</span><span class="sxs-lookup"><span data-stu-id="1eeb2-107">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="1eeb2-108">не установлены классические приложения Office (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access и OneDrive)</span><span class="sxs-lookup"><span data-stu-id="1eeb2-108">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="1eeb2-109">или</span><span class="sxs-lookup"><span data-stu-id="1eeb2-109">or</span></span>
    
- <span data-ttu-id="1eeb2-110">установлена версия Office "нажми и работай".</span><span class="sxs-lookup"><span data-stu-id="1eeb2-110">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="1eeb2-111">Чтобы определить, есть ли на компьютере версия Office "нажми и работай", в любом приложении Office выберите **Файл** \> **Учетная запись** (в Outlook: **Учетная запись Office**).</span><span class="sxs-lookup"><span data-stu-id="1eeb2-111">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="1eeb2-112">Если вы видите **обновления Office,** как показано на следующем рисунке, установка была сделана с помощью "нажми и работай".</span><span class="sxs-lookup"><span data-stu-id="1eeb2-112">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="1eeb2-114">**Преимущества этой функции**</span><span class="sxs-lookup"><span data-stu-id="1eeb2-114">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="1eeb2-115">Пользователю, компьютер которого удовлетворяет указанным ниже условиям.</span><span class="sxs-lookup"><span data-stu-id="1eeb2-115">The end user whose PC:</span></span>
  
- <span data-ttu-id="1eeb2-116">**Имеет**  пользовательской лицензии на Windows 10 для бизнеса, активную лицензию Microsoft 365 для бизнеса, Windows 10 Creators Update и присоединяется к Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1eeb2-116">**Has**  a Windows 10 Business user license, an active Microsoft 365 for business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="1eeb2-117">**Не имеет** 64-битных приложений Office (например, Word, Excel, PowerPoint).</span><span class="sxs-lookup"><span data-stu-id="1eeb2-117">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="1eeb2-118">Если требуются 64-битные приложения Office, эта функция не подходит, так как не поддерживается запуск 64-битной версии Office "нажми и нажми и выйди" из консоли администрирования Microsoft 365 для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1eeb2-118">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 for business admin console.</span></span> 
    
- <span data-ttu-id="1eeb2-119">На нем **нет** автономных приложений версии 2016, установленных с помощью установщика Windows Installer (MSI) (например, Visio или Project).</span><span class="sxs-lookup"><span data-stu-id="1eeb2-119">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="1eeb2-120">Microsoft 365 для бизнеса обновляет Office до версии Office 2016 "нажми и работай" и не работает с автономными приложениями Office 2016 MSI.</span><span class="sxs-lookup"><span data-stu-id="1eeb2-120">Microsoft 365 for business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="1eeb2-121">В следующей таблице показано, какие действия могут потребоваться конечным пользователям или администраторам в зависимости от их состояния, чтобы успешно выполнить развертывание Office с использованием технологии "нажми и выйдай" из консоли администрирования Microsoft 365 для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1eeb2-121">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 for business admin console.</span></span>
  
|<span data-ttu-id="1eeb2-122">**Начальное состояние экземпляра Office**</span><span class="sxs-lookup"><span data-stu-id="1eeb2-122">**Starting Office install status**</span></span>|<span data-ttu-id="1eeb2-123">**Действие перед установкой Microsoft 365 для бизнеса Office**</span><span class="sxs-lookup"><span data-stu-id="1eeb2-123">**Action to take before Microsoft 365 for business Office install**</span></span>|<span data-ttu-id="1eeb2-124">**Конечное состояние**</span><span class="sxs-lookup"><span data-stu-id="1eeb2-124">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1eeb2-125">Набор Office не установлен</span><span class="sxs-lookup"><span data-stu-id="1eeb2-125">No Office suite installed</span></span>  <br/> |<span data-ttu-id="1eeb2-126">Нет</span><span class="sxs-lookup"><span data-stu-id="1eeb2-126">None</span></span>  <br/> |<span data-ttu-id="1eeb2-127">32-битная система Office 2016 устанавливается с помощью "нажми и нажми и запускай"</span><span class="sxs-lookup"><span data-stu-id="1eeb2-127">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="1eeb2-128">Есть 32-разрядная версия Office "нажми и работай" (2016 или более ранняя), но нет автономных приложений</span><span class="sxs-lookup"><span data-stu-id="1eeb2-128">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="1eeb2-129">Нет</span><span class="sxs-lookup"><span data-stu-id="1eeb2-129">None</span></span>  <br/> |<span data-ttu-id="1eeb2-130">Выполнено обновление до последней 32-разрядной версии Office 2016 "нажми и работай", если необходимо **\***</span><span class="sxs-lookup"><span data-stu-id="1eeb2-130">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="1eeb2-131">Существующие 32-битные версии Office "нажми и нажми и запуск" 32- или 64-битных автономных приложений Office (например, Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="1eeb2-131">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="1eeb2-132">Нет</span><span class="sxs-lookup"><span data-stu-id="1eeb2-132">None</span></span>  <br/> |<span data-ttu-id="1eeb2-133">Автономные приложения не затронуты.</span><span class="sxs-lookup"><span data-stu-id="1eeb2-133">Standalone apps aren't affected.</span></span> <span data-ttu-id="1eeb2-134">Набор обновлен до 32-разрядной версии Office 2016 "нажми и работай"</span><span class="sxs-lookup"><span data-stu-id="1eeb2-134">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="1eeb2-135">Есть 32-разрядная версия Office "нажми и работай", а также любые 32- или 64-разрядные автономные MSI-приложения Office (кроме версии 2016)</span><span class="sxs-lookup"><span data-stu-id="1eeb2-135">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="1eeb2-136">Нет</span><span class="sxs-lookup"><span data-stu-id="1eeb2-136">None</span></span>  <br/> |<span data-ttu-id="1eeb2-137">Автономные приложения не затронуты.</span><span class="sxs-lookup"><span data-stu-id="1eeb2-137">Standalone apps aren't affected.</span></span> <span data-ttu-id="1eeb2-138">Набор обновлен до 32-разрядной версии Office 2016 "нажми и работай"</span><span class="sxs-lookup"><span data-stu-id="1eeb2-138">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="1eeb2-139">Есть любая 64-разрядная версия Office "нажми и работай"</span><span class="sxs-lookup"><span data-stu-id="1eeb2-139">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="1eeb2-140">Удалить 64-битные приложения Office, если их можно заменить 32-битными приложениями Office</span><span class="sxs-lookup"><span data-stu-id="1eeb2-140">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="1eeb2-141">При удалении 64-разрядных приложений Office устанавливается 32-разрядная версия Office 2016 "нажми и работай".</span><span class="sxs-lookup"><span data-stu-id="1eeb2-141">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="1eeb2-142">Есть MSI-версия Office 2016 при наличии или отсутствии автономных приложений</span><span class="sxs-lookup"><span data-stu-id="1eeb2-142">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="1eeb2-143">Удалите MSI-версию Office 2016.</span><span class="sxs-lookup"><span data-stu-id="1eeb2-143">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="1eeb2-p106">Установлена 32-разрядная версия Office 2016 "нажми и работай". Автономные приложения  без изменений.</span><span class="sxs-lookup"><span data-stu-id="1eeb2-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="1eeb2-146">Есть MSI-версия Office 2013 (или более ранней версии) при наличии или отсутствии автономных приложений Office</span><span class="sxs-lookup"><span data-stu-id="1eeb2-146">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="1eeb2-147">Нет</span><span class="sxs-lookup"><span data-stu-id="1eeb2-147">None</span></span>  <br/> |<span data-ttu-id="1eeb2-148">Сосуществуют 32-разрядная версия Office 2016 "нажми и работай" и предустановленная MSI-версия Office (и автономные приложения)</span><span class="sxs-lookup"><span data-stu-id="1eeb2-148">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="1eeb2-149">**( \* Примечание.** Не обновляется до 32-битной версии Office 2016 "нажми и работы" из-за известной ошибки.</span><span class="sxs-lookup"><span data-stu-id="1eeb2-149">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="1eeb2-150">Исправление уже идет.</span><span class="sxs-lookup"><span data-stu-id="1eeb2-150">A fix is in progress.</span></span> 
  
