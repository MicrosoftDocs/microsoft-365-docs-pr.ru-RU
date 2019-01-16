---
title: Требования к Microsoft Desktop управляемых приложений
description: ''
keywords: Службы Microsoft Desktop управляемых, Microsoft 365, документация
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.openlocfilehash: 6b6c6f6a2e719496578ac1d15c9b94a92a2ab492
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870423"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="ff91a-103">Требования к Microsoft Desktop управляемых приложений</span><span class="sxs-lookup"><span data-stu-id="ff91a-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="ff91a-104">Бизнес приложений, которые вы хотите развернуть устройств Microsoft Desktop управляемых должны соответствовать требованиям в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="ff91a-104">Line-of-business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span> 

## <a name="application-condition"></a><span data-ttu-id="ff91a-105">Условие приложения</span><span class="sxs-lookup"><span data-stu-id="ff91a-105">Application condition</span></span>

<span data-ttu-id="ff91a-p101">Важно, что приложения не отрицательно влиять Microsoft Desktop управляемой среды. Ниже приведены требования, что приложения должны соответствовать в порядке корпорации Майкрософт развернуть его. Для данного приложения или драйвера Корпорация Майкрософт может отказаться от любого требования, приведенные в настоящем документе. Корпорация Майкрософт может приостановить для удаления любого приложения или драйвера, негативно влияет на производительность и надежность Microsoft Desktop управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="ff91a-p101">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment. The following are the requirements that an application must meet in order for Microsoft to deploy it. For any given application or driver, Microsoft may waive any requirement provided herein. Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="deployable-using-microsoft-technologies"></a><span data-ttu-id="ff91a-110">Развертывание с помощью технологий Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ff91a-110">Deployable using Microsoft technologies</span></span>

<span data-ttu-id="ff91a-p102">Microsoft Desktop управляемых использует Intune, хранилища Майкрософт и хранилища Майкрософт для бизнеса для развертывания приложений. Следовательно приложения должна быть упакована в виде могут быть развернуты с момент версия этих служб.</span><span class="sxs-lookup"><span data-stu-id="ff91a-p102">Microsoft Managed Desktop uses Intune,  Microsoft Store, and  Microsoft Store for Business to deploy applications. Consequently, applications must be packaged in a manner able to be deployed by the then-current version of those services.</span></span>

## <a name="prohibited-app-classes"></a><span data-ttu-id="ff91a-113">Классы запрещенного приложения</span><span class="sxs-lookup"><span data-stu-id="ff91a-113">Prohibited app classes</span></span>

<span data-ttu-id="ff91a-114">На устройствах Microsoft Desktop управляемых не разрешены определенные типы приложений:</span><span class="sxs-lookup"><span data-stu-id="ff91a-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="ff91a-115">сторонних производителей защиты от вирусов, безопасности или программного обеспечения аудита</span><span class="sxs-lookup"><span data-stu-id="ff91a-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="ff91a-116">веб-браузеры сторонних производителей</span><span class="sxs-lookup"><span data-stu-id="ff91a-116">3rd party web browsers</span></span>
- <span data-ttu-id="ff91a-117">Версий Microsoft Office до Office 365 профессиональный плюс</span><span class="sxs-lookup"><span data-stu-id="ff91a-117">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="ff91a-118">Приложения, установка или объединяют другое программное обеспечение, сторонних производителей</span><span class="sxs-lookup"><span data-stu-id="ff91a-118">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="ff91a-119">Поведение ограниченных приложения</span><span class="sxs-lookup"><span data-stu-id="ff91a-119">Restricted app behaviors</span></span>

<span data-ttu-id="ff91a-p103">Поведение конкретных приложений можно будет отрицательно влиять на взаимодействие с пользователем или существующий риск для Microsoft Desktop управляемых устройств. Приложения не должны представляют следующие модели поведения и их характеристики:</span><span class="sxs-lookup"><span data-stu-id="ff91a-p103">Certain application behaviors can either be detrimental to user experience or present a security risk to Microsoft Managed Desktop devices. Applications shall not exhibit the following behaviors or characteristics:</span></span> 

<span data-ttu-id="ff91a-122">Взаимодействие с пользователем:</span><span class="sxs-lookup"><span data-stu-id="ff91a-122">User Experience:</span></span>
- <span data-ttu-id="ff91a-123">Установка служб фона или обнаружения создают длительным фоновых процессах</span><span class="sxs-lookup"><span data-stu-id="ff91a-123">Install background services or spawn long-running background processes</span></span>
- <span data-ttu-id="ff91a-124">Добавление путь загрузки Windows</span><span class="sxs-lookup"><span data-stu-id="ff91a-124">Add itself to the Windows startup path</span></span>

<span data-ttu-id="ff91a-125">Безопасность</span><span class="sxs-lookup"><span data-stu-id="ff91a-125">Security:</span></span>
- <span data-ttu-id="ff91a-126">Звонок недокументированного Windows или интерфейсы API Office или принимать зависимости от внутренних структур данных Windows или Office</span><span class="sxs-lookup"><span data-stu-id="ff91a-126">Call undocumented Windows or Office APIs or take dependencies on internal Windows or Office data structures</span></span>
- <span data-ttu-id="ff91a-127">Выступать в качестве хранилище приложений или использовать диспетчер встроенных расширений</span><span class="sxs-lookup"><span data-stu-id="ff91a-127">Act as an app store or have built-in extension manager</span></span>
- <span data-ttu-id="ff91a-128">Повысить уровень привилегий конечного пользователя</span><span class="sxs-lookup"><span data-stu-id="ff91a-128">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="ff91a-129">Выявлены уязвимые места системы безопасности</span><span class="sxs-lookup"><span data-stu-id="ff91a-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="ff91a-130">С помощью которого не выполнять сведение доверенного корневого сертификата</span><span class="sxs-lookup"><span data-stu-id="ff91a-130">Signed using a certificate which doesn’t roll up to a trusted root</span></span>
- <span data-ttu-id="ff91a-131">Шифрование и ограничить доступ к данным конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="ff91a-131">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="ff91a-132">Изменение кода операционной системы во время выполнения</span><span class="sxs-lookup"><span data-stu-id="ff91a-132">Modify operating system code at run time</span></span>

## <a name="driver-deployment"></a><span data-ttu-id="ff91a-133">Драйвер развертывания</span><span class="sxs-lookup"><span data-stu-id="ff91a-133">Driver deployment</span></span>

<span data-ttu-id="ff91a-134">Если драйвер доступен в центре обновления Windows или отдельно подписана с Windows аппаратных средств лаборатории (WHQL), Microsoft драйвер после утверждения Microsoft развернете драйвер устройства Microsoft управляемых Desktop.</span><span class="sxs-lookup"><span data-stu-id="ff91a-134">Unless a driver is available in Windows Update or is separately signed by Windows Hardware Quality Lab (WHQL), Microsoft must approve a driver before Microsoft will deploy the driver to Microsoft Managed Desktop devices.</span></span>
