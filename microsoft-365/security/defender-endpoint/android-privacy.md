---
title: Microsoft Defender ATP для Android — сведения о конфиденциальности
description: Управление конфиденциальностью, настройка параметров политики, которые влияют на конфиденциальность и сведения о диагностических данных, собранных в MICROSOFT Defender ATP для Android.
keywords: Microsoft, defender, atp, Android, privacy, diagnostic
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d38d7a54aa860049e1968e5b92c801107bea0514
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687965"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a><span data-ttu-id="f06dd-104">Microsoft Defender для конечной точки на Android — сведения о конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="f06dd-104">Microsoft Defender for Endpoint on Android - Privacy information</span></span>

<span data-ttu-id="f06dd-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f06dd-105">**Applies to:**</span></span>
- [<span data-ttu-id="f06dd-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f06dd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f06dd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f06dd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f06dd-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="f06dd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f06dd-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="f06dd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="f06dd-110">Defender for Endpoint для Android собирает сведения с настроенных android-устройств и хранит их в том же клиенте, где у вас есть Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="f06dd-110">Defender for Endpoint for Android collects information from your configured Android devices and stores it in the same tenant where you have Defender for Endpoint.</span></span>

<span data-ttu-id="f06dd-111">Сведения собираются, чтобы защитить Defender для конечной точки для Android в соответствии с ожидаемым сроком выполнения и поддерживать службу.</span><span class="sxs-lookup"><span data-stu-id="f06dd-111">Information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected and to support the service.</span></span>

## <a name="required-data"></a><span data-ttu-id="f06dd-112">Необходимые данные</span><span class="sxs-lookup"><span data-stu-id="f06dd-112">Required Data</span></span> 

<span data-ttu-id="f06dd-113">Необходимые данные состоят из данных, необходимых для обеспечения работы Defender для Конечной точки для Android, как и ожидалось.</span><span class="sxs-lookup"><span data-stu-id="f06dd-113">Required data consists of data that is necessary to make Defender for Endpoint for Android work as expected.</span></span> <span data-ttu-id="f06dd-114">Эти данные необходимы для работы службы и могут включать данные, связанные с конечным пользователем, организацией, устройством и приложениями.</span><span class="sxs-lookup"><span data-stu-id="f06dd-114">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> <span data-ttu-id="f06dd-115">Вот список типов собираемой информации:</span><span class="sxs-lookup"><span data-stu-id="f06dd-115">Here's a list of the types of data being collected:</span></span>

### <a name="app-information"></a><span data-ttu-id="f06dd-116">Сведения о приложении</span><span class="sxs-lookup"><span data-stu-id="f06dd-116">App information</span></span>

<span data-ttu-id="f06dd-117">Сведения о пакетах приложений для Android (APKs) на устройстве, включая</span><span class="sxs-lookup"><span data-stu-id="f06dd-117">Information about Android application packages (APKs) on the device including</span></span>

-  <span data-ttu-id="f06dd-118">Источник установки</span><span class="sxs-lookup"><span data-stu-id="f06dd-118">Install source</span></span>
-  <span data-ttu-id="f06dd-119">Расположение хранилища (путь файла) apK</span><span class="sxs-lookup"><span data-stu-id="f06dd-119">Storage location (file path) of the APK</span></span>
-  <span data-ttu-id="f06dd-120">Время установки, размер AK и разрешения</span><span class="sxs-lookup"><span data-stu-id="f06dd-120">Time of install, size of APK and permissions</span></span>

### <a name="web-page--network-information"></a><span data-ttu-id="f06dd-121">Веб-страница / Сведения о сети</span><span class="sxs-lookup"><span data-stu-id="f06dd-121">Web page / Network information</span></span>

- <span data-ttu-id="f06dd-122">Полный URL-адрес (в поддерживаемых браузерах) при нажатии</span><span class="sxs-lookup"><span data-stu-id="f06dd-122">Full URL (on supported browsers), when clicked</span></span>
- <span data-ttu-id="f06dd-123">Сведения о подключении</span><span class="sxs-lookup"><span data-stu-id="f06dd-123">Connection information</span></span>
- <span data-ttu-id="f06dd-124">Тип протокола (например, HTTP, HTTPS и т.д.)</span><span class="sxs-lookup"><span data-stu-id="f06dd-124">Protocol type (such as HTTP, HTTPS, etc.)</span></span>


### <a name="device-and-account-information"></a><span data-ttu-id="f06dd-125">Сведения об устройстве и учетной записи</span><span class="sxs-lookup"><span data-stu-id="f06dd-125">Device and account information</span></span>

- <span data-ttu-id="f06dd-126">Сведения об устройстве, такие как & времени, версия Android, OEM-модель, сведения о ЦП и идентификатор устройства</span><span class="sxs-lookup"><span data-stu-id="f06dd-126">Device information such as date & time, Android version, OEM model, CPU       info, and Device identifier</span></span>
- <span data-ttu-id="f06dd-127">Идентификатор устройства — один из ниже:</span><span class="sxs-lookup"><span data-stu-id="f06dd-127">Device identifier is one of the below:</span></span>
    - <span data-ttu-id="f06dd-128">Wi-Fi MAC-адрес адаптер</span><span class="sxs-lookup"><span data-stu-id="f06dd-128">Wi-Fi adapter MAC address</span></span>
    - <span data-ttu-id="f06dd-129">[Android ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (созданный Android во время первой загрузки устройства)</span><span class="sxs-lookup"><span data-stu-id="f06dd-129">[Android       ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (as generated by Android at the time of first boot of the device)</span></span>
    - <span data-ttu-id="f06dd-130">Случайно созданный глобальный уникальный идентификатор (GUID)</span><span class="sxs-lookup"><span data-stu-id="f06dd-130">Randomly generated globally unique identifier (GUID)</span></span>

- <span data-ttu-id="f06dd-131">Сведения о клиентах, устройствах и пользователях</span><span class="sxs-lookup"><span data-stu-id="f06dd-131">Tenant, Device and User information</span></span>
    -   <span data-ttu-id="f06dd-132">Идентификатор устройства Azure Active Directory (AD) и идентификатор пользователя Azure: уникально идентифицирует устройство, пользователь соответственно в каталоге Azure Active.</span><span class="sxs-lookup"><span data-stu-id="f06dd-132">Azure Active Directory (AD) Device ID and Azure User ID: Uniquely     identifies the device, User respectively at Azure Active directory.</span></span>

    -   <span data-ttu-id="f06dd-133">Идентификатор клиента Azure — GUID, идентифицирует организацию в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f06dd-133">Azure tenant ID - GUID that identifies your organization within     Azure Active Directory</span></span>

    -   <span data-ttu-id="f06dd-134">Идентификатор оргии Microsoft Defender ATP — уникальный идентификатор, связанный с предприятием, к котором принадлежит устройство.</span><span class="sxs-lookup"><span data-stu-id="f06dd-134">Microsoft Defender ATP org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="f06dd-135">Позволяет Корпорации Майкрософт определить, влияют ли проблемы на выбранный набор предприятий и какое количество предприятий</span><span class="sxs-lookup"><span data-stu-id="f06dd-135">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted</span></span> 

    -   <span data-ttu-id="f06dd-136">Имя пользователя — ID электронной почты пользователя</span><span class="sxs-lookup"><span data-stu-id="f06dd-136">User Principal Name – Email ID of the user</span></span>

### <a name="product-and-service-usage-data"></a><span data-ttu-id="f06dd-137">Данные об использовании продуктов и служб</span><span class="sxs-lookup"><span data-stu-id="f06dd-137">Product and service usage data</span></span>
-   <span data-ttu-id="f06dd-138">Сведения о пакете приложений, включая имя, версию и состояние обновления приложения</span><span class="sxs-lookup"><span data-stu-id="f06dd-138">App package info, including name, version, and app upgrade status</span></span>

-   <span data-ttu-id="f06dd-139">Действия, выполняемые в приложении</span><span class="sxs-lookup"><span data-stu-id="f06dd-139">Actions performed in the app</span></span>

-   <span data-ttu-id="f06dd-140">Сведения об обнаружении угроз, такие как имя угрозы, категория и т. д.</span><span class="sxs-lookup"><span data-stu-id="f06dd-140">Threat detection information, such as threat name, category, etc.</span></span>

-   <span data-ttu-id="f06dd-141">Журналы отчетов о сбоях, созданные Android</span><span class="sxs-lookup"><span data-stu-id="f06dd-141">Crash report logs generated by Android</span></span>

## <a name="optional-data"></a><span data-ttu-id="f06dd-142">Необязательные данные</span><span class="sxs-lookup"><span data-stu-id="f06dd-142">Optional Data</span></span>

<span data-ttu-id="f06dd-143">Необязательные данные включают диагностические данные и данные обратной связи.</span><span class="sxs-lookup"><span data-stu-id="f06dd-143">Optional data includes diagnostic data and feedback data.</span></span> <span data-ttu-id="f06dd-144">Необязательные диагностические данные — это дополнительные данные, помогающие улучшать продукты, а также предоставляющие расширенные сведения для обнаружения, диагностики и устранения проблем.</span><span class="sxs-lookup"><span data-stu-id="f06dd-144">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="f06dd-145">Необязательные диагностические данные:</span><span class="sxs-lookup"><span data-stu-id="f06dd-145">Optional diagnostic data includes:</span></span>

-   <span data-ttu-id="f06dd-146">Использование приложений, ЦП и сети</span><span class="sxs-lookup"><span data-stu-id="f06dd-146">App, CPU, and network usage</span></span>

-   <span data-ttu-id="f06dd-147">Состояние устройства с точки зрения приложения, включая состояние сканирования, сроки сканирования, предоставленные разрешения приложения и состояние обновления</span><span class="sxs-lookup"><span data-stu-id="f06dd-147">State of the device from the app perspective, including scan status, scan timings, app permissions granted, and upgrade status</span></span>

-   <span data-ttu-id="f06dd-148">Функции, настроенные администратором</span><span class="sxs-lookup"><span data-stu-id="f06dd-148">Features configured by the admin</span></span>

-   <span data-ttu-id="f06dd-149">Основные сведения о браузерах на устройстве</span><span class="sxs-lookup"><span data-stu-id="f06dd-149">Basic information about the browsers on the device</span></span>

<span data-ttu-id="f06dd-150">**Данные обратной** связи собираются с помощью обратной связи в приложении, предоставляемой пользователем</span><span class="sxs-lookup"><span data-stu-id="f06dd-150">**Feedback Data** is collected through in-app feedback provided by the user</span></span>

-   <span data-ttu-id="f06dd-151">Адрес электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="f06dd-151">The user’s email address, if they choose to provide it</span></span>

-   <span data-ttu-id="f06dd-152">Тип отзывов (улыбка, хмурый, идея) и любые комментарии, представленные пользователем</span><span class="sxs-lookup"><span data-stu-id="f06dd-152">Feedback type (smile, frown, idea) and any feedback comments submitted by the user</span></span>
