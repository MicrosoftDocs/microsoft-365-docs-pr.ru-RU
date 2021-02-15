---
title: Многофакторная проверка подлинности в тестовой среде Microsoft 365 для предприятий
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
description: Настройте многофакторную проверку подлинности с помощью текстовых сообщений, отправленных на смартфон в тестовой среде Microsoft 365 для предприятий.
ms.openlocfilehash: 4c59405c1ce59cafaf0309e2314e5cbfa4eb080a
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558446"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="5c8fe-103">Многофакторная проверка подлинности для тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="5c8fe-103">Multi-factor authentication for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="5c8fe-104">*Это руководство по лаборатории тестирования можно использовать для тестовых сред Microsoft 365 для предприятий и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="5c8fe-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="5c8fe-105">Чтобы обеспечить дополнительный уровень безопасности при входе в Microsoft 365 или любую службу или приложение, использующее клиент Azure AD для подписки, вы можете включить многофакторную проверку подлинности Azure AD, для проверки учетной записи которой требуется не только имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-105">For an additional level of security for signing in to Microsoft 365 or any service or application that uses the Azure AD tenant for your subscription, you can enable Azure AD multi-factor authentication, which requires more than just a username and password to verify an account.</span></span>

<span data-ttu-id="5c8fe-106">При многофакторной проверке подлинности пользователи должны подтвердить телефонный звонок, ввести код проверки, отправленный в текстовом сообщении, или проверить проверку подлинности с помощью приложения на смартфонах после правильного ввода паролей.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-106">With multi-factor authentication, users are required to acknowledge a phone call, type a verification code sent in a text message, or verify the authentication with an app on their smart phones after correctly entering their passwords.</span></span> <span data-ttu-id="5c8fe-107">Они могут войти только после того, как этот второй фактор проверки подлинности будет удовлетворены.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-107">They can sign in only after this second authentication factor is satisfied.</span></span>
  
<span data-ttu-id="5c8fe-108">В этой статье описывается, как включить и протестировать проверку подлинности на основе текстовых сообщений для определенной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-108">This article describes how to enable and test text message-based authentication for a specific user account.</span></span>
  
<span data-ttu-id="5c8fe-109">Настройка многофакторной проверки подлинности для учетной записи в тестовой среде Microsoft 365 для предприятий состоит из двух этапов и третьего дополнительного этапа:</span><span class="sxs-lookup"><span data-stu-id="5c8fe-109">Setting up multi-factor authentication for an account in your Microsoft 365 for enterprise test environment involves two phases and a third optional phase:</span></span>
- [<span data-ttu-id="5c8fe-110">Этап 1. Создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="5c8fe-110">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="5c8fe-111">Этап 2. Включение и проверка многофакторной проверки подлинности для учетной записи User 2</span><span class="sxs-lookup"><span data-stu-id="5c8fe-111">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [<span data-ttu-id="5c8fe-112">Этап 3. Включить и протестировать многофакторную проверку подлинности с помощью политики условного доступа</span><span class="sxs-lookup"><span data-stu-id="5c8fe-112">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="5c8fe-114">Чтобы получить визуальную карту со всеми статьями в руководстве по лаборатории тестирования Microsoft 365 для предприятий, перейдите в стек руководств по лаборатории тестирования [Microsoft 365 для предприятий.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="5c8fe-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="5c8fe-115">Этап 1. Создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="5c8fe-115">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="5c8fe-116">Если вы хотите просто протестировать многофакторную проверку подлинности с минимальными требованиями, следуйте инструкциям в базовой конфигурации [lightweight.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="5c8fe-116">If you just want to test multi-factor authentication in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="5c8fe-117">Если вы хотите протестировать многофакторную проверку подлинности на имитированном предприятии, следуйте инструкциям в сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="5c8fe-117">If you want to test multi-factor authentication in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5c8fe-118">Для тестирования многофакторной проверки подлинности не требуется тестовая среда имитации предприятия, которая включает имитированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="5c8fe-118">Testing multi-factor authentication does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="5c8fe-119">Она показана здесь лишь для того, чтобы вы могли проверить многофакторную проверку подлинности и поэкспериментировать с этим компонентом в типичной для организаций среде.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-119">It is provided here as an option so that you can test multi-factor authentication and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a><span data-ttu-id="5c8fe-120">Этап 2. Включение и проверка многофакторной проверки подлинности для учетной записи User 2</span><span class="sxs-lookup"><span data-stu-id="5c8fe-120">Phase 2: Enable and test multi-factor authentication for the User 2 account</span></span>

<span data-ttu-id="5c8fe-121">Чтобы включить многофакторную проверку подлинности для учетной записи User 2, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="5c8fe-121">Enable multi-factor authentication for the User 2 account with these steps:</span></span>
  
1. <span data-ttu-id="5c8fe-122">Откройте отдельный частный экземпляр браузера, перейдите в Центр администрирования Microsoft 365 (), а затем войдите с помощью учетной записи [https://portal.microsoft.com](https://portal.microsoft.com) глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-122">Open a separate, private instance of your browser, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)), and then sign in with your global administrator account.</span></span>
    
2. <span data-ttu-id="5c8fe-123">В области навигации слева выберите **"Пользователи**  >  **активные пользователи".**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-123">In the left navigation, select **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="5c8fe-124">В области "Активные пользователи" выберите **многофакторную проверку подлинности.**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-124">In the Active users pane, select **Multi-factor authentication**.</span></span>
    
4. <span data-ttu-id="5c8fe-125">В списке выберите учетную **запись User 2.**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-125">In the list, select the **User 2** account.</span></span>
    
5. <span data-ttu-id="5c8fe-126">В разделе **"Пользователь 2" в** разделе **"Быстрые действия"** выберите **"Включить".**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-126">In the **User 2** section, under **Quick steps**, select **Enable**.</span></span>
    
6. <span data-ttu-id="5c8fe-127">В **диалоговом окне "Включение многофакторной auth"** выберите "Включить **многофакторную auth".**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-127">In the **About enabling multi-factor auth** dialog box, select **Enable multi-factor auth**.</span></span>
    
7. <span data-ttu-id="5c8fe-128">В **диалоговом окне "Обновления** успешно" выберите **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-128">In the **Updates successful** dialog box, select **Close**.</span></span>
    
8. <span data-ttu-id="5c8fe-129">На **вкладке "Центр администрирования Microsoft 365"** выберите значок учетной записи пользователя в правом верхнем верхнем окте, а затем выберите **"Выйти".**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-129">On the **Microsoft 365 admin center** tab, select the user account icon in the upper right, and then select **Sign out**.</span></span>
    
9. <span data-ttu-id="5c8fe-130">Закройте окно браузера.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-130">Close your browser instance.</span></span>
   
<span data-ttu-id="5c8fe-131">Чтобы настроить отправку текстового сообщения для проверки учетной записи User 2 и проверить ее, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="5c8fe-131">Complete the configuration for the User 2 account to use a text message for validation and test it with these steps:</span></span>
  
1. <span data-ttu-id="5c8fe-132">Откройте новый частный экземпляр браузера.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-132">Open a new, private instance of your browser.</span></span>
    
2. <span data-ttu-id="5c8fe-133">Перейдите в [Центр администрирования Microsoft 365](https://admin.microsoft.com) и войдите с помощью имени и пароля учетной записи User 2.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-133">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with the User 2 account name and password.</span></span>
    
3. <span data-ttu-id="5c8fe-134">После этого вам будет предложено настроить учетную запись для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-134">After signing in, you are prompted to set up the account for more information.</span></span> <span data-ttu-id="5c8fe-135">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-135">Select **Next**.</span></span>
    
4. <span data-ttu-id="5c8fe-136">На странице **Дополнительная проверка безопасности**: </span><span class="sxs-lookup"><span data-stu-id="5c8fe-136">On the **Additional security verification** page:</span></span>
    
   - <span data-ttu-id="5c8fe-137">Выберите свою страну или регион.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-137">Select your country or region.</span></span>
    
   - <span data-ttu-id="5c8fe-138">Введите номер телефона смартфона, который будет получать текстовые сообщения.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-138">Enter the phone number of the smart phone that will receive text messages.</span></span>
    
   - <span data-ttu-id="5c8fe-139">In **Method**, select **Send me a code by text message**.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-139">In **Method**, select **Send me a code by text message**.</span></span>
    
5. <span data-ttu-id="5c8fe-140">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-140">Select **Next**.</span></span>
    
6. <span data-ttu-id="5c8fe-141">Введите код проверки из текстового сообщения, полученного на смартфоне, а затем выберите **"Проверить".**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-141">Enter the verification code from the text message received on your smart phone, and then select **Verify**.</span></span>
    
7. <span data-ttu-id="5c8fe-142">На **шаге 3 "Сохранение существующих приложений"** выберите **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-142">On the **Step 3: Keep your existing applications** page, select **Done**.</span></span>
    
8. <span data-ttu-id="5c8fe-143">При первом входе в учетную запись User 2 вам будет предложено изменить пароль.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-143">If this is the first time you signed in with the User 2 account, you are prompted to change the password.</span></span> <span data-ttu-id="5c8fe-144">Введите исходный пароль и новый пароль дважды, а затем выберите "Обновить **пароль" и войдите.**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-144">Enter the original password and a new password twice, and then select **Update password and sign in**.</span></span> <span data-ttu-id="5c8fe-145">Запишите новый пароль в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-145">Record the new password in a secure location.</span></span>
    
    <span data-ttu-id="5c8fe-146">Вы увидите портал Office для пользователя 2 на вкладке Microsoft Office **"Главная"** браузера.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-146">You should see the Office portal for User 2 on the **Microsoft Office Home** tab of your browser.</span></span>

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a><span data-ttu-id="5c8fe-147">Этап 3. Включить и протестировать многофакторную проверку подлинности с помощью политики условного доступа</span><span class="sxs-lookup"><span data-stu-id="5c8fe-147">Phase 3: Enable and test multi-factor authentication with a conditional access policy</span></span>

<span data-ttu-id="5c8fe-148">*Этот этап можно использовать только для тестовой среды Microsoft 365 для предприятий.*</span><span class="sxs-lookup"><span data-stu-id="5c8fe-148">*This phase can only be used for a Microsoft 365 for enterprise test environment.*</span></span>

<span data-ttu-id="5c8fe-149">На этом этапе включается многофакторная проверка подлинности для учетной записи User 3 с помощью группы и политики условного доступа.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-149">In this phase, you enable multi-factor authentication for the User 3 account using a group and a conditional access policy.</span></span>

<span data-ttu-id="5c8fe-150">Затем создайте группу MFAUsers и добавьте в нее учетную запись User 3.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-150">Next, create a new group named MFAUsers and add the User 3 account to it.</span></span>

1. <span data-ttu-id="5c8fe-151">На **вкладке Центра администрирования Microsoft 365** выберите **"Группы"** в области навигации слева, а затем выберите **"Группы".**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-151">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="5c8fe-152">Выберите **"Добавить группу"**.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-152">Select **Add a group**.</span></span>
3. <span data-ttu-id="5c8fe-153">В области **"Выбор типа** группы" выберите "Безопасность" **и** выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-153">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="5c8fe-154">В области **"Настройка основ" выберите** "Создать **группу",** а затем выберите **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-154">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="5c8fe-155">В области **просмотра и завершения добавления группы** введите **MFAUsers** и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-155">In the **Review and finish adding group** pane, enter **MFAUsers**, and then select **Next**.</span></span>
6. <span data-ttu-id="5c8fe-156">В списке групп выберите группу **MFAUsers.**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-156">In the list of groups, select the **MFAUsers** group.</span></span>
7. <span data-ttu-id="5c8fe-157">В области **MFAUsers** выберите "Члены", а затем выберите **"Просмотреть все и управлять участниками".**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-157">In the **MFAUsers** pane, select **Members**, and then select **View all and manage members**.</span></span>
8. <span data-ttu-id="5c8fe-158">В области **MFAUsers** выберите "Добавить участников", выберите учетную запись **"Пользователь 3",** а затем выберите "Сохранить   >    >  **закрыть".**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-158">In the **MFAUsers** pane, select **Add members**, select the **User 3** account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="5c8fe-159">Затем создайте политику условного доступа, чтобы требовать многофакторную проверку подлинности для членов группы MFAUsers.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-159">Next, create a conditional access policy to require multifactor authentication for members of the MFAUsers group.</span></span>

1. <span data-ttu-id="5c8fe-160">На новой вкладке браузера перейдите к [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="5c8fe-160">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="5c8fe-161">Выберите **условный доступ безопасности Azure Active Directory.**  >    >  </span><span class="sxs-lookup"><span data-stu-id="5c8fe-161">Select **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="5c8fe-162">В области **"Условный доступ — политики"** выберите **"Новая политика".**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-162">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
4. <span data-ttu-id="5c8fe-163">В области **"Новая"** введите **MFA для учетных** записей пользователей в поле **"Имя".**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-163">In the **New** pane, enter **MFA for user accounts** in the **Name** box.</span></span>
5. <span data-ttu-id="5c8fe-164">В разделе **"Назначения"** выберите **"Пользователи и группы".**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-164">In the **Assignments** section, select **Users and groups**.</span></span>
6. <span data-ttu-id="5c8fe-165">На **вкладке "Включить"** **области** "Пользователи и группы" выберите "Выбор пользователей и   >  **групп" "Выбор пользователей и**  >  **групп".**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-165">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
7. <span data-ttu-id="5c8fe-166">В области **"Выбор"** выберите группу **MFAUsers,** а затем выберите   >  **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-166">In the **Select** pane, select the **MFAUsers** group, and then select **Select** > **Done**.</span></span>
8. <span data-ttu-id="5c8fe-167">В разделе **элементов управления Access** на **новой** области выберите **"Предоставить".**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-167">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="5c8fe-168">В области **предоставления** выберите **"Требовать** многофакторную проверку подлинности" и выберите **"Выбрать".**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-168">In the **Grant** pane, select **Require multi-factor authentication**, and then select **Select**.</span></span>
10. <span data-ttu-id="5c8fe-169">В области **"Создать"** выберите **"Включить"** для политики **"Включить",** а затем выберите **"Создать".**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-169">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="5c8fe-170">**Закроем портал Azure** и вкладки Центра администрирования Microsoft **365.**</span><span class="sxs-lookup"><span data-stu-id="5c8fe-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="5c8fe-171">Чтобы протестировать эту политику, вы сможете выйти из нее и войти с помощью учетной записи User 3.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-171">To test this policy, sign out and sign in with the User 3 account.</span></span> <span data-ttu-id="5c8fe-172">Вам будет предложено настроить MFA.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-172">You should be prompted to configure MFA.</span></span> <span data-ttu-id="5c8fe-173">Это демонстрирует, что применяется политика MFAUsers.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-173">This demonstrates that the MFAUsers policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="5c8fe-174">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="5c8fe-174">Next step</span></span>

<span data-ttu-id="5c8fe-175">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="5c8fe-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c8fe-176">См. также</span><span class="sxs-lookup"><span data-stu-id="5c8fe-176">See also</span></span>

[<span data-ttu-id="5c8fe-177">План удостоверений</span><span class="sxs-lookup"><span data-stu-id="5c8fe-177">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="5c8fe-178">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="5c8fe-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5c8fe-179">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="5c8fe-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5c8fe-180">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="5c8fe-180">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
