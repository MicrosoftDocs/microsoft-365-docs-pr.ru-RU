---
title: Wipe a mobile device in Basic Mobility and Security
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
search.appverid:
- MET150
description: Используйте встроенную базовую мобильность и безопасность для удаления сведений с зарегистрированных устройств.
ms.openlocfilehash: 8c873923505fe527f5a44df0e8b15d290e92023b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706146"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="cd8ff-103">Wipe a mobile device in Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="cd8ff-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="cd8ff-104">Вы можете использовать встроенную базовую мобильность и безопасность для Microsoft 365 для удаления только организационных сведений или для выполнения заводского сброса, чтобы удалить всю информацию с мобильного устройства и восстановить ее до заводских параметров.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="cd8ff-105">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="cd8ff-105">Before you begin</span></span>

<span data-ttu-id="cd8ff-106">Мобильные устройства могут хранить конфиденциальные организационные сведения и предоставлять доступ к ресурсам Microsoft 365 организации.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="cd8ff-107">Чтобы защитить сведения организации, можно сбросить или удалить данные компании:</span><span class="sxs-lookup"><span data-stu-id="cd8ff-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>

- <span data-ttu-id="cd8ff-108">**Сброс фабрики.** Удаляет все данные на мобильном устройстве пользователя, включая установленные приложения, фотографии и персональные данные.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="cd8ff-109">После завершения стирки устройство восстанавливается до заводских параметров.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-109">When the wipe is complete, the device is restored to its factory settings.</span></span>

- <span data-ttu-id="cd8ff-110">**Удаление данных компании.** Удаляет только данные организации и оставляет установленные приложения, фотографии и персональные данные на мобильном устройстве пользователя.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>

- <span data-ttu-id="cd8ff-111">**При стирании устройства (сброс или** удаление данных компании) устройство удаляется из списка управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="cd8ff-112">**Автоматически сбросить** устройство. Можно настроить политику базовой мобильности и безопасности, которая автоматически сбрасывает устройство после неудачной попытки пользователя ввести пароль устройства определенное количество раз.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="cd8ff-113">Для этого выполните действия в области Создания политик безопасности устройств [в области базовой](create-device-security-policies.md)мобильности и безопасности.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="cd8ff-114">**Если вы хотите знать пользовательский интерфейс** при стирки устройства, см. в этой записи, какие последствия для пользователя   [и устройства?](#whats-the-user-and-device-impact).</span><span class="sxs-lookup"><span data-stu-id="cd8ff-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="cd8ff-115">Протрите мобильное устройство</span><span class="sxs-lookup"><span data-stu-id="cd8ff-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="cd8ff-116">Перейдите в [центр Microsoft 365 администрирования.](../../admin/admin-overview/about-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="cd8ff-116">Go to the [Microsoft 365 admin center](../../admin/admin-overview/about-the-admin-center.md).</span></span>

2. <span data-ttu-id="cd8ff-117">Введите управление мобильными устройствами в поле поиска и выберите **управление** мобильными устройствами из списка результатов.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Вариант управления мобильными устройствами Basic Mobility и Secruity":::

3. <span data-ttu-id="cd8ff-119">Выберите **Управление устройствами.**</span><span class="sxs-lookup"><span data-stu-id="cd8ff-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="cd8ff-120">Выберите устройство, которое нужно очистить.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="cd8ff-121">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-121">Select **Manage**.</span></span>

6. <span data-ttu-id="cd8ff-122">Выберите тип удаленной очистки.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="cd8ff-123">Чтобы полностью стереть и восстановить устройство до параметров фабрики, выберите **Сброс фабрики.**</span><span class="sxs-lookup"><span data-stu-id="cd8ff-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="cd8ff-124">Чтобы сделать выборочное удаление и удалить только Microsoft 365 организации, выберите **Удалить данные компании.**</span><span class="sxs-lookup"><span data-stu-id="cd8ff-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="cd8ff-125">Чтобы удалить устройство из организации, выберите **Удалить устройство.**</span><span class="sxs-lookup"><span data-stu-id="cd8ff-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="cd8ff-126">Нажмите кнопку **Да** для подтверждения.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="cd8ff-127">Как узнать, что это сработало?</span><span class="sxs-lookup"><span data-stu-id="cd8ff-127">How do I know it worked?</span></span>

<span data-ttu-id="cd8ff-128">Мобильное устройство больше не будет видеться в списке управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="cd8ff-129">Зачем нужно стирать устройство?</span><span class="sxs-lookup"><span data-stu-id="cd8ff-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="cd8ff-130">Wipe a device for these reasons:</span><span class="sxs-lookup"><span data-stu-id="cd8ff-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="cd8ff-131">Мобильные устройства, такие как смартфоны и планшеты, становятся все более полно функций.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="cd8ff-132">Это означает, что пользователям проще хранить конфиденциальные корпоративные сведения, такие как личная идентификация или конфиденциальные сообщения, и получать к ним доступ в режиме движения.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="cd8ff-133">Если одно из этих мобильных устройств потеряно или украдено, стирка устройства может помочь предотвратить в конечном итоге сведения организации в неправильных руках.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="cd8ff-134">Когда пользователь покидает организацию с личным устройством, которое зачисляется в Basic Mobility and Security, вы можете предотвратить организационную информацию, которая будет поступать с этим пользователем, выполняя заводской сброс.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="cd8ff-135">Если ваша организация предоставляет мобильные устройства пользователям, может потребоваться время от времени перенанащать устройства.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="cd8ff-136">При сбросе фабрики на устройстве перед назначением его новому пользователю гарантируется удаление конфиденциальной информации от предыдущего владельца.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="cd8ff-137">Какое влияние оказывает пользователь и устройство?</span><span class="sxs-lookup"><span data-stu-id="cd8ff-137">What's the user and device impact?</span></span>

<span data-ttu-id="cd8ff-138">Стирка немедленно отправляется на мобильное устройство, и устройство помечено как не соответствующим требованиям в активном каталоге Azure.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="cd8ff-139">Несмотря на то, что все данные удаляются при сбросе устройства в заводские по умолчанию, в следующей таблице описывается, какой контент удаляется для каждого типа устройства при удалении данных компании.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="cd8ff-140">**Влияние контента**</span><span class="sxs-lookup"><span data-stu-id="cd8ff-140">**Content impact**</span></span>|<span data-ttu-id="cd8ff-141">**iOS 10 и более поздний**</span><span class="sxs-lookup"><span data-stu-id="cd8ff-141">**iOS 10 and later**</span></span>|<span data-ttu-id="cd8ff-142">**Android 5 и более поздний**</span><span class="sxs-lookup"><span data-stu-id="cd8ff-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cd8ff-143">Microsoft 365 данные приложения стирают, если устройство защищено политиками защиты приложений Intune.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="cd8ff-144">Приложения не удаляются.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-144">The apps aren't removed.</span></span> <span data-ttu-id="cd8ff-145">Для устройств, не защищенных политиками управления мобильными приложениями( MAM), Outlook и OneDrive не будут удалять кэшные данные.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="cd8ff-146">**Примечание** Для применения политик защиты приложений Intune необходимо иметь лицензию Intune.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="cd8ff-147">Да</span><span class="sxs-lookup"><span data-stu-id="cd8ff-147">Yes</span></span>|<span data-ttu-id="cd8ff-148">Да</span><span class="sxs-lookup"><span data-stu-id="cd8ff-148">Yes</span></span>|
|<span data-ttu-id="cd8ff-149">Параметры политики, применяемые Службой базовой мобильности и безопасности для устройств, больше не применяются; пользователи могут изменять параметры.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="cd8ff-150">Да</span><span class="sxs-lookup"><span data-stu-id="cd8ff-150">Yes</span></span>|<span data-ttu-id="cd8ff-151">Да</span><span class="sxs-lookup"><span data-stu-id="cd8ff-151">Yes</span></span>|
|<span data-ttu-id="cd8ff-152">Профили электронной почты, созданные Basic Mobility and Security, удаляются, а кэшная электронная почта на устройстве удаляется.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="cd8ff-153">Да</span><span class="sxs-lookup"><span data-stu-id="cd8ff-153">Yes</span></span>|<span data-ttu-id="cd8ff-154">Недоступно</span><span class="sxs-lookup"><span data-stu-id="cd8ff-154">N/A</span></span>|
>[!NOTE]
><span data-ttu-id="cd8ff-155">Корпоративный портал приложение доступно в App Store для iOS и в магазине Play для android-устройств.</span><span class="sxs-lookup"><span data-stu-id="cd8ff-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>
