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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Сведения о состояниях устройств в Microsoft 365 Business.
ms.openlocfilehash: 26b218cb7b6a14f17e33d34a2e712b06ac814c0c
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065780"
---
# <a name="device-states"></a><span data-ttu-id="30086-103">Состояния устройств</span><span class="sxs-lookup"><span data-stu-id="30086-103">Device states</span></span>

<span data-ttu-id="30086-104">Устройства в списке **Действия устройств** (домашняя страница администратора \> **Действия устройств**) могут находиться в перечисленных ниже состояниях.</span><span class="sxs-lookup"><span data-stu-id="30086-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="30086-106">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="30086-106">**Status**</span></span>|<span data-ttu-id="30086-107">**Описание**</span><span class="sxs-lookup"><span data-stu-id="30086-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="30086-108">Под управлением Intune</span><span class="sxs-lookup"><span data-stu-id="30086-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="30086-109">Устройство находится под управлением Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="30086-109">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="30086-110">Снятие с учета ожидается</span><span class="sxs-lookup"><span data-stu-id="30086-110">Retire pending</span></span>  <br/> |<span data-ttu-id="30086-111">В Office 365 бизнес идет подготовка к удалению данных компании с устройства.</span><span class="sxs-lookup"><span data-stu-id="30086-111">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="30086-112">Снятие с учета выполняется</span><span class="sxs-lookup"><span data-stu-id="30086-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="30086-113">Office 365 бизнес в настоящее время удаляет данные компании с устройства.</span><span class="sxs-lookup"><span data-stu-id="30086-113">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="30086-114">Не удалось снять с учета</span><span class="sxs-lookup"><span data-stu-id="30086-114">Retire failed</span></span>  <br/> | <span data-ttu-id="30086-115">Не удалось удалить данные компании.</span><span class="sxs-lookup"><span data-stu-id="30086-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="30086-116">Отмена снятия с учета</span><span class="sxs-lookup"><span data-stu-id="30086-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="30086-117">Действие снятия с учета отменено.</span><span class="sxs-lookup"><span data-stu-id="30086-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="30086-118">Ожидает очистки</span><span class="sxs-lookup"><span data-stu-id="30086-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="30086-119">Ожидается сброс до заводских настроек.</span><span class="sxs-lookup"><span data-stu-id="30086-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="30086-120">Очистка выполняется</span><span class="sxs-lookup"><span data-stu-id="30086-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="30086-121">Сброс до заводских настроек был инициирован.</span><span class="sxs-lookup"><span data-stu-id="30086-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="30086-122">Не удалось выполнить очистку</span><span class="sxs-lookup"><span data-stu-id="30086-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="30086-123">Не удалось выполнить сброс заводских настроек.</span><span class="sxs-lookup"><span data-stu-id="30086-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="30086-124">Очистка отменена</span><span class="sxs-lookup"><span data-stu-id="30086-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="30086-125">Очистка фабрики отменена.</span><span class="sxs-lookup"><span data-stu-id="30086-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="30086-126">Неработоспособное</span><span class="sxs-lookup"><span data-stu-id="30086-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="30086-127">Действие находится в состоянии ожидания (или выполняется), но устройство не было возвращено в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="30086-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="30086-128">Ожидает удаления</span><span class="sxs-lookup"><span data-stu-id="30086-128">Delete pending</span></span>  <br/> |<span data-ttu-id="30086-129">Ожидается удаление.</span><span class="sxs-lookup"><span data-stu-id="30086-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="30086-130">Обнаружено</span><span class="sxs-lookup"><span data-stu-id="30086-130">Discovered</span></span>  <br/> |<span data-ttu-id="30086-131">Система Office 365 бизнес обнаружила устройство.</span><span class="sxs-lookup"><span data-stu-id="30086-131">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
