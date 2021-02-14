---
title: Устранение ошибок, связанных с устройствами AutoPilot
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Узнайте, как устранять ошибки, которые могут возникнуть при работе с файлами устройств AutoPilot в Microsoft 365 бизнес премиум.
ms.openlocfilehash: bec5126696ee322db42e4b7c5cd8e0df485ab2c9
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403417"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="1637f-103">Устранение ошибок, связанных с устройствами AutoPilot</span><span class="sxs-lookup"><span data-stu-id="1637f-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="1637f-104">Сообщения об ошибках файла устройства</span><span class="sxs-lookup"><span data-stu-id="1637f-104">Device file error messages</span></span>

<span data-ttu-id="1637f-105">Вот сведения о некоторых ошибках, которые могут возникнуть при работе с файлами устройств AutoPilot в Microsoft 365 бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="1637f-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business Premium.</span></span> 
  
|<span data-ttu-id="1637f-106">**Код ошибки**</span><span class="sxs-lookup"><span data-stu-id="1637f-106">**Error code**</span></span>|<span data-ttu-id="1637f-107">**Исправление для попробовать**</span><span class="sxs-lookup"><span data-stu-id="1637f-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1637f-108">Недопустимый тело запроса</span><span class="sxs-lookup"><span data-stu-id="1637f-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="1637f-109">Эта ошибка должна происходить редко, если вы видите эту ошибку, повторите операцию еще раз.</span><span class="sxs-lookup"><span data-stu-id="1637f-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="1637f-110">Неправильное значение аппаратного hash-значения для устройства.</span><span class="sxs-lookup"><span data-stu-id="1637f-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="1637f-111">Если вы видите эту ошибку, это означает, что значение, предоставленное в CSV-файле для аппаратного hash одного устройства, не является правильным.</span><span class="sxs-lookup"><span data-stu-id="1637f-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="1637f-112">Сначала убедитесь, что значение введите правильно.</span><span class="sxs-lookup"><span data-stu-id="1637f-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="1637f-113">Если вы считаете, что значение правильное, но эта ошибка все еще происходит, попросите своего поставщика оборудования за помощью.</span><span class="sxs-lookup"><span data-stu-id="1637f-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="1637f-114">Устройство, назначенное другому арендатору</span><span class="sxs-lookup"><span data-stu-id="1637f-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="1637f-115">Если вы видите эту ошибку, это означает, что значение, предоставленное в CSV-файле для серийного номера или ключа продукта одного или нескольких устройств, является некорректным.</span><span class="sxs-lookup"><span data-stu-id="1637f-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="1637f-116">Сначала убедитесь, что значение введите правильно.</span><span class="sxs-lookup"><span data-stu-id="1637f-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="1637f-117">Если вы считаете, что значение правильное, но эта ошибка все еще происходит, попросите своего поставщика оборудования за помощью.</span><span class="sxs-lookup"><span data-stu-id="1637f-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="1637f-118">CSV-файл содержит недопустимый серийный номер или ключ продукта</span><span class="sxs-lookup"><span data-stu-id="1637f-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="1637f-119">Если вы видите эту ошибку, это означает, что устройство, которое вы пытаетесь зарегистрировать, уже зарегистрировано другой организацией.</span><span class="sxs-lookup"><span data-stu-id="1637f-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="1637f-120">Чтобы устранить эту ошибку, попросите поставщика оборудования обратиться за помощью.</span><span class="sxs-lookup"><span data-stu-id="1637f-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="1637f-121">Это устройство не поддерживается для установки с помощью AutoPilot</span><span class="sxs-lookup"><span data-stu-id="1637f-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="1637f-122">Эта ошибка означает, что устройство не соответствует требованиям к развертыванию AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="1637f-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="1637f-123">Устройства должны отвечать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="1637f-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="1637f-124">Windows 10 версии 1703 или более поздней;</span><span class="sxs-lookup"><span data-stu-id="1637f-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="1637f-125">Новые устройства, которые не прошли через функцию "Windows при вехах".</span><span class="sxs-lookup"><span data-stu-id="1637f-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="1637f-126">Устройство не найдено</span><span class="sxs-lookup"><span data-stu-id="1637f-126">Device not found</span></span>  <br/> |<span data-ttu-id="1637f-127">Эта ошибка означает, что одно или несколько устройств в CSV-файле не зарегистрированы в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1637f-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="1637f-128">Чтобы устранить эту проблему, попросите своего поставщика оборудования обратиться за помощью.</span><span class="sxs-lookup"><span data-stu-id="1637f-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
