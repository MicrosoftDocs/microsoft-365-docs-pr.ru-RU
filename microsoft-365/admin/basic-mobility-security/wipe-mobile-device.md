---
title: Очистка мобильного устройства в базовом мобильном и системном обеспечении безопасности
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
description: Использование встроенных базовых функций мобильной связи и безопасности для удаления данных с зарегистрированных устройств.
ms.openlocfilehash: 4627b0cb2d0963ae724c425a6a7ea6279f271856
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429954"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="5caa2-103">Очистка мобильного устройства в базовом мобильном и системном обеспечении безопасности</span><span class="sxs-lookup"><span data-stu-id="5caa2-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="5caa2-104">Вы можете использовать встроенные базовые возможности мобильной работы и обеспечения безопасности для Microsoft 365, чтобы удалить только сведения о организации или выполнить сброс, чтобы удалить все данные с мобильного устройства и восстановить заводские настройки.</span><span class="sxs-lookup"><span data-stu-id="5caa2-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5caa2-105">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="5caa2-105">Before you begin</span></span>

<span data-ttu-id="5caa2-106">Мобильные устройства могут хранить конфиденциальную организационную информацию и предоставлять доступ к ресурсам Microsoft 365 Организации.</span><span class="sxs-lookup"><span data-stu-id="5caa2-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="5caa2-107">Чтобы обеспечить защиту информации Организации, можно выполнить сброс или удалить данные компании:</span><span class="sxs-lookup"><span data-stu-id="5caa2-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>
    
- <span data-ttu-id="5caa2-108">**Reset Factory**: удаляет все данные на мобильном устройстве пользователя, в том числе установленные приложения, фотографии и персональные данные.</span><span class="sxs-lookup"><span data-stu-id="5caa2-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="5caa2-109">После завершения очистки устройство восстанавливается до заводских настроек.</span><span class="sxs-lookup"><span data-stu-id="5caa2-109">When the wipe is complete, the device is restored to its factory settings.</span></span>
    
- <span data-ttu-id="5caa2-110">**Удалить данные компании**: удаляет только данные организации и оставляет установленные приложения, фотографии и персональные данные на мобильном устройстве пользователя.</span><span class="sxs-lookup"><span data-stu-id="5caa2-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>   

- <span data-ttu-id="5caa2-111">**Когда устройство стерто (заводская очистка или удаление данных компании)**, устройство удаляется из списка управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="5caa2-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="5caa2-112">**Автоматически сбросить устройство**: вы можете настроить базовую политику для мобильных устройств и безопасности, которая автоматически переустанавливает устройство после неудачной попытки ввода пароля устройства в указанное число раз.</span><span class="sxs-lookup"><span data-stu-id="5caa2-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="5caa2-113">Для этого выполните действия, описанные в статье [Создание политик безопасности устройств в базовых службах мобильной связи и безопасности](create-device-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5caa2-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="5caa2-114">**Если вы хотите узнать, как попытаться работать с пользователем** при очистке устройства, посмотрите,  [что влияет на их воздействие на пользователя и устройство?](#whats-the-user-and-device-impact).</span><span class="sxs-lookup"><span data-stu-id="5caa2-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>   

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="5caa2-115">Очистка мобильного устройства</span><span class="sxs-lookup"><span data-stu-id="5caa2-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="5caa2-116">Перейдите в [центр администрирования Microsoft 365](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span><span class="sxs-lookup"><span data-stu-id="5caa2-116">Go to the [Microsoft 365 admin center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span></span>
    
2. <span data-ttu-id="5caa2-117">Введите "Управление мобильными устройствами" в поле поиска и выберите **Управление мобильными устройствами** из списка результатов.</span><span class="sxs-lookup"><span data-stu-id="5caa2-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span> 

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Базовый режим управления мобильными и мобильными устройствами Секруити":::

3. <span data-ttu-id="5caa2-119">Выберите **Управление устройствами**.</span><span class="sxs-lookup"><span data-stu-id="5caa2-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="5caa2-120">Выберите устройство, которое нужно очистить.</span><span class="sxs-lookup"><span data-stu-id="5caa2-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="5caa2-121">Выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="5caa2-121">Select **Manage**.</span></span>

6. <span data-ttu-id="5caa2-122">Выберите тип удаленной очистки.</span><span class="sxs-lookup"><span data-stu-id="5caa2-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="5caa2-123">Чтобы выполнить полное удаление и восстановить заводские настройки устройства, установите флажок **Reset Factory (заводская**).</span><span class="sxs-lookup"><span data-stu-id="5caa2-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="5caa2-124">Чтобы выполнить выборочную очистку и удалить только сведения об организации Microsoft 365, выберите **удалить данные компании**.</span><span class="sxs-lookup"><span data-stu-id="5caa2-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="5caa2-125">Чтобы удалить устройство из вашей организации, выберите пункт **удалить устройство**.</span><span class="sxs-lookup"><span data-stu-id="5caa2-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="5caa2-126">Нажмите кнопку **Да** для подтверждения.</span><span class="sxs-lookup"><span data-stu-id="5caa2-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="5caa2-127">Как убедиться в том, что он работал?</span><span class="sxs-lookup"><span data-stu-id="5caa2-127">How do I know it worked?</span></span>

<span data-ttu-id="5caa2-128">Вы больше не видите мобильное устройство в списке управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="5caa2-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="5caa2-129">Зачем нужно очистить устройство?</span><span class="sxs-lookup"><span data-stu-id="5caa2-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="5caa2-130">Очистка устройства по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="5caa2-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="5caa2-131">Мобильные устройства, такие как смартфоны и Планшетные ПК, становятся более полнофункциональными в течение всего времени.</span><span class="sxs-lookup"><span data-stu-id="5caa2-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="5caa2-132">Это означает, что пользователям проще хранить конфиденциальную корпоративную информацию, например персональную идентификацию или конфиденциальную связь, а также получать доступ к ней в дороге.</span><span class="sxs-lookup"><span data-stu-id="5caa2-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="5caa2-133">Если какое-либо из этих мобильных устройств потеряно или украдено, очистка устройства может помочь предотвратить появление данных вашей организации в неправильной руки.</span><span class="sxs-lookup"><span data-stu-id="5caa2-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="5caa2-134">Когда пользователь оставляет организацию с персональным устройством, зарегистрированным в базовом мобильном и защищенном виде, можно предотвратить перезагрузку с этого пользователя в Организации.</span><span class="sxs-lookup"><span data-stu-id="5caa2-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="5caa2-135">Если ваша организация предоставляет пользователям мобильные устройства, возможно, вам потребуется переназначить устройства на время.</span><span class="sxs-lookup"><span data-stu-id="5caa2-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="5caa2-136">Выполнение аппаратного сброса на устройстве перед назначением его новому пользователю позволяет убедиться, что все конфиденциальные данные из предыдущего владельца удалены.</span><span class="sxs-lookup"><span data-stu-id="5caa2-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="5caa2-137">Каковы последствия для пользователей и устройств?</span><span class="sxs-lookup"><span data-stu-id="5caa2-137">What's the user and device impact?</span></span>

<span data-ttu-id="5caa2-138">Очистка немедленно отправляется на мобильное устройство, и устройство помечается как несоответствие в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5caa2-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="5caa2-139">Несмотря на то, что все данные удаляются при восстановлении устройств по умолчанию, в следующей таблице описывается удаление содержимого для каждого типа устройства при удалении данных компании.</span><span class="sxs-lookup"><span data-stu-id="5caa2-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="5caa2-140">**Неинтенсивность содержимого**</span><span class="sxs-lookup"><span data-stu-id="5caa2-140">**Content impace**</span></span>|<span data-ttu-id="5caa2-141">**iOS 10 и более поздние версии**</span><span class="sxs-lookup"><span data-stu-id="5caa2-141">**iOS 10 and later**</span></span>|<span data-ttu-id="5caa2-142">**Android 5 и более поздних версий**</span><span class="sxs-lookup"><span data-stu-id="5caa2-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5caa2-143">Данные приложений Microsoft 365 не заменяются, если устройство защищено политиками защиты приложений Intune.</span><span class="sxs-lookup"><span data-stu-id="5caa2-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="5caa2-144">Приложения не удаляются.</span><span class="sxs-lookup"><span data-stu-id="5caa2-144">The apps aren't removed.</span></span> <span data-ttu-id="5caa2-145">Для устройств, не защищенных политиками управления мобильными приложениями (MAM), Outlook и OneDrive не удаляют кэшированные данные.</span><span class="sxs-lookup"><span data-stu-id="5caa2-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="5caa2-146">**Note (Примечание** ) Для применения политик защиты приложений Intune необходима лицензия Intune.</span><span class="sxs-lookup"><span data-stu-id="5caa2-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="5caa2-147">Да</span><span class="sxs-lookup"><span data-stu-id="5caa2-147">Yes</span></span>|<span data-ttu-id="5caa2-148">Да</span><span class="sxs-lookup"><span data-stu-id="5caa2-148">Yes</span></span>|
|<span data-ttu-id="5caa2-149">Параметры политики, применяемые базовыми мобильностью и безопасностью на устройствах, больше не применяются; Пользователи могут изменять параметры.</span><span class="sxs-lookup"><span data-stu-id="5caa2-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="5caa2-150">Да</span><span class="sxs-lookup"><span data-stu-id="5caa2-150">Yes</span></span>|<span data-ttu-id="5caa2-151">Да</span><span class="sxs-lookup"><span data-stu-id="5caa2-151">Yes</span></span>|
|<span data-ttu-id="5caa2-152">Профили электронной почты, созданные базовыми мобильностью и безопасностью, удаляются, а кэшированные сообщения электронной почты на устройстве удаляются.</span><span class="sxs-lookup"><span data-stu-id="5caa2-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="5caa2-153">Да</span><span class="sxs-lookup"><span data-stu-id="5caa2-153">Yes</span></span>|<span data-ttu-id="5caa2-154">Недоступно</span><span class="sxs-lookup"><span data-stu-id="5caa2-154">N/A</span></span>|
>[!NOTE] 
><span data-ttu-id="5caa2-155">Приложение корпоративного портала доступно в магазине App Store for iOS и Device Store for Android Devices.</span><span class="sxs-lookup"><span data-stu-id="5caa2-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5caa2-156">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="5caa2-156">Related topics</span></span>

[<span data-ttu-id="5caa2-157">Настройка Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="5caa2-157">Set up Basic Mobility and Security</span></span>](set-up.md)