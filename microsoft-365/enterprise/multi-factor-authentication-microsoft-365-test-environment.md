---
title: Многофакторная проверка подлинности для тестовой среды Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Настройка многофакторной проверки подлинности с помощью текстовых сообщений, отправленных на смарт-телефон в тестовой среде Microsoft 365 Enterprise.
ms.openlocfilehash: 319f8058aa4504c52cacf5f0d97982d115c41c8a
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074219"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="35efc-103">Многофакторная проверка подлинности для тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="35efc-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="35efc-104">Для дополнительного уровня безопасности при входе в Office 365 или любой другой службы или приложения, использующего клиент Azure AD для вашей организации, вы можете включить многофакторную проверку подлинности Azure, которая требует больше, чем просто имя пользователя и пароль для проверки финансового.</span><span class="sxs-lookup"><span data-stu-id="35efc-104">For an additional level of security for signing in to Office 365 or any service or application that uses the Azure AD tenant for your organization, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> <span data-ttu-id="35efc-105">При использовании многофакторной проверки подлинности пользователям необходимо подтвердить телефонный звонок, ввести код проверки, отправленный в текстовом сообщении, или указать пароль приложения на смарт-телефонах после правильного ввода пароля.</span><span class="sxs-lookup"><span data-stu-id="35efc-105">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="35efc-106">Только после этого он сможет войти в свою учетную запись.</span><span class="sxs-lookup"><span data-stu-id="35efc-106">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="35efc-107">В этой статье описывается, как включить и протестировать проверку подлинности на основе текстовых сообщений для определенной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="35efc-107">This article describes how to enable and test text message-based authentication for a specific account.</span></span>
  
<span data-ttu-id="35efc-108">Настройка многофакторной проверки подлинности для учетной записи в тестовой среде Microsoft 365 Enterprise состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="35efc-108">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="35efc-109">Создайте среду тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="35efc-109">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="35efc-110">Включение и проверка многофакторной проверки подлинности для учетной записи User 2.</span><span class="sxs-lookup"><span data-stu-id="35efc-110">Enable and test multi-factor authentication for the User 2 account.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="35efc-112">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="35efc-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="35efc-113">Этап 1: создание тестовой среды Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="35efc-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="35efc-114">Если вы только хотите протестировать многофакторную проверку подлинности в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="35efc-114">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="35efc-115">Если вы хотите протестировать многофакторную проверку подлинности на имитируемом предприятии, следуйте инструкциям в [сквозной проверке](pass-through-auth-m365-ent-test-environment.md)подлинности.</span><span class="sxs-lookup"><span data-stu-id="35efc-115">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="35efc-116">Для тестирования многофакторной проверки подлинности не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="35efc-116">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="35efc-117">Она показана здесь лишь для того, чтобы вы могли проверить многофакторную проверку подлинности и поэкспериментировать с этим компонентом в типичной для организаций среде.</span><span class="sxs-lookup"><span data-stu-id="35efc-117">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="35efc-118">Этап 2. Включение и проверка многофакторной проверки подлинности для учетной записи User 2</span><span class="sxs-lookup"><span data-stu-id="35efc-118">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="35efc-119">Чтобы включить многофакторную проверку подлинности для учетной записи User 2, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="35efc-119">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="35efc-120">Откройте отдельный частный экземпляр браузера, перейдите в центр администрирования Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)), а затем войдите с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="35efc-120">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="35efc-121">На панели навигации слева выберите **Пользователи > Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="35efc-121">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="35efc-122">В области активные пользователи щелкните **дополнительные > настройке многофакторной проверки**подлинности.</span><span class="sxs-lookup"><span data-stu-id="35efc-122">In the Active users pane, click **More > Multi-factor authentication setup**.</span></span>
    
4. <span data-ttu-id="35efc-123">В списке выберите учетную запись **пользователя 2** .</span><span class="sxs-lookup"><span data-stu-id="35efc-123">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="35efc-124">В разделе **пользователь 2** в разделе **быстрые действия**нажмите кнопку **включить**.</span><span class="sxs-lookup"><span data-stu-id="35efc-124">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
6. <span data-ttu-id="35efc-125">В диалоговом окне **Сведения о включении многофакторной проверки подлинности** нажмите **Включить проверку Multi-Factor Auth**.</span><span class="sxs-lookup"><span data-stu-id="35efc-125">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="35efc-126">В диалоговом окне **успешное обновление** нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="35efc-126">In the **Updates successful** dialog box, click **Close**.</span></span>
    
8. <span data-ttu-id="35efc-127">На вкладке **центра администрирования Microsoft 365** щелкните значок учетной записи пользователя в правом верхнем углу, а затем нажмите **выйти**.</span><span class="sxs-lookup"><span data-stu-id="35efc-127">On the **Microsoft 365 admin center** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
9. <span data-ttu-id="35efc-128">Закройте окно браузера.</span><span class="sxs-lookup"><span data-stu-id="35efc-128">Close your browser instance.</span></span>
   
<span data-ttu-id="35efc-129">Чтобы настроить отправку текстового сообщения для проверки учетной записи User 2 и проверить ее, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="35efc-129">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="35efc-130">Откройте новый частный экземпляр браузера.</span><span class="sxs-lookup"><span data-stu-id="35efc-130">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="35efc-131">Перейдите на портал Office 365 ([https://portal.office.com](https://portal.office.com)) и войдите в систему, используя имя и пароль учетной записи пользователя 2.</span><span class="sxs-lookup"><span data-stu-id="35efc-131">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="35efc-132">После входа вам будет предложено настроить учетную запись для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="35efc-132">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="35efc-133">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="35efc-133">Click **Next**.</span></span>
    
4. <span data-ttu-id="35efc-134">На странице **Дополнительная проверка безопасности**: </span><span class="sxs-lookup"><span data-stu-id="35efc-134">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="35efc-135">Выберите свою страну или регион.</span><span class="sxs-lookup"><span data-stu-id="35efc-135">Select your country or region.</span></span>
    
   - <span data-ttu-id="35efc-136">Введите номер телефона, на который будут отправляться текстовые сообщения.</span><span class="sxs-lookup"><span data-stu-id="35efc-136">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="35efc-137">В поле **метод**нажмите кнопку **отправить код по текстовому сообщению**.</span><span class="sxs-lookup"><span data-stu-id="35efc-137">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="35efc-138">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="35efc-138">Click **Next**.</span></span>
    
6. <span data-ttu-id="35efc-139">Введите код проверки из текстового сообщения, полученного на смартфон, и нажмите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="35efc-139">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="35efc-140">На странице **Шаг 3. Продолжайте использовать имеющиеся приложения** скопируйте отображаемый пароль приложения для учетной записи User 2 в надежное место и нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="35efc-140">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="35efc-p104">При первом входе в учетную запись User 2 вам будет предложено изменить пароль. Введите исходный пароль и новый пароль дважды и нажмите **Обновить пароль и войти**. Запишите новый пароль в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="35efc-p104">If this is the first time you signed in with the User 2 account, you are prompted to change the password. Type the original password and a new password twice, and then click **Update password and sign in**. Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="35efc-144">Вы должны увидеть портал Office для пользователя 2 на вкладке **Microsoft Office Главная** в браузере.</span><span class="sxs-lookup"><span data-stu-id="35efc-144">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>


<span data-ttu-id="35efc-145">Чтобы получить сведения и ссылки для развертывания многофакторной проверки подлинности в рабочей среде, просмотрите этап " [Настройка многофакторной проверки](identity-multi-factor-authentication.md#identity-mfa) подлинности" на этапе идентификации.</span><span class="sxs-lookup"><span data-stu-id="35efc-145">See the [Set up multi-factor authentication](identity-multi-factor-authentication.md#identity-mfa) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="35efc-146">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="35efc-146">Next step</span></span>

<span data-ttu-id="35efc-147">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="35efc-147">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="35efc-148">См. также</span><span class="sxs-lookup"><span data-stu-id="35efc-148">See also</span></span>

[<span data-ttu-id="35efc-149">Шаг 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="35efc-149">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="35efc-150">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="35efc-150">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="35efc-151">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="35efc-151">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="35efc-152">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="35efc-152">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
