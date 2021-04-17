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
ms.openlocfilehash: 79f8882e21f23e75d85813cde03260ef17adf246
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876113"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a><span data-ttu-id="a5235-104">Microsoft Defender для конечной точки на Android — сведения о конфиденциальности</span><span class="sxs-lookup"><span data-stu-id="a5235-104">Microsoft Defender for Endpoint on Android - Privacy information</span></span>

<span data-ttu-id="a5235-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="a5235-105">**Applies to:**</span></span>
- [<span data-ttu-id="a5235-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a5235-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a5235-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5235-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a5235-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="a5235-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a5235-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="a5235-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="a5235-110">Defender for Endpoint для Android собирает сведения с настроенных android-устройств и хранит их в том же клиенте, где у вас есть Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="a5235-110">Defender for Endpoint for Android collects information from your configured Android devices and stores it in the same tenant where you have Defender for Endpoint.</span></span> <span data-ttu-id="a5235-111">Сведения собираются, чтобы защитить Defender для конечной точки для iOS в соответствии с ожидаемым сроком выполнения, а также поддерживать службу.</span><span class="sxs-lookup"><span data-stu-id="a5235-111">The information is collected to help keep Defender for Endpoint for iOS secure, up-to-date, performing as expected, and to support the service.</span></span>

<span data-ttu-id="a5235-112">Дополнительные сведения о хранении данных см. в [веб-сайте Microsoft Defender для хранения и конфиденциальности данных конечной точки.](data-storage-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="a5235-112">For more information about data storage, see [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).</span></span>

<span data-ttu-id="a5235-113">Сведения собираются, чтобы защитить Defender для конечной точки для Android в соответствии с ожидаемым сроком выполнения и поддерживать службу.</span><span class="sxs-lookup"><span data-stu-id="a5235-113">Information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected and to support the service.</span></span>

## <a name="required-data"></a><span data-ttu-id="a5235-114">Необходимые данные</span><span class="sxs-lookup"><span data-stu-id="a5235-114">Required Data</span></span> 

<span data-ttu-id="a5235-115">Необходимые данные состоят из данных, необходимых для обеспечения работы Defender для Конечной точки для Android, как и ожидалось.</span><span class="sxs-lookup"><span data-stu-id="a5235-115">Required data consists of data that is necessary to make Defender for Endpoint for Android work as expected.</span></span> <span data-ttu-id="a5235-116">Эти данные необходимы для работы службы и могут включать данные, связанные с конечным пользователем, организацией, устройством и приложениями.</span><span class="sxs-lookup"><span data-stu-id="a5235-116">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> <span data-ttu-id="a5235-117">Вот список типов собираемой информации:</span><span class="sxs-lookup"><span data-stu-id="a5235-117">Here's a list of the types of data being collected:</span></span>

### <a name="app-information"></a><span data-ttu-id="a5235-118">Сведения о приложении</span><span class="sxs-lookup"><span data-stu-id="a5235-118">App information</span></span>

<span data-ttu-id="a5235-119">Сведения о **вредоносных** пакетах приложений для Android (APKs) на устройстве, включая</span><span class="sxs-lookup"><span data-stu-id="a5235-119">Information about **malicious** Android application packages (APKs) on the device including</span></span>

-  <span data-ttu-id="a5235-120">Источник установки</span><span class="sxs-lookup"><span data-stu-id="a5235-120">Install source</span></span>
-  <span data-ttu-id="a5235-121">Расположение хранилища (путь файла) apK</span><span class="sxs-lookup"><span data-stu-id="a5235-121">Storage location (file path) of the APK</span></span>
-  <span data-ttu-id="a5235-122">Время установки, размер AK и разрешения</span><span class="sxs-lookup"><span data-stu-id="a5235-122">Time of install, size of APK and permissions</span></span>

### <a name="web-page--network-information"></a><span data-ttu-id="a5235-123">Веб-страница / Сведения о сети</span><span class="sxs-lookup"><span data-stu-id="a5235-123">Web page / Network information</span></span>

- <span data-ttu-id="a5235-124">Полный URL-адрес веб-сайта только при обнаружении вредоносного подключения или веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="a5235-124">Full URL of the website only when a malicious connection or web page is detected.</span></span>
- <span data-ttu-id="a5235-125">Сведения о подключении</span><span class="sxs-lookup"><span data-stu-id="a5235-125">Connection information</span></span>
- <span data-ttu-id="a5235-126">Тип протокола (например, HTTP, HTTPS и т.д.)</span><span class="sxs-lookup"><span data-stu-id="a5235-126">Protocol type (such as HTTP, HTTPS, etc.)</span></span>


### <a name="device-and-account-information"></a><span data-ttu-id="a5235-127">Сведения об устройстве и учетной записи</span><span class="sxs-lookup"><span data-stu-id="a5235-127">Device and account information</span></span>

- <span data-ttu-id="a5235-128">Сведения об устройстве, такие как & времени, версия Android, OEM-модель, сведения о ЦП и идентификатор устройства</span><span class="sxs-lookup"><span data-stu-id="a5235-128">Device information such as date & time, Android version, OEM model, CPU       info, and Device identifier</span></span>
- <span data-ttu-id="a5235-129">Идентификатор устройства — один из ниже:</span><span class="sxs-lookup"><span data-stu-id="a5235-129">Device identifier is one of the below:</span></span>
    - <span data-ttu-id="a5235-130">Wi-Fi MAC-адрес адаптер</span><span class="sxs-lookup"><span data-stu-id="a5235-130">Wi-Fi adapter MAC address</span></span>
    - <span data-ttu-id="a5235-131">[Android ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (созданный Android во время первой загрузки устройства)</span><span class="sxs-lookup"><span data-stu-id="a5235-131">[Android       ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (as generated by Android at the time of first boot of the device)</span></span>
    - <span data-ttu-id="a5235-132">Случайно созданный глобальный уникальный идентификатор (GUID)</span><span class="sxs-lookup"><span data-stu-id="a5235-132">Randomly generated globally unique identifier (GUID)</span></span>

- <span data-ttu-id="a5235-133">Сведения о клиентах, устройствах и пользователях</span><span class="sxs-lookup"><span data-stu-id="a5235-133">Tenant, Device and User information</span></span>
    -   <span data-ttu-id="a5235-134">Идентификатор устройства Azure Active Directory (AD) и идентификатор пользователя Azure: уникально идентифицирует устройство, пользователь соответственно в каталоге Azure Active.</span><span class="sxs-lookup"><span data-stu-id="a5235-134">Azure Active Directory (AD) Device ID and Azure User ID: Uniquely     identifies the device, User respectively at Azure Active directory.</span></span>

    -   <span data-ttu-id="a5235-135">Идентификатор клиента Azure — GUID, идентифицирует организацию в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a5235-135">Azure tenant ID - GUID that identifies your organization within     Azure Active Directory</span></span>

    -   <span data-ttu-id="a5235-136">Идентификатор оргии Microsoft Defender ATP — уникальный идентификатор, связанный с предприятием, к котором принадлежит устройство.</span><span class="sxs-lookup"><span data-stu-id="a5235-136">Microsoft Defender ATP org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="a5235-137">Позволяет Корпорации Майкрософт определить, влияют ли проблемы на выбранный набор предприятий и какое количество предприятий</span><span class="sxs-lookup"><span data-stu-id="a5235-137">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted</span></span> 

    -   <span data-ttu-id="a5235-138">Имя пользователя — ID электронной почты пользователя</span><span class="sxs-lookup"><span data-stu-id="a5235-138">User Principal Name – Email ID of the user</span></span>

### <a name="product-and-service-usage-data"></a><span data-ttu-id="a5235-139">Данные об использовании продуктов и служб</span><span class="sxs-lookup"><span data-stu-id="a5235-139">Product and service usage data</span></span>

<span data-ttu-id="a5235-140">Следующие сведения собираются только для приложения Microsoft Defender for Endpoint, установленного на устройстве.</span><span class="sxs-lookup"><span data-stu-id="a5235-140">The following information is collected only for Microsoft Defender for Endpoint app installed on the device.</span></span> 

-   <span data-ttu-id="a5235-141">Сведения о пакете приложений, включая имя, версию и состояние обновления приложения</span><span class="sxs-lookup"><span data-stu-id="a5235-141">App package info, including name, version, and app upgrade status</span></span>

-   <span data-ttu-id="a5235-142">Действия, выполняемые в приложении</span><span class="sxs-lookup"><span data-stu-id="a5235-142">Actions performed in the app</span></span>

-   <span data-ttu-id="a5235-143">Сведения об обнаружении угроз, такие как имя угрозы, категория и т. д.</span><span class="sxs-lookup"><span data-stu-id="a5235-143">Threat detection information, such as threat name, category, etc.</span></span>

-   <span data-ttu-id="a5235-144">Журналы отчетов о сбоях, созданные Android</span><span class="sxs-lookup"><span data-stu-id="a5235-144">Crash report logs generated by Android</span></span>

## <a name="optional-data"></a><span data-ttu-id="a5235-145">Необязательные данные</span><span class="sxs-lookup"><span data-stu-id="a5235-145">Optional Data</span></span>

<span data-ttu-id="a5235-146">Необязательные данные включают диагностические данные и данные обратной связи.</span><span class="sxs-lookup"><span data-stu-id="a5235-146">Optional data includes diagnostic data and feedback data.</span></span> <span data-ttu-id="a5235-147">Необязательные диагностические данные — это дополнительные данные, помогающие улучшать продукты, а также предоставляющие расширенные сведения для обнаружения, диагностики и устранения проблем.</span><span class="sxs-lookup"><span data-stu-id="a5235-147">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="a5235-148">Необязательные диагностические данные:</span><span class="sxs-lookup"><span data-stu-id="a5235-148">Optional diagnostic data includes:</span></span>

-   <span data-ttu-id="a5235-149">Использование приложений, ЦП и сети</span><span class="sxs-lookup"><span data-stu-id="a5235-149">App, CPU, and network usage</span></span>

-   <span data-ttu-id="a5235-150">Состояние устройства с точки зрения приложения, включая состояние сканирования, сроки сканирования, предоставленные разрешения приложения и состояние обновления</span><span class="sxs-lookup"><span data-stu-id="a5235-150">State of the device from the app perspective, including scan status, scan timings, app permissions granted, and upgrade status</span></span>

-   <span data-ttu-id="a5235-151">Функции, настроенные администратором</span><span class="sxs-lookup"><span data-stu-id="a5235-151">Features configured by the admin</span></span>

-   <span data-ttu-id="a5235-152">Основные сведения о браузерах на устройстве</span><span class="sxs-lookup"><span data-stu-id="a5235-152">Basic information about the browsers on the device</span></span>

<span data-ttu-id="a5235-153">**Данные обратной** связи собираются с помощью обратной связи в приложении, предоставляемой пользователем</span><span class="sxs-lookup"><span data-stu-id="a5235-153">**Feedback Data** is collected through in-app feedback provided by the user</span></span>

-   <span data-ttu-id="a5235-154">Адрес электронной почты пользователя.</span><span class="sxs-lookup"><span data-stu-id="a5235-154">The user’s email address, if they choose to provide it</span></span>

-   <span data-ttu-id="a5235-155">Тип отзывов (улыбка, хмурый, идея) и любые комментарии, представленные пользователем</span><span class="sxs-lookup"><span data-stu-id="a5235-155">Feedback type (smile, frown, idea) and any feedback comments submitted by the user</span></span>
