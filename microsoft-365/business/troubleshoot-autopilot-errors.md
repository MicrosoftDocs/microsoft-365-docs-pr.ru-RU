---
title: Устранение ошибок, связанных с устройствами AutoPilot
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: troubleshooting
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
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Узнайте, как устранять ошибки, которые могут возникнуть при работе с файлами устройств с автопилотом в Microsoft 365 Business.
ms.openlocfilehash: 7569f18097a1f5959b3dd491958c78886e1e05d6
ms.sourcegitcommit: 41c0bc5cf50f4ca63b4286d1ea0f58ab82984b7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "42547478"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="aab70-103">Устранение ошибок, связанных с устройствами AutoPilot</span><span class="sxs-lookup"><span data-stu-id="aab70-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="aab70-104">Сообщения об ошибках файлов устройств</span><span class="sxs-lookup"><span data-stu-id="aab70-104">Device file error messages</span></span>

<span data-ttu-id="aab70-105">Ниже приведены сведения о некоторых ошибках, которые могут возникнуть при работе с файлами устройств с автопилотным развертыванием в Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="aab70-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="aab70-106">**Код ошибки**</span><span class="sxs-lookup"><span data-stu-id="aab70-106">**Error code**</span></span>|<span data-ttu-id="aab70-107">**Исправление для попытки**</span><span class="sxs-lookup"><span data-stu-id="aab70-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aab70-108">Недопустимый текст запроса</span><span class="sxs-lookup"><span data-stu-id="aab70-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="aab70-109">Эта ошибка должна происходить редко, если вы видите эту ошибку, повторите операцию.</span><span class="sxs-lookup"><span data-stu-id="aab70-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="aab70-110">Неправильное аппаратное значение хэша для устройства.</span><span class="sxs-lookup"><span data-stu-id="aab70-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="aab70-111">Если вы видите эту ошибку, это означает, что значение, указанное в CSV-файле для аппаратного хеша одного устройства, является неверным.</span><span class="sxs-lookup"><span data-stu-id="aab70-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="aab70-112">Сначала убедитесь, что значение было введено правильно.</span><span class="sxs-lookup"><span data-stu-id="aab70-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="aab70-113">Если вы считаете, что значение задано правильно, но эта ошибка по-прежнему возникает, обратитесь за помощью к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="aab70-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="aab70-114">Устройство, назначенное другому клиенту</span><span class="sxs-lookup"><span data-stu-id="aab70-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="aab70-115">Если вы видите эту ошибку, это означает, что значение, указанное в CSV-файле либо для серийного номера, либо для ключа продукта одного или нескольких устройств, является неверным.</span><span class="sxs-lookup"><span data-stu-id="aab70-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="aab70-116">Сначала убедитесь, что значение было введено правильно.</span><span class="sxs-lookup"><span data-stu-id="aab70-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="aab70-117">Если вы считаете, что значение задано правильно, но эта ошибка по-прежнему возникает, обратитесь за помощью к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="aab70-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="aab70-118">CSV-файл содержит недопустимый серийный номер или ключ продукта</span><span class="sxs-lookup"><span data-stu-id="aab70-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="aab70-119">Если вы видите эту ошибку, это означает, что устройство, которое вы пытаетесь зарегистрировать, уже зарегистрировано другой организацией.</span><span class="sxs-lookup"><span data-stu-id="aab70-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="aab70-120">Чтобы устранить эту ошибку, обратитесь за помощью к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="aab70-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="aab70-121">Это устройство не поддерживается программой установки с помощью автопилота</span><span class="sxs-lookup"><span data-stu-id="aab70-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="aab70-122">Эта ошибка означает, что устройство не соответствует требованиям к развертыванию по подпилотным этапам.</span><span class="sxs-lookup"><span data-stu-id="aab70-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="aab70-123">Устройства должны отвечать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="aab70-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="aab70-124">Windows 10 версии 1703 или более поздней;</span><span class="sxs-lookup"><span data-stu-id="aab70-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="aab70-125">Новые устройства, которые не прошли предварительный интерфейс Windows.</span><span class="sxs-lookup"><span data-stu-id="aab70-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="aab70-126">Устройство не найдено</span><span class="sxs-lookup"><span data-stu-id="aab70-126">Device not found</span></span>  <br/> |<span data-ttu-id="aab70-127">Эта ошибка означает, что одно или несколько устройств в вашем CSV-файле не зарегистрированы в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="aab70-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="aab70-128">Чтобы устранить эту проблему, обратитесь за помощью к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="aab70-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
