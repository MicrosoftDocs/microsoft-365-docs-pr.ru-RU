---
title: Включение современной проверки подлинности для Office 2013 на устройствах с Windows
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Сведения о настройке разделов реестра для включения современной проверки подлинности для устройств, на которых установлен Microsoft Office 2013.
ms.openlocfilehash: 8edcedefc04d5018b8b61022c26cbe027f7c24a9
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779969"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a><span data-ttu-id="f9d50-103">Включение современной проверки подлинности для Office 2013 на устройствах с Windows</span><span class="sxs-lookup"><span data-stu-id="f9d50-103">Enable Modern Authentication for Office 2013 on Windows devices</span></span>

<span data-ttu-id="f9d50-104">Чтобы включить современную проверку подлинности для устройств Windows, на которых установлен Office 2013, необходимо настроить разделы реестра.</span><span class="sxs-lookup"><span data-stu-id="f9d50-104">To enable modern authentication for any Windows devices that have Office 2013 installed, you need to set specific registry keys.</span></span>
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a><span data-ttu-id="f9d50-105">Включение современной проверки подлинности для клиентов Office 2013</span><span class="sxs-lookup"><span data-stu-id="f9d50-105">Enable modern authentication for Office 2013 clients</span></span>

> [!NOTE]
> <span data-ttu-id="f9d50-106">Современная проверка подлинности уже включена для клиентов Office 2016. Настраивать разделы реестра для Office 2016 не нужно.</span><span class="sxs-lookup"><span data-stu-id="f9d50-106">Modern authentication is already enabled for Office 2016 clients, you do not need to set registry keys for Office 2016.</span></span> 
  
<span data-ttu-id="f9d50-p101">Чтобы включить современную проверку подлинности для устройства с Windows (например, ноутбука или планшета), на котором установлен Microsoft Office 2013, необходимо настроить указанные ниже разделы реестра. Это нужно сделать для каждого устройства, на котором вы хотите включить современную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="f9d50-p101">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:</span></span>
  
|<span data-ttu-id="f9d50-109">**Раздел реестра**</span><span class="sxs-lookup"><span data-stu-id="f9d50-109">**Registry key**</span></span>|<span data-ttu-id="f9d50-110">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f9d50-110">**Type**</span></span>|<span data-ttu-id="f9d50-111">**Значение**</span><span class="sxs-lookup"><span data-stu-id="f9d50-111">**Value**</span></span> |
|:-------|:------:|--------:|
|<span data-ttu-id="f9d50-112">Hkcu\software\microsoft\office\15.0\common\identity\enableadal нулевое</span><span class="sxs-lookup"><span data-stu-id="f9d50-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  |<span data-ttu-id="f9d50-113">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="f9d50-113">REG_DWORD</span></span>  |<span data-ttu-id="f9d50-114">1 </span><span class="sxs-lookup"><span data-stu-id="f9d50-114">1</span></span>  |
|<span data-ttu-id="f9d50-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="f9d50-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span> |<span data-ttu-id="f9d50-116">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="f9d50-116">REG_DWORD</span></span> |<span data-ttu-id="f9d50-117">1 </span><span class="sxs-lookup"><span data-stu-id="f9d50-117">1</span></span> |
   
<span data-ttu-id="f9d50-118">После настройки разделов реестра можно настроить приложения Office 2013 для использования [многофакторной проверки подлинности (MFA)](set-up-multi-factor-authentication.md) с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f9d50-118">Once you have set the registry keys, you can set Office 2013 devices apps to use [multifactor authentication (MFA)](set-up-multi-factor-authentication.md) with Microsoft 365.</span></span> 
  
<span data-ttu-id="f9d50-p102">Если вы вошли в одно из клиентских приложений, выйдите из него и войдите снова, чтобы изменения вступили в силу. В противном случае, файлы, с которыми вы недавно работали, и настройки роуминга останутся недоступными до тех пор, пока не будет установлено удостоверение библиотек ADAL.</span><span class="sxs-lookup"><span data-stu-id="f9d50-p102">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span></span>
  
## <a name="disable-modern-authentication-on-devices"></a><span data-ttu-id="f9d50-121">Отключение современный проверки подлинности на устройствах</span><span class="sxs-lookup"><span data-stu-id="f9d50-121">Disable modern authentication on devices</span></span>

<span data-ttu-id="f9d50-122">Чтобы отключить современную проверку подлинности на устройстве, настройте на нем следующие разделы реестра:</span><span class="sxs-lookup"><span data-stu-id="f9d50-122">To disable modern authentication on a device, set the following registry keys on the device:</span></span>
  
|<span data-ttu-id="f9d50-123">**Раздел реестра**</span><span class="sxs-lookup"><span data-stu-id="f9d50-123">**Registry key**</span></span>|<span data-ttu-id="f9d50-124">**Тип**</span><span class="sxs-lookup"><span data-stu-id="f9d50-124">**Type**</span></span>|<span data-ttu-id="f9d50-125">**Значение**</span><span class="sxs-lookup"><span data-stu-id="f9d50-125">**Value**</span></span>|
|:-------|:------:|--------:|
|<span data-ttu-id="f9d50-126">Hkcu\software\microsoft\office\15.0\common\identity\enableadal нулевое</span><span class="sxs-lookup"><span data-stu-id="f9d50-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span> |<span data-ttu-id="f9d50-127">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="f9d50-127">REG_DWORD</span></span>|<span data-ttu-id="f9d50-128">нуль</span><span class="sxs-lookup"><span data-stu-id="f9d50-128">0</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="f9d50-129">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="f9d50-129">Related articles</span></span>
[<span data-ttu-id="f9d50-130">Вход в Office 2013 со вторым способом проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f9d50-130">Sign in to Office 2013 with a second verification method</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

  

