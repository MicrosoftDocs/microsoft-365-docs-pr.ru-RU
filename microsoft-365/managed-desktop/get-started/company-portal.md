---
title: Установка портала компании Intune на устройствах
description: Сведения об установке приложения портала компании на устройствах Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Портал компании
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f4c5d20529a210207e225d4a2b46d5935ae112c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925778"
---
# <a name="install-intune-company-portal-on-devices"></a><span data-ttu-id="9729a-104">Установка портала компании Intune на устройствах</span><span class="sxs-lookup"><span data-stu-id="9729a-104">Install Intune Company Portal on devices</span></span>

<span data-ttu-id="9729a-105">Microsoft Managed Desktop требует, чтобы ИТ-администраторы устанавливали портал компании Intune для своих пользователей на устройствах Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="9729a-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="9729a-106">Вот некоторые преимущества для организации:</span><span class="sxs-lookup"><span data-stu-id="9729a-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="9729a-107">У пользователей есть одно место для просмотра и установки доступных приложений.</span><span class="sxs-lookup"><span data-stu-id="9729a-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="9729a-108">ИТ-администраторы могут организовывать приложения по категориям для своих пользователей.</span><span class="sxs-lookup"><span data-stu-id="9729a-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="9729a-109">Некоторые приложения (например, Microsoft Project и Microsoft Visio) требуют развертывания портала компании с помощью Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="9729a-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="9729a-110">ИТ-администраторы могут настраивать портал компании для своей организации.</span><span class="sxs-lookup"><span data-stu-id="9729a-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="9729a-111">Это включает визуализацию бренда, добавление локальных контактов поддержки и другие.</span><span class="sxs-lookup"><span data-stu-id="9729a-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="9729a-112">Дополнительные сведения см. [в сайте How to Configure the Microsoft Intune Company Portal app](/intune/company-portal-app).</span><span class="sxs-lookup"><span data-stu-id="9729a-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](/intune/company-portal-app).</span></span>   

<span data-ttu-id="9729a-113">В этом разделе документироваться процесс развертывания портала компании Intune для пользователей управляемых настольных компьютеров Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9729a-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="9729a-114">Общий процесс выглядит так:</span><span class="sxs-lookup"><span data-stu-id="9729a-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="9729a-115">Покупка портала компании в Microsoft Store для бизнеса и синхронизация с Intune</span><span class="sxs-lookup"><span data-stu-id="9729a-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="9729a-116">Назначение портала компании пользователям</span><span class="sxs-lookup"><span data-stu-id="9729a-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="9729a-117">Сообщить пользователям об изменении</span><span class="sxs-lookup"><span data-stu-id="9729a-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="9729a-118">Шаг 1 — Покупка портала компании в Microsoft Store для бизнеса и синхронизация с Intune</span><span class="sxs-lookup"><span data-stu-id="9729a-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="9729a-119">Сведения о том, как приобрести приложения и синхронизироваться с Intune, см. в [веб-сайте Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in Deploy apps to Microsoft Managed Desktop *devices.*</span><span class="sxs-lookup"><span data-stu-id="9729a-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="9729a-120">В этом разделе приводится информация о том, как:</span><span class="sxs-lookup"><span data-stu-id="9729a-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="9729a-121">Покупка портала компании в Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="9729a-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="9729a-122">Синхронизация усилий между Intune и Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="9729a-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="9729a-123">Проверка активной синхронизации между Intune и Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="9729a-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="9729a-124">Шаг 2 . Назначение портала компании пользователям</span><span class="sxs-lookup"><span data-stu-id="9729a-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="9729a-125">После регистрации в Microsoft Managed Desktop Microsoft Managed Desktop Operations автоматически развертывает портал компании для клиента и установит приложение на устройствах Microsoft Managed Desktop в организации.</span><span class="sxs-lookup"><span data-stu-id="9729a-125">Following your enrollment in Microsoft Managed Desktop, Microsoft Managed Desktop Operations will automatically deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="9729a-126">Шаг 3 . Изменение связи с пользователями</span><span class="sxs-lookup"><span data-stu-id="9729a-126">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="9729a-127">В качестве ИТ-администратора организации важно, чтобы пользователи знали, как использовать портал компании в организации.</span><span class="sxs-lookup"><span data-stu-id="9729a-127">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="9729a-128">Microsoft Managed Desktop рекомендует:</span><span class="sxs-lookup"><span data-stu-id="9729a-128">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="9729a-129">Действия по установке приложений с портала компании.</span><span class="sxs-lookup"><span data-stu-id="9729a-129">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="9729a-130">Дополнительные сведения см. в [раздел Установка и совместное приложение на устройстве.](/intune-user-help/install-apps-cpapp-windows)</span><span class="sxs-lookup"><span data-stu-id="9729a-130">For more information, see [Install and share apps on your device](/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="9729a-131">Отправка запросов ИТ-администраторам для приложений, недоступных в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="9729a-131">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="9729a-132">Дополнительные сведения см. в [примере Request an app for work or school.](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)</span><span class="sxs-lookup"><span data-stu-id="9729a-132">For more information, see [Request an app for work or school](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="9729a-133">Действия по началу работы с управляемым рабочим столом Майкрософт</span><span class="sxs-lookup"><span data-stu-id="9729a-133">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="9729a-134">Добавление и проверка контактов администратора на портале администрирования</span><span class="sxs-lookup"><span data-stu-id="9729a-134">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="9729a-135">Настройка условного доступа</span><span class="sxs-lookup"><span data-stu-id="9729a-135">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="9729a-136">Назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="9729a-136">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="9729a-137">Развертывание портала компании Intune (этот раздел)</span><span class="sxs-lookup"><span data-stu-id="9729a-137">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="9729a-138">Включение службы Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="9729a-138">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="9729a-139">Настройка устройств</span><span class="sxs-lookup"><span data-stu-id="9729a-139">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="9729a-140">Подготовка пользователей к работе с устройствами</span><span class="sxs-lookup"><span data-stu-id="9729a-140">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="9729a-141">Развертывание приложений</span><span class="sxs-lookup"><span data-stu-id="9729a-141">Deploy apps</span></span>](deploy-apps.md)