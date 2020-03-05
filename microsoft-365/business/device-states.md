---
title: Состояния устройств
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Сведения о различных состояниях устройств в списке действия устройств в домашней странице администрирования Microsoft 365 бизнес.
ms.openlocfilehash: cb1e5172a6e2d0bfc5748fe982024ead26e8cd62
ms.sourcegitcommit: d6c871bf3f94d9299d22695f5dbaf25dc1bd6ff9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "42417323"
---
# <a name="device-states"></a><span data-ttu-id="89564-103">Состояния устройств</span><span class="sxs-lookup"><span data-stu-id="89564-103">Device states</span></span>

<span data-ttu-id="89564-104">Устройства в списке **Действия устройств** (домашняя страница администратора \> **Действия устройств**) могут находиться в перечисленных ниже состояниях.</span><span class="sxs-lookup"><span data-stu-id="89564-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="89564-106">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="89564-106">**Status**</span></span>|<span data-ttu-id="89564-107">**Описание**</span><span class="sxs-lookup"><span data-stu-id="89564-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="89564-108">Под управлением Intune</span><span class="sxs-lookup"><span data-stu-id="89564-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="89564-109">Устройство находится под управлением Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="89564-109">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="89564-110">Снятие с учета ожидается</span><span class="sxs-lookup"><span data-stu-id="89564-110">Retire pending</span></span>  <br/> |<span data-ttu-id="89564-111">В Office 365 бизнес идет подготовка к удалению данных компании с устройства.</span><span class="sxs-lookup"><span data-stu-id="89564-111">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="89564-112">Снятие с учета выполняется</span><span class="sxs-lookup"><span data-stu-id="89564-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="89564-113">Office 365 бизнес в настоящее время удаляет данные компании с устройства.</span><span class="sxs-lookup"><span data-stu-id="89564-113">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="89564-114">Не удалось снять с учета</span><span class="sxs-lookup"><span data-stu-id="89564-114">Retire failed</span></span>  <br/> | <span data-ttu-id="89564-115">Не удалось удалить данные компании.</span><span class="sxs-lookup"><span data-stu-id="89564-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="89564-116">Отмена снятия с учета</span><span class="sxs-lookup"><span data-stu-id="89564-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="89564-117">Действие снятия с учета отменено.</span><span class="sxs-lookup"><span data-stu-id="89564-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="89564-118">Ожидает очистки</span><span class="sxs-lookup"><span data-stu-id="89564-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="89564-119">Ожидается сброс до заводских настроек.</span><span class="sxs-lookup"><span data-stu-id="89564-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="89564-120">Очистка выполняется</span><span class="sxs-lookup"><span data-stu-id="89564-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="89564-121">Сброс до заводских настроек был инициирован.</span><span class="sxs-lookup"><span data-stu-id="89564-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="89564-122">Не удалось выполнить очистку</span><span class="sxs-lookup"><span data-stu-id="89564-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="89564-123">Не удалось выполнить сброс заводских настроек.</span><span class="sxs-lookup"><span data-stu-id="89564-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="89564-124">Очистка отменена</span><span class="sxs-lookup"><span data-stu-id="89564-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="89564-125">Очистка фабрики отменена.</span><span class="sxs-lookup"><span data-stu-id="89564-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="89564-126">Неработоспособное</span><span class="sxs-lookup"><span data-stu-id="89564-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="89564-127">Действие находится в состоянии ожидания (или выполняется), но устройство не было возвращено в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="89564-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="89564-128">Ожидает удаления</span><span class="sxs-lookup"><span data-stu-id="89564-128">Delete pending</span></span>  <br/> |<span data-ttu-id="89564-129">Ожидается удаление.</span><span class="sxs-lookup"><span data-stu-id="89564-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="89564-130">Обнаружено</span><span class="sxs-lookup"><span data-stu-id="89564-130">Discovered</span></span>  <br/> |<span data-ttu-id="89564-131">Система Office 365 бизнес обнаружила устройство.</span><span class="sxs-lookup"><span data-stu-id="89564-131">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
