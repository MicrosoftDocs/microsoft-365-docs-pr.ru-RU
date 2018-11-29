---
title: Многофакторная проверка подлинности для вашего предприятия 365 Microsoft тестовой среды
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Настройка многофакторной проверки подлинности с помощью текст сообщения, отправленные на смарт-телефон в тестовой среде Microsoft 365 Enterprise.
ms.openlocfilehash: aae493e79a197635b2e14fa7f238a3189ed695ae
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870441"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="307d3-103">Многофакторная проверка подлинности для вашего предприятия 365 Microsoft тестовой среды</span><span class="sxs-lookup"><span data-stu-id="307d3-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="307d3-p101">Для дополнительного уровня безопасности для входа в Office 365 или любые службы или приложения, использующего клиент Azure AD для вашей организации, можно включить Azure многофакторной проверки подлинности, который требуется больше, чем просто имя пользователя и пароль для проверки Учетная запись. С многофакторной проверки подлинности пользователей необходимы для подтверждения на телефонный звонок, введите код подтверждения, отправленных в текстовом сообщении или укажите пароль приложения на свои смартфоны после правильно ввода пароля. Они могут входить только после этой второй фактор проверки подлинности были выполнены.</span><span class="sxs-lookup"><span data-stu-id="307d3-p101">For an additional level of security for signing in to Office 365 or any service or application that uses the Azure AD tenant for your organization, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account. With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or specify an app password on their smart phones after correctly entering their passwords. They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="307d3-107">В этой статье описывается включение и тестирование текста сообщения проверки подлинности на основе для конкретной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="307d3-107">This article describes how to enable and test text message-based authentication for a specific account.</span></span>
  
<span data-ttu-id="307d3-108">Существует два этапа Настройка многофакторной проверки подлинности для учетной записи в тестовой среде Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="307d3-108">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="307d3-109">Создание тестовой среды Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="307d3-109">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="307d3-110">Включение и проверка многофакторной проверки подлинности для учетной записи User 2.</span><span class="sxs-lookup"><span data-stu-id="307d3-110">Enable and test multi-factor authentication for the User 2 account.</span></span>

![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="307d3-112">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="307d3-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="307d3-113">Этап 1: Создание масштабирование тестовой среды Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="307d3-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="307d3-114">Если необходимо проверить многофакторной проверки подлинности в облегченный путь с минимальным требованиям, следуйте инструкциям в [упрощенной базовой конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="307d3-114">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="307d3-115">Если вы хотите проверить многофакторной проверки подлинности в имитации enterprise, следуйте инструкциям в [сквозная проверка подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="307d3-115">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="307d3-p102">Тестирование многофакторная проверка подлинности не требуется тестовой среды имитации предприятия, включающая имитации интрасети, подключенных к Интернету и синхронизации каталогов для леса Windows Server AD. Предоставляется здесь как вариант, чтобы проверить многофакторной проверки подлинности и экспериментировать с его в среде, которая представляет типичное организации.</span><span class="sxs-lookup"><span data-stu-id="307d3-p102">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="307d3-118">Этап 2. Включение и проверка многофакторной проверки подлинности для учетной записи User 2</span><span class="sxs-lookup"><span data-stu-id="307d3-118">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="307d3-119">Чтобы включить многофакторную проверку подлинности для учетной записи User 2, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="307d3-119">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="307d3-120">Откройте отдельные закрытый экземпляр браузера, перейдите к порталу Office 365 ([https://portal.office.com](https://portal.office.com)), а затем выполните вход с учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="307d3-120">Open a separate, private instance of your browser, go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="307d3-121">На главной странице портала нажмите **Администратор**.</span><span class="sxs-lookup"><span data-stu-id="307d3-121">From the main portal page, click **Admin**.</span></span>
    
3. <span data-ttu-id="307d3-122">На панели навигации слева выберите **Пользователи > Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="307d3-122">In the left navigation, click **Users > Active users**.</span></span>
    
4. <span data-ttu-id="307d3-123">В области активных пользователей щелкните **более > Настройка многофакторной проверки подлинности**.</span><span class="sxs-lookup"><span data-stu-id="307d3-123">In the Active users pane, click **More > Multi-factor authentication setup**.</span></span>
    
5. <span data-ttu-id="307d3-124">В списке выберите учетную запись **пользователя 2** .</span><span class="sxs-lookup"><span data-stu-id="307d3-124">In the list, select the **User 2** account.</span></span>
    
6. <span data-ttu-id="307d3-125">В разделе **2 пользователя** в разделе **Быстрые действия**, нажмите кнопку **Включить**.</span><span class="sxs-lookup"><span data-stu-id="307d3-125">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
7. <span data-ttu-id="307d3-126">В диалоговом окне **Сведения о включении многофакторной проверки подлинности** нажмите **Включить проверку Multi-Factor Auth**.</span><span class="sxs-lookup"><span data-stu-id="307d3-126">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
8. <span data-ttu-id="307d3-127">В диалоговом окне **обновление успешно** нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="307d3-127">In the **Updates successful** dialog box, click **Close**.</span></span>
    
9. <span data-ttu-id="307d3-128">На вкладке **Домашняя страница Microsoft Office** щелкните значок учетной записи пользователя в правом верхнем углу и нажмите **Выйти**.</span><span class="sxs-lookup"><span data-stu-id="307d3-128">On the **Microsoft Office Home** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
10. <span data-ttu-id="307d3-129">Закройте окно браузера.</span><span class="sxs-lookup"><span data-stu-id="307d3-129">Close your browser instance.</span></span>
   
<span data-ttu-id="307d3-130">Чтобы настроить отправку текстового сообщения для проверки учетной записи User 2 и проверить ее, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="307d3-130">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="307d3-131">Откройте новый экземпляр закрытого браузера.</span><span class="sxs-lookup"><span data-stu-id="307d3-131">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="307d3-132">Последовательно выберите пункты портала Office 365 ([https://portal.office.com](https://portal.office.com)) и входа в систему с учетной записью пользователя 2 (Пользователь2 @\<название организации >. onmicrosoft.com) и пароль.</span><span class="sxs-lookup"><span data-stu-id="307d3-132">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in with the User 2 account (user2@\<organization name>.onmicrosoft.com) and password.</span></span>
    
3. <span data-ttu-id="307d3-p103">После входа в запрос для настройки учетной записи для получения дополнительных сведений. Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="307d3-p103">After signing in, you are prompted to set up the account for more information. Click **Next**.</span></span>
    
4. <span data-ttu-id="307d3-135">На странице **Дополнительная проверка безопасности**: </span><span class="sxs-lookup"><span data-stu-id="307d3-135">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="307d3-136">Выберите свою страну или регион.</span><span class="sxs-lookup"><span data-stu-id="307d3-136">Select your country or region.</span></span>
    
   - <span data-ttu-id="307d3-137">Введите номер телефона, на который будут отправляться текстовые сообщения.</span><span class="sxs-lookup"><span data-stu-id="307d3-137">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="307d3-138">В **метод**нажмите кнопку **Отправить мне кода с текстовое сообщение**.</span><span class="sxs-lookup"><span data-stu-id="307d3-138">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="307d3-139">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="307d3-139">Click **Next**.</span></span>
    
6. <span data-ttu-id="307d3-140">Введите код проверки из текстового сообщения, полученного на смартфон, и нажмите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="307d3-140">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="307d3-141">На странице **Шаг 3. Продолжайте использовать имеющиеся приложения** скопируйте отображаемый пароль приложения для учетной записи User 2 в надежное место и нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="307d3-141">On the **Step 3: Keep your existing applications** page, record the displayed app password for the User 2 account in a secure location, and then click **Done**.</span></span>
    
8. <span data-ttu-id="307d3-p104">При первом входе в учетную запись User 2 вам будет предложено изменить пароль. Введите исходный пароль и новый пароль дважды и нажмите **Обновить пароль и войти**. Запишите новый пароль в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="307d3-p104">If this is the first time you signed in with the User 2 account, you are prompted to change the password. Type the original password and a new password twice, and then click **Update password and sign in**. Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="307d3-145">Вы должны увидеть портала Office 365 для пользователя 2 на вкладке **Microsoft Office для дома** браузера.</span><span class="sxs-lookup"><span data-stu-id="307d3-145">You should see the Office 365 portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>


<span data-ttu-id="307d3-146">Просмотрите шаг [Настройка многофакторной проверки подлинности](identity-multi-factor-authentication.md) на этапе Identity сведения и ссылки на развертывание многофакторной проверки подлинности в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="307d3-146">See the [Set up multi-factor authentication](identity-multi-factor-authentication.md) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="307d3-147">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="307d3-147">Next step</span></span>

<span data-ttu-id="307d3-148">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="307d3-148">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="307d3-149">См. также</span><span class="sxs-lookup"><span data-stu-id="307d3-149">See also</span></span>

[<span data-ttu-id="307d3-150">Этап 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="307d3-150">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="307d3-151">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="307d3-151">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="307d3-152">Развертывание Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="307d3-152">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="307d3-153">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="307d3-153">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
