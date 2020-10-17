---
title: Защита учетных записей глобального администратора в тестовой среде Microsoft 365 для предприятий
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
description: Используйте следующие действия для защиты учетных записей глобального администратора в тестовой среде Microsoft 365 для предприятия.
ms.openlocfilehash: 1ae04e4761ed86e087e647464ad522466ed6abef
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487640"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7f7fc-103">Защита учетных записей глобального администратора в тестовой среде Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="7f7fc-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7f7fc-104">*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для тестовых сред предприятия.*</span><span class="sxs-lookup"><span data-stu-id="7f7fc-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="7f7fc-105">Вы можете предотвратить цифровые атаки в Организации, убедившись, что учетные записи администраторов максимально надежны.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> 

<span data-ttu-id="7f7fc-106">В этой статье описывается, как использовать политики условного доступа Azure Active Directory (Azure AD) для защиты учетных записей глобальных администраторов.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="7f7fc-107">Защита учетных записей глобальных администраторов в среде тестирования Microsoft 365 для предприятий состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="7f7fc-107">Protecting global administrator accounts in your Microsoft 365 for enterprise test environment involves two phases:</span></span>
- [<span data-ttu-id="7f7fc-108">Этап 1: создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="7f7fc-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="7f7fc-109">Этап 2: Настройка политик условного доступа</span><span class="sxs-lookup"><span data-stu-id="7f7fc-109">Phase 2: Configure conditional access policies</span></span>](#phase-2-configure-conditional-access-policies)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="7f7fc-111">Для отображения всех статей, посвященных руководству по лаборатории тестирования Microsoft 365 для предприятий, перейдите к разделу [руководство по лаборатории тестирования microsoft 365 для предприятия](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="7f7fc-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7f7fc-112">Этап 1: создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="7f7fc-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7f7fc-113">Чтобы протестировать защиту учетной записи глобального администратора в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="7f7fc-113">If you want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="7f7fc-114">Если вы хотите протестировать защиту учетной записи глобального администратора на имитации предприятия, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="7f7fc-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7f7fc-115">Для тестирования защиты учетной записи глобального администратора не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету, и синхронизацию каталогов для доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="7f7fc-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="7f7fc-116">Он предоставляется в качестве параметра, чтобы можно было тестировать защиту учетной записи глобального администратора и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="7f7fc-117">Этап 2: Настройка политик условного доступа</span><span class="sxs-lookup"><span data-stu-id="7f7fc-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="7f7fc-118">Сначала создайте новую учетную запись пользователя в качестве выделенного глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="7f7fc-119">На отдельной вкладке откройте [центр администрирования Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="7f7fc-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="7f7fc-120">Выберите пункт **Пользователи**  >  **Активные пользователи**и нажмите кнопку **Добавить пользователя**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-120">Select **Users** > **Active users**, and then select **Add a user**.</span></span>
3. <span data-ttu-id="7f7fc-121">В области **Добавление пользователя** введите **дедикатедадмин** в полях **имя**, **Отображаемое имя**и имя **пользователя** .</span><span class="sxs-lookup"><span data-stu-id="7f7fc-121">In the **Add user** pane, enter **DedicatedAdmin** in the **First name**, **Display name**, and **Username** boxes.</span></span>
4. <span data-ttu-id="7f7fc-122">Выберите **пароль**, выберите **параметр Разрешить создание пароля**, а затем введите надежный пароль.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-122">Select **Password**, select **Let me create the password**, and then enter a strong password.</span></span> <span data-ttu-id="7f7fc-123">Запишите пароль для новой учетной записи в надежном расположении.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="7f7fc-124">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-124">Select **Next**.</span></span>
6. <span data-ttu-id="7f7fc-125">В области **Назначение лицензий на продукты** выберите **Microsoft 365**а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then select **Next**.</span></span>
7. <span data-ttu-id="7f7fc-126">В области **необязательные параметры** выберите **роли**  >  глобальный администратор**доступа к центру администрирования**  >  **Global admin**  >  **Next**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-126">In the **Optional settings** pane, select **Roles** > **Admin center access** > **Global admin** > **Next**.</span></span>
8. <span data-ttu-id="7f7fc-127">В области **почти готово** нажмите кнопку **завершить добавление**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-127">On the **You're almost done** pane, select **Finish adding**, and then select **Close**.</span></span>

<span data-ttu-id="7f7fc-128">Затем создайте группу с именем Глобаладминс и добавьте в нее учетную запись Дедикатедадмин.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="7f7fc-129">На вкладке **центра администрирования Microsoft 365** выберите **группы** в левой области навигации, а затем выберите пункт **группы**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-129">On the **Microsoft 365 admin center** tab, select **Groups** in the left navigation, and then select **Groups**.</span></span>
2. <span data-ttu-id="7f7fc-130">Нажмите кнопку **Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-130">Select **Add a group**.</span></span>
3. <span data-ttu-id="7f7fc-131">В области **Выбор типа группы** выберите **Безопасность**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-131">In the **Choose a group type** pane, select **Security**, and then select **Next**.</span></span>
4. <span data-ttu-id="7f7fc-132">В области **Настройка основных принципов** выберите **создать группу**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-132">In the **Set up the basics** pane, select **Create group**, and then select **Close**.</span></span>
5. <span data-ttu-id="7f7fc-133">В области **Проверка и Добавление группы** введите **глобаладминс**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-133">In the **Review and finish adding group** pane, enter **GlobalAdmins**, and then select **Next**.</span></span>
7. <span data-ttu-id="7f7fc-134">В списке групп выберите группу **глобаладминс** .</span><span class="sxs-lookup"><span data-stu-id="7f7fc-134">In the list of groups, select the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="7f7fc-135">В области **глобаладминс** выберите **элемент элементы**, а затем нажмите кнопку **Просмотр всех элементов и управление ими**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-135">In the **GlobalAdmins** pane, select **Members**, and then select **View all and manage members**.</span></span>
9. <span data-ttu-id="7f7fc-136">В области **глобаладминс** выберите **Добавить участников**, выберите учетную запись **дедикатедадмин** и учетную запись глобального администратора, а затем нажмите кнопку **сохранить**  >  **Закрыть**  >  **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-136">In the **GlobalAdmins** pane, select **Add members**, select the **DedicatedAdmin** account and your global admin account, and then select **Save** > **Close** > **Close**.</span></span>

<span data-ttu-id="7f7fc-137">Затем создайте политики условного доступа, чтобы использовать многофакторную проверку подлинности для учетных записей глобальных администраторов, а также отказаться от проверки подлинности, если риск для входа имеет средний или высокий уровень.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-137">Next, create conditional access policies to require multi-factor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="7f7fc-138">Эта первая политика требует, чтобы все учетные записи глобального администратора использовали MFA.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="7f7fc-139">На новой вкладке браузера перейдите в раздел [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="7f7fc-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="7f7fc-140">Выберите **Azure Active Directory**пункт  >  **Security**  >  **Условный доступ к**системе безопасности Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-140">Click **Azure Active Directory** > **Security** > **Conditional Access**.</span></span>
3. <span data-ttu-id="7f7fc-141">В области **Условный доступ — политики** выберите **Базовая политика: требовать MFA для администраторов (Предварительная версия)**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-141">In the **Conditional access – Policies** pane, select **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="7f7fc-142">В области **Базовая политика** выберите **параметр использовать политику сразу > сохранения**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-142">In the **Baseline policy** pane, select **Use policy immediately > Save**.</span></span>

<span data-ttu-id="7f7fc-143">Эта вторая политика блокирует доступ к проверке подлинности глобальной учетной записи администратора, если риск для входа имеет средний или высокий уровень.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="7f7fc-144">В области **Условный доступ — политики** выберите **создать политику**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-144">In the **Conditional access – Policies** pane, select **New policy**.</span></span>
2. <span data-ttu-id="7f7fc-145">В **новой** области введите **имя**в поле **Глобальные администраторы** .</span><span class="sxs-lookup"><span data-stu-id="7f7fc-145">In the **New** pane, enter **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="7f7fc-146">В разделе **назначения** выберите **Пользователи и группы**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-146">In the **Assignments** section, select **Users and groups**.</span></span>
4. <span data-ttu-id="7f7fc-147">На вкладке **включить** в области **Пользователи и группы** выберите пункт **Выбор пользователей и групп**,  >  **Users and groups**  >  **Выбор**пользователей и групп.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-147">On the **Include** tab of the **Users and groups** pane, select **Select users and groups** > **Users and groups** > **Select**.</span></span>
5. <span data-ttu-id="7f7fc-148">В области **Выбор** выберите группу **глобаладминс** и нажмите **кнопку Выбрать**  >  **Готово**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-148">In the **Select** pane, select the **GlobalAdmins** group, and then select **Select** > **Done**.</span></span>
6. <span data-ttu-id="7f7fc-149">В разделе **назначения** выберите пункт **условия**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-149">In the **Assignments** section, select **Conditions**.</span></span>
7. <span data-ttu-id="7f7fc-150">В области **условия** выберите пункт **риск входа**, выберите **Да** для параметра **Настройка**, установите переключатель **высокий** и **средний**и нажмите **кнопку Выбрать** и **Готово**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-150">In the **Conditions** pane, select **Sign-in risk**, select **Yes** for **Configure**, select **High** and **Medium**, and then select **Select** and **Done**.</span></span>
8. <span data-ttu-id="7f7fc-151">В разделе **элементы управления доступом** в области **создать** нажмите кнопку **предоставить**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-151">In the **Access controls** section of the **New** pane, select **Grant**.</span></span>
9. <span data-ttu-id="7f7fc-152">В области **предоставление** выберите **блокировать доступ**, а затем нажмите **кнопку Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-152">In the **Grant** pane, select **Block access**, and then select **Select**.</span></span>
10. <span data-ttu-id="7f7fc-153">В области **создать** выберите Включить, **On** чтобы **включить политику**, а затем нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-153">In the **New** pane, select **On** for **Enable policy**, and then select **Create**.</span></span>
11. <span data-ttu-id="7f7fc-154">Закройте вкладки **портал Azure** и **центр администрирования Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="7f7fc-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="7f7fc-155">Чтобы проверить первую политику, выйдите из учетной записи Дедикатедадмин и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="7f7fc-156">Вам будет предложено настроить MFA.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="7f7fc-157">Это показывает, что применяется первая политика.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="7f7fc-158">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="7f7fc-158">Next step</span></span>

<span data-ttu-id="7f7fc-159">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="7f7fc-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f7fc-160">См. также</span><span class="sxs-lookup"><span data-stu-id="7f7fc-160">See also</span></span>

[<span data-ttu-id="7f7fc-161">Схема удостоверений</span><span class="sxs-lookup"><span data-stu-id="7f7fc-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="7f7fc-162">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="7f7fc-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7f7fc-163">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="7f7fc-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="7f7fc-164">Microsoft 365 для корпоративных документов</span><span class="sxs-lookup"><span data-stu-id="7f7fc-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
