---
title: Многофакторная проверка подлинности для тестовой среды Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Настройка многофакторной проверки подлинности с помощью текстовых сообщений, отправленных на смарт-телефон в тестовой среде Microsoft 365 Enterprise.
ms.openlocfilehash: 8e202936451030718c0c86601c2c621c50f78e1a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291144"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6a886-103">Многофакторная проверка подлинности для тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="6a886-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6a886-104">Для дополнительного уровня безопасности при входе в Office 365 или любой другой службы или приложения, использующего клиент Azure AD для вашей организации, вы можете включить многофакторную проверку подлинности Azure, которая требует больше, чем просто имя пользователя и пароль для проверки финансового.</span><span class="sxs-lookup"><span data-stu-id="6a886-104">For an additional level of security for signing in to Office 365 or any service or application that uses the Azure AD tenant for your organization, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> <span data-ttu-id="6a886-105">При использовании многофакторной проверки подлинности пользователям необходимо подтвердить телефонный звонок, ввести код проверки, отправленный в текстовом сообщении, или указать пароль приложения на смарт-телефонах после правильного ввода пароля.</span><span class="sxs-lookup"><span data-stu-id="6a886-105">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="6a886-106">Только после этого он сможет войти в свою учетную запись.</span><span class="sxs-lookup"><span data-stu-id="6a886-106">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="6a886-107">В этой статье описывается, как включить и протестировать проверку подлинности на основе текстовых сообщений для определенной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="6a886-107">This article describes how to enable and test text message-based authentication for a specific account.</span></span>
  
<span data-ttu-id="6a886-108">Настройка многофакторной проверки подлинности для учетной записи в тестовой среде Microsoft 365 Enterprise состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="6a886-108">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="6a886-109">Создайте корпоративную тестовую среду Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6a886-109">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="6a886-110">Включение и проверка многофакторной проверки подлинности для учетной записи User 2.</span><span class="sxs-lookup"><span data-stu-id="6a886-110">Enable and test multi-factor authentication for the User 2 account.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="6a886-112">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="6a886-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6a886-113">Этап 1: создание тестовой среды Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6a886-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6a886-114">Если вы только хотите протестировать многофакторную проверку подлинности в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="6a886-114">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="6a886-115">Если вы хотите протестировать многофакторную проверку подлинности на имитируемом предприятии, следуйте инструкциям в [сквозной проверке](pass-through-auth-m365-ent-test-environment.md)подлинности.</span><span class="sxs-lookup"><span data-stu-id="6a886-115">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6a886-116">Для тестирования многофакторной проверки подлинности не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="6a886-116">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="6a886-117">Она показана здесь лишь для того, чтобы вы могли проверить многофакторную проверку подлинности и поэкспериментировать с этим компонентом в типичной для организаций среде.</span><span class="sxs-lookup"><span data-stu-id="6a886-117">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="6a886-118">Этап 2. Включение и проверка многофакторной проверки подлинности для учетной записи User 2</span><span class="sxs-lookup"><span data-stu-id="6a886-118">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="6a886-119">Чтобы включить многофакторную проверку подлинности для учетной записи User 2, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="6a886-119">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="6a886-120">Откройте отдельный, частный экземпляр браузера, перейдите на портал Office ([https://office.com](https://office.com)), а затем войдите в свою учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="6a886-120">Open a separate, private instance of your browser, go to the Office portal ([https://office.com](https://office.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="6a886-121">На главной странице портала нажмите **Администрирование**.</span><span class="sxs-lookup"><span data-stu-id="6a886-121">From the main portal page, click **Admin**.</span></span>
    
3. <span data-ttu-id="6a886-122">На панели навигации слева выберите **Пользователи > Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="6a886-122">In the left navigation, click **Users > Active users**.</span></span>
    
4. <span data-ttu-id="6a886-123">В области активные пользователи щелкните **Дополнительные настройки многофакторной проверки подлиннОсти _гт_**.</span><span class="sxs-lookup"><span data-stu-id="6a886-123">In the Active users pane, click **More > Multi-factor authentication setup**.</span></span>
    
5. <span data-ttu-id="6a886-124">В списке выберите учетную запись **пользователя 2** .</span><span class="sxs-lookup"><span data-stu-id="6a886-124">In the list, select the **User 2** account.</span></span>
    
6. <span data-ttu-id="6a886-125">В разделе **пользователь 2** в разделе **быстрые действия**нажмите кнопку **включить**.</span><span class="sxs-lookup"><span data-stu-id="6a886-125">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
7. <span data-ttu-id="6a886-126">В диалоговом окне **Сведения о включении многофакторной проверки подлинности** нажмите **Включить проверку Multi-Factor Auth**.</span><span class="sxs-lookup"><span data-stu-id="6a886-126">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
8. <span data-ttu-id="6a886-127">В диалоговом окне **успешное обновление** нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="6a886-127">In the **Updates successful** dialog box, click **Close**.</span></span>
    
9. <span data-ttu-id="6a886-128">На вкладке **Домашняя страница Microsoft Office** щелкните значок учетной записи пользователя в правом верхнем углу и нажмите **Выйти**.</span><span class="sxs-lookup"><span data-stu-id="6a886-128">On the **Microsoft Office Home** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
10. <span data-ttu-id="6a886-129">Закройте окно браузера.</span><span class="sxs-lookup"><span data-stu-id="6a886-129">Close your browser instance.</span></span>
   
<span data-ttu-id="6a886-130">Чтобы настроить отправку текстового сообщения для проверки учетной записи User 2 и проверить ее, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="6a886-130">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="6a886-131">Откройте новый частный экземпляр браузера.</span><span class="sxs-lookup"><span data-stu-id="6a886-131">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="6a886-132">Перейдите на портал Office ([https://office.com](https://office.com)) и войдите в систему с учетной записью пользователя 2 (\<Пользователь2 @ Organization наме_гт_. onmicrosoft. com) и паролем.</span><span class="sxs-lookup"><span data-stu-id="6a886-132">Go to the Office portal ([https://office.com](https://office.com)) and sign in with the User 2 account (user2@\<organization name>.onmicrosoft.com) and password.</span></span>
    
3. <span data-ttu-id="6a886-133">После входа вам будет предложено настроить учетную запись для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="6a886-133">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="6a886-134">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6a886-134">Click **Next**.</span></span>
    
4. <span data-ttu-id="6a886-135">На странице **Дополнительная проверка безопасности**: </span><span class="sxs-lookup"><span data-stu-id="6a886-135">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="6a886-136">Выберите свою страну или регион.</span><span class="sxs-lookup"><span data-stu-id="6a886-136">Select your country or region.</span></span>
    
   - <span data-ttu-id="6a886-137">Введите номер телефона, на который будут отправляться текстовые сообщения.</span><span class="sxs-lookup"><span data-stu-id="6a886-137">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="6a886-138">В поле **метод**нажмите кнопку **отправить код по текстовому сообщению**.</span><span class="sxs-lookup"><span data-stu-id="6a886-138">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="6a886-139">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6a886-139">Click **Next**.</span></span>
    
6. <span data-ttu-id="6a886-140">Введите код проверки из текстового сообщения, полученного на смартфон, и нажмите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="6a886-140">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="6a886-141">На странице **Шаг 3. Продолжайте использовать имеющиеся приложения** скопируйте отображаемый пароль приложения для учетной записи User 2 в надежное место и нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="6a886-141">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="6a886-p104">При первом входе в учетную запись User 2 вам будет предложено изменить пароль. Введите исходный пароль и новый пароль дважды и нажмите **Обновить пароль и войти**. Запишите новый пароль в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="6a886-p104">If this is the first time you signed in with the User 2 account, you are prompted to change the password. Type the original password and a new password twice, and then click **Update password and sign in**. Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="6a886-145">Вы должны увидеть портал Office для пользователя 2 на вкладке **Microsoft Office Главная** в браузере.</span><span class="sxs-lookup"><span data-stu-id="6a886-145">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>


<span data-ttu-id="6a886-146">Чтобы получить сведения и ссылки для развертывания многофакторной проверки подлинности в рабочей среде, просмотрите этап " [Настройка многофакторной проверки](identity-multi-factor-authentication.md#identity-mfa) подлинности" на этапе идентификации.</span><span class="sxs-lookup"><span data-stu-id="6a886-146">See the [Set up multi-factor authentication](identity-multi-factor-authentication.md#identity-mfa) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="6a886-147">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="6a886-147">Next step</span></span>

<span data-ttu-id="6a886-148">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="6a886-148">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a886-149">См. также</span><span class="sxs-lookup"><span data-stu-id="6a886-149">See also</span></span>

[<span data-ttu-id="6a886-150">Шаг 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="6a886-150">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="6a886-151">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="6a886-151">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6a886-152">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="6a886-152">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="6a886-153">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="6a886-153">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
