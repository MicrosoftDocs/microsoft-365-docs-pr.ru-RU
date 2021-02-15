---
title: Защита учетных записей глобальных администраторов в тестовой среде Microsoft 365 для предприятий
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
description: С помощью этих действий можно защитить учетные записи глобальных администраторов в тестовой среде Microsoft 365 для предприятий.
ms.openlocfilehash: 1ae04e4761ed86e087e647464ad522466ed6abef
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487640"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="fd7c6-103">Защита учетных записей глобальных администраторов в тестовой среде Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="fd7c6-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="fd7c6-104">*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для корпоративных тестовых сред.*</span><span class="sxs-lookup"><span data-stu-id="fd7c6-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="fd7c6-105">Вы можете предотвращать цифровые атаки на вашу организацию, обеспечивая максимально надежную защиту учетных записей администраторов.</span><span class="sxs-lookup"><span data-stu-id="fd7c6-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> 

<span data-ttu-id="fd7c6-106">В этой статье описывается использование политик условного доступа Azure Active Directory (Azure AD) для защиты учетных записей глобальных администраторов.</span><span class="sxs-lookup"><span data-stu-id="fd7c6-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="fd7c6-107">Защита учетных записей глобальных администраторов в тестовой среде Microsoft 365 для предприятий состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="fd7c6-107">Protecting global administrator accounts in your Microsoft 365 for enterprise test environment involves two phases:</span></span>
- [<span data-ttu-id="fd7c6-108">Этап 1. Создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="fd7c6-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="fd7c6-109">Этап 2. Настройка политик условного доступа</span><span class="sxs-lookup"><span data-stu-id="fd7c6-109">Phase 2: Configure conditional access policies</span></span>](#phase-2-configure-conditional-access-policies)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="fd7c6-111">Чтобы получить визуальную карту всех статей в руководстве по лаборатории тестирования Microsoft 365 для предприятий, перейдите в стек руководств по лаборатории тестирования [Microsoft 365 для предприятий.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="fd7c6-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="fd7c6-112">Этап 1. Создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="fd7c6-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="fd7c6-113">Если вы хотите протестировать защиту учетных записей глобального администратора облегченным способом с минимальными требованиями, следуйте инструкциям в базовой конфигурации [lightweight.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="fd7c6-113">If you want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="fd7c6-114">Если вы хотите протестировать защиту учетных записей глобального администратора на имитированном предприятии, следуйте инструкциям в сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="fd7c6-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="fd7c6-115">Для тестирования защиты учетных записей глобального администратора не требуется тестовая среда имитированной организации, которая включает имитированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="fd7c6-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="fd7c6-116">Она предоставляется здесь в качестве варианта, чтобы вы могли протестировать защиту учетной записи глобального администратора и поэкспериментировать с ней в типичной для организации среде.</span><span class="sxs-lookup"><span data-stu-id="fd7c6-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="fd7c6-117">Этап 2. Настройка политик условного доступа</span><span class="sxs-lookup"><span data-stu-id="fd7c6-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="fd7c6-118">Сначала создайте новую учетную запись пользователя в качестве выделенного глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="fd7c6-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="fd7c6-119">На отдельной вкладке откройте [Центр администрирования Microsoft 365.](https://admin.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="fd7c6-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="fd7c6-120">Выберите   >  **"Пользователи активные пользователи",** а затем выберите **"Добавить пользователя".**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-120">Select **Users** > **Active users**, and then select **Add a user**.</span></span>
3. <span data-ttu-id="fd7c6-121">В области **"Добавить** пользователя" введите **DedicatedAdmin** в полях **"Имя",**"Отображаемая **имя"** и **"Имя пользователя".**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-121">In the **Add user** pane, enter **DedicatedAdmin** in the **First name**, **Display name**, and **Username** boxes.</span></span>
4. <span data-ttu-id="fd7c6-122">Выберите **"Пароль",** **"Позволить мне создать пароль",** а затем введите надежный пароль.</span><span class="sxs-lookup"><span data-stu-id="fd7c6-122">Select **Password**, select **Let me create the password**, and then enter a strong password.</span></span> <span data-ttu-id="fd7c6-123">Зафиксировать пароль для этой новой учетной записи в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="fd7c6-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="fd7c6-124">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fd7c6-124">Select **Next**.</span></span>
6. <span data-ttu-id="fd7c6-125">В области **"Назначение лицензий на** продукты" выберите **Microsoft 365 E5** и затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then select **Next**.</span></span>
7. <span data-ttu-id="fd7c6-126">В области **"Необязательные параметры"** выберите **"Центр** администрирования  >  **ролей" "Глобальный**  >  **администратор**  >  **далее".**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-126">In the **Optional settings** pane, select **Roles** > **Admin center access** > **Global admin** > **Next**.</span></span>
8. <span data-ttu-id="fd7c6-127">On the **You're almost done** pane, select **Finish adding,** and then select **Close**.</span><span class="sxs-lookup"><span data-stu-id="fd7c6-127">On the **You're almost done** pane, select **Finish adding**, and then select **Close**.</span></span>

<span data-ttu-id="fd7c6-128">Затем создайте группу GlobalAdmins и добавьте в нее учетную запись DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="fd7c6-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="fd7c6-129">На **вкладке Центра администрирования Microsoft 365** выберите **"Группы"** в области навигации слева, а затем выберите **"Группы".**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-129">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="fd7c6-130">Выберите **"Добавить группу"**.</span><span class="sxs-lookup"><span data-stu-id="fd7c6-130">Select **Add a group**.</span></span>
3. <span data-ttu-id="fd7c6-131">В области **"Выбор типа** группы" выберите "Безопасность" **и** выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-131">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="fd7c6-132">В области **"Настройка основ" выберите** "Создать **группу",** а затем выберите **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-132">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="fd7c6-133">В области **просмотра и завершения добавления группы** введите **GlobalAdmins** и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-133">In the **Review and finish adding group** pane, enter **GlobalAdmins**, and then select **Next**.</span></span>
7. <span data-ttu-id="fd7c6-134">В списке групп выберите группу **GlobalAdmins.**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-134">In the list of groups, select the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="fd7c6-135">В области **GlobalAdmins** выберите **"Члены",** а затем выберите **"Просмотреть все и управлять участниками".**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-135">In the **GlobalAdmins** pane, select **Members**, and then select **View all and manage members**.</span></span>
9. <span data-ttu-id="fd7c6-136">В области **GlobalAdmins** выберите "Добавить участников", выберите учетную запись **DedicatedAdmin** и учетную запись глобального администратора, а затем выберите "Сохранить    >    >  **закрыть".**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-136">In the **GlobalAdmins** pane, select **Add members**, select the **DedicatedAdmin** account and your global admin account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="fd7c6-137">Затем создайте политики условного доступа, чтобы требовать многофакторную проверку подлинности для учетных записей глобальных администраторов и запретить проверку подлинности, если риск для входов средний или высокий.</span><span class="sxs-lookup"><span data-stu-id="fd7c6-137">Next, create conditional access policies to require multi-factor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="fd7c6-138">Для этой первой политики требуется, чтобы все учетные записи глобальных администраторов использовали MFA.</span><span class="sxs-lookup"><span data-stu-id="fd7c6-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="fd7c6-139">На новой вкладке браузера перейдите к [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="fd7c6-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="fd7c6-140">Щелкните **условный доступ безопасности Azure Active Directory.**  >    >  </span><span class="sxs-lookup"><span data-stu-id="fd7c6-140">Click **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="fd7c6-141">В области **"Условный доступ** — политики" выберите базовую политику: требовать многофакторную оценку для **администраторов (предварительная версия).**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-141">In the **Conditional access – Policies** pane, select **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="fd7c6-142">В области **"Базовая** политика" выберите "Использовать **политику немедленно> сохранить.**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-142">In the **Baseline policy** pane, select **Use policy immediately > Save**.</span></span>

<span data-ttu-id="fd7c6-143">Эта вторая политика блокирует доступ к проверке подлинности учетной записи глобального администратора, если риск для входов средний или высокий.</span><span class="sxs-lookup"><span data-stu-id="fd7c6-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="fd7c6-144">В области **"Условный доступ — политики"** выберите **"Новая политика".**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-144">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
2. <span data-ttu-id="fd7c6-145">В области **"Новая"** **введите "Глобальные администраторы" в** **"Имя".**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-145">In the **New** pane, enter **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="fd7c6-146">В разделе **"Назначения"** выберите **"Пользователи и группы".**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-146">In the **Assignments** section, select **Users and groups**.</span></span>
4. <span data-ttu-id="fd7c6-147">На **вкладке "Включить"** **области** "Пользователи и группы" выберите "Выбор пользователей и   >  **групп" "Выбор пользователей и**  >  **групп".**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-147">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
5. <span data-ttu-id="fd7c6-148">В области **"Выбор"** выберите группу **GlobalAdmins** и выберите   >  **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-148">In the **Select** pane, select the **GlobalAdmins** group, and then select **Select** > **Done**.</span></span>
6. <span data-ttu-id="fd7c6-149">В разделе **"Назначения"** выберите **"Условия".**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-149">In the **Assignments** section, select **Conditions**.</span></span>
7. <span data-ttu-id="fd7c6-150"> В области **условий** выберите риск для  **входов,** выберите "Да" для **настройки,** выберите "Высокий" и "Средний", а затем выберите **"Выбрать"** и **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-150">In the **Conditions** pane, select **Sign-in risk**, select **Yes** for **Configure**, select **High** and **Medium**, and then select **Select** and **Done**.</span></span>
8. <span data-ttu-id="fd7c6-151">В разделе **элементов управления Access** на **новой** области выберите **"Предоставить".**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-151">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="fd7c6-152">В области **предоставления** выберите **блокирование доступа,** а затем выберите **"Выбрать".**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-152">In the **Grant** pane, select **Block access**, and then select **Select**.</span></span>
10. <span data-ttu-id="fd7c6-153">В области **"Создать"** выберите **"Включить"** для политики **"Включить",** а затем выберите **"Создать".**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-153">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="fd7c6-154">**Закроем портал Azure** и вкладки Центра администрирования Microsoft **365.**</span><span class="sxs-lookup"><span data-stu-id="fd7c6-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="fd7c6-155">Чтобы протестировать первую политику, выпишитесь и во sign in с помощью учетной записи DedicatedAdmin.</span><span class="sxs-lookup"><span data-stu-id="fd7c6-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="fd7c6-156">Вам будет предложено настроить MFA.</span><span class="sxs-lookup"><span data-stu-id="fd7c6-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="fd7c6-157">Это показывает, что применяется первая политика.</span><span class="sxs-lookup"><span data-stu-id="fd7c6-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="fd7c6-158">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="fd7c6-158">Next step</span></span>

<span data-ttu-id="fd7c6-159">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="fd7c6-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd7c6-160">См. также</span><span class="sxs-lookup"><span data-stu-id="fd7c6-160">See also</span></span>

[<span data-ttu-id="fd7c6-161">План удостоверений</span><span class="sxs-lookup"><span data-stu-id="fd7c6-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="fd7c6-162">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="fd7c6-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="fd7c6-163">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="fd7c6-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="fd7c6-164">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="fd7c6-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
