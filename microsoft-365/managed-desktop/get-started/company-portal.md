---
title: Установка Корпоративный портал Intune на устройствах
description: Сведения об установке приложения портала компании на компьютеры, управляемые Майкрософт устройствах
keywords: компьютеры, управляемые Майкрософт, Microsoft 365, Корпоративный портал
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f9f36d6ca14be610ce9374380349264439282a6a
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086689"
---
# <a name="install-intune-company-portal-on-devices"></a><span data-ttu-id="8fdb4-104">Установка Корпоративный портал Intune на устройствах</span><span class="sxs-lookup"><span data-stu-id="8fdb4-104">Install Intune Company Portal on devices</span></span>

<span data-ttu-id="8fdb4-105">компьютеры, управляемые Майкрософт, что ИТ-администраторы Корпоративный портал Intune для своих пользователей с помощью компьютеры, управляемые Майкрософт устройств.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8fdb4-106">Вот некоторые преимущества для организации:</span><span class="sxs-lookup"><span data-stu-id="8fdb4-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="8fdb4-107">У пользователей есть одно место для просмотра и установки доступных приложений.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="8fdb4-108">ИТ-администраторы могут организовывать приложения по категориям для своих пользователей.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="8fdb4-109">Некоторым приложениям (например, Microsoft Project и Microsoft Visio) Корпоративный портал развертывание с помощью компьютеры, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="8fdb4-110">ИТ-администраторы могут настраивать Корпоративный портал для своей организации.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="8fdb4-111">Это включает визуализацию бренда, добавление локальных контактов поддержки и другие.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="8fdb4-112">Дополнительные сведения см. [в приложении How to Configure the Microsoft Intune Корпоративный портал.](/intune/company-portal-app)</span><span class="sxs-lookup"><span data-stu-id="8fdb4-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](/intune/company-portal-app).</span></span>   

<span data-ttu-id="8fdb4-113">В этом разделе документироваться процесс развертывания Корпоративный портал Intune для компьютеры, управляемые Майкрософт пользователей.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="8fdb4-114">Общий процесс выглядит так:</span><span class="sxs-lookup"><span data-stu-id="8fdb4-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="8fdb4-115">Покупка Корпоративный портал в Microsoft Store для бизнеса и синхронизация с Intune</span><span class="sxs-lookup"><span data-stu-id="8fdb4-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="8fdb4-116">Назначение Корпоративный портал пользователям</span><span class="sxs-lookup"><span data-stu-id="8fdb4-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="8fdb4-117">Сообщить пользователям об изменении</span><span class="sxs-lookup"><span data-stu-id="8fdb4-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="8fdb4-118">Шаг 1 . Покупка Корпоративный портал из Microsoft Store для бизнеса и синхронизация с Intune</span><span class="sxs-lookup"><span data-stu-id="8fdb4-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="8fdb4-119">Сведения о том, как приобрести приложения и синхронизировать их с Intune, см. Microsoft Store для бизнеса [приложениях](deploy-apps.md#msfb-apps) в *Deploy apps to компьютеры, управляемые Майкрософт устройствах.*</span><span class="sxs-lookup"><span data-stu-id="8fdb4-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="8fdb4-120">В этом разделе приводится информация о том, как:</span><span class="sxs-lookup"><span data-stu-id="8fdb4-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="8fdb4-121">Покупка Корпоративный портал в Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="8fdb4-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="8fdb4-122">Синхронизация усилий между Intune и Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="8fdb4-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="8fdb4-123">Проверка активной синхронизации между Intune и Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="8fdb4-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="8fdb4-124">Шаг 2 . Назначение Корпоративный портал пользователям</span><span class="sxs-lookup"><span data-stu-id="8fdb4-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="8fdb4-125">После регистрации в компьютеры, управляемые Майкрософт мы автоматически Корпоративный портал клиента и установим приложение на компьютеры, управляемые Майкрософт устройствах в организации.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-125">Following your enrollment in Microsoft Managed Desktop, we will automatically deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="8fdb4-126">Шаг 3 . Изменение связи с пользователями</span><span class="sxs-lookup"><span data-stu-id="8fdb4-126">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="8fdb4-127">В качестве ИТ-администратора организации важно, чтобы пользователи знали, как использовать Корпоративный портал в организации.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-127">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="8fdb4-128">компьютеры, управляемые Майкрософт рекомендует:</span><span class="sxs-lookup"><span data-stu-id="8fdb4-128">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="8fdb4-129">Действия по установке приложений из Корпоративный портал.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-129">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="8fdb4-130">Дополнительные сведения см. в [раздел Установка и совместное приложение на устройстве.](/intune-user-help/install-apps-cpapp-windows)</span><span class="sxs-lookup"><span data-stu-id="8fdb4-130">For more information, see [Install and share apps on your device](/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="8fdb4-131">Отправка запросов ИТ-администраторам для приложений, недоступных в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-131">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="8fdb4-132">Дополнительные сведения см. в [примере Request an app for work or school.](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)</span><span class="sxs-lookup"><span data-stu-id="8fdb4-132">For more information, see [Request an app for work or school](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="8fdb4-133">Шаги для начала работы с компьютеры, управляемые Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8fdb4-133">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="8fdb4-134">Добавление и проверка контактов администратора на портале администрирования</span><span class="sxs-lookup"><span data-stu-id="8fdb4-134">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="8fdb4-135">Настройка условного доступа</span><span class="sxs-lookup"><span data-stu-id="8fdb4-135">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="8fdb4-136">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="8fdb4-136">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="8fdb4-137">Развертывание Корпоративный портал Intune (этот раздел)</span><span class="sxs-lookup"><span data-stu-id="8fdb4-137">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="8fdb4-138">Включение службы Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="8fdb4-138">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="8fdb4-139">Настройка устройств</span><span class="sxs-lookup"><span data-stu-id="8fdb4-139">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="8fdb4-140">Подготовка пользователей к работе с устройствами</span><span class="sxs-lookup"><span data-stu-id="8fdb4-140">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="8fdb4-141">Развертывание приложений</span><span class="sxs-lookup"><span data-stu-id="8fdb4-141">Deploy apps</span></span>](deploy-apps.md)
