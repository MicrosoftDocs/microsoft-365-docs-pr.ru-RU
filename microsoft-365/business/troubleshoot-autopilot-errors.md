---
title: Устранение ошибок, связанных с устройствами AutoPilot
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Узнайте, как устранить ошибки, которые можно увидеть при работе с файлами устройств АвтоПилота в Microsoft 365 Business Premium.
ms.openlocfilehash: 1078ab74b07952e4bb565555a081b98ecce9db5c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578094"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="c33ea-103">Устранение ошибок, связанных с устройствами AutoPilot</span><span class="sxs-lookup"><span data-stu-id="c33ea-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="c33ea-104">Сообщения об ошибках файлов устройств</span><span class="sxs-lookup"><span data-stu-id="c33ea-104">Device file error messages</span></span>

<span data-ttu-id="c33ea-105">Вот сведения о некоторых ошибках, которые можно увидеть при работе с файлами устройств AutoPilot в Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="c33ea-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business Premium.</span></span> 
  
|<span data-ttu-id="c33ea-106">**Код ошибки**</span><span class="sxs-lookup"><span data-stu-id="c33ea-106">**Error code**</span></span>|<span data-ttu-id="c33ea-107">**Исправление, чтобы попытаться**</span><span class="sxs-lookup"><span data-stu-id="c33ea-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c33ea-108">Недействительное тело запроса</span><span class="sxs-lookup"><span data-stu-id="c33ea-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="c33ea-109">Эта ошибка должна происходить редко, если вы видите эту ошибку, повторите операцию.</span><span class="sxs-lookup"><span data-stu-id="c33ea-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="c33ea-110">Значение хаши оборудования для устройства неправильно.</span><span class="sxs-lookup"><span data-stu-id="c33ea-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="c33ea-111">Если вы видите эту ошибку, это означает, что значение, которое вы предоставили в CSV-файле для аппаратного хаши одного устройства, неправильно.</span><span class="sxs-lookup"><span data-stu-id="c33ea-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="c33ea-112">Сначала убедитесь, что значение было введите правильно.</span><span class="sxs-lookup"><span data-stu-id="c33ea-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="c33ea-113">Если вы считаете, что значение правильное, но эта ошибка все еще происходит, попросите поставщика оборудования о помощи.</span><span class="sxs-lookup"><span data-stu-id="c33ea-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="c33ea-114">Устройство, назначенное другому клиенту</span><span class="sxs-lookup"><span data-stu-id="c33ea-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="c33ea-115">Если вы видите эту ошибку, это означает, что значение, которое вы предоставили в CSV-файле для серийного номера или ключа продукта одного или нескольких устройств, неправильно.</span><span class="sxs-lookup"><span data-stu-id="c33ea-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="c33ea-116">Сначала убедитесь, что значение было введите правильно.</span><span class="sxs-lookup"><span data-stu-id="c33ea-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="c33ea-117">Если вы считаете, что значение правильное, но эта ошибка все еще происходит, попросите поставщика оборудования о помощи.</span><span class="sxs-lookup"><span data-stu-id="c33ea-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="c33ea-118">Файл CSV содержит недопустимый серийный номер или ключ продукта</span><span class="sxs-lookup"><span data-stu-id="c33ea-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="c33ea-119">Если вы видите эту ошибку, это означает, что устройство, которое вы пытаетесь зарегистрировать, уже зарегистрировано другой организацией.</span><span class="sxs-lookup"><span data-stu-id="c33ea-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="c33ea-120">Чтобы устранить эту ошибку, попросите поставщика оборудования о помощи.</span><span class="sxs-lookup"><span data-stu-id="c33ea-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="c33ea-121">Это устройство не поддерживается для установки с помощью AutoPilot</span><span class="sxs-lookup"><span data-stu-id="c33ea-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="c33ea-122">Эта ошибка означает, что устройство не соответствует требованиям развертывания AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="c33ea-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="c33ea-123">Устройства должны отвечать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="c33ea-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="c33ea-124">Windows 10 версии 1703 или более поздней;</span><span class="sxs-lookup"><span data-stu-id="c33ea-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="c33ea-125">Новые устройства, которые не прошли через windows вне окна.</span><span class="sxs-lookup"><span data-stu-id="c33ea-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="c33ea-126">Устройство не найдено</span><span class="sxs-lookup"><span data-stu-id="c33ea-126">Device not found</span></span>  <br/> |<span data-ttu-id="c33ea-127">Эта ошибка означает, что одно или несколько устройств в вашем CSV-файле не зарегистрированы в организации.</span><span class="sxs-lookup"><span data-stu-id="c33ea-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="c33ea-128">Чтобы исправить это, попросите поставщика оборудования о помощи.</span><span class="sxs-lookup"><span data-stu-id="c33ea-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
