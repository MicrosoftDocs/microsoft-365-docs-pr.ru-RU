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
description: Сведения о различных состояниях устройств в списке действия устройств в домашней странице администратора Microsoft 365 для бизнеса.
ms.openlocfilehash: 90c11caa03249408ba2916d303bcb4a59fbcca8c
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400961"
---
# <a name="device-states"></a><span data-ttu-id="57373-103">Состояния устройств</span><span class="sxs-lookup"><span data-stu-id="57373-103">Device states</span></span>

<span data-ttu-id="57373-104">Устройства в списке **Действия устройств** (домашняя страница администратора \> **Действия устройств**) могут находиться в перечисленных ниже состояниях.</span><span class="sxs-lookup"><span data-stu-id="57373-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="57373-106">**Состояние**</span><span class="sxs-lookup"><span data-stu-id="57373-106">**Status**</span></span>|<span data-ttu-id="57373-107">**Описание**</span><span class="sxs-lookup"><span data-stu-id="57373-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="57373-108">Под управлением Intune</span><span class="sxs-lookup"><span data-stu-id="57373-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="57373-109">Управляется службой Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="57373-109">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="57373-110">Снятие с учета ожидается</span><span class="sxs-lookup"><span data-stu-id="57373-110">Retire pending</span></span>  <br/> |<span data-ttu-id="57373-111">Microsoft 365 Business Premium готовится к удалению данных компании с устройства.</span><span class="sxs-lookup"><span data-stu-id="57373-111">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="57373-112">Снятие с учета выполняется</span><span class="sxs-lookup"><span data-stu-id="57373-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="57373-113">Microsoft 365 бизнес премиум в настоящее время удаляет данные компании с устройства.</span><span class="sxs-lookup"><span data-stu-id="57373-113">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="57373-114">Не удалось снять с учета</span><span class="sxs-lookup"><span data-stu-id="57373-114">Retire failed</span></span>  <br/> | <span data-ttu-id="57373-115">Не удалось удалить данные компании.</span><span class="sxs-lookup"><span data-stu-id="57373-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="57373-116">Отмена снятия с учета</span><span class="sxs-lookup"><span data-stu-id="57373-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="57373-117">Действие снятия с учета отменено.</span><span class="sxs-lookup"><span data-stu-id="57373-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="57373-118">Ожидает очистки</span><span class="sxs-lookup"><span data-stu-id="57373-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="57373-119">Ожидается сброс до заводских настроек.</span><span class="sxs-lookup"><span data-stu-id="57373-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="57373-120">Очистка выполняется</span><span class="sxs-lookup"><span data-stu-id="57373-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="57373-121">Сброс до заводских настроек был инициирован.</span><span class="sxs-lookup"><span data-stu-id="57373-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="57373-122">Не удалось выполнить очистку</span><span class="sxs-lookup"><span data-stu-id="57373-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="57373-123">Не удалось выполнить сброс заводских настроек.</span><span class="sxs-lookup"><span data-stu-id="57373-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="57373-124">Очистка отменена</span><span class="sxs-lookup"><span data-stu-id="57373-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="57373-125">Очистка фабрики отменена.</span><span class="sxs-lookup"><span data-stu-id="57373-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="57373-126">Неработоспособное</span><span class="sxs-lookup"><span data-stu-id="57373-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="57373-127">Действие находится в состоянии ожидания (или выполняется), но устройство не было возвращено в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="57373-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="57373-128">Ожидает удаления</span><span class="sxs-lookup"><span data-stu-id="57373-128">Delete pending</span></span>  <br/> |<span data-ttu-id="57373-129">Ожидается удаление.</span><span class="sxs-lookup"><span data-stu-id="57373-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="57373-130">Обнаружено</span><span class="sxs-lookup"><span data-stu-id="57373-130">Discovered</span></span>  <br/> |<span data-ttu-id="57373-131">Microsoft 365 Business Premium обнаружил устройство.</span><span class="sxs-lookup"><span data-stu-id="57373-131">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
