---
title: Состояния устройств
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Узнайте о различных состояниях устройств в списке действий устройства в доме администрирования в Microsoft 365 для бизнеса.
ms.openlocfilehash: e6f1b428413d094e0a1ce3afb026528074038736
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578474"
---
# <a name="device-states"></a><span data-ttu-id="6fd42-103">Состояния устройств</span><span class="sxs-lookup"><span data-stu-id="6fd42-103">Device states</span></span>

<span data-ttu-id="6fd42-104">Эта статья применима к Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="6fd42-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="6fd42-105">Устройства в списке **Действия устройств** (домашняя страница администратора \> **Действия устройств**) могут находиться в перечисленных ниже состояниях.</span><span class="sxs-lookup"><span data-stu-id="6fd42-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="6fd42-107">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="6fd42-107">**Status**</span></span>|<span data-ttu-id="6fd42-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6fd42-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6fd42-109">Под управлением Intune</span><span class="sxs-lookup"><span data-stu-id="6fd42-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="6fd42-110">Управляемый Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="6fd42-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="6fd42-111">Снятие с учета ожидается</span><span class="sxs-lookup"><span data-stu-id="6fd42-111">Retire pending</span></span>  <br/> |<span data-ttu-id="6fd42-112">Microsoft 365 бизнес премиум готовится удалить данные компании с устройства.</span><span class="sxs-lookup"><span data-stu-id="6fd42-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="6fd42-113">Снятие с учета выполняется</span><span class="sxs-lookup"><span data-stu-id="6fd42-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="6fd42-114">Microsoft 365 бизнес премиум в настоящее время удаляет данные компании с устройства.</span><span class="sxs-lookup"><span data-stu-id="6fd42-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="6fd42-115">Не удалось снять с учета</span><span class="sxs-lookup"><span data-stu-id="6fd42-115">Retire failed</span></span>  <br/> | <span data-ttu-id="6fd42-116">Не удалось удалить данные компании.</span><span class="sxs-lookup"><span data-stu-id="6fd42-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="6fd42-117">Отмена отмены</span><span class="sxs-lookup"><span data-stu-id="6fd42-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="6fd42-118">Действие по отмене было отменено.</span><span class="sxs-lookup"><span data-stu-id="6fd42-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="6fd42-119">Ожидает очистки</span><span class="sxs-lookup"><span data-stu-id="6fd42-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="6fd42-120">Ожидается сброс до заводских настроек.</span><span class="sxs-lookup"><span data-stu-id="6fd42-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="6fd42-121">Очистка выполняется</span><span class="sxs-lookup"><span data-stu-id="6fd42-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="6fd42-122">Сброс до заводских настроек был инициирован.</span><span class="sxs-lookup"><span data-stu-id="6fd42-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="6fd42-123">Не удалось выполнить очистку</span><span class="sxs-lookup"><span data-stu-id="6fd42-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="6fd42-124">Не удалось сделать заводской сброс.</span><span class="sxs-lookup"><span data-stu-id="6fd42-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="6fd42-125">Wipe canceled</span><span class="sxs-lookup"><span data-stu-id="6fd42-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="6fd42-126">Стирка фабрики была отменена.</span><span class="sxs-lookup"><span data-stu-id="6fd42-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="6fd42-127">Неработоспособное</span><span class="sxs-lookup"><span data-stu-id="6fd42-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="6fd42-128">Действие ожидается (или находится в процессе), но устройство не регистрируется более 30 дней.</span><span class="sxs-lookup"><span data-stu-id="6fd42-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="6fd42-129">Ожидает удаления</span><span class="sxs-lookup"><span data-stu-id="6fd42-129">Delete pending</span></span>  <br/> |<span data-ttu-id="6fd42-130">Ожидается удаление.</span><span class="sxs-lookup"><span data-stu-id="6fd42-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="6fd42-131">Обнаружено</span><span class="sxs-lookup"><span data-stu-id="6fd42-131">Discovered</span></span>  <br/> |<span data-ttu-id="6fd42-132">Microsoft 365 бизнес премиум обнаружено устройство.</span><span class="sxs-lookup"><span data-stu-id="6fd42-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
