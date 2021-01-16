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
description: Используйте встроенные средства Basic Mobility and Security для удаления информации с зарегистрированных устройств.
ms.openlocfilehash: 3bb9bfe55653b021ce5a86dd5d3dbc3de45ed19a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876832"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="c3364-103">Wipe a mobile device in Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="c3364-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="c3364-104">Вы можете использовать встроенную функцию Базовой мобильности и безопасности для Microsoft 365, чтобы удалить только данные организации или выполнить сброс заводских настроек, чтобы удалить всю информацию с мобильного устройства и восстановить ее до заводских настроек.</span><span class="sxs-lookup"><span data-stu-id="c3364-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c3364-105">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="c3364-105">Before you begin</span></span>

<span data-ttu-id="c3364-106">Мобильные устройства могут хранить конфиденциальную организационную информацию и предоставлять доступ к ресурсам Microsoft 365 вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c3364-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="c3364-107">Чтобы защитить сведения организации, можно сбросить заводские настройки или удалить данные компании:</span><span class="sxs-lookup"><span data-stu-id="c3364-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>

- <span data-ttu-id="c3364-108">**Сброс фабрики:** удаляет все данные на мобильном устройстве пользователя, включая установленные приложения, фотографии и персональные данные.</span><span class="sxs-lookup"><span data-stu-id="c3364-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="c3364-109">После завершения стирки устройство восстанавливается до заводских настроек.</span><span class="sxs-lookup"><span data-stu-id="c3364-109">When the wipe is complete, the device is restored to its factory settings.</span></span>

- <span data-ttu-id="c3364-110">**Удаление данных компании:** удаляет только данные организации и оставляет установленные приложения, фотографии и персональные данные на мобильном устройстве пользователя.</span><span class="sxs-lookup"><span data-stu-id="c3364-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>

- <span data-ttu-id="c3364-111">**При стирании устройства (сброс** заводских насилий или удаление данных компании) устройство удаляется из списка управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="c3364-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="c3364-112">**Автоматический** сброс устройства: вы можете настроить политику Basic Mobility and Security, которая автоматически сбрасывает устройство после того, как пользователь безуспешно попытается ввести пароль устройства определенное количество раз.</span><span class="sxs-lookup"><span data-stu-id="c3364-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="c3364-113">Для этого выполните действия, которые необходимо предпринять в области создания политик безопасности устройств [в базовой мобильности и безопасности.](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c3364-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="c3364-114">**Если вы хотите узнать о пользовательском** интерфейсе при стирии его устройства, посмотрите, как это влияет на   [пользователя и устройство?](#whats-the-user-and-device-impact)</span><span class="sxs-lookup"><span data-stu-id="c3364-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="c3364-115">Стирать мобильное устройство</span><span class="sxs-lookup"><span data-stu-id="c3364-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="c3364-116">Перейдите в [Центр администрирования Microsoft 365.](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)</span><span class="sxs-lookup"><span data-stu-id="c3364-116">Go to the [Microsoft 365 admin center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span></span>

2. <span data-ttu-id="c3364-117">Введите "Управление мобильными устройствами" в поле поиска и выберите "Управление мобильными **устройствами"** в списке результатов.</span><span class="sxs-lookup"><span data-stu-id="c3364-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Вариант управления мобильными устройствами Basic Mobility и Secruity":::

3. <span data-ttu-id="c3364-119">Выберите **"Управление устройствами".**</span><span class="sxs-lookup"><span data-stu-id="c3364-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="c3364-120">Выберите устройство, которое нужно очистить.</span><span class="sxs-lookup"><span data-stu-id="c3364-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="c3364-121">Выберите **"Управление".**</span><span class="sxs-lookup"><span data-stu-id="c3364-121">Select **Manage**.</span></span>

6. <span data-ttu-id="c3364-122">Выберите тип удаленной очистки.</span><span class="sxs-lookup"><span data-stu-id="c3364-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="c3364-123">Чтобы полностью сбросить устройство и восстановить заводские параметры, выберите **"Сброс заводских настроек".**</span><span class="sxs-lookup"><span data-stu-id="c3364-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="c3364-124">Чтобы выборочно стереть и удалить только сведения об организации Microsoft 365, выберите **"Удалить данные компании".**</span><span class="sxs-lookup"><span data-stu-id="c3364-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="c3364-125">Чтобы удалить устройство из организации, выберите **"Удалить устройство".**</span><span class="sxs-lookup"><span data-stu-id="c3364-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="c3364-126">Нажмите кнопку **Да** для подтверждения.</span><span class="sxs-lookup"><span data-stu-id="c3364-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="c3364-127">Как узнать, что это сработало?</span><span class="sxs-lookup"><span data-stu-id="c3364-127">How do I know it worked?</span></span>

<span data-ttu-id="c3364-128">Мобильное устройство больше не находится в списке управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="c3364-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="c3364-129">Зачем вам стирать устройство?</span><span class="sxs-lookup"><span data-stu-id="c3364-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="c3364-130">Стирать устройство по указанным причинам:</span><span class="sxs-lookup"><span data-stu-id="c3364-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="c3364-131">Мобильные устройства, такие как смартфоны и планшеты, постоянно становятся все более полно функций.</span><span class="sxs-lookup"><span data-stu-id="c3364-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="c3364-132">Это означает, что пользователям будет проще хранить конфиденциальную корпоративную информацию, например личную идентификацию или конфиденциальные сообщения, и получать к ним доступ в путь.</span><span class="sxs-lookup"><span data-stu-id="c3364-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="c3364-133">Если одно из этих мобильных устройств потеряно или украдено, стирка устройства может помочь предотвратить использование информации организации в неправильных руках.</span><span class="sxs-lookup"><span data-stu-id="c3364-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="c3364-134">Когда пользователь покидает организацию с личным устройством, зарегистрированным в Basic Mobility and Security, вы можете предотвратить разгрузку организационной информации с этим пользователем, выполив заводской сброс.</span><span class="sxs-lookup"><span data-stu-id="c3364-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="c3364-135">Если ваша организация предоставляет мобильные устройства пользователям, может потребоваться время от времени перенамерять устройства.</span><span class="sxs-lookup"><span data-stu-id="c3364-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="c3364-136">Сброс заводских насилий на устройстве перед назначением его новому пользователю помогает гарантировать удаление конфиденциальной информации от предыдущего владельца.</span><span class="sxs-lookup"><span data-stu-id="c3364-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="c3364-137">Какое влияние оказывает пользователь и устройство?</span><span class="sxs-lookup"><span data-stu-id="c3364-137">What's the user and device impact?</span></span>

<span data-ttu-id="c3364-138">Стирка немедленно отправляется на мобильное устройство, а устройство помечается как не совместимое в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c3364-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="c3364-139">Хотя все данные удаляются при сбросе заводских насайтов на устройстве, в следующей таблице описывается, какой контент удаляется для каждого типа устройства при удалении данных компании.</span><span class="sxs-lookup"><span data-stu-id="c3364-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="c3364-140">**Угрозы содержимого**</span><span class="sxs-lookup"><span data-stu-id="c3364-140">**Content impace**</span></span>|<span data-ttu-id="c3364-141">**iOS 10 и более поздние**</span><span class="sxs-lookup"><span data-stu-id="c3364-141">**iOS 10 and later**</span></span>|<span data-ttu-id="c3364-142">**Android 5 и более поздние версии**</span><span class="sxs-lookup"><span data-stu-id="c3364-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c3364-143">Данные приложения Microsoft 365 будут стираться, если устройство защищено политиками Защиты приложений Intune.</span><span class="sxs-lookup"><span data-stu-id="c3364-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="c3364-144">Приложения не удаляются.</span><span class="sxs-lookup"><span data-stu-id="c3364-144">The apps aren't removed.</span></span> <span data-ttu-id="c3364-145">Для устройств, не защищенных политиками управления мобильными приложениями (MAM), Outlook и OneDrive не будут удалять кэшные данные.</span><span class="sxs-lookup"><span data-stu-id="c3364-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="c3364-146">**Примечание** Для применения политик защиты приложений Intune необходимо иметь лицензию Intune.</span><span class="sxs-lookup"><span data-stu-id="c3364-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="c3364-147">Да</span><span class="sxs-lookup"><span data-stu-id="c3364-147">Yes</span></span>|<span data-ttu-id="c3364-148">Да</span><span class="sxs-lookup"><span data-stu-id="c3364-148">Yes</span></span>|
|<span data-ttu-id="c3364-149">Параметры политики, применяемые базовой мобильностью и безопасностью к устройствам, больше не применяются; пользователи могут изменять параметры.</span><span class="sxs-lookup"><span data-stu-id="c3364-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="c3364-150">Да</span><span class="sxs-lookup"><span data-stu-id="c3364-150">Yes</span></span>|<span data-ttu-id="c3364-151">Да</span><span class="sxs-lookup"><span data-stu-id="c3364-151">Yes</span></span>|
|<span data-ttu-id="c3364-152">Профили электронной почты, созданные с помощью Basic Mobility and Security, удаляются, а кэшная электронная почта на устройстве удаляется.</span><span class="sxs-lookup"><span data-stu-id="c3364-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="c3364-153">Да</span><span class="sxs-lookup"><span data-stu-id="c3364-153">Yes</span></span>|<span data-ttu-id="c3364-154">Недоступно</span><span class="sxs-lookup"><span data-stu-id="c3364-154">N/A</span></span>|
>[!NOTE]
><span data-ttu-id="c3364-155">Приложение "Портал компании" доступно в Магазине приложений для iOS и Магазине воспроизведения для устройств с Android.</span><span class="sxs-lookup"><span data-stu-id="c3364-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c3364-156">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="c3364-156">Related topics</span></span>

[<span data-ttu-id="c3364-157">Настройка Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="c3364-157">Set up Basic Mobility and Security</span></span>](set-up.md)