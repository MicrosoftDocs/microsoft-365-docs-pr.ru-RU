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
ms.openlocfilehash: 02b4eebac62a48e3ddd53d362db2d60067ac05eb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593978"
---
# <a name="device-states"></a><span data-ttu-id="9d31d-103">Состояния устройств</span><span class="sxs-lookup"><span data-stu-id="9d31d-103">Device states</span></span>

<span data-ttu-id="9d31d-104">Устройства в списке **Действия устройств** (домашняя страница администратора \> **Действия устройств**) могут находиться в перечисленных ниже состояниях.</span><span class="sxs-lookup"><span data-stu-id="9d31d-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="9d31d-106">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="9d31d-106">**Status**</span></span>|<span data-ttu-id="9d31d-107">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9d31d-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9d31d-108">Под управлением Intune</span><span class="sxs-lookup"><span data-stu-id="9d31d-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="9d31d-109">Устройство находится под управлением Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="9d31d-109">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="9d31d-110">Снятие с учета ожидается</span><span class="sxs-lookup"><span data-stu-id="9d31d-110">Retire pending</span></span>  <br/> |<span data-ttu-id="9d31d-111">В Office 365 бизнес идет подготовка к удалению данных компании с устройства.</span><span class="sxs-lookup"><span data-stu-id="9d31d-111">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="9d31d-112">Снятие с учета выполняется</span><span class="sxs-lookup"><span data-stu-id="9d31d-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="9d31d-113">Office 365 бизнес в настоящее время удаляет данные компании с устройства.</span><span class="sxs-lookup"><span data-stu-id="9d31d-113">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="9d31d-114">Не удалось снять с учета</span><span class="sxs-lookup"><span data-stu-id="9d31d-114">Retire failed</span></span>  <br/> | <span data-ttu-id="9d31d-115">Не удалось удалить данные компании.</span><span class="sxs-lookup"><span data-stu-id="9d31d-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="9d31d-116">Отмена снятия с учета</span><span class="sxs-lookup"><span data-stu-id="9d31d-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="9d31d-117">Действие снятия с учета отменено.</span><span class="sxs-lookup"><span data-stu-id="9d31d-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="9d31d-118">Ожидает очистки</span><span class="sxs-lookup"><span data-stu-id="9d31d-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="9d31d-119">Ожидается сброс до заводских настроек.</span><span class="sxs-lookup"><span data-stu-id="9d31d-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="9d31d-120">Очистка выполняется</span><span class="sxs-lookup"><span data-stu-id="9d31d-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="9d31d-121">Сброс до заводских настроек был инициирован.</span><span class="sxs-lookup"><span data-stu-id="9d31d-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="9d31d-122">Не удалось выполнить очистку</span><span class="sxs-lookup"><span data-stu-id="9d31d-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="9d31d-123">Не удалось выполнить сброс заводских настроек.</span><span class="sxs-lookup"><span data-stu-id="9d31d-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="9d31d-124">Очистка отменена</span><span class="sxs-lookup"><span data-stu-id="9d31d-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="9d31d-125">Очистка фабрики отменена.</span><span class="sxs-lookup"><span data-stu-id="9d31d-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="9d31d-126">Неработоспособное</span><span class="sxs-lookup"><span data-stu-id="9d31d-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="9d31d-127">Действие находится в состоянии ожидания (или выполняется), но устройство не было возвращено в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="9d31d-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="9d31d-128">Ожидает удаления</span><span class="sxs-lookup"><span data-stu-id="9d31d-128">Delete pending</span></span>  <br/> |<span data-ttu-id="9d31d-129">Ожидается удаление.</span><span class="sxs-lookup"><span data-stu-id="9d31d-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="9d31d-130">Обнаружено</span><span class="sxs-lookup"><span data-stu-id="9d31d-130">Discovered</span></span>  <br/> |<span data-ttu-id="9d31d-131">Система Office 365 бизнес обнаружила устройство.</span><span class="sxs-lookup"><span data-stu-id="9d31d-131">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
