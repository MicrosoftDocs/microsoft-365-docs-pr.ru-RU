---
title: Подготовка к развертыванию Office для клиента с помощью Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Узнайте, как автоматически установить 32 приложения Office на компьютеры с Windows 10 и оставить их обновленными.
ms.openlocfilehash: fa5b2ce1852ebdb1e76c1fa844793fee56af3d68
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593626"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a><span data-ttu-id="7717c-103">Подготовка к развертыванию Office для клиента с помощью Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="7717c-103">Prepare for Office client deployment by Microsoft 365 Business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="7717c-104">Подготовка к автоматической установке приложений Office на клиентские компьютеры</span><span class="sxs-lookup"><span data-stu-id="7717c-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="7717c-105">Вы можете использовать Microsoft 365 Business для автоматической установки 32-разрядных приложений Office на компьютеры с Windows 10 и поддерживать их последние обновления.</span><span class="sxs-lookup"><span data-stu-id="7717c-105">You can use Microsoft 365 Business to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="7717c-106">Автоматическая установка работает лучше, если компьютер конечного пользователя включен в Windows 10 бизнес и:</span><span class="sxs-lookup"><span data-stu-id="7717c-106">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="7717c-107">не установлены классические приложения Office (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access и OneDrive)</span><span class="sxs-lookup"><span data-stu-id="7717c-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="7717c-108">или</span><span class="sxs-lookup"><span data-stu-id="7717c-108">or</span></span>
    
- <span data-ttu-id="7717c-109">установлена версия Office "нажми и работай".</span><span class="sxs-lookup"><span data-stu-id="7717c-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="7717c-110">Чтобы определить, есть ли на компьютере версия Office "нажми и работай", в любом приложении Office выберите **Файл** \> **Учетная запись** (в Outlook: **Учетная запись Office**).</span><span class="sxs-lookup"><span data-stu-id="7717c-110">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="7717c-111">Если вы видите **обновления Office** , как показано на следующем рисунке, то установка выполнялась с помощью функции "нажми и работай".</span><span class="sxs-lookup"><span data-stu-id="7717c-111">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="7717c-113">**Преимущества этой функции**</span><span class="sxs-lookup"><span data-stu-id="7717c-113">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="7717c-114">Пользователю, компьютер которого удовлетворяет указанным ниже условиям.</span><span class="sxs-lookup"><span data-stu-id="7717c-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="7717c-115">На нем **есть** пользовательская лицензия Windows 10 для бизнеса, активная лицензия Office 365 бизнес, обновление Windows 10 Creators Update и он подключен к Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7717c-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 Business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="7717c-116">**У него нет** 64-разрядных приложений Office (пример: Word, Excel, PowerPoint).</span><span class="sxs-lookup"><span data-stu-id="7717c-116">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="7717c-117">Если требуются 64-разрядные приложения Office, эта функция не подходит, так как в консоли администрирования Microsoft 365 Business вы не поддерживаете активацию 64-разрядной версии 2016 "нажми и работай".</span><span class="sxs-lookup"><span data-stu-id="7717c-117">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 Business admin console.</span></span> 
    
- <span data-ttu-id="7717c-118">На нем **нет** автономных приложений версии 2016, установленных с помощью установщика Windows Installer (MSI) (например, Visio или Project).</span><span class="sxs-lookup"><span data-stu-id="7717c-118">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="7717c-119">Microsoft 365 Business обновляет Office до версии "нажми и работай" для Office 2016 и не работает с автономными приложениями Office 2016 MSI.</span><span class="sxs-lookup"><span data-stu-id="7717c-119">Microsoft 365 Business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="7717c-120">В следующей таблице показано, какие действия могут потребоваться для пользователей и администраторов в зависимости от их начального состояния, чтобы получить успешную 32-разрядную версию развертывания Office с помощью консоли администрирования Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="7717c-120">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 Business admin console.</span></span>
  
|<span data-ttu-id="7717c-121">**Начальное состояние экземпляра Office**</span><span class="sxs-lookup"><span data-stu-id="7717c-121">**Starting Office install status**</span></span>|<span data-ttu-id="7717c-122">**Необходимое действие перед установкой Office 365 бизнес Office**</span><span class="sxs-lookup"><span data-stu-id="7717c-122">**Action to take before Microsoft 365 Business Office install**</span></span>|<span data-ttu-id="7717c-123">**Конечное состояние**</span><span class="sxs-lookup"><span data-stu-id="7717c-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7717c-124">Набор Office не установлен</span><span class="sxs-lookup"><span data-stu-id="7717c-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="7717c-125">Нет</span><span class="sxs-lookup"><span data-stu-id="7717c-125">None</span></span>  <br/> |<span data-ttu-id="7717c-126">Office 2016 32-bit устанавливается с помощью функции "нажми и работай"</span><span class="sxs-lookup"><span data-stu-id="7717c-126">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="7717c-127">Есть 32-разрядная версия Office "нажми и работай" (2016 или более ранняя), но нет автономных приложений</span><span class="sxs-lookup"><span data-stu-id="7717c-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="7717c-128">Нет</span><span class="sxs-lookup"><span data-stu-id="7717c-128">None</span></span>  <br/> |<span data-ttu-id="7717c-129">Выполнено обновление до последней 32-разрядной версии Office 2016 "нажми и работай", если необходимо **\***</span><span class="sxs-lookup"><span data-stu-id="7717c-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="7717c-130">Существующая версия Office "нажми и работай: 32-разрядная версия Office" и "нажми и работай", 32-разрядная или 64-bit автономные приложения Office (например, Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="7717c-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="7717c-131">Нет</span><span class="sxs-lookup"><span data-stu-id="7717c-131">None</span></span>  <br/> |<span data-ttu-id="7717c-132">Отдельные приложения не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="7717c-132">Standalone apps aren't affected.</span></span> <span data-ttu-id="7717c-133">Набор обновлен до 32-разрядной версии Office 2016 "нажми и работай"</span><span class="sxs-lookup"><span data-stu-id="7717c-133">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="7717c-134">Есть 32-разрядная версия Office "нажми и работай", а также любые 32- или 64-разрядные автономные MSI-приложения Office (кроме версии 2016)</span><span class="sxs-lookup"><span data-stu-id="7717c-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="7717c-135">Нет</span><span class="sxs-lookup"><span data-stu-id="7717c-135">None</span></span>  <br/> |<span data-ttu-id="7717c-136">Отдельные приложения не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="7717c-136">Standalone apps aren't affected.</span></span> <span data-ttu-id="7717c-137">Набор обновлен до 32-разрядной версии Office 2016 "нажми и работай"</span><span class="sxs-lookup"><span data-stu-id="7717c-137">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="7717c-138">Есть любая 64-разрядная версия Office "нажми и работай"</span><span class="sxs-lookup"><span data-stu-id="7717c-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="7717c-139">Удалите 64 приложений Office, если их можно заменить на 32 — разрядные приложения Office</span><span class="sxs-lookup"><span data-stu-id="7717c-139">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="7717c-140">При удалении 64-разрядных приложений Office устанавливается 32-разрядная версия Office 2016 "нажми и работай".</span><span class="sxs-lookup"><span data-stu-id="7717c-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="7717c-141">Есть MSI-версия Office 2016 при наличии или отсутствии автономных приложений</span><span class="sxs-lookup"><span data-stu-id="7717c-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="7717c-142">Удалите MSI-версию Office 2016.</span><span class="sxs-lookup"><span data-stu-id="7717c-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="7717c-p106">Установлена 32-разрядная версия Office 2016 "нажми и работай". Автономные приложения  без изменений.</span><span class="sxs-lookup"><span data-stu-id="7717c-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="7717c-145">Есть MSI-версия Office 2013 (или более ранней версии) при наличии или отсутствии автономных приложений Office</span><span class="sxs-lookup"><span data-stu-id="7717c-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="7717c-146">Нет</span><span class="sxs-lookup"><span data-stu-id="7717c-146">None</span></span>  <br/> |<span data-ttu-id="7717c-147">Сосуществуют 32-разрядная версия Office 2016 "нажми и работай" и предустановленная MSI-версия Office (и автономные приложения)</span><span class="sxs-lookup"><span data-stu-id="7717c-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="7717c-148">**(\*) Примечание:** Обновление до "нажми и работай" до "нажми и работай" для 32-разрядной версии Office 2016 из-за известной ошибки.</span><span class="sxs-lookup"><span data-stu-id="7717c-148">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="7717c-149">Выполняется исправление.</span><span class="sxs-lookup"><span data-stu-id="7717c-149">A fix is in progress.</span></span> 
  