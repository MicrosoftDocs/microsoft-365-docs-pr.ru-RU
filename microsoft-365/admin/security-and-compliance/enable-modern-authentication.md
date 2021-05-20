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
description: Научитесь устанавливать ключи реестра, чтобы обеспечить современную аутентификацию для устройств, которые Microsoft Office 2013 года.
ms.openlocfilehash: d358cb2ffb4284a51779e5a7c1dc894052b9ebc0
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572289"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a><span data-ttu-id="d76e8-103">Включение современной проверки подлинности для Office 2013 на устройствах с Windows</span><span class="sxs-lookup"><span data-stu-id="d76e8-103">Enable Modern Authentication for Office 2013 on Windows devices</span></span>

<span data-ttu-id="d76e8-104">Чтобы включить современную проверку подлинности для устройств Windows, на которых установлен Office 2013, необходимо настроить разделы реестра.</span><span class="sxs-lookup"><span data-stu-id="d76e8-104">To enable modern authentication for any Windows devices that have Office 2013 installed, you need to set specific registry keys.</span></span>
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a><span data-ttu-id="d76e8-105">Включение современной проверки подлинности для клиентов Office 2013</span><span class="sxs-lookup"><span data-stu-id="d76e8-105">Enable modern authentication for Office 2013 clients</span></span>

> [!NOTE]
> <span data-ttu-id="d76e8-106">Современная проверка подлинности уже включена для клиентов Office 2016. Настраивать разделы реестра для Office 2016 не нужно.</span><span class="sxs-lookup"><span data-stu-id="d76e8-106">Modern authentication is already enabled for Office 2016 clients, you do not need to set registry keys for Office 2016.</span></span> 
  
<span data-ttu-id="d76e8-p101">Чтобы включить современную проверку подлинности для устройства с Windows (например, ноутбука или планшета), на котором установлен Microsoft Office 2013, необходимо настроить указанные ниже разделы реестра. Это нужно сделать для каждого устройства, на котором вы хотите включить современную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="d76e8-p101">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:</span></span>
  
|<span data-ttu-id="d76e8-109">**Раздел реестра**</span><span class="sxs-lookup"><span data-stu-id="d76e8-109">**Registry key**</span></span>|<span data-ttu-id="d76e8-110">**Тип**</span><span class="sxs-lookup"><span data-stu-id="d76e8-110">**Type**</span></span>|<span data-ttu-id="d76e8-111">**Значение**</span><span class="sxs-lookup"><span data-stu-id="d76e8-111">**Value**</span></span> |
|:-------|:------:|--------:|
|<span data-ttu-id="d76e8-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="d76e8-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  |<span data-ttu-id="d76e8-113">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="d76e8-113">REG_DWORD</span></span>  |<span data-ttu-id="d76e8-114">1</span><span class="sxs-lookup"><span data-stu-id="d76e8-114">1</span></span>  |
|<span data-ttu-id="d76e8-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="d76e8-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span> |<span data-ttu-id="d76e8-116">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="d76e8-116">REG_DWORD</span></span> |<span data-ttu-id="d76e8-117">1</span><span class="sxs-lookup"><span data-stu-id="d76e8-117">1</span></span> |
   
<span data-ttu-id="d76e8-118">После того как вы установили ключи реестра, вы можете установить приложения Office 2013 года для использования [многофакторной аутентификации (MFA)](set-up-multi-factor-authentication.md) с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d76e8-118">Once you have set the registry keys, you can set Office 2013 devices apps to use [multifactor authentication (MFA)](set-up-multi-factor-authentication.md) with Microsoft 365.</span></span> 
  
<span data-ttu-id="d76e8-p102">Если вы вошли в одно из клиентских приложений, выйдите из него и войдите снова, чтобы изменения вступили в силу. В противном случае, файлы, с которыми вы недавно работали, и настройки роуминга останутся недоступными до тех пор, пока не будет установлено удостоверение библиотек ADAL.</span><span class="sxs-lookup"><span data-stu-id="d76e8-p102">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span></span>
  
## <a name="disable-modern-authentication-on-devices"></a><span data-ttu-id="d76e8-121">Отключение современный проверки подлинности на устройствах</span><span class="sxs-lookup"><span data-stu-id="d76e8-121">Disable modern authentication on devices</span></span>

<span data-ttu-id="d76e8-122">Чтобы отключить современную проверку подлинности на устройстве, настройте на нем следующие разделы реестра:</span><span class="sxs-lookup"><span data-stu-id="d76e8-122">To disable modern authentication on a device, set the following registry keys on the device:</span></span>
  
|<span data-ttu-id="d76e8-123">**Раздел реестра**</span><span class="sxs-lookup"><span data-stu-id="d76e8-123">**Registry key**</span></span>|<span data-ttu-id="d76e8-124">**Тип**</span><span class="sxs-lookup"><span data-stu-id="d76e8-124">**Type**</span></span>|<span data-ttu-id="d76e8-125">**Значение**</span><span class="sxs-lookup"><span data-stu-id="d76e8-125">**Value**</span></span>|
|:-------|:------:|--------:|
|<span data-ttu-id="d76e8-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="d76e8-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span> |<span data-ttu-id="d76e8-127">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="d76e8-127">REG_DWORD</span></span>|<span data-ttu-id="d76e8-128">0</span><span class="sxs-lookup"><span data-stu-id="d76e8-128">0</span></span>|
   
## <a name="related-content"></a><span data-ttu-id="d76e8-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="d76e8-129">Related content</span></span>

<span data-ttu-id="d76e8-130">[Во вопишитесь Office 2013 года со вторым методом проверки](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) (статья)</span><span class="sxs-lookup"><span data-stu-id="d76e8-130">[Sign in to Office 2013 with a second verification method](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) (article)</span></span>

<span data-ttu-id="d76e8-131">[Outlook запросы на пароль и не использует современную аутентификацию для подключения к Office 365](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled) (статья)</span><span class="sxs-lookup"><span data-stu-id="d76e8-131">[Outlook prompts for password and doesn't use Modern Authentication to connect to Office 365](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled) (article)</span></span>

