---
title: Многофакторная проверка подлинности Microsoft 365 Enterprise тестовая среда
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
description: Настройка многофакторной проверки подлинности с помощью текстовых сообщений, отправленных на смарт-телефон в тестовой среде Microsoft 365 Enterprise.
ms.openlocfilehash: e26fb7470e01397266f5f424ee45941a79a2940c
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819380"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4ed38-103">Многофакторная проверка подлинности для тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="4ed38-103">Multi-factor authentication for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4ed38-104">*Это руководство по лаборатории тестирования можно использовать для тестовых сред Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="4ed38-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="4ed38-105">Для дополнительного уровня безопасности при входе в Microsoft 365 или любой другой службы или приложения, использующего клиент Azure AD для вашей подписки, вы можете включить многофакторную проверку подлинности Azure, которая требует больше имени пользователя и пароля, чтобы проверить учетную запись.</span><span class="sxs-lookup"><span data-stu-id="4ed38-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure multi-factor authentication, which requires more than just a username and password to verify an account.</span></span> 

<span data-ttu-id="4ed38-106">При использовании многофакторной проверки подлинности пользователям необходимо подтвердить телефонный звонок, ввести код проверки, отправленный в текстовом сообщении, или проверить проверку подлинности с помощью приложения на смарт-телефонах после правильного ввода паролей.</span><span class="sxs-lookup"><span data-stu-id="4ed38-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="4ed38-107">Только после этого он сможет войти в свою учетную запись.</span><span class="sxs-lookup"><span data-stu-id="4ed38-107">They can sign in only after this second authentication factor has been satisfied.</span></span> 
  
<span data-ttu-id="4ed38-108">В этой статье описывается, как включить и протестировать проверку подлинности на основе текстовых сообщений для конкретной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="4ed38-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="4ed38-109">Настройка многофакторной проверки подлинности для учетной записи в тестовой среде Microsoft 365 Enterprise состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="4ed38-109">There are two phases to setting up multi-factor authentication for an account in your Microsoft 365 Enterprise test environment:</span></span>
  
1. <span data-ttu-id="4ed38-110">Создайте среду тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="4ed38-110">Create the Microsoft 365 Enterprise test environment.</span></span>
    
2. <span data-ttu-id="4ed38-111">Включение и проверка многофакторной проверки подлинности для учетной записи User 2.</span><span class="sxs-lookup"><span data-stu-id="4ed38-111">Enable and test multi-factor authentication for the User 2 account.</span></span>

3. <span data-ttu-id="4ed38-112">Включение и тестирование многофакторной проверки подлинности с помощью политики условного доступа (необязательно).</span><span class="sxs-lookup"><span data-stu-id="4ed38-112">Enable and test multi-factor authentication with a conditional access policy (optional).</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="4ed38-114">Перейдите к разделу [Test Lab Guide](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) для визуальной карты со всеми статьями руководства по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="4ed38-114">Go to [Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4ed38-115">Этап 1. Создание собственной тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="4ed38-115">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4ed38-116">Если вы только хотите протестировать многофакторную проверку подлинности в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="4ed38-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="4ed38-117">Если вы хотите протестировать многофакторную проверку подлинности на имитируемом предприятии, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="4ed38-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4ed38-118">Для тестирования многофакторной проверки подлинности не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="4ed38-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="4ed38-119">Она показана здесь лишь для того, чтобы вы могли проверить многофакторную проверку подлинности и поэкспериментировать с этим компонентом в типичной для организаций среде.</span><span class="sxs-lookup"><span data-stu-id="4ed38-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="4ed38-120">Этап 2. Включение и проверка многофакторной проверки подлинности для учетной записи User 2</span><span class="sxs-lookup"><span data-stu-id="4ed38-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="4ed38-121">Чтобы включить многофакторную проверку подлинности для учетной записи User 2, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="4ed38-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="4ed38-122">Откройте отдельный частный экземпляр браузера, перейдите в центр администрирования Microsoft 365 ( [https://portal.microsoft.com](https://portal.microsoft.com) ), а затем войдите с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="4ed38-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="4ed38-123">На панели навигации слева выберите элементы **Пользователи > Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-123">In the left navigation, click **Users > Active users**.</span></span>
    
3. <span data-ttu-id="4ed38-124">В области активные пользователи выберите **многофакторную проверку подлинности**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-124">In the Active users pane, click **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="4ed38-125">В списке выберите учетную запись **пользователя 2** .</span><span class="sxs-lookup"><span data-stu-id="4ed38-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="4ed38-126">В разделе **пользователь 2** в разделе **быстрые действия**нажмите кнопку **включить**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-126">In the **User 2** section, under **Quick steps**, click **Enable**.</span></span>
    
6. <span data-ttu-id="4ed38-127">В диалоговом окне **Сведения о включении многофакторной проверки подлинности** нажмите **Включить проверку Multi-Factor Auth**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-127">In the **About enabling multi-factor auth** dialog box, click **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="4ed38-128">В диалоговом окне **успешное обновление** нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-128">In the **Updates successful** dialog box, click **Close**.</span></span>
    
8. <span data-ttu-id="4ed38-129">На вкладке **центра администрирования Microsoft 365** щелкните значок учетной записи пользователя в правом верхнем углу, а затем нажмите **выйти**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-129">On the **Microsoft 365 admin center** tab, click the user account icon in the upper right, and then click **Sign out**.</span></span>
    
9. <span data-ttu-id="4ed38-130">Закройте окно браузера.</span><span class="sxs-lookup"><span data-stu-id="4ed38-130">Close your browser instance.</span></span>
   
<span data-ttu-id="4ed38-131">Чтобы настроить отправку текстового сообщения для проверки учетной записи User 2 и проверить ее, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="4ed38-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="4ed38-132">Откройте новый частный экземпляр браузера.</span><span class="sxs-lookup"><span data-stu-id="4ed38-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="4ed38-133">Перейдите на портал Office 365 ( [https://portal.office.com](https://portal.office.com) ) и войдите в систему, используя имя и пароль учетной записи пользователя 2.</span><span class="sxs-lookup"><span data-stu-id="4ed38-133">Go to the Office 365 portal ([https://portal.office.com](https://portal.office.com)) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="4ed38-134">После входа вам будет предложено настроить учетную запись для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="4ed38-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="4ed38-135">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-135">Click **Next**.</span></span>
    
4. <span data-ttu-id="4ed38-136">На странице **Дополнительная проверка безопасности**: </span><span class="sxs-lookup"><span data-stu-id="4ed38-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="4ed38-137">Выберите свою страну или регион.</span><span class="sxs-lookup"><span data-stu-id="4ed38-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="4ed38-138">Введите номер телефона, на который будут отправляться текстовые сообщения.</span><span class="sxs-lookup"><span data-stu-id="4ed38-138">Type phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="4ed38-139">В поле **метод**нажмите кнопку **отправить код по текстовому сообщению**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-139">In **Method**, click **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="4ed38-140">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-140">Click **Next**.</span></span>
    
6. <span data-ttu-id="4ed38-141">Введите код проверки из текстового сообщения, полученного на смартфон, и нажмите **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-141">Enter the verification code from the text message received on your smart phone, and then click **Verify**.</span></span>
    
7. <span data-ttu-id="4ed38-142">На странице **Шаг 3: сохраните существующие приложения** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-142">On the **Step 3: Keep your existing applications** page, click **Done**.</span></span>
    
8. <span data-ttu-id="4ed38-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span><span class="sxs-lookup"><span data-stu-id="4ed38-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="4ed38-144">Type the original password and a new password twice, and then click **Update password and sign in**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-144">Type the original password and a new password twice, and then click **Update password and sign in**.</span></span> <span data-ttu-id="4ed38-145">Record the new password in a secure location.</span><span class="sxs-lookup"><span data-stu-id="4ed38-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="4ed38-146">Вы должны увидеть портал Office для пользователя 2 на вкладке **Microsoft Office Главная** в браузере.</span><span class="sxs-lookup"><span data-stu-id="4ed38-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="4ed38-147">Этап 3: Включение и тестирование многофакторной проверки подлинности с помощью политики условного доступа</span><span class="sxs-lookup"><span data-stu-id="4ed38-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="4ed38-148">*Этот этап можно использовать только для тестовой среды Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4ed38-148">*This phase can only be used for a Microsoft 365 Enterprise test environment.*</span></span>

<span data-ttu-id="4ed38-149">На этом этапе включается многофакторная проверка подлинности для учетной записи пользователя 3 с использованием политики группы и условного доступа.</span><span class="sxs-lookup"><span data-stu-id="4ed38-149">In this phase you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="4ed38-150">Затем создайте новую группу с именем Мфаусерс и добавьте к ней учетную запись пользователя 3.</span><span class="sxs-lookup"><span data-stu-id="4ed38-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="4ed38-151">На вкладке **центра администрирования Microsoft 365** щелкните **группы** в левой области навигации, а затем щелкните **группы**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-151">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="4ed38-152">Нажмите кнопку **Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-152">Click **Add a group**.</span></span>
3. <span data-ttu-id="4ed38-153">В области **Выбор типа группы** выберите **Безопасность**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-153">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="4ed38-154">В области **Настройка основных принципов** нажмите кнопку **создать группу**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-154">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="4ed38-155">В области **Проверка и Добавление группы** введите **мфаусерс**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-155">In the **Review and finish adding group** pane, type **MFAUsers**, and then click **Next**.</span></span>
6. <span data-ttu-id="4ed38-156">В списке групп выберите группу **мфаусерс** .</span><span class="sxs-lookup"><span data-stu-id="4ed38-156">In the list of groups, click the **MFAUsers** group.</span></span>
7. <span data-ttu-id="4ed38-157">В области **мфаусерс** щелкните **элементы**, а затем щелкните **Просмотр всех элементов и управление ими**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-157">In the **MFAUsers** pane, click **Members**, and then click **View all and manage members**.</span></span>
8. <span data-ttu-id="4ed38-158">В области **мфаусерс** нажмите кнопку **Добавить участников**, выберите учетную запись **пользователя 3** , а затем нажмите кнопку **сохранить > закрыть > закрыть**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-158">In the **MFAUsers** pane, click **Add members**, select the **User 3** account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="4ed38-159">Затем создайте политику условного доступа, которая будет требовать многофакторную проверку подлинности для членов группы Мфаусерс.</span><span class="sxs-lookup"><span data-stu-id="4ed38-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="4ed38-160">На новой вкладке браузера перейдите в раздел [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="4ed38-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="4ed38-161">Щелкните элемент **Azure Active Directory > безопасность > условный доступ**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-161">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="4ed38-162">В области **Условный доступ – политики** щелкните **создать политику**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-162">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
4. <span data-ttu-id="4ed38-163">В области **создать** введите **MFA для учетных записей пользователей** в **поле имя**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-163">In the **New** pane, type **MFA for user accounts** in **Name**.</span></span>
5. <span data-ttu-id="4ed38-164">В разделе **назначения** выберите **Пользователи и группы**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-164">In the **Assignments** section, click **Users and groups**.</span></span>
6. <span data-ttu-id="4ed38-165">На вкладке **включить** в области **Пользователи и группы** щелкните **Выбор пользователей и групп > пользователи и группы > выбрать**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-165">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
7. <span data-ttu-id="4ed38-166">В области **Выбор** выберите группу **мфаусерс** и нажмите кнопку **выбрать > готово**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-166">In the **Select** pane, click the **MFAUsers** group, and then click **Select > Done**.</span></span>
8. <span data-ttu-id="4ed38-167">В разделе **элементы управления доступом** в области **создать** нажмите кнопку **предоставить**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-167">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="4ed38-168">В области **предоставление** выберите пункт **требовать многофакторную проверку подлинности**, а затем нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-168">In the **Grant** pane, click **Require multi-factor authentication**, and then click **Select**.</span></span>
10. <span data-ttu-id="4ed38-169">В области **создать** выберите пункт **включить политику**, а **затем нажмите кнопку** **создать**.</span><span class="sxs-lookup"><span data-stu-id="4ed38-169">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="4ed38-170">Закройте вкладки **портал Azure** и **центр администрирования Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="4ed38-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="4ed38-171">Чтобы проверить эту политику, выйдите из учетной записи пользователя 3 и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="4ed38-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="4ed38-172">Вам будет предложено настроить MFA.</span><span class="sxs-lookup"><span data-stu-id="4ed38-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="4ed38-173">В этом примере показано, что применяется политика Мфаусерс.</span><span class="sxs-lookup"><span data-stu-id="4ed38-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

<span data-ttu-id="4ed38-174">Чтобы получить сведения и ссылки для развертывания многофакторной проверки подлинности в рабочей среде, просмотрите этап " [Настройка многофакторной проверки подлинности](identity-secure-user-sign-ins.md#identity-mfa) " на этапе идентификации.</span><span class="sxs-lookup"><span data-stu-id="4ed38-174">See the [Set up multi-factor authentication](identity-secure-user-sign-ins.md#identity-mfa) step in the Identity phase for information and links to deploy multi-factor authentication in production.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="4ed38-175">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="4ed38-175">Next step</span></span>

<span data-ttu-id="4ed38-176">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="4ed38-176">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ed38-177">См. также</span><span class="sxs-lookup"><span data-stu-id="4ed38-177">See also</span></span>

[<span data-ttu-id="4ed38-178">Шаг 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="4ed38-178">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="4ed38-179">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="4ed38-179">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4ed38-180">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="4ed38-180">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="4ed38-181">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="4ed38-181">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
