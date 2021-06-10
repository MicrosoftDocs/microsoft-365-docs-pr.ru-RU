---
title: Включение современной проверки подлинности для Office 2013 на устройствах с Windows
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Научитесь устанавливать ключи реестра, чтобы включить современную проверку подлинности для устройств, Microsoft Office 2013 г.
ms.openlocfilehash: 917ecd5c668ea43b0627ba2361f951ebc5e19725
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635694"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a><span data-ttu-id="f371a-103">Включение современной проверки подлинности для Office 2013 на устройствах с Windows</span><span class="sxs-lookup"><span data-stu-id="f371a-103">Enable Modern Authentication for Office 2013 on Windows devices</span></span>

<span data-ttu-id="f371a-104">Чтобы включить современную проверку подлинности для устройств Windows, на которых установлен Office 2013, необходимо настроить разделы реестра.</span><span class="sxs-lookup"><span data-stu-id="f371a-104">To enable modern authentication for any Windows devices that have Office 2013 installed, you need to set specific registry keys.</span></span>
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a><span data-ttu-id="f371a-105">Включение современной проверки подлинности для клиентов Office 2013</span><span class="sxs-lookup"><span data-stu-id="f371a-105">Enable modern authentication for Office 2013 clients</span></span>

> [!NOTE]
> <span data-ttu-id="f371a-106">Современная проверка подлинности уже включена для клиентов Office 2016. Настраивать разделы реестра для Office 2016 не нужно.</span><span class="sxs-lookup"><span data-stu-id="f371a-106">Modern authentication is already enabled for Office 2016 clients, you do not need to set registry keys for Office 2016.</span></span> 
  
<span data-ttu-id="f371a-p101">Чтобы включить современную проверку подлинности для устройства с Windows (например, ноутбука или планшета), на котором установлен Microsoft Office 2013, необходимо настроить указанные ниже разделы реестра. Это нужно сделать для каждого устройства, на котором вы хотите включить современную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="f371a-p101">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:</span></span>
  
|<span data-ttu-id="f371a-109">**Раздел реестра**</span><span class="sxs-lookup"><span data-stu-id="f371a-109">**Registry key**</span></span>|<span data-ttu-id="f371a-110">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f371a-110">**Type**</span></span>|<span data-ttu-id="f371a-111">**Значение**</span><span class="sxs-lookup"><span data-stu-id="f371a-111">**Value**</span></span> |
|:-------|:------:|--------:|
|<span data-ttu-id="f371a-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="f371a-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  |<span data-ttu-id="f371a-113">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="f371a-113">REG_DWORD</span></span>  |<span data-ttu-id="f371a-114">1</span><span class="sxs-lookup"><span data-stu-id="f371a-114">1</span></span>  |
|<span data-ttu-id="f371a-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="f371a-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span> |<span data-ttu-id="f371a-116">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="f371a-116">REG_DWORD</span></span> |<span data-ttu-id="f371a-117">1</span><span class="sxs-lookup"><span data-stu-id="f371a-117">1</span></span> |
   
<span data-ttu-id="f371a-118">После задания ключей реестра можно Office 2013 г. приложениям для использования многофакторной проверки подлинности [(MFA)](set-up-multi-factor-authentication.md) с помощью Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f371a-118">Once you have set the registry keys, you can set Office 2013 devices apps to use [multifactor authentication (MFA)](set-up-multi-factor-authentication.md) with Microsoft 365.</span></span> 
  
<span data-ttu-id="f371a-p102">Если вы вошли в одно из клиентских приложений, выйдите из него и войдите снова, чтобы изменения вступили в силу. В противном случае, файлы, с которыми вы недавно работали, и настройки роуминга останутся недоступными до тех пор, пока не будет установлено удостоверение библиотек ADAL.</span><span class="sxs-lookup"><span data-stu-id="f371a-p102">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span></span>
  
## <a name="disable-modern-authentication-on-devices"></a><span data-ttu-id="f371a-121">Отключение современный проверки подлинности на устройствах</span><span class="sxs-lookup"><span data-stu-id="f371a-121">Disable modern authentication on devices</span></span>

<span data-ttu-id="f371a-122">Чтобы отключить современную проверку подлинности на устройстве, настройте на нем следующие разделы реестра:</span><span class="sxs-lookup"><span data-stu-id="f371a-122">To disable modern authentication on a device, set the following registry keys on the device:</span></span>
  
|<span data-ttu-id="f371a-123">**Раздел реестра**</span><span class="sxs-lookup"><span data-stu-id="f371a-123">**Registry key**</span></span>|<span data-ttu-id="f371a-124">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f371a-124">**Type**</span></span>|<span data-ttu-id="f371a-125">**Значение**</span><span class="sxs-lookup"><span data-stu-id="f371a-125">**Value**</span></span>|
|:-------|:------:|--------:|
|<span data-ttu-id="f371a-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="f371a-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span> |<span data-ttu-id="f371a-127">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="f371a-127">REG_DWORD</span></span>|<span data-ttu-id="f371a-128">0</span><span class="sxs-lookup"><span data-stu-id="f371a-128">0</span></span>|
   
## <a name="related-content"></a><span data-ttu-id="f371a-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="f371a-129">Related content</span></span>

<span data-ttu-id="f371a-130">[Вход в Office 2013 г.](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) со вторым методом проверки (статья)</span><span class="sxs-lookup"><span data-stu-id="f371a-130">[Sign in to Office 2013 with a second verification method](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) (article)</span></span>\
<span data-ttu-id="f371a-131">[Outlook для](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled) пароля и не использует современную проверку подлинности для подключения к Office 365 (статья)</span><span class="sxs-lookup"><span data-stu-id="f371a-131">[Outlook prompts for password and doesn't use Modern Authentication to connect to Office 365](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled) (article)</span></span>

