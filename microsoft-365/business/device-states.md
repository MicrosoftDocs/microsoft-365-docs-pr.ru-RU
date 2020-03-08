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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Сведения о различных состояниях устройств в списке действия устройств в домашней странице администрирования Microsoft 365 бизнес.
ms.openlocfilehash: bed1610814ca0d60adb4b4b3d0018e3e7e6d763f
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2020
ms.locfileid: "42560827"
---
# <a name="device-states"></a><span data-ttu-id="2db48-103">Состояния устройств</span><span class="sxs-lookup"><span data-stu-id="2db48-103">Device states</span></span>

<span data-ttu-id="2db48-104">Устройства в списке **Действия устройств** (домашняя страница администратора \> **Действия устройств**) могут находиться в перечисленных ниже состояниях.</span><span class="sxs-lookup"><span data-stu-id="2db48-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="2db48-106">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="2db48-106">**Status**</span></span>|<span data-ttu-id="2db48-107">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2db48-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2db48-108">Под управлением Intune</span><span class="sxs-lookup"><span data-stu-id="2db48-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="2db48-109">Устройство находится под управлением Office 365 бизнес.</span><span class="sxs-lookup"><span data-stu-id="2db48-109">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="2db48-110">Снятие с учета ожидается</span><span class="sxs-lookup"><span data-stu-id="2db48-110">Retire pending</span></span>  <br/> |<span data-ttu-id="2db48-111">В Office 365 бизнес идет подготовка к удалению данных компании с устройства.</span><span class="sxs-lookup"><span data-stu-id="2db48-111">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="2db48-112">Снятие с учета выполняется</span><span class="sxs-lookup"><span data-stu-id="2db48-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="2db48-113">Office 365 бизнес в настоящее время удаляет данные компании с устройства.</span><span class="sxs-lookup"><span data-stu-id="2db48-113">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="2db48-114">Не удалось снять с учета</span><span class="sxs-lookup"><span data-stu-id="2db48-114">Retire failed</span></span>  <br/> | <span data-ttu-id="2db48-115">Не удалось удалить данные компании.</span><span class="sxs-lookup"><span data-stu-id="2db48-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="2db48-116">Отмена снятия с учета</span><span class="sxs-lookup"><span data-stu-id="2db48-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="2db48-117">Действие снятия с учета отменено.</span><span class="sxs-lookup"><span data-stu-id="2db48-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="2db48-118">Ожидает очистки</span><span class="sxs-lookup"><span data-stu-id="2db48-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="2db48-119">Ожидается сброс до заводских настроек.</span><span class="sxs-lookup"><span data-stu-id="2db48-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="2db48-120">Очистка выполняется</span><span class="sxs-lookup"><span data-stu-id="2db48-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="2db48-121">Сброс до заводских настроек был инициирован.</span><span class="sxs-lookup"><span data-stu-id="2db48-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="2db48-122">Не удалось выполнить очистку</span><span class="sxs-lookup"><span data-stu-id="2db48-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="2db48-123">Не удалось выполнить сброс заводских настроек.</span><span class="sxs-lookup"><span data-stu-id="2db48-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="2db48-124">Очистка отменена</span><span class="sxs-lookup"><span data-stu-id="2db48-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="2db48-125">Очистка фабрики отменена.</span><span class="sxs-lookup"><span data-stu-id="2db48-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="2db48-126">Неработоспособное</span><span class="sxs-lookup"><span data-stu-id="2db48-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="2db48-127">Действие находится в состоянии ожидания (или выполняется), но устройство не было возвращено в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="2db48-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="2db48-128">Ожидает удаления</span><span class="sxs-lookup"><span data-stu-id="2db48-128">Delete pending</span></span>  <br/> |<span data-ttu-id="2db48-129">Ожидается удаление.</span><span class="sxs-lookup"><span data-stu-id="2db48-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="2db48-130">Обнаружено</span><span class="sxs-lookup"><span data-stu-id="2db48-130">Discovered</span></span>  <br/> |<span data-ttu-id="2db48-131">Система Office 365 бизнес обнаружила устройство.</span><span class="sxs-lookup"><span data-stu-id="2db48-131">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
