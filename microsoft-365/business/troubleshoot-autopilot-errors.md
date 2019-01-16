---
title: Устранение ошибок устройства с AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: troubleshooting
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Узнайте, как устранять ошибки файл устройства автопилот.
ms.openlocfilehash: 9b8d8ab424dd3189ff5c228dab8f5c513ff5dafc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870619"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="4263c-103">Устранение ошибок устройства с AutoPilot</span><span class="sxs-lookup"><span data-stu-id="4263c-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="4263c-104">Сообщения об ошибках файла устройства</span><span class="sxs-lookup"><span data-stu-id="4263c-104">Device file error messages</span></span>

<span data-ttu-id="4263c-105">Вот — информация о некоторых сообщений об ошибках, можно увидеть при работе с файлами автопилот устройство в Майкрософт 365 для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4263c-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="4263c-106">**Код ошибки**</span><span class="sxs-lookup"><span data-stu-id="4263c-106">**Error code**</span></span>|<span data-ttu-id="4263c-107">**Исправление, чтобы попробовать**</span><span class="sxs-lookup"><span data-stu-id="4263c-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4263c-108">Недопустимый запрос body</span><span class="sxs-lookup"><span data-stu-id="4263c-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="4263c-109">Эта ошибка должны быть выполнены редко, если эта ошибка отображается, повторите операцию.</span><span class="sxs-lookup"><span data-stu-id="4263c-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="4263c-110">Значения хэш-функции оборудования для устройства, неверно.</span><span class="sxs-lookup"><span data-stu-id="4263c-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="4263c-p101">При появлении этой ошибки, это означает, что значения, указанного в CSV-файл для хэш оборудования одно устройство не будет правильно. Во-первых убедитесь, что значение было введено правильно. Если предполагается, что значение является правильным, но эта ошибка происходит по-прежнему, обратитесь за помощью к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="4263c-p101">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct. First, verify that the value was typed correctly. If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="4263c-114">Устройство, назначенных для другого клиента</span><span class="sxs-lookup"><span data-stu-id="4263c-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="4263c-p102">При появлении этой ошибки, это означает, что значение, заданное в CSV-файл для серийный номер или ключ продукта из одного или нескольких устройств не будет правильно. Во-первых убедитесь, что значение было введено правильно. Если предполагается, что значение является правильным, но эта ошибка происходит по-прежнему, обратитесь за помощью к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="4263c-p102">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct. First, verify that the value was typed correctly. If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="4263c-118">CSV-файл содержит недопустимый порядковый номер или ключ продукта</span><span class="sxs-lookup"><span data-stu-id="4263c-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="4263c-p103">При появлении этой ошибки означает, что устройства, которые tyring для регистрации уже зарегистрирован другой организацией. Чтобы устранить эту неполадку, обратитесь за помощью к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="4263c-p103">If you see this error it means that the device you are tyring to register is already registered by an other organization. To fix this, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="4263c-121">Это устройство не поддерживается для программы установки с помощью автопилот</span><span class="sxs-lookup"><span data-stu-id="4263c-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="4263c-p104">Эта ошибка означает, что устройства не соответствует требованиям развертывания автопилот. Устройства должны соответствовать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="4263c-p104">This error means the device does not meet AutoPilot deployment requirements. Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="4263c-124">Windows 10 версии 1703 или более поздней;</span><span class="sxs-lookup"><span data-stu-id="4263c-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="4263c-125">новые устройства, на которых еще не был пройден этап запуска Windows при первом включении.</span><span class="sxs-lookup"><span data-stu-id="4263c-125">New devices that have not been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="4263c-126">Устройство не найдено</span><span class="sxs-lookup"><span data-stu-id="4263c-126">Device not found</span></span>  <br/> |<span data-ttu-id="4263c-p105">Эта ошибка означает, что один или несколько устройств в CSV-файл не зарегистрирован в вашей организации. Чтобы устранить эту неполадку, обратитесь за помощью к поставщику оборудования.</span><span class="sxs-lookup"><span data-stu-id="4263c-p105">This error means that one or more devices in your CSV file is not registered to your organization. To fix this, ask your hardware vendor for help.</span></span>  <br/> |
   
