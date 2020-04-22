---
title: Требования к классическому приложению, управляемому корпорацией Майкрософт
description: ''
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5889a4e80f44349b4f149ee4f2a631f12b32251e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637856"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="f26bb-103">Требования к классическому приложению, управляемому корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f26bb-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="f26bb-104">Для обеспечения производительности, надежности и возможности обслуживания настольных устройств, управляемых корпорацией Майкрософт, бизнес-приложения клиента не должны серьезно повлиять на работу конечных пользователей или изменять станце безопасности.</span><span class="sxs-lookup"><span data-stu-id="f26bb-104">In order to guarantee the performance, reliability, and serviceability of Microsoft Managed Desktop devices a customer’s line of business apps must not seriously impact end user experience or modify the security stance.</span></span> <span data-ttu-id="f26bb-105">Следовательно, бизнес-приложения, которые вы хотите развернуть на настольных устройствах, управляемых Майкрософт, должны соответствовать требованиям, описанным в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="f26bb-105">Consequently, line of business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span>

## <a name="application-condition"></a><span data-ttu-id="f26bb-106">Условие приложения</span><span class="sxs-lookup"><span data-stu-id="f26bb-106">Application condition</span></span>

<span data-ttu-id="f26bb-107">Важно, чтобы приложения не влияли на настольные среды, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f26bb-107">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="f26bb-108">Ниже приведены требования, которым должно соответствовать приложение для развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="f26bb-108">The following are the requirements that an application must meet for an application to be deployed.</span></span> <span data-ttu-id="f26bb-109">Для любого конкретного приложения или драйвера Корпорация Майкрософт может отказаться от указанных здесь требований.</span><span class="sxs-lookup"><span data-stu-id="f26bb-109">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="f26bb-110">Корпорация Майкрософт может удалить все приложения и драйверы, которые негативно влияют на производительность и надежность управляемых устройств, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f26bb-110">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="centrally-managed-apps"></a><span data-ttu-id="f26bb-111">Централизованно управляемые приложения</span><span class="sxs-lookup"><span data-stu-id="f26bb-111">Centrally managed apps</span></span>

<span data-ttu-id="f26bb-112">Все приложения и драйверы, установленные на управляемых устройствах Майкрософт, должны быть развернуты с помощью Microsoft Intune, Microsoft Store или Microsoft Store для бизнеса; Если это возможно, драйверы также будут развернуты через службу центра обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="f26bb-112">All applications and drivers installed on Microsoft Managed Devices must be deployed through Microsoft Intune, the Microsoft Store, or the Microsoft Store for Business; if available, drivers will also be deployed through the Windows Update service.</span></span> 

## <a name="prohibited-app-classes"></a><span data-ttu-id="f26bb-113">Запрещенные классы приложений</span><span class="sxs-lookup"><span data-stu-id="f26bb-113">Prohibited app classes</span></span>

<span data-ttu-id="f26bb-114">Некоторые типы приложений не разрешены на компьютерах, управляемых корпорацией Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="f26bb-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="f26bb-115">антивирусное программное обеспечение сторонних производителей, безопасность и аудит</span><span class="sxs-lookup"><span data-stu-id="f26bb-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="f26bb-116">Версии Microsoft Office до Microsoft 365 приложений для предприятий</span><span class="sxs-lookup"><span data-stu-id="f26bb-116">Versions of Microsoft Office prior to Microsoft 365 Apps for enterprise</span></span>
- <span data-ttu-id="f26bb-117">Приложения, которые устанавливают или объединяют другое стороннее программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="f26bb-117">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="f26bb-118">Запрещенные варианты поведения приложений</span><span class="sxs-lookup"><span data-stu-id="f26bb-118">Restricted app behaviors</span></span>

<span data-ttu-id="f26bb-119">Некоторые варианты поведения приложений могут негативно сказаться на пользовательском интерфейсе или могут представлять угрозу безопасности для настольных устройств, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f26bb-119">Certain app behaviors can negatively impact the user experience or may present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f26bb-120">Приложения со следующими характеристиками не разрешается запускать в среде настольных компьютеров, управляемой корпорацией Майкрософт, без необходимости от корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f26bb-120">Apps with the following behaviors are not permitted to run in the Microsoft Managed Desktop environment without a specific  from Microsoft.</span></span>

<span data-ttu-id="f26bb-121">Взаимодействие с пользователем.</span><span class="sxs-lookup"><span data-stu-id="f26bb-121">User Experience:</span></span>
- <span data-ttu-id="f26bb-122">Установка фоновых служб</span><span class="sxs-lookup"><span data-stu-id="f26bb-122">Install background services</span></span>
- <span data-ttu-id="f26bb-123">Добавление себя в путь запуска Windows</span><span class="sxs-lookup"><span data-stu-id="f26bb-123">Add itself to the Windows startup path</span></span>
- <span data-ttu-id="f26bb-124">Приложения, зависящие от драйверов</span><span class="sxs-lookup"><span data-stu-id="f26bb-124">Applications dependent on drivers</span></span>
- <span data-ttu-id="f26bb-125">сторонние веб-браузеры</span><span class="sxs-lookup"><span data-stu-id="f26bb-125">3rd party web browsers</span></span>

<span data-ttu-id="f26bb-126">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f26bb-126">Security:</span></span>
- <span data-ttu-id="f26bb-127">Повышение привилегий конечного пользователя</span><span class="sxs-lookup"><span data-stu-id="f26bb-127">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="f26bb-128">Работа в качестве хранилища приложений или встроенного диспетчера расширений</span><span class="sxs-lookup"><span data-stu-id="f26bb-128">Act as an app store or have a built-in extension manager</span></span>
- <span data-ttu-id="f26bb-129">Известные уязвимости системы безопасности</span><span class="sxs-lookup"><span data-stu-id="f26bb-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="f26bb-130">Шифрование или ограничение доступа к данным конечного пользователя</span><span class="sxs-lookup"><span data-stu-id="f26bb-130">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="f26bb-131">Не является подписанным или подписано с помощью сертификата, который не выполняет накат до доверенного корня</span><span class="sxs-lookup"><span data-stu-id="f26bb-131">Is unsigned or is signed using a certificate which doesn’t roll up to a trusted root</span></span>


## <a name="driver-deployment"></a><span data-ttu-id="f26bb-132">Развертывание драйвера</span><span class="sxs-lookup"><span data-stu-id="f26bb-132">Driver deployment</span></span>

<span data-ttu-id="f26bb-133">На рабочем столе Майкрософт поддерживаются только драйверы устройств, доступные через обновление Windows или установленную папку "Входящие" с управляемым устройством Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f26bb-133">Microsoft Managed Desktop only supports device drivers that are available through Windows Update or installed inbox with the Microsoft Managed Device.</span></span> 

<span data-ttu-id="f26bb-134">Если приложению требуется определенный драйвер для запуска, оно считается ограниченным приложением и требует исключения перед развертыванием в управляемом рабочем столе Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f26bb-134">If an application requires a specific driver(s) to run it is considered a Restricted Application and requires an exception before being deployed to Microsoft Managed Desktop.</span></span> 

