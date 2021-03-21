---
title: Защита учетных записей глобального администратора в microsoft 365 для корпоративной тестовой среды
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
description: Используйте эти действия для защиты учетных записей глобального администратора в microsoft 365 для корпоративной тестовой среды.
ms.openlocfilehash: 3eab538b59e460857e2fa195aaacf51051f94d6b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918886"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="11872-103">Защита учетных записей глобального администратора в microsoft 365 для корпоративной тестовой среды</span><span class="sxs-lookup"><span data-stu-id="11872-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="11872-104">*Это руководство по тестовой лаборатории можно использовать только для Microsoft 365 для корпоративных тестовых сред.*</span><span class="sxs-lookup"><span data-stu-id="11872-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="11872-105">Вы можете предотвратить цифровые атаки на организацию, обеспечив безопасность учетных записей администратора.</span><span class="sxs-lookup"><span data-stu-id="11872-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> 

<span data-ttu-id="11872-106">В этой статье описывается использование политик условного доступа Azure Active Directory (Azure AD) для защиты учетных записей глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="11872-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="11872-107">Защита учетных записей глобального администратора в microsoft 365 для корпоративной тестовой среды включает два этапа:</span><span class="sxs-lookup"><span data-stu-id="11872-107">Protecting global administrator accounts in your Microsoft 365 for enterprise test environment involves two phases:</span></span>
- [<span data-ttu-id="11872-108">Этап 1. Создание microsoft 365 для корпоративной тестовой среды</span><span class="sxs-lookup"><span data-stu-id="11872-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="11872-109">Этап 2. Настройка политик условного доступа</span><span class="sxs-lookup"><span data-stu-id="11872-109">Phase 2: Configure conditional access policies</span></span>](#phase-2-configure-conditional-access-policies)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="11872-111">Чтобы получить визуальную карту для всех статей в стеке Руководство по корпоративной тестовой лаборатории Microsoft 365, перейдите в [Microsoft 365 для](../downloads/Microsoft365EnterpriseTLGStack.pdf)корпоративного руководства по тестовой лаборатории.</span><span class="sxs-lookup"><span data-stu-id="11872-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="11872-112">Этап 1. Создание microsoft 365 для корпоративной тестовой среды</span><span class="sxs-lookup"><span data-stu-id="11872-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="11872-113">Если вы хотите проверить глобальную защиту учетных записей администратора в легком режиме с минимальными требованиями, следуйте инструкциям в [базовой конфигурации Lightweight.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="11872-113">If you want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="11872-114">Если вы хотите протестировать глобальную защиту учетных записей администратора в смоделированном предприятии, следуйте инструкциям в сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="11872-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="11872-115">Тестирование глобальной защиты учетных записей администратора не требует имитации тестовой среды предприятия, которая включает смоделированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для служб домена Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="11872-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="11872-116">Он предоставляется здесь в качестве параметра, чтобы можно было протестировать глобальную защиту учетной записи администратора и поэкспериментировать с ней в среде, которая представляет типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="11872-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="11872-117">Этап 2. Настройка политик условного доступа</span><span class="sxs-lookup"><span data-stu-id="11872-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="11872-118">Сначала создайте новую учетную запись пользователя в качестве выделенного глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="11872-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="11872-119">На отдельной вкладке откройте [центр администрирования Microsoft 365.](https://admin.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="11872-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="11872-120">Выберите **Пользователей**  >  **Активные пользователи,** а затем **выберите Добавить пользователя**.</span><span class="sxs-lookup"><span data-stu-id="11872-120">Select **Users** > **Active users**, and then select **Add a user**.</span></span>
3. <span data-ttu-id="11872-121">В области **Добавить пользователя** введите **DedicatedAdmin** в поле **Имя,** Отображайте **имя** и **имя** пользователя.</span><span class="sxs-lookup"><span data-stu-id="11872-121">In the **Add user** pane, enter **DedicatedAdmin** in the **First name**, **Display name**, and **Username** boxes.</span></span>
4. <span data-ttu-id="11872-122">Выберите **пароль,** **выберите Дайте мне создать пароль,** а затем введите надежный пароль.</span><span class="sxs-lookup"><span data-stu-id="11872-122">Select **Password**, select **Let me create the password**, and then enter a strong password.</span></span> <span data-ttu-id="11872-123">Запись пароля для этой новой учетной записи в безопасном расположении.</span><span class="sxs-lookup"><span data-stu-id="11872-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="11872-124">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="11872-124">Select **Next**.</span></span>
6. <span data-ttu-id="11872-125">В области **Назначение лицензий на** продукт выберите **Microsoft 365 E5** и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="11872-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then select **Next**.</span></span>
7. <span data-ttu-id="11872-126">В области **Необязательных параметров** выберите **центр доступа Центра администрирования ролей** к  >    >  **глобальному администратору**  >  **Далее.**</span><span class="sxs-lookup"><span data-stu-id="11872-126">In the **Optional settings** pane, select **Roles** > **Admin center access** > **Global admin** > **Next**.</span></span>
8. <span data-ttu-id="11872-127">На области **Вы почти закончили,** выберите **добавление Готово,** а затем выберите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="11872-127">On the **You're almost done** pane, select **Finish adding**, and then select **Close**.</span></span>

<span data-ttu-id="11872-128">Далее создайте новую группу с именем GlobalAdmins и добавьте к ней учетную запись DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="11872-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="11872-129">На вкладке Центр администрирования **Microsoft 365** выберите **Группы** в левой навигации, а затем выберите **Группы.**</span><span class="sxs-lookup"><span data-stu-id="11872-129">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="11872-130">Выберите **Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="11872-130">Select **Add a group**.</span></span>
3. <span data-ttu-id="11872-131">В области **Выберите групповую группу** выберите **безопасность** и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="11872-131">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="11872-132">В области **Настройка базовых элементов** выберите **Создать** группу, а затем выберите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="11872-132">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="11872-133">В области **Просмотреть и завершить добавление групповой** области введите **GlobalAdmins** и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="11872-133">In the **Review and finish adding group** pane, enter **GlobalAdmins**, and then select **Next**.</span></span>
7. <span data-ttu-id="11872-134">В списке групп выберите **группу GlobalAdmins.**</span><span class="sxs-lookup"><span data-stu-id="11872-134">In the list of groups, select the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="11872-135">В области **GlobalAdmins** выберите **Членов,** а затем выберите Просмотр всех и **управление участниками.**</span><span class="sxs-lookup"><span data-stu-id="11872-135">In the **GlobalAdmins** pane, select **Members**, and then select **View all and manage members**.</span></span>
9. <span data-ttu-id="11872-136">В области **GlobalAdmins** выберите Добавить **участников,** выберите учетную запись **DedicatedAdmin** и глобальную учетную запись администратора, а затем выберите **Сохранить**  >  **закрыть**  >  **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="11872-136">In the **GlobalAdmins** pane, select **Add members**, select the **DedicatedAdmin** account and your global admin account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="11872-137">Далее создайте политики условного доступа, чтобы требовать многофакторной проверки подлинности для учетных записей глобального администратора и отказывать в проверке подлинности, если риск входной записи средний или высокий.</span><span class="sxs-lookup"><span data-stu-id="11872-137">Next, create conditional access policies to require multi-factor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="11872-138">Эта первая политика требует, чтобы все глобальные учетные записи администратора использовали MFA.</span><span class="sxs-lookup"><span data-stu-id="11872-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="11872-139">В новой вкладке браузера перейдите к [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="11872-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="11872-140">Нажмите **кнопку Azure Active Directory**  >  **Security**  >  **Conditional Access**.</span><span class="sxs-lookup"><span data-stu-id="11872-140">Click **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="11872-141">В области **условного доступа — политики** выберите базовую **политику: требуется MFA для администраторов (предварительный просмотр).**</span><span class="sxs-lookup"><span data-stu-id="11872-141">In the **Conditional access – Policies** pane, select **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="11872-142">В области **базовой политики** выберите **политику Use немедленно > Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="11872-142">In the **Baseline policy** pane, select **Use policy immediately > Save**.</span></span>

<span data-ttu-id="11872-143">Эта вторая политика блокирует доступ к глобальной проверке подлинности учетных записей администратора, если риск входной записи средний или высокий.</span><span class="sxs-lookup"><span data-stu-id="11872-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="11872-144">В области **условного доступа — политики выберите** новую **политику.**</span><span class="sxs-lookup"><span data-stu-id="11872-144">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
2. <span data-ttu-id="11872-145">В новой **области** введите **глобальные администраторы** в **Name**.</span><span class="sxs-lookup"><span data-stu-id="11872-145">In the **New** pane, enter **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="11872-146">В разделе **Назначения выберите** Пользователей **и группы.**</span><span class="sxs-lookup"><span data-stu-id="11872-146">In the **Assignments** section, select **Users and groups**.</span></span>
4. <span data-ttu-id="11872-147">На **вкладке Включить** области **Пользователи** и группы выберите **Выберите** пользователей и группы Пользователи  >  **и группы**  >  **Выберите**.</span><span class="sxs-lookup"><span data-stu-id="11872-147">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
5. <span data-ttu-id="11872-148">В области **Выбор** выберите группу **GlobalAdmins** и выберите **Выберите Сделано**  >  .</span><span class="sxs-lookup"><span data-stu-id="11872-148">In the **Select** pane, select the **GlobalAdmins** group, and then select **Select** > **Done**.</span></span>
6. <span data-ttu-id="11872-149">В разделе **Назначения выберите** **Условия**.</span><span class="sxs-lookup"><span data-stu-id="11872-149">In the **Assignments** section, select **Conditions**.</span></span>
7. <span data-ttu-id="11872-150">В области  **Условия** выберите риск для входов, выберите **Да** для **Настройки,** выберите высокой и средней, а затем **выберите Выберите** и **Сделать**.  </span><span class="sxs-lookup"><span data-stu-id="11872-150">In the **Conditions** pane, select **Sign-in risk**, select **Yes** for **Configure**, select **High** and **Medium**, and then select **Select** and **Done**.</span></span>
8. <span data-ttu-id="11872-151">В разделе **Элементы управления доступом** в **новой области** выберите **Grant**.</span><span class="sxs-lookup"><span data-stu-id="11872-151">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="11872-152">В области **Грант** выберите **блок-доступ** и выберите **Выберите**.</span><span class="sxs-lookup"><span data-stu-id="11872-152">In the **Grant** pane, select **Block access**, and then select **Select**.</span></span>
10. <span data-ttu-id="11872-153">В новой **области** выберите **политику "Включить",** а затем выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="11872-153">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="11872-154">Закрой **портал Azure** и **вкладки центра администрирования Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="11872-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="11872-155">Чтобы протестировать первую политику, вопишитесь и вопишитесь в учетную запись DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="11872-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="11872-156">Вы должны быть предложены для настройки MFA.</span><span class="sxs-lookup"><span data-stu-id="11872-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="11872-157">Это показывает, что применяется первая политика.</span><span class="sxs-lookup"><span data-stu-id="11872-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="11872-158">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="11872-158">Next step</span></span>

<span data-ttu-id="11872-159">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="11872-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="11872-160">См. также</span><span class="sxs-lookup"><span data-stu-id="11872-160">See also</span></span>

[<span data-ttu-id="11872-161">Дорожная карта удостоверений</span><span class="sxs-lookup"><span data-stu-id="11872-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="11872-162">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="11872-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="11872-163">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="11872-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="11872-164">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="11872-164">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)