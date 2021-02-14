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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Узнайте о различных состояниях устройств в списке действий устройства на домашней сайте администратора в Microsoft 365 для бизнеса.
ms.openlocfilehash: 64138e2b6ae73c067709cde1912a96615d08ebf1
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471186"
---
# <a name="device-states"></a><span data-ttu-id="02bbd-103">Состояния устройств</span><span class="sxs-lookup"><span data-stu-id="02bbd-103">Device states</span></span>

<span data-ttu-id="02bbd-104">Эта статья относится к Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="02bbd-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="02bbd-105">Устройства в списке **Действия устройств** (домашняя страница администратора \> **Действия устройств**) могут находиться в перечисленных ниже состояниях.</span><span class="sxs-lookup"><span data-stu-id="02bbd-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="02bbd-107">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="02bbd-107">**Status**</span></span>|<span data-ttu-id="02bbd-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="02bbd-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="02bbd-109">Под управлением Intune</span><span class="sxs-lookup"><span data-stu-id="02bbd-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="02bbd-110">Управляется Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="02bbd-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="02bbd-111">Снятие с учета ожидается</span><span class="sxs-lookup"><span data-stu-id="02bbd-111">Retire pending</span></span>  <br/> |<span data-ttu-id="02bbd-112">Microsoft 365 бизнес премиум готов к удалению данных компании с устройства.</span><span class="sxs-lookup"><span data-stu-id="02bbd-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="02bbd-113">Снятие с учета выполняется</span><span class="sxs-lookup"><span data-stu-id="02bbd-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="02bbd-114">Microsoft 365 бизнес премиум в настоящее время удаляет данные компании с устройства.</span><span class="sxs-lookup"><span data-stu-id="02bbd-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="02bbd-115">Не удалось снять с учета</span><span class="sxs-lookup"><span data-stu-id="02bbd-115">Retire failed</span></span>  <br/> | <span data-ttu-id="02bbd-116">Не удалось удалить данные компании.</span><span class="sxs-lookup"><span data-stu-id="02bbd-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="02bbd-117">Отмена отмены</span><span class="sxs-lookup"><span data-stu-id="02bbd-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="02bbd-118">Действие отмены отменено.</span><span class="sxs-lookup"><span data-stu-id="02bbd-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="02bbd-119">Ожидает очистки</span><span class="sxs-lookup"><span data-stu-id="02bbd-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="02bbd-120">Ожидается сброс до заводских настроек.</span><span class="sxs-lookup"><span data-stu-id="02bbd-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="02bbd-121">Очистка выполняется</span><span class="sxs-lookup"><span data-stu-id="02bbd-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="02bbd-122">Сброс до заводских настроек был инициирован.</span><span class="sxs-lookup"><span data-stu-id="02bbd-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="02bbd-123">Не удалось выполнить очистку</span><span class="sxs-lookup"><span data-stu-id="02bbd-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="02bbd-124">Не удалось восстановить заводские настройки.</span><span class="sxs-lookup"><span data-stu-id="02bbd-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="02bbd-125">"Wipe canceled" (Стирать отменено</span><span class="sxs-lookup"><span data-stu-id="02bbd-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="02bbd-126">Заводская стирка отменена.</span><span class="sxs-lookup"><span data-stu-id="02bbd-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="02bbd-127">Неработоспособное</span><span class="sxs-lookup"><span data-stu-id="02bbd-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="02bbd-128">Действие ожидает выполнения (или находится в процессе), но устройство не находится в состоянии ожидания в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="02bbd-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="02bbd-129">Ожидает удаления</span><span class="sxs-lookup"><span data-stu-id="02bbd-129">Delete pending</span></span>  <br/> |<span data-ttu-id="02bbd-130">Ожидается удаление.</span><span class="sxs-lookup"><span data-stu-id="02bbd-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="02bbd-131">Обнаружено</span><span class="sxs-lookup"><span data-stu-id="02bbd-131">Discovered</span></span>  <br/> |<span data-ttu-id="02bbd-132">Microsoft 365 бизнес премиум обнаружил устройство.</span><span class="sxs-lookup"><span data-stu-id="02bbd-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
