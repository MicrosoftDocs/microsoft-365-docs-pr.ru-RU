---
title: Требования к классическому приложению, управляемому корпорацией Майкрософт
description: ''
keywords: НаСтольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: de6cc7d77e023a9d41961e5fbcce060f1bb659ae
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278339"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="fc90a-103">Требования к классическому приложению, управляемому корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="fc90a-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="fc90a-104">Бизнес-приложения, которые необходимо развернуть на наСтольных устройствах, управляемых корпорацией Майкрософт, должны соответствовать требованиям, описанным в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="fc90a-104">Line-of-business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span> 

## <a name="application-condition"></a><span data-ttu-id="fc90a-105">Условие приложения</span><span class="sxs-lookup"><span data-stu-id="fc90a-105">Application condition</span></span>

<span data-ttu-id="fc90a-106">Важно, чтобы приложения не влияли на наСтольные среды, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fc90a-106">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="fc90a-107">Ниже приведены требования, которым должно соответствовать приложение, чтобы оно было развернуто корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fc90a-107">The following are the requirements that an application must meet in order for Microsoft to deploy it.</span></span> <span data-ttu-id="fc90a-108">Для любого конкретного приложения или драйвера Корпорация Майкрософт может отказаться от указанных здесь требований.</span><span class="sxs-lookup"><span data-stu-id="fc90a-108">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="fc90a-109">Корпорация Майкрософт может удалить все приложения и драйверы, которые негативно влияют на производительность и надежность управляемых устройств, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fc90a-109">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="deployable-using-microsoft-technologies"></a><span data-ttu-id="fc90a-110">Развертывание с помощью технологий Майкрософт</span><span class="sxs-lookup"><span data-stu-id="fc90a-110">Deployable using Microsoft technologies</span></span>

<span data-ttu-id="fc90a-111">Для развертывания приложений на рабочем столе Майкрософт используются Intune, Microsoft Store и Microsoft Store для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="fc90a-111">Microsoft Managed Desktop uses Intune,  Microsoft Store, and  Microsoft Store for Business to deploy applications.</span></span> <span data-ttu-id="fc90a-112">Следовательно, приложения должны быть упакованы таким образом, чтобы их можно было развернуть с помощью последней версии этих служб.</span><span class="sxs-lookup"><span data-stu-id="fc90a-112">Consequently, applications must be packaged in a manner able to be deployed by the then-current version of those services.</span></span>

## <a name="prohibited-app-classes"></a><span data-ttu-id="fc90a-113">Запрещенные классы приложений</span><span class="sxs-lookup"><span data-stu-id="fc90a-113">Prohibited app classes</span></span>

<span data-ttu-id="fc90a-114">Некоторые типы приложений не разрешены на компьютерах, управляемых корпорацией Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="fc90a-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="fc90a-115">антивирусное программное обеспечение сторонних производителей, безопасность и аудит</span><span class="sxs-lookup"><span data-stu-id="fc90a-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="fc90a-116">сторонние веб-браузеры</span><span class="sxs-lookup"><span data-stu-id="fc90a-116">3rd party web browsers</span></span>
- <span data-ttu-id="fc90a-117">Версии Microsoft Office до Office 365 профессиональный плюс</span><span class="sxs-lookup"><span data-stu-id="fc90a-117">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="fc90a-118">Приложения, которые устанавливают или объединяют другое стороннее программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="fc90a-118">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="fc90a-119">Запрещенные варианты поведения приложений</span><span class="sxs-lookup"><span data-stu-id="fc90a-119">Restricted app behaviors</span></span>

<span data-ttu-id="fc90a-120">Некоторые варианты поведения приложений могут быть негативными для взаимодействия с пользователем или представлять угрозу безопасности для наСтольных устройств, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fc90a-120">Certain application behaviors can either be detrimental to user experience or present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fc90a-121">Приложения не будут обладать следующими характеристиками или характеристиками:</span><span class="sxs-lookup"><span data-stu-id="fc90a-121">Applications shall not exhibit the following behaviors or characteristics:</span></span> 

<span data-ttu-id="fc90a-122">Взаимодействие с пользователем.</span><span class="sxs-lookup"><span data-stu-id="fc90a-122">User Experience:</span></span>
- <span data-ttu-id="fc90a-123">Установка фоновых служб или запуск долгосрочных фоновых процессов</span><span class="sxs-lookup"><span data-stu-id="fc90a-123">Install background services or spawn long-running background processes</span></span>
- <span data-ttu-id="fc90a-124">Добавление себя в путь запуска Windows</span><span class="sxs-lookup"><span data-stu-id="fc90a-124">Add itself to the Windows startup path</span></span>

<span data-ttu-id="fc90a-125">Безопасность</span><span class="sxs-lookup"><span data-stu-id="fc90a-125">Security:</span></span>
- <span data-ttu-id="fc90a-126">Вызов недокументированных интерфейсов API Windows или Office или получение зависимостей от внутренних структур данных Windows или Office</span><span class="sxs-lookup"><span data-stu-id="fc90a-126">Call undocumented Windows or Office APIs or take dependencies on internal Windows or Office data structures</span></span>
- <span data-ttu-id="fc90a-127">Работа в качестве хранилища приложений или встроенного диспетчера расширений</span><span class="sxs-lookup"><span data-stu-id="fc90a-127">Act as an app store or have built-in extension manager</span></span>
- <span data-ttu-id="fc90a-128">Повышение привилегий конечного пользователя</span><span class="sxs-lookup"><span data-stu-id="fc90a-128">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="fc90a-129">Известные уязвимости системы безопасности</span><span class="sxs-lookup"><span data-stu-id="fc90a-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="fc90a-130">Подписан с помощью сертификата, который не выполняет накат до доверенного корня</span><span class="sxs-lookup"><span data-stu-id="fc90a-130">Signed using a certificate which doesn’t roll up to a trusted root</span></span>
- <span data-ttu-id="fc90a-131">Шифрование или ограничение доступа к данным конечного пользователя</span><span class="sxs-lookup"><span data-stu-id="fc90a-131">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="fc90a-132">Изменение кода операционной системы во время выполнения</span><span class="sxs-lookup"><span data-stu-id="fc90a-132">Modify operating system code at run time</span></span>

## <a name="driver-deployment"></a><span data-ttu-id="fc90a-133">Развертывание драйвера</span><span class="sxs-lookup"><span data-stu-id="fc90a-133">Driver deployment</span></span>

<span data-ttu-id="fc90a-134">Если драйвер не доступен в средстве обновления Windows или не подписан с помощью Windows Hardware Quality Lab (WHQL), корпорация Майкрософт должна утвердить драйвер до того, как корпорация Майкрософт будет развертывать драйвер на наСтольных устройствах, управляемых корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fc90a-134">Unless a driver is available in Windows Update or is separately signed by Windows Hardware Quality Lab (WHQL), Microsoft must approve a driver before Microsoft will deploy the driver to Microsoft Managed Desktop devices.</span></span>
