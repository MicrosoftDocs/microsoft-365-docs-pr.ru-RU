---
title: Состояния устройств
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Сведения о состояниях устройств в Microsoft 365 Business.
ms.openlocfilehash: 15114835a5014f5bfac600eac79bcdffdaec481a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276995"
---
# <a name="device-states"></a><span data-ttu-id="653a2-103">Состояния устройств</span><span class="sxs-lookup"><span data-stu-id="653a2-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="653a2-104">Состояния устройств</span><span class="sxs-lookup"><span data-stu-id="653a2-104">Device states</span></span>

<span data-ttu-id="653a2-105">Устройства в списке **Действия устройств** (домашняя страница администратора \> **Действия устройств**) могут находиться в перечисленных ниже состояниях.</span><span class="sxs-lookup"><span data-stu-id="653a2-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="653a2-107">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="653a2-107">**Status**</span></span>|<span data-ttu-id="653a2-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="653a2-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="653a2-109">Под управлением Intune</span><span class="sxs-lookup"><span data-stu-id="653a2-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="653a2-110">Устройство находится под управлением Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="653a2-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="653a2-111">Снятие с учета ожидается</span><span class="sxs-lookup"><span data-stu-id="653a2-111">Retire pending</span></span>  <br/> |<span data-ttu-id="653a2-112">В Office 365 бизнес идет подготовка к удалению данных компании с устройства.</span><span class="sxs-lookup"><span data-stu-id="653a2-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="653a2-113">Снятие с учета выполняется</span><span class="sxs-lookup"><span data-stu-id="653a2-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="653a2-114">Office 365 бизнес в настоящее время удаляет данные компании с устройства.</span><span class="sxs-lookup"><span data-stu-id="653a2-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="653a2-115">Не удалось снять с учета</span><span class="sxs-lookup"><span data-stu-id="653a2-115">Retire failed</span></span>  <br/> | <span data-ttu-id="653a2-116">Не удалось удалить данные компании.</span><span class="sxs-lookup"><span data-stu-id="653a2-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="653a2-117">Снятие с учета отменено</span><span class="sxs-lookup"><span data-stu-id="653a2-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="653a2-118">Операция снятия с учета была отменена.</span><span class="sxs-lookup"><span data-stu-id="653a2-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="653a2-119">Ожидает очистки</span><span class="sxs-lookup"><span data-stu-id="653a2-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="653a2-120">Ожидается сброс до заводских настроек.</span><span class="sxs-lookup"><span data-stu-id="653a2-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="653a2-121">Очистка выполняется</span><span class="sxs-lookup"><span data-stu-id="653a2-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="653a2-122">Сброс до заводских настроек был инициирован.</span><span class="sxs-lookup"><span data-stu-id="653a2-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="653a2-123">Не удалось выполнить очистку</span><span class="sxs-lookup"><span data-stu-id="653a2-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="653a2-124">Не удалось выполнить сброс до заводских настроек.</span><span class="sxs-lookup"><span data-stu-id="653a2-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="653a2-125">Очистка отменена</span><span class="sxs-lookup"><span data-stu-id="653a2-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="653a2-126">Сброс до заводских настроек был отменен.</span><span class="sxs-lookup"><span data-stu-id="653a2-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="653a2-127">Неработоспособное</span><span class="sxs-lookup"><span data-stu-id="653a2-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="653a2-128">Означает, что действие ожидается (или выполняется), но устройство не подключалось к системе 30 дней или более.</span><span class="sxs-lookup"><span data-stu-id="653a2-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="653a2-129">Ожидает удаления</span><span class="sxs-lookup"><span data-stu-id="653a2-129">Delete pending</span></span>  <br/> |<span data-ttu-id="653a2-130">Ожидается удаление.</span><span class="sxs-lookup"><span data-stu-id="653a2-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="653a2-131">Обнаружено</span><span class="sxs-lookup"><span data-stu-id="653a2-131">Discovered</span></span>  <br/> |<span data-ttu-id="653a2-132">Система Office 365 бизнес обнаружила устройство.</span><span class="sxs-lookup"><span data-stu-id="653a2-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
