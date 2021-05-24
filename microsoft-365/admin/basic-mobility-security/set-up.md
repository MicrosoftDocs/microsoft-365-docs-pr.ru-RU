---
title: Настройка Basic Mobility + Security
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
description: Настройка базовой мобильности и безопасности для защиты и управления мобильными устройствами пользователей путем выполнения действий, например удаленного вытирания устройства.
ms.openlocfilehash: 02ba28deca6286456af5f87841a741262c1a135d
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52634296"
---
# <a name="set-up-basic-mobility-and-security"></a><span data-ttu-id="51162-103">Настройка Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="51162-103">Set up Basic Mobility and Security</span></span>

<span data-ttu-id="51162-104">Встроенная базовая мобильность и безопасность для Microsoft 365 позволяет обезопасить и управлять мобильными устройствами пользователей, такими как iPhone, iPad, Android и Windows телефонов.</span><span class="sxs-lookup"><span data-stu-id="51162-104">The built-in Basic Mobility and Security for Microsoft 365 helps you secure and manage users' mobile devices such as iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="51162-105">Вы можете создавать политики безопасности устройств и управлять ими, удаленно очищать устройства и просматривать подробные отчеты об устройствах.</span><span class="sxs-lookup"><span data-stu-id="51162-105">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

<span data-ttu-id="51162-106">Есть вопросы?</span><span class="sxs-lookup"><span data-stu-id="51162-106">Have questions?</span></span> <span data-ttu-id="51162-107">Вопросы часто задаваемой вопросы см. в справке [Basic Mobility and Security Frequently-asked questions (FAQ).](frequently-asked-questions.md)</span><span class="sxs-lookup"><span data-stu-id="51162-107">For a FAQ to help address common questions, see [Basic Mobility and Security Frequently-asked questions (FAQ)](frequently-asked-questions.md).</span></span> <span data-ttu-id="51162-108">Следует помнить, что для управления базовой мобильностью и безопасностью нельзя использовать делегированную учетную запись администратора.</span><span class="sxs-lookup"><span data-stu-id="51162-108">Be aware that you cannot use a delegated administrator account to manage Basic Mobility and Security.</span></span> <span data-ttu-id="51162-109">Дополнительные сведения см. в [сайте Partners: Предложение делегирования администрирования.](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e)</span><span class="sxs-lookup"><span data-stu-id="51162-109">For more info, see [Partners: Offer delegated administration](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e).</span></span> 

<span data-ttu-id="51162-110">Управление устройствами является частью Центра & безопасности, поэтому вам потребуется перейти туда, чтобы приумнотить базовую настройку мобильности и безопасности.</span><span class="sxs-lookup"><span data-stu-id="51162-110">Device management is part of the Security & Compliance Center so you'll need to go there to kick off Basic Mobility and Security setup.</span></span>

## <a name="activate-the-basic-mobility-and-security-service"></a><span data-ttu-id="51162-111">Активация службы базовой мобильности и безопасности</span><span class="sxs-lookup"><span data-stu-id="51162-111">Activate the Basic Mobility and Security service</span></span>

1. <span data-ttu-id="51162-112">Во входе Microsoft 365 с глобальной учетной записью администратора.</span><span class="sxs-lookup"><span data-stu-id="51162-112">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="51162-113">Перейдите к [активации базовой мобильности и безопасности](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span><span class="sxs-lookup"><span data-stu-id="51162-113">Go to [Activate Basic Mobility and Security](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span>

   <span data-ttu-id="51162-114">Активация basic Mobility и Security может занять некоторое время.</span><span class="sxs-lookup"><span data-stu-id="51162-114">It can take some time to activate Basic Mobility and Security.</span></span> <span data-ttu-id="51162-115">По его завершению вы получите сообщение электронной почты с объяснением следующих действий.</span><span class="sxs-lookup"><span data-stu-id="51162-115">When it finishes, you'll receive an email that explains the next steps to take.</span></span>

## <a name="set-up-mobile-device-management"></a><span data-ttu-id="51162-116">Настройка управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="51162-116">Set up Mobile Device Management</span></span>

<span data-ttu-id="51162-117">Когда служба будет готова, выполните следующие действия, чтобы завершить настройку.</span><span class="sxs-lookup"><span data-stu-id="51162-117">When the service is ready, complete the following steps to finish setup.</span></span>

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a><span data-ttu-id="51162-118">Шаг 1. (Обязательно) Настройка доменов для базовой мобильности и безопасности</span><span class="sxs-lookup"><span data-stu-id="51162-118">Step 1: (Required) Configure domains for Basic Mobility and Security</span></span>

<span data-ttu-id="51162-119">Если у вас нет настраиваемой области, связанной с Microsoft 365 или если вы не управляете устройствами Windows, вы можете пропустить этот раздел.</span><span class="sxs-lookup"><span data-stu-id="51162-119">If you don't have a custom domain associated with Microsoft 365 or if you're not managing Windows devices, you can skip this section.</span></span> <span data-ttu-id="51162-120">В противном случае необходимо добавить записи DNS для домена на вашем DNS-хозяйте.</span><span class="sxs-lookup"><span data-stu-id="51162-120">Otherwise, you'll need to add DNS records for the domain at your DNS host.</span></span> <span data-ttu-id="51162-121">Если вы уже добавили записи, в рамках настройки домена с Microsoft 365, вы все настроены.</span><span class="sxs-lookup"><span data-stu-id="51162-121">If you've added the records already, as part of setting up your domain with Microsoft 365, you're all set.</span></span> <span data-ttu-id="51162-122">После добавления записей пользователи Microsoft 365 в организации, которые вписываются на Windows с электронным адресом, использующим настраиваемый домен, перенаправляются для регистрации в Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="51162-122">After you add the records, Microsoft 365 users in your organization who sign in on their Windows device with an email address that uses your custom domain are redirected to enroll in Basic Mobility and Security.</span></span>

<span data-ttu-id="51162-123">Нужна помощь в настройке записей?</span><span class="sxs-lookup"><span data-stu-id="51162-123">Need help setting up the records?</span></span> <span data-ttu-id="51162-124">Найдите регистратор домена и выберите имя регистратора, чтобы пошаговая помощь по созданию записи DNS в списке, представленном в записях Добавить DNS для подключения [домена.](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)</span><span class="sxs-lookup"><span data-stu-id="51162-124">Find your domain registrar and select the registrar name to go to step-by-step help for creating DNS record in the list provided in [Add DNS records to connect your domain](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span> <span data-ttu-id="51162-125">Используйте эти инструкции для создания записей CNAME, описанных в Windows регистрации без [Azure AD Premium](/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium).</span><span class="sxs-lookup"><span data-stu-id="51162-125">Use those instructions to create CNAME records described in [Simplify Windows enrollment without Azure AD Premium](/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium).</span></span>

<span data-ttu-id="51162-126">После добавления двух записей CNAME перейдите в Центр & безопасности и перейдите к управлению устройствами для предотвращения потери данных, чтобы выполнить  >     следующий шаг.</span><span class="sxs-lookup"><span data-stu-id="51162-126">After you add the two CNAME records, go back to the Security & Compliance Center and go to **Data loss prevention** > **Device management** to complete the next step.</span></span>

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="51162-127">Шаг 2. (Обязательно) Настройка сертификата APNs для устройств iOS</span><span class="sxs-lookup"><span data-stu-id="51162-127">Step 2: (Required) Configure an APNs Certificate for iOS devices</span></span>

<span data-ttu-id="51162-128">Чтобы управлять устройствами iOS iPad iPhone и iPhone, необходимо создать сертификат APNs.</span><span class="sxs-lookup"><span data-stu-id="51162-128">To manage iOS devices like iPad and iPhones, you need to create an APNs certificate.</span></span>

1. <span data-ttu-id="51162-129">Во входе Microsoft 365 с глобальной учетной записью администратора.</span><span class="sxs-lookup"><span data-stu-id="51162-129">Sign in to  Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="51162-130">В типе браузера:  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="51162-130">In your browser type: [https://protection.office.com](https://protection.office.com/).</span></span>

3. <span data-ttu-id="51162-131">Выберите  **управление устройствами для** предотвращения   >  **потери данных** и выберите сертификат **APNs для устройств iOS.**</span><span class="sxs-lookup"><span data-stu-id="51162-131">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>

4. <span data-ttu-id="51162-132">На странице Apple Push Notification Certificate Параметры выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="51162-132">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>

5. <span data-ttu-id="51162-133">Выберите **Скачайте CSR-файл** и сохраните запрос на подписание сертификата на вашем компьютере, который   запомнится.</span><span class="sxs-lookup"><span data-stu-id="51162-133">Select **Download your CSR file** and save the Certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="51162-134">Выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="51162-134">Select **Next**.</span></span>

6. <span data-ttu-id="51162-135">На странице Создание сертификата APNs:</span><span class="sxs-lookup"><span data-stu-id="51162-135">On the Create an APNs certificate page:</span></span>

   - <span data-ttu-id="51162-136">Выберите портал APNS Apple, чтобы открыть портал push-сертификатов Apple.</span><span class="sxs-lookup"><span data-stu-id="51162-136">Select Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>
   - <span data-ttu-id="51162-137">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="51162-137">Sign in with an Apple ID.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="51162-p107">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="51162-p107">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

   - <span data-ttu-id="51162-140">Выберите Создать сертификат и принять условия использования.</span><span class="sxs-lookup"><span data-stu-id="51162-140">Select Create a Certificate and accept the Terms of Use.</span></span>
   - <span data-ttu-id="51162-141">Просмотрите запрос на подписание сертификата, загруженный на компьютер с Microsoft 365 и selectUpload.</span><span class="sxs-lookup"><span data-stu-id="51162-141">Browse to the Certificate signing request you downloaded to your computer from Microsoft 365 and selectUpload.</span></span>
   - <span data-ttu-id="51162-142">Download the APN certificate created by the Apple Push Certificate Portal to your computer.</span><span class="sxs-lookup"><span data-stu-id="51162-142">Download the APN certificate created by the Apple Push Certificate Portal to your computer.</span></span>

     > [!TIP]
     > <span data-ttu-id="51162-143">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="51162-143">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="51162-144">Возвращайся к Microsoft 365 и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="51162-144">Go back to Microsoft 365 and select **Next**.</span></span>

8. <span data-ttu-id="51162-145"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="51162-145">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>

9. <span data-ttu-id="51162-146">Выберите  **Готово**.</span><span class="sxs-lookup"><span data-stu-id="51162-146">Select  **Finish**.</span></span>

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a><span data-ttu-id="51162-147">Шаг 3. (Рекомендуется) Настройка многофакторной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="51162-147">Step 3: (Recommended) Set up multi-factor authentication</span></span>

<span data-ttu-id="51162-148">MFA помогает обеспечить вход Microsoft 365 для регистрации мобильных устройств, требуя второй формы проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="51162-148">MFA helps secure the sign in to Microsoft 365 for mobile device enrollment by requiring a second form of authentication.</span></span> <span data-ttu-id="51162-149">Пользователи должны подтвердить телефонный звонок, текстовое сообщение или уведомление о приложении на своем мобильном устройстве после правильного ввода пароля учетной записи работы.</span><span class="sxs-lookup"><span data-stu-id="51162-149">Users are required to acknowledge a phone call, text message, or app notification on their mobile device after correctly entering their work account password.</span></span> <span data-ttu-id="51162-150">Они могут записать свое устройство только после завершения второй формы проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="51162-150">They can enroll their device only after this second form of authentication is completed.</span></span> <span data-ttu-id="51162-151">После регистрации устройств пользователей в Basic Mobility and Security пользователи могут получать доступ к Microsoft 365 только своей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="51162-151">After user devices are enrolled in Basic Mobility and Security, users can access Microsoft 365 resources with only their work account.</span></span>

<span data-ttu-id="51162-152">Чтобы узнать, как включить MFA на портале Azure AD, см. в этой ссылке [Настройка многофакторной проверки подлинности.](../security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="51162-152">To learn how to turn on MFA in the Azure AD portal, see [Set up multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="51162-153">После настройка MFA возвращайтесь в Центр & безопасности и \*\*\*\* перейдите к политикам управления устройствами управления устройствами для предотвращения потери данных, чтобы выполнить   >     >  \*\*\*\*   следующий шаг.</span><span class="sxs-lookup"><span data-stu-id="51162-153">After you set up MFA, go back to the Security & Compliance Center and navigate to  **Data loss prevention** > **Device management** > **Device policies** to complete the next step.</span></span>

### <a name="step-4-recommended-manage-device-security-policies"></a><span data-ttu-id="51162-154">Шаг 4. (Рекомендуется) Управление политиками безопасности устройств</span><span class="sxs-lookup"><span data-stu-id="51162-154">Step 4: (Recommended) Manage device security policies</span></span>

<span data-ttu-id="51162-155">Следующий шаг — создание и развертывание политик безопасности устройств для защиты данных Microsoft 365 организации.</span><span class="sxs-lookup"><span data-stu-id="51162-155">The next step is to create and deploy device security policies to help protect your Microsoft 365 organization data.</span></span> <span data-ttu-id="51162-156">Например, вы можете предотвратить потерю данных, если пользователь теряет устройство, создав политику блокировки устройств после пяти минут бездействия и стирая устройства после трех сбоев при входе.</span><span class="sxs-lookup"><span data-stu-id="51162-156">For example, you can help prevent data loss if a user loses their device by creating a policy to lock devices after five minutes of inactivity and wipe devices after three sign-in failures.</span></span>

1. <span data-ttu-id="51162-157">Во входе Microsoft 365 с глобальной учетной записью администратора.</span><span class="sxs-lookup"><span data-stu-id="51162-157">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="51162-158">Выберите [активировать управление мобильными устройствами.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)</span><span class="sxs-lookup"><span data-stu-id="51162-158">Select [Activate Mobile Device Management](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="51162-159">Если служба активирована, вместо действий активации вы увидите ссылку на [управление устройствами.](https://admin.microsoft.com/adminportal/home#/MifoDevices)  </span><span class="sxs-lookup"><span data-stu-id="51162-159">If the service is activated, instead the activation steps you'll see a link to [Manage Devices](https://admin.microsoft.com/adminportal/home#/MifoDevices) .</span></span>

3. <span data-ttu-id="51162-160">Перейдите к **политикам устройства.**</span><span class="sxs-lookup"><span data-stu-id="51162-160">Go to **Device policies**.</span></span>

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Основные параметры политики безопасности и мобильности":::

4. <span data-ttu-id="51162-162">Создание и развертывание политик безопасности устройств, соответствующих вашей организации, в соответствии с действиями в Области создания политик безопасности устройств [в Basic Mobility and Security.](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="51162-162">Create and deploy device security policies appropriate for your organization following the steps in [Create device security policies in Basic Mobility and Security](create-device-security-policies.md).</span></span>

> [!TIP]
>
> - <span data-ttu-id="51162-163">При создании новой политики может потребоваться установить политику, чтобы разрешить доступ и сообщать о нарушении политики, если устройство пользователя не соответствует политике.</span><span class="sxs-lookup"><span data-stu-id="51162-163">When you create a new policy, you might want to set the policy to allow access and report policy violation where a user device isn't compliant with the policy.</span></span> <span data-ttu-id="51162-164">Это позволяет увидеть, сколько мобильных устройств влияет на политику, не блокируя доступ к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="51162-164">This allows you see how many mobile devices are impacted by the policy without blocking access to Microsoft 365.</span></span>
>
> - <span data-ttu-id="51162-165">Перед развертыванием новой политики для всех сотрудников организации рекомендуется протестировать ее на устройствах, используемых небольшим числом пользователей.</span><span class="sxs-lookup"><span data-stu-id="51162-165">Before you deploy a new policy to everyone in your organization, we recommend you test it on the devices used by a small number of users.</span></span>
>
> - <span data-ttu-id="51162-166">Кроме того, перед развертыванием политик дайте организации знать о потенциальных последствиях регистрации устройства в Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="51162-166">Also, before you deploy policies, let your organization know the potential impacts of enrolling a device in Basic Mobility and Security.</span></span> <span data-ttu-id="51162-167">В зависимости от того, как настроить политики, устройства, не соответствующие политикам (устройства, не соответствующие требованиям), могут быть заблокированы для доступа к Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="51162-167">Depending on how you set up the policies, devices that don't comply with policies (non-compliant devices) could be blocked from accessing Microsoft 365.</span></span> <span data-ttu-id="51162-168">На устройствах, не совместимых с установленными приложениями, фотографиями и другими персональными данными, которые на зарегистрированных устройствах могут быть удалены в случае стирки устройства.</span><span class="sxs-lookup"><span data-stu-id="51162-168">Non-compliant devices might also have apps installed, photos, and other personal information which, on an enrolled device, could be deleted if the device is wiped.</span></span> <span data-ttu-id="51162-169">Дополнительные сведения см. в [приложении Wipe a mobile device in Basic Mobility and Security.](wipe-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="51162-169">For more info, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="make-sure-users-enroll-their-devices"></a><span data-ttu-id="51162-170">Убедитесь, что пользователи зачислили свои устройства</span><span class="sxs-lookup"><span data-stu-id="51162-170">Make sure users enroll their devices</span></span>

<span data-ttu-id="51162-171">После создания и развертывания политики управления мобильными устройствами каждый лицензированный Microsoft 365 в организации, применяемой политикой устройств, получает сообщение о регистрации при следующем входе Microsoft 365 с мобильного устройства.</span><span class="sxs-lookup"><span data-stu-id="51162-171">After you've created and deployed a mobile device management policy, each licensed Microsoft 365 user in your organization that the device policy applies receives an enrollment message the next time they sign into Microsoft 365 from their mobile device.</span></span> <span data-ttu-id="51162-172">Они должны завершить действия по регистрации и активации, прежде чем они смогут получить доступ Microsoft 365 электронной почты и документов.</span><span class="sxs-lookup"><span data-stu-id="51162-172">They must complete the enrollment and activation steps before they can access Microsoft 365 email and documents.</span></span> <span data-ttu-id="51162-173">Дополнительные сведения см. в [записи мобильного устройства с помощью Basic Mobility and Security.](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="51162-173">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51162-174">Если предпочтительный язык пользователя не поддерживается процессом регистрации, пользователи могут получать уведомления о регистрации и шаги на мобильных устройствах на другом языке.</span><span class="sxs-lookup"><span data-stu-id="51162-174">If a user's preferred language isn't supported by the enrollment process, users might receive enrollment notification and steps on their mobile devices in another language.</span></span> <span data-ttu-id="51162-175">Не все языки, поддерживаемые Microsoft 365, в настоящее время поддерживаются для процесса регистрации на мобильных устройствах.</span><span class="sxs-lookup"><span data-stu-id="51162-175">Not all languages supported in Microsoft 365 are currently supported for the enrollment process on mobile devices.</span></span>

<span data-ttu-id="51162-176">Пользователи с устройствами Android или iOS должны установить Корпоративный портал приложение в рамках процесса регистрации.</span><span class="sxs-lookup"><span data-stu-id="51162-176">Users with Android or iOS devices are required to install the Company Portal app as part of the enrollment process.</span></span>

## <a name="related-content"></a><span data-ttu-id="51162-177">См. также:</span><span class="sxs-lookup"><span data-stu-id="51162-177">Related content</span></span>

<span data-ttu-id="51162-178">[Возможности базовой мобильности и безопасности](capabilities.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="51162-178">[Capabilities of Basic Mobility and Security](capabilities.md) (article)</span></span>\
<span data-ttu-id="51162-179">[Создание политик безопасности устройств в Basic Mobility and Security](create-device-security-policies.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="51162-179">[Create device security policies in Basic Mobility and Security](create-device-security-policies.md) (article)</span></span>