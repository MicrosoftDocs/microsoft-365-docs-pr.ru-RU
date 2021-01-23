---
title: Установка портала компании Intune на устройствах
description: Сведения об установке приложения портала компании на устройствах, управляемых Майкрософт
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, портал компании
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bddf46e451408e4f17e58cc62186b7cd6cefb382
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939288"
---
# <a name="install-intune-company-portal-on-devices"></a><span data-ttu-id="49a03-104">Установка портала компании Intune на устройствах</span><span class="sxs-lookup"><span data-stu-id="49a03-104">Install Intune Company Portal on devices</span></span>

<span data-ttu-id="49a03-105">Компьютеры, управляемые Майкрософт, требуют, чтобы ИТ-администраторы установили портал компании Intune для своих пользователей с управляемыми Майкрософт настольными устройствами.</span><span class="sxs-lookup"><span data-stu-id="49a03-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="49a03-106">Вот некоторые преимущества для вашей организации:</span><span class="sxs-lookup"><span data-stu-id="49a03-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="49a03-107">Пользователи могут просматривать и устанавливать доступные приложения в одном месте.</span><span class="sxs-lookup"><span data-stu-id="49a03-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="49a03-108">ИТ-администраторы могут упорядоизировать приложения по категориям для своих пользователей.</span><span class="sxs-lookup"><span data-stu-id="49a03-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="49a03-109">Некоторые приложения (например, Microsoft Project и Microsoft Visio) требуют развертывания портала компании с управляемыми Майкрософт настольными компьютерами.</span><span class="sxs-lookup"><span data-stu-id="49a03-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="49a03-110">ИТ-администраторы могут настраивать портал компании для своей организации.</span><span class="sxs-lookup"><span data-stu-id="49a03-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="49a03-111">К ним относятся фирменный образ, добавление контактов локальной службы поддержки и другие.</span><span class="sxs-lookup"><span data-stu-id="49a03-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="49a03-112">Дополнительные сведения см. в сведениях о настройке приложения "Портал компании [Microsoft Intune".](https://docs.microsoft.com/intune/company-portal-app)</span><span class="sxs-lookup"><span data-stu-id="49a03-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](https://docs.microsoft.com/intune/company-portal-app).</span></span>   

<span data-ttu-id="49a03-113">В этом разделе документироваться процесс развертывания портала компании Intune для пользователей компьютеров, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="49a03-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="49a03-114">Общий процесс выглядит так:</span><span class="sxs-lookup"><span data-stu-id="49a03-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="49a03-115">Приобретение портала компании в Microsoft Store для бизнеса и синхронизация с Intune</span><span class="sxs-lookup"><span data-stu-id="49a03-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="49a03-116">Назначение портала компании пользователям</span><span class="sxs-lookup"><span data-stu-id="49a03-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="49a03-117">Общение с пользователями об изменениях</span><span class="sxs-lookup"><span data-stu-id="49a03-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="49a03-118">Шаг 1. Приобретение портала компании в Microsoft Store для бизнеса и синхронизация с Intune</span><span class="sxs-lookup"><span data-stu-id="49a03-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="49a03-119">Сведения о том, как приобрести приложения и синхронизировать с Intune, см. в подстройке ["Развертывание](deploy-apps.md#msfb-apps) приложений на настольных устройствах, управляемых Майкрософт".</span><span class="sxs-lookup"><span data-stu-id="49a03-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="49a03-120">В этом разделе содержится информация о том, как:</span><span class="sxs-lookup"><span data-stu-id="49a03-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="49a03-121">Приобретение портала компании в Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="49a03-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="49a03-122">При принудительной синхронизации между Intune и Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="49a03-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="49a03-123">Проверка активной синхронизации Между Intune и Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="49a03-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="49a03-124">Шаг 2. Назначение портала компании пользователям</span><span class="sxs-lookup"><span data-stu-id="49a03-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="49a03-125">После регистрации на компьютере, управляемом Майкрософт, операции microsoft Managed Desktop Operations автоматически развернет портал компании в клиенте и установит приложение на компьютерах, управляемых Майкрософт, в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="49a03-125">Following your enrollment in Microsoft Managed Desktop, Microsoft Managed Desktop Operations will automatically deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="49a03-126">Шаг 3. Общение с пользователями об изменениях</span><span class="sxs-lookup"><span data-stu-id="49a03-126">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="49a03-127">Как ИТ-администратор организации, важно дать пользователям знать, как использовать портал компании в организации.</span><span class="sxs-lookup"><span data-stu-id="49a03-127">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="49a03-128">На компьютере, управляемом Майкрософт, рекомендуется:</span><span class="sxs-lookup"><span data-stu-id="49a03-128">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="49a03-129">Действия по установке приложений с портала компании.</span><span class="sxs-lookup"><span data-stu-id="49a03-129">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="49a03-130">Дополнительные сведения см. в [теме "Установка и совместное использовать приложения на устройстве".](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows)</span><span class="sxs-lookup"><span data-stu-id="49a03-130">For more information, see [Install and share apps on your device](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="49a03-131">Отправка запросов ИТ-администраторам для приложений, которые в настоящее время недоступны.</span><span class="sxs-lookup"><span data-stu-id="49a03-131">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="49a03-132">Дополнительные сведения см. в [запросе приложения для работы или учебного заведения.](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)</span><span class="sxs-lookup"><span data-stu-id="49a03-132">For more information, see [Request an app for work or school](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="49a03-133">Действия по началу работы с компьютером, управляемым Майкрософт</span><span class="sxs-lookup"><span data-stu-id="49a03-133">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="49a03-134">Добавление и проверка контактов администратора на портале администрирования</span><span class="sxs-lookup"><span data-stu-id="49a03-134">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="49a03-135">Настройка условного доступа</span><span class="sxs-lookup"><span data-stu-id="49a03-135">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="49a03-136">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="49a03-136">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="49a03-137">Развертывание портала компании Intune (этот раздел)</span><span class="sxs-lookup"><span data-stu-id="49a03-137">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="49a03-138">Включение службы Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="49a03-138">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="49a03-139">Настройка устройств</span><span class="sxs-lookup"><span data-stu-id="49a03-139">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="49a03-140">Подготовка пользователей к работе с устройствами</span><span class="sxs-lookup"><span data-stu-id="49a03-140">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="49a03-141">Развертывание приложений</span><span class="sxs-lookup"><span data-stu-id="49a03-141">Deploy apps</span></span>](deploy-apps.md)
