---
title: Состояния устройств
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
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
description: Сведения о состояниях устройство в Майкрософт 365 для бизнеса.
ms.openlocfilehash: bd6f1ad7f7671d9616fd14d477dfcfb164ff6bd0
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870667"
---
# <a name="device-states"></a><span data-ttu-id="c5586-103">Состояния устройств</span><span class="sxs-lookup"><span data-stu-id="c5586-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="c5586-104">Состояния устройств</span><span class="sxs-lookup"><span data-stu-id="c5586-104">Device states</span></span>

<span data-ttu-id="c5586-105">Устройства в списке **Действия устройств** (домашняя страница администратора \> **Действия устройств**) могут находиться в перечисленных ниже состояниях.</span><span class="sxs-lookup"><span data-stu-id="c5586-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="c5586-107">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="c5586-107">**Status**</span></span>|<span data-ttu-id="c5586-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c5586-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c5586-109">Под управлением Intune</span><span class="sxs-lookup"><span data-stu-id="c5586-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="c5586-110">Устройство находится под управлением Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="c5586-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="c5586-111">Снятие с учета ожидается</span><span class="sxs-lookup"><span data-stu-id="c5586-111">Retire pending</span></span>  <br/> |<span data-ttu-id="c5586-112">В Office 365 бизнес идет подготовка к удалению данных компании с устройства.</span><span class="sxs-lookup"><span data-stu-id="c5586-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="c5586-113">Снятие с учета выполняется</span><span class="sxs-lookup"><span data-stu-id="c5586-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="c5586-114">Office 365 бизнес в настоящее время удаляет данные компании с устройства.</span><span class="sxs-lookup"><span data-stu-id="c5586-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="c5586-115">Не удалось снять с учета</span><span class="sxs-lookup"><span data-stu-id="c5586-115">Retire failed</span></span>  <br/> | <span data-ttu-id="c5586-116">Не удалось удалить данные компании.</span><span class="sxs-lookup"><span data-stu-id="c5586-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="c5586-117">Снятие с учета отменено</span><span class="sxs-lookup"><span data-stu-id="c5586-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="c5586-118">Операция снятия с учета была отменена.</span><span class="sxs-lookup"><span data-stu-id="c5586-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="c5586-119">Ожидает очистки</span><span class="sxs-lookup"><span data-stu-id="c5586-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="c5586-120">Ожидается сброс до заводских настроек.</span><span class="sxs-lookup"><span data-stu-id="c5586-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="c5586-121">Очистка выполняется</span><span class="sxs-lookup"><span data-stu-id="c5586-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="c5586-122">Сброс до заводских настроек был инициирован.</span><span class="sxs-lookup"><span data-stu-id="c5586-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="c5586-123">Не удалось выполнить очистку</span><span class="sxs-lookup"><span data-stu-id="c5586-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="c5586-124">Не удалось выполнить сброс до заводских настроек.</span><span class="sxs-lookup"><span data-stu-id="c5586-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="c5586-125">Очистка отменена</span><span class="sxs-lookup"><span data-stu-id="c5586-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="c5586-126">Сброс до заводских настроек был отменен.</span><span class="sxs-lookup"><span data-stu-id="c5586-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="c5586-127">Неработоспособное</span><span class="sxs-lookup"><span data-stu-id="c5586-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="c5586-128">Означает, что действие ожидается (или выполняется), но устройство не подключалось к системе 30 дней или более.</span><span class="sxs-lookup"><span data-stu-id="c5586-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="c5586-129">Ожидает удаления</span><span class="sxs-lookup"><span data-stu-id="c5586-129">Delete pending</span></span>  <br/> |<span data-ttu-id="c5586-130">Ожидается удаление.</span><span class="sxs-lookup"><span data-stu-id="c5586-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="c5586-131">Обнаружено</span><span class="sxs-lookup"><span data-stu-id="c5586-131">Discovered</span></span>  <br/> |<span data-ttu-id="c5586-132">Система Office 365 бизнес обнаружила устройство.</span><span class="sxs-lookup"><span data-stu-id="c5586-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
