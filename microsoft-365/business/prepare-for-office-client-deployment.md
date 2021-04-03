---
title: Подготовка к развертыванию клиентов Office в Microsoft 365 для бизнеса
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Узнайте, как автоматически устанавливать 32-битные приложения Office на компьютерах Windows 10 и обновлять их.
ms.openlocfilehash: 868d06fadfef0f55b41131b7fdfbb368b9128405
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580061"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a><span data-ttu-id="c2ba2-103">Подготовка к развертыванию клиентов Office в Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c2ba2-103">Prepare for Office client deployment by Microsoft 365 for business</span></span>

<span data-ttu-id="c2ba2-104">Эта статья применима к Microsoft 365 Бизнес Премиум.</span><span class="sxs-lookup"><span data-stu-id="c2ba2-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="c2ba2-105">Подготовка к автоматической установке приложений Office на клиентские компьютеры</span><span class="sxs-lookup"><span data-stu-id="c2ba2-105">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="c2ba2-106">С помощью Microsoft 365 Бизнес Премиум можно автоматически установить 32-битные приложения Office на компьютерах Windows 10 и сохранить их в курсе обновлений.</span><span class="sxs-lookup"><span data-stu-id="c2ba2-106">You can use Microsoft 365 Business Premium to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="c2ba2-107">Автоматическая установка лучше всего работает, если компьютер пользователя находится на Windows 10 Business и:</span><span class="sxs-lookup"><span data-stu-id="c2ba2-107">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="c2ba2-108">не установлены классические приложения Office (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access и OneDrive)</span><span class="sxs-lookup"><span data-stu-id="c2ba2-108">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="c2ba2-109">или</span><span class="sxs-lookup"><span data-stu-id="c2ba2-109">or</span></span>
    
- <span data-ttu-id="c2ba2-110">установлена версия Office "нажми и работай".</span><span class="sxs-lookup"><span data-stu-id="c2ba2-110">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="c2ba2-111">Чтобы определить, есть ли на компьютере версия Office "нажми и работай", в любом приложении Office выберите **Файл** \> **Учетная запись** (в Outlook: **Учетная запись Office**).</span><span class="sxs-lookup"><span data-stu-id="c2ba2-111">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="c2ba2-112">Если вы видите **обновления Office,** как показано на следующем рисунке, то установка была сделана с помощью click-to-Run.</span><span class="sxs-lookup"><span data-stu-id="c2ba2-112">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="c2ba2-114">**Кому выгодна эта функция**</span><span class="sxs-lookup"><span data-stu-id="c2ba2-114">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="c2ba2-115">Пользователю, компьютер которого удовлетворяет указанным ниже условиям.</span><span class="sxs-lookup"><span data-stu-id="c2ba2-115">The end user whose PC:</span></span>
  
- <span data-ttu-id="c2ba2-116">**Имеет**  лицензию пользователя Windows 10 Business, активную microsoft 365 для бизнес-лицензии, Windows 10 Creators Update и присоединяется к Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c2ba2-116">**Has**  a Windows 10 Business user license, an active Microsoft 365 for business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="c2ba2-117">**Не имеет** 64-битных приложений Office (например: Word, Excel, PowerPoint).</span><span class="sxs-lookup"><span data-stu-id="c2ba2-117">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="c2ba2-118">Если требуются 64-битные приложения Office, то эта функция не подходит, так как нет поддержки для запуска 64-битной версии Office 2016 click-to-Run из консоли Microsoft 365 для бизнес-администратора.</span><span class="sxs-lookup"><span data-stu-id="c2ba2-118">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 for business admin console.</span></span> 
    
- <span data-ttu-id="c2ba2-119">На нем **нет** автономных приложений версии 2016, установленных с помощью установщика Windows Installer (MSI) (например, Visio или Project).</span><span class="sxs-lookup"><span data-stu-id="c2ba2-119">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="c2ba2-120">Microsoft 365 для бизнеса обновляет Office до версии Office 2016 и не работает с автономными приложениями MSI Office 2016.</span><span class="sxs-lookup"><span data-stu-id="c2ba2-120">Microsoft 365 for business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="c2ba2-121">В следующей таблице показано, какие действия могут потребоваться конечным пользователям и администраторам в зависимости от их состояния, чтобы иметь успешную 32-битную 32-битную версию развертывания Office из консоли Microsoft 365 для бизнес-администратора.</span><span class="sxs-lookup"><span data-stu-id="c2ba2-121">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 for business admin console.</span></span>
  
|<span data-ttu-id="c2ba2-122">**Начальное состояние экземпляра Office**</span><span class="sxs-lookup"><span data-stu-id="c2ba2-122">**Starting Office install status**</span></span>|<span data-ttu-id="c2ba2-123">**Действия, которые необходимо принять перед установкой Microsoft 365 для бизнеса Office**</span><span class="sxs-lookup"><span data-stu-id="c2ba2-123">**Action to take before Microsoft 365 for business Office install**</span></span>|<span data-ttu-id="c2ba2-124">**Конечное состояние**</span><span class="sxs-lookup"><span data-stu-id="c2ba2-124">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c2ba2-125">Набор Office не установлен</span><span class="sxs-lookup"><span data-stu-id="c2ba2-125">No Office suite installed</span></span>  <br/> |<span data-ttu-id="c2ba2-126">Нет</span><span class="sxs-lookup"><span data-stu-id="c2ba2-126">None</span></span>  <br/> |<span data-ttu-id="c2ba2-127">Office 2016 32-bit устанавливается с помощью click-to-Run</span><span class="sxs-lookup"><span data-stu-id="c2ba2-127">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="c2ba2-128">Есть 32-разрядная версия Office "нажми и работай" (2016 или более ранняя), но нет автономных приложений</span><span class="sxs-lookup"><span data-stu-id="c2ba2-128">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="c2ba2-129">Нет</span><span class="sxs-lookup"><span data-stu-id="c2ba2-129">None</span></span>  <br/> |<span data-ttu-id="c2ba2-130">Выполнено обновление до последней 32-разрядной версии Office 2016 "нажми и работай", если необходимо **\***</span><span class="sxs-lookup"><span data-stu-id="c2ba2-130">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="c2ba2-131">Существующие 32-битные версии Office и Click-to-Run 32-bit или 64-bit автономных приложений Office (например, Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="c2ba2-131">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="c2ba2-132">Нет</span><span class="sxs-lookup"><span data-stu-id="c2ba2-132">None</span></span>  <br/> |<span data-ttu-id="c2ba2-133">Автономные приложения не затронуты.</span><span class="sxs-lookup"><span data-stu-id="c2ba2-133">Standalone apps aren't affected.</span></span> <span data-ttu-id="c2ba2-134">Набор обновлен до 32-разрядной версии Office 2016 "нажми и работай"</span><span class="sxs-lookup"><span data-stu-id="c2ba2-134">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="c2ba2-135">Есть 32-разрядная версия Office "нажми и работай", а также любые 32- или 64-разрядные автономные MSI-приложения Office (кроме версии 2016)</span><span class="sxs-lookup"><span data-stu-id="c2ba2-135">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="c2ba2-136">Нет</span><span class="sxs-lookup"><span data-stu-id="c2ba2-136">None</span></span>  <br/> |<span data-ttu-id="c2ba2-137">Автономные приложения не затронуты.</span><span class="sxs-lookup"><span data-stu-id="c2ba2-137">Standalone apps aren't affected.</span></span> <span data-ttu-id="c2ba2-138">Набор обновлен до 32-разрядной версии Office 2016 "нажми и работай"</span><span class="sxs-lookup"><span data-stu-id="c2ba2-138">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="c2ba2-139">Есть любая 64-разрядная версия Office "нажми и работай"</span><span class="sxs-lookup"><span data-stu-id="c2ba2-139">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="c2ba2-140">Удалить 64-битные приложения Office, если их можно заменить 32-битными приложениями Office</span><span class="sxs-lookup"><span data-stu-id="c2ba2-140">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="c2ba2-141">При удалении 64-разрядных приложений Office устанавливается 32-разрядная версия Office 2016 "нажми и работай".</span><span class="sxs-lookup"><span data-stu-id="c2ba2-141">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="c2ba2-142">Есть MSI-версия Office 2016 при наличии или отсутствии автономных приложений</span><span class="sxs-lookup"><span data-stu-id="c2ba2-142">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="c2ba2-143">Удалите MSI-версию Office 2016.</span><span class="sxs-lookup"><span data-stu-id="c2ba2-143">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="c2ba2-p106">Установлена 32-разрядная версия Office 2016 "нажми и работай". Автономные приложения  без изменений.</span><span class="sxs-lookup"><span data-stu-id="c2ba2-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="c2ba2-146">Есть MSI-версия Office 2013 (или более ранней версии) при наличии или отсутствии автономных приложений Office</span><span class="sxs-lookup"><span data-stu-id="c2ba2-146">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="c2ba2-147">Нет</span><span class="sxs-lookup"><span data-stu-id="c2ba2-147">None</span></span>  <br/> |<span data-ttu-id="c2ba2-148">Сосуществуют 32-разрядная версия Office 2016 "нажми и работай" и предустановленная MSI-версия Office (и автономные приложения)</span><span class="sxs-lookup"><span data-stu-id="c2ba2-148">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="c2ba2-149">**( \* Примечание.** Не обновляется до 32-битной версии Office 2016 из-за известной ошибки.</span><span class="sxs-lookup"><span data-stu-id="c2ba2-149">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="c2ba2-150">Исправление продолжается.</span><span class="sxs-lookup"><span data-stu-id="c2ba2-150">A fix is in progress.</span></span> 
  
