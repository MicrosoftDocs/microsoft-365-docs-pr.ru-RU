---
title: Поддержка многофакторной проверки подлинности Microsoft 365 для предприятия тестовой среды
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
description: Настройка многофакторной проверки подлинности с помощью текстовых сообщений, отправленных на смарт-телефон в тестовой среде Microsoft 365 для предприятий.
ms.openlocfilehash: 4c59405c1ce59cafaf0309e2314e5cbfa4eb080a
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558446"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="07a01-103">Многофакторная проверка подлинности для тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="07a01-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="07a01-104">*Это руководство по лаборатории тестирования можно использовать как для Microsoft 365 Enterprise, так и для корпоративных тестовых сред Office 365.*</span><span class="sxs-lookup"><span data-stu-id="07a01-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="07a01-105">Для дополнительного уровня безопасности при входе в Microsoft 365 или любых служб или приложений, использующих клиент Azure AD для вашей подписки, можно включить многофакторную проверку подлинности Azure AD, которая требует больше имени пользователя и пароля, чтобы проверить учетную запись.</span><span class="sxs-lookup"><span data-stu-id="07a01-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure AD multi-factor authentication, which requires more than just a username and password to verify an account.</span></span>

<span data-ttu-id="07a01-106">При использовании многофакторной проверки подлинности пользователям необходимо подтвердить телефонный звонок, ввести код проверки, отправленный в текстовом сообщении, или проверить проверку подлинности с помощью приложения на смарт-телефонах после правильного ввода паролей.</span><span class="sxs-lookup"><span data-stu-id="07a01-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="07a01-107">Они могут войти только после того, как будет удовлетворен второй фактор проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="07a01-107">They can sign in only after this second authentication factor is satisfied.</span></span>
  
<span data-ttu-id="07a01-108">В этой статье описывается, как включить и протестировать проверку подлинности на основе текстовых сообщений для конкретной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="07a01-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="07a01-109">Настройка многофакторной проверки подлинности для учетной записи в тестовой среде Microsoft 365 для предприятий включает два этапа и третий дополнительный этап:</span><span class="sxs-lookup"><span data-stu-id="07a01-109">Setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment involves two phases and a third optional phase:</span></span>
- [<span data-ttu-id="07a01-110">Этап 1: создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="07a01-110">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="07a01-111">Этап 2. Включение и проверка многофакторной проверки подлинности для учетной записи User 2</span><span class="sxs-lookup"><span data-stu-id="07a01-111">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [<span data-ttu-id="07a01-112">Этап 3: Включение и тестирование многофакторной проверки подлинности с помощью политики условного доступа</span><span class="sxs-lookup"><span data-stu-id="07a01-112">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="07a01-114">Для отображения всех статей, посвященных руководству по лаборатории тестирования Microsoft 365 для предприятий, перейдите к разделу [руководство по лаборатории тестирования microsoft 365 для предприятия](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="07a01-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="07a01-115">Этап 1: создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="07a01-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="07a01-116">Если вы только хотите протестировать многофакторную проверку подлинности в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="07a01-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="07a01-117">Если вы хотите протестировать многофакторную проверку подлинности на имитируемом предприятии, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="07a01-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="07a01-118">Для тестирования многофакторной проверки подлинности не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="07a01-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="07a01-119">Она показана здесь лишь для того, чтобы вы могли проверить многофакторную проверку подлинности и поэкспериментировать с этим компонентом в типичной для организаций среде.</span><span class="sxs-lookup"><span data-stu-id="07a01-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="07a01-120">Этап 2. Включение и проверка многофакторной проверки подлинности для учетной записи User 2</span><span class="sxs-lookup"><span data-stu-id="07a01-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="07a01-121">Чтобы включить многофакторную проверку подлинности для учетной записи User 2, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="07a01-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="07a01-122">Откройте отдельный частный экземпляр браузера, перейдите в центр администрирования Microsoft 365 ( [https://portal.microsoft.com](https://portal.microsoft.com) ), а затем войдите с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="07a01-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="07a01-123">В области навигации слева выберите пункт **Пользователи**  >  **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="07a01-123">In the left navigation, select **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="07a01-124">В области активные пользователи выберите **многофакторную проверку подлинности**.</span><span class="sxs-lookup"><span data-stu-id="07a01-124">In the Active users pane, select **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="07a01-125">В списке выберите учетную запись **пользователя 2** .</span><span class="sxs-lookup"><span data-stu-id="07a01-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="07a01-126">В разделе **пользователь 2** в разделе **быстрые действия** выберите **включить**.</span><span class="sxs-lookup"><span data-stu-id="07a01-126">In the **User 2** section, under **Quick steps**, select **Enable**.</span></span>
    
6. <span data-ttu-id="07a01-127">В диалоговом окне **сведения о включении многофакторной проверки подлинности** выберите **включить многофакторную проверку подлинности**.</span><span class="sxs-lookup"><span data-stu-id="07a01-127">In the **About enabling multi-factor auth** dialog box, select **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="07a01-128">В диалоговом окне **успешное обновление** нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="07a01-128">In the **Updates successful** dialog box, select **Close**.</span></span>
    
8. <span data-ttu-id="07a01-129">На вкладке **центра администрирования Microsoft 365** выберите значок учетной записи пользователя в правом верхнем углу, а затем нажмите **выйти**.</span><span class="sxs-lookup"><span data-stu-id="07a01-129">On the **Microsoft 365 admin center** tab, select the user account icon in the upper right, and then select **Sign out**.</span></span>
    
9. <span data-ttu-id="07a01-130">Закройте окно браузера.</span><span class="sxs-lookup"><span data-stu-id="07a01-130">Close your browser instance.</span></span>
   
<span data-ttu-id="07a01-131">Чтобы настроить отправку текстового сообщения для проверки учетной записи User 2 и проверить ее, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="07a01-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="07a01-132">Откройте новый частный экземпляр браузера.</span><span class="sxs-lookup"><span data-stu-id="07a01-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="07a01-133">Перейдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) и войдите в систему, используя имя и пароль учетной записи пользователя 2.</span><span class="sxs-lookup"><span data-stu-id="07a01-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="07a01-134">После входа вам будет предложено настроить учетную запись для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="07a01-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="07a01-135">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="07a01-135">Select **Next**.</span></span>
    
4. <span data-ttu-id="07a01-136">На странице **Дополнительная проверка безопасности**: </span><span class="sxs-lookup"><span data-stu-id="07a01-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="07a01-137">Выберите свою страну или регион.</span><span class="sxs-lookup"><span data-stu-id="07a01-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="07a01-138">Введите телефонный номер смарт-телефона, который будет получать текстовые сообщения.</span><span class="sxs-lookup"><span data-stu-id="07a01-138">Enter the phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="07a01-139">В поле **метод** выберите **отправить код по текстовому сообщению**.</span><span class="sxs-lookup"><span data-stu-id="07a01-139">In **Method**, select **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="07a01-140">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="07a01-140">Select **Next**.</span></span>
    
6. <span data-ttu-id="07a01-141">Введите код проверки из текстового сообщения, полученного на смарт-телефоне, и нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="07a01-141">Enter the verification code from the text message received on your smart phone, and then select **Verify**.</span></span>
    
7. <span data-ttu-id="07a01-142">На странице **Шаг 3: сохраните существующие приложения** нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="07a01-142">On the **Step 3: Keep your existing applications** page, select **Done**.</span></span>
    
8. <span data-ttu-id="07a01-143">При первом входе в учетную запись User 2 вам будет предложено изменить пароль.</span><span class="sxs-lookup"><span data-stu-id="07a01-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="07a01-144">Введите исходный пароль и новый пароль дважды, а затем выберите пункт **Обновить пароль и войдите в систему**.</span><span class="sxs-lookup"><span data-stu-id="07a01-144">Enter the original password and a new password twice, and then select **Update password and sign in**.</span></span> <span data-ttu-id="07a01-145">Запишите новый пароль в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="07a01-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="07a01-146">Вы должны увидеть портал Office для пользователя 2 на вкладке **Microsoft Office Главная** в браузере.</span><span class="sxs-lookup"><span data-stu-id="07a01-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="07a01-147">Этап 3: Включение и тестирование многофакторной проверки подлинности с помощью политики условного доступа</span><span class="sxs-lookup"><span data-stu-id="07a01-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="07a01-148">*Этот этап можно использовать только для тестовой среды Microsoft 365 для предприятий.*</span><span class="sxs-lookup"><span data-stu-id="07a01-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="07a01-149">На этом этапе включается многофакторная проверка подлинности для учетной записи пользователя 3 с использованием политики группы и условного доступа.</span><span class="sxs-lookup"><span data-stu-id="07a01-149">In this phase, you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="07a01-150">Затем создайте новую группу с именем Мфаусерс и добавьте к ней учетную запись пользователя 3.</span><span class="sxs-lookup"><span data-stu-id="07a01-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="07a01-151">На вкладке **центра администрирования Microsoft 365** выберите **группы** в левой области навигации, а затем выберите пункт **группы**.</span><span class="sxs-lookup"><span data-stu-id="07a01-151">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="07a01-152">Нажмите кнопку **Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="07a01-152">Select **Add a group**.</span></span>
3. <span data-ttu-id="07a01-153">В области **Выбор типа группы** выберите **Безопасность**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="07a01-153">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="07a01-154">В области **Настройка основных принципов** выберите **создать группу**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="07a01-154">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="07a01-155">В области **Проверка и Добавление группы** введите **мфаусерс**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="07a01-155">In the **Review and finish adding group** pane, enter **MFAUsers**, and then select **Next**.</span></span>
6. <span data-ttu-id="07a01-156">В списке групп выберите группу **мфаусерс** .</span><span class="sxs-lookup"><span data-stu-id="07a01-156">In the list of groups, select the **MFAUsers** group.</span></span>
7. <span data-ttu-id="07a01-157">В области **мфаусерс** выберите **элемент элементы**, а затем нажмите кнопку **Просмотр всех элементов и управление ими**.</span><span class="sxs-lookup"><span data-stu-id="07a01-157">In the **MFAUsers** pane, select **Members**, and then select **View all and manage members**.</span></span>
8. <span data-ttu-id="07a01-158">В области **мфаусерс** выберите **Добавить участников**, выберите учетную запись **пользователя 3** , а затем нажмите кнопку **сохранить**  >  **Закрыть**  >  **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="07a01-158">In the **MFAUsers** pane, select **Add members**, select the **User 3** account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="07a01-159">Затем создайте политику условного доступа, которая будет требовать многофакторную проверку подлинности для членов группы Мфаусерс.</span><span class="sxs-lookup"><span data-stu-id="07a01-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="07a01-160">На новой вкладке браузера перейдите в раздел [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="07a01-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="07a01-161">Выберите **Azure Active Directory** пункт "  >  **Security**  >  **Условный доступ к** системе безопасности Azure Active Directory".</span><span class="sxs-lookup"><span data-stu-id="07a01-161">Select **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="07a01-162">В области **Условный доступ — политики** выберите **создать политику**.</span><span class="sxs-lookup"><span data-stu-id="07a01-162">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
4. <span data-ttu-id="07a01-163">В области **создать** введите **MFA для учетных записей пользователей** в поле **имя** .</span><span class="sxs-lookup"><span data-stu-id="07a01-163">In the **New** pane, enter **MFA for user accounts** in the **Name** box.</span></span>
5. <span data-ttu-id="07a01-164">В разделе **назначения** выберите **Пользователи и группы**.</span><span class="sxs-lookup"><span data-stu-id="07a01-164">In the **Assignments** section, select **Users and groups**.</span></span>
6. <span data-ttu-id="07a01-165">На вкладке **включить** в области **Пользователи и группы** выберите пункт **Выбор пользователей и групп**,  >  **Users and groups**  >  **Выбор** пользователей и групп.</span><span class="sxs-lookup"><span data-stu-id="07a01-165">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
7. <span data-ttu-id="07a01-166">В области **Выбор** выберите группу **мфаусерс** и нажмите **кнопку Выбрать**  >  **Готово**.</span><span class="sxs-lookup"><span data-stu-id="07a01-166">In the **Select** pane, select the **MFAUsers** group, and then select **Select** > **Done**.</span></span>
8. <span data-ttu-id="07a01-167">В разделе **элементы управления доступом** в области **создать** нажмите кнопку **предоставить**.</span><span class="sxs-lookup"><span data-stu-id="07a01-167">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="07a01-168">В области **предоставление** выберите пункт **требовать многофакторную проверку подлинности** и нажмите **кнопку Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="07a01-168">In the **Grant** pane, select **Require multi-factor authentication**, and then select **Select**.</span></span>
10. <span data-ttu-id="07a01-169">В области **создать** выберите Включить, **On** чтобы **включить политику**, а затем нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="07a01-169">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="07a01-170">Закройте вкладки **портал Azure** и **центр администрирования Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="07a01-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="07a01-171">Чтобы проверить эту политику, выйдите из учетной записи пользователя 3 и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="07a01-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="07a01-172">Вам будет предложено настроить MFA.</span><span class="sxs-lookup"><span data-stu-id="07a01-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="07a01-173">В этом примере показано, что применяется политика Мфаусерс.</span><span class="sxs-lookup"><span data-stu-id="07a01-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="07a01-174">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="07a01-174">Next step</span></span>

<span data-ttu-id="07a01-175">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="07a01-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="07a01-176">См. также</span><span class="sxs-lookup"><span data-stu-id="07a01-176">See also</span></span>

[<span data-ttu-id="07a01-177">Схема удостоверений</span><span class="sxs-lookup"><span data-stu-id="07a01-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="07a01-178">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="07a01-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="07a01-179">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="07a01-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="07a01-180">Microsoft 365 для корпоративных документов</span><span class="sxs-lookup"><span data-stu-id="07a01-180">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
