---
title: Подготовка к развертыванию Office для клиента с помощью Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Узнайте, как автоматически установить 32 приложения Office на компьютеры с Windows 10 и оставить их обновленными.
ms.openlocfilehash: c8e93746b89925d6b6a928a474fe5736e2834987
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286665"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a><span data-ttu-id="dced0-103">Подготовка к развертыванию Office для клиента с помощью Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="dced0-103">Prepare for Office client deployment by Microsoft 365 Business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="dced0-104">Подготовка к автоматической установке приложений Office на клиентские компьютеры</span><span class="sxs-lookup"><span data-stu-id="dced0-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="dced0-105">С помощью Office 365 бизнес можно автоматически устанавливать 32-разрядные приложения Office и их последующие обновления на компьютеры с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="dced0-105">You can use Microsoft 365 Business to automatically install the 32-bit Office apps to Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="dced0-106">Это лучше всего работает на пользовательском компьютере с Windows 10, на котором:</span><span class="sxs-lookup"><span data-stu-id="dced0-106">This works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="dced0-107">не установлены классические приложения Office (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access и OneDrive)</span><span class="sxs-lookup"><span data-stu-id="dced0-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="dced0-108">или</span><span class="sxs-lookup"><span data-stu-id="dced0-108">or</span></span>
    
- <span data-ttu-id="dced0-109">установлена версия Office "нажми и работай".</span><span class="sxs-lookup"><span data-stu-id="dced0-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="dced0-p101">Чтобы определить, есть ли на компьютере версия Office "нажми и работай", в любом приложении Office выберите **Файл** \> **Учетная запись** (в Outlook: **Учетная запись Office**). Если вы видите элемент "Обновления Office", показанный на рисунке ниже, при установке использовалась технология "нажми и работай".</span><span class="sxs-lookup"><span data-stu-id="dced0-p101">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook). If you see Office Updates as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="dced0-113">**Кому будет полезна эта функция?**</span><span class="sxs-lookup"><span data-stu-id="dced0-113">**Who will benefit from having this feature**</span></span>
  
<span data-ttu-id="dced0-114">Пользователю, компьютер которого удовлетворяет указанным ниже условиям.</span><span class="sxs-lookup"><span data-stu-id="dced0-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="dced0-115">На нем **есть** пользовательская лицензия Windows 10 для бизнеса, активная лицензия Office 365 бизнес, обновление Windows 10 Creators Update и он подключен к Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dced0-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 Business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="dced0-p102">На нем **нет** 64-разрядных приложений Office (например, Word, Excel или Powerpoint). Если вам необходимы 64-разрядные приложения Office, лучше не использовать эту функцию, поскольку не существует поддержки для запуска 64-разрядной версии Office 2016 "нажми и работай" из консоли администрирования Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="dced0-p102">**Doesn't have** 64-bit Office apps (example: Word, Excel, Powerpoint). If 64-bit Office apps are required, then this feature is not a good fit because there is no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 Business admin console.</span></span> 
    
- <span data-ttu-id="dced0-p103">На нем **нет** автономных приложений версии 2016, установленных с помощью установщика Windows Installer (MSI) (например, Visio или Project). Office 365 бизнес обновляет Office до версии Office 2016 "нажми и работай", но это не сработает с автономными MSI-приложениями Office 2016.</span><span class="sxs-lookup"><span data-stu-id="dced0-p103">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project). Microsoft 365 Business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="dced0-120">В таблице ниже указаны действия, которые в зависимости от начального состояния системы может потребоваться выполнить пользователям или администраторам, чтобы успешно развернуть 32-разрядную версию Office "нажми и работай" с консоли администрирования Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="dced0-120">The following table details what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 Business admin console.</span></span>
  
|<span data-ttu-id="dced0-121">**Начальное состояние экземпляра Office**</span><span class="sxs-lookup"><span data-stu-id="dced0-121">**Starting Office install status**</span></span>|<span data-ttu-id="dced0-122">**Необходимое действие перед установкой Office 365 бизнес Office**</span><span class="sxs-lookup"><span data-stu-id="dced0-122">**Action to take before Microsoft 365 Business Office install**</span></span>|<span data-ttu-id="dced0-123">**Конечное состояние**</span><span class="sxs-lookup"><span data-stu-id="dced0-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dced0-124">Набор Office не установлен</span><span class="sxs-lookup"><span data-stu-id="dced0-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="dced0-125">Нет</span><span class="sxs-lookup"><span data-stu-id="dced0-125">None</span></span>  <br/> |<span data-ttu-id="dced0-126">Установлена 32-разрядная версия Office 2016 с помощью технологии "нажми и работай"</span><span class="sxs-lookup"><span data-stu-id="dced0-126">Office 2016 32-bit is installed by using click-to-run</span></span>  <br/> |
|<span data-ttu-id="dced0-127">Есть 32-разрядная версия Office "нажми и работай" (2016 или более ранняя), но нет автономных приложений</span><span class="sxs-lookup"><span data-stu-id="dced0-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="dced0-128">Нет</span><span class="sxs-lookup"><span data-stu-id="dced0-128">None</span></span>  <br/> |<span data-ttu-id="dced0-129">Выполнено обновление до последней 32-разрядной версии Office 2016 "нажми и работай", если необходимо **\***</span><span class="sxs-lookup"><span data-stu-id="dced0-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="dced0-130">Есть 32-разрядная версия Office "нажми и работай", а также 32- или 64-разрядные автономные приложения Office "нажми и работай" (например, Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="dced0-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32- or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="dced0-131">Нет</span><span class="sxs-lookup"><span data-stu-id="dced0-131">None</span></span>  <br/> |<span data-ttu-id="dced0-p104">Автономные приложения  без изменений. Набор обновлен до 32-разрядной версии Office 2016 "нажми и работай"</span><span class="sxs-lookup"><span data-stu-id="dced0-p104">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="dced0-134">Есть 32-разрядная версия Office "нажми и работай", а также любые 32- или 64-разрядные автономные MSI-приложения Office (кроме версии 2016)</span><span class="sxs-lookup"><span data-stu-id="dced0-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="dced0-135">Нет</span><span class="sxs-lookup"><span data-stu-id="dced0-135">None</span></span>  <br/> |<span data-ttu-id="dced0-p105">Автономные приложения  без изменений. Набор обновлен до 32-разрядной версии Office 2016 "нажми и работай"</span><span class="sxs-lookup"><span data-stu-id="dced0-p105">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="dced0-138">Есть любая 64-разрядная версия Office "нажми и работай"</span><span class="sxs-lookup"><span data-stu-id="dced0-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="dced0-139">Удалите 64-разрядные приложения Office, если готовы перейти на 32-разрядные.</span><span class="sxs-lookup"><span data-stu-id="dced0-139">Uninstall the 64-bit Office apps, if it is OK to replace it with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="dced0-140">При удалении 64-разрядных приложений Office устанавливается 32-разрядная версия Office 2016 "нажми и работай".</span><span class="sxs-lookup"><span data-stu-id="dced0-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="dced0-141">Есть MSI-версия Office 2016 при наличии или отсутствии автономных приложений</span><span class="sxs-lookup"><span data-stu-id="dced0-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="dced0-142">Удалите MSI-версию Office 2016.</span><span class="sxs-lookup"><span data-stu-id="dced0-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="dced0-p106">Установлена 32-разрядная версия Office 2016 "нажми и работай". Автономные приложения  без изменений.</span><span class="sxs-lookup"><span data-stu-id="dced0-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="dced0-145">Есть MSI-версия Office 2013 (или более ранней версии) при наличии или отсутствии автономных приложений Office</span><span class="sxs-lookup"><span data-stu-id="dced0-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="dced0-146">Нет</span><span class="sxs-lookup"><span data-stu-id="dced0-146">None</span></span>  <br/> |<span data-ttu-id="dced0-147">Сосуществуют 32-разрядная версия Office 2016 "нажми и работай" и предустановленная MSI-версия Office (и автономные приложения)</span><span class="sxs-lookup"><span data-stu-id="dced0-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="dced0-p107">**\* Примечание.** Не обновляется до 32-разрядной версии Office 2016 "нажми и работай" из-за известной ошибки. Идет работа над исправлением.</span><span class="sxs-lookup"><span data-stu-id="dced0-p107">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug. Fix is in progress.</span></span> 
  


