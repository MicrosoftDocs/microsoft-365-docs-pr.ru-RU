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
ms.openlocfilehash: fff09ca41ff0b648d46b5c33f753affc01242264
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695186"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="29552-103">Защита учетных записей глобального администратора в тестовой среде Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="29552-103">Protect global administrator accounts in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="29552-104">*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для тестовых сред предприятия.*</span><span class="sxs-lookup"><span data-stu-id="29552-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="29552-105">Вы можете предотвратить цифровые атаки в Организации, убедившись, что учетные записи администраторов максимально надежны.</span><span class="sxs-lookup"><span data-stu-id="29552-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="29552-106">В этой статье описывается, как использовать политики условного доступа Azure Active Directory (Azure AD) для защиты учетных записей глобальных администраторов.</span><span class="sxs-lookup"><span data-stu-id="29552-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="29552-107">Существует два этапа защиты учетных записей глобального администратора в тестовой среде Microsoft 365 для предприятий:</span><span class="sxs-lookup"><span data-stu-id="29552-107">There are two phases to protecting global administrator accounts in your Microsoft 365 for enterprise test environment:</span></span>

1.  <span data-ttu-id="29552-108">Создайте тестовую среду Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="29552-108">Create the Microsoft 365 for enterprise test environment.</span></span>
2.  <span data-ttu-id="29552-109">Защитите выделенную учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="29552-109">Protect your dedicated global administrator account.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="29552-111">Щелкните [здесь](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 для крупных предприятий.</span><span class="sxs-lookup"><span data-stu-id="29552-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="29552-112">Этап 1: создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="29552-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="29552-113">Если вы хотите просто протестировать защиту учетной записи глобального администратора в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="29552-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="29552-114">Если вы хотите протестировать защиту учетной записи глобального администратора на имитации предприятия, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="29552-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="29552-115">Для тестирования защиты учетной записи глобального администратора не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету, и синхронизацию каталогов для доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="29552-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="29552-116">Он предоставляется в качестве параметра, чтобы можно было тестировать защиту учетной записи глобального администратора и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="29552-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="29552-117">Этап 2: Настройка политик условного доступа</span><span class="sxs-lookup"><span data-stu-id="29552-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="29552-118">Сначала создайте новую учетную запись пользователя в качестве выделенного глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="29552-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="29552-119">На отдельной вкладке откройте [центр администрирования Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="29552-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="29552-120">Щелкните **пользователи > активные пользователи**, а затем щелкните **Добавить пользователя**.</span><span class="sxs-lookup"><span data-stu-id="29552-120">Click **Users > Active users**, and then click **Add a user**.</span></span>
3. <span data-ttu-id="29552-121">В области **Добавление пользователя** введите **дедикатедадмин** в поле **имя**, **Отображаемое имя**и **имя пользователя**.</span><span class="sxs-lookup"><span data-stu-id="29552-121">In the **Add user** pane, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="29552-122">Нажмите **пароль**, выберите пункт **создать пароль**, а затем введите надежный пароль.</span><span class="sxs-lookup"><span data-stu-id="29552-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="29552-123">Запишите пароль для новой учетной записи в надежном расположении.</span><span class="sxs-lookup"><span data-stu-id="29552-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="29552-124">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="29552-124">Click **Next**.</span></span>
6. <span data-ttu-id="29552-125">В области **Назначение лицензий на продукты** выберите **Microsoft 365**а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="29552-125">In the **Assign product licenses** pane, select **Microsoft 365 E5**, and then click **Next**.</span></span>
7. <span data-ttu-id="29552-126">В области **необязательные параметры** щелкните **роли**, а затем выберите **доступ к центру администрирования** и **глобальному администратору**. Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="29552-126">In the **Optional settings** pane, click **Roles**, and then select **Admin center access** and **Global admin**. Click **Next**.</span></span>
8. <span data-ttu-id="29552-127">В области **почти готово** нажмите кнопку **завершить добавление**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="29552-127">On the **You're almost done** pane, click **Finish adding**, and then click **Close**.</span></span>

<span data-ttu-id="29552-128">Затем создайте группу с именем Глобаладминс и добавьте в нее учетную запись Дедикатедадмин.</span><span class="sxs-lookup"><span data-stu-id="29552-128">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="29552-129">На вкладке **центра администрирования Microsoft 365** щелкните **группы** в левой области навигации, а затем щелкните **группы**.</span><span class="sxs-lookup"><span data-stu-id="29552-129">On the **Microsoft 365 admin center** tab, click **Groups** in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="29552-130">Нажмите кнопку **Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="29552-130">Click **Add a group**.</span></span>
3. <span data-ttu-id="29552-131">В области **Выбор типа группы** выберите **Безопасность**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="29552-131">In the **Choose a group type** pane, select **Security**, and then click **Next**.</span></span>
4. <span data-ttu-id="29552-132">В области **Настройка основных принципов** нажмите кнопку **создать группу**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="29552-132">In the **Set up the basics** pane, click **Create group**, and then click **Close**.</span></span>
5. <span data-ttu-id="29552-133">В области **Проверка и Добавление группы** введите **глобаладминс**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="29552-133">In the **Review and finish adding group** pane, type **GlobalAdmins**, and then click **Next**.</span></span>
7. <span data-ttu-id="29552-134">В списке групп выберите группу **глобаладминс** .</span><span class="sxs-lookup"><span data-stu-id="29552-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
8. <span data-ttu-id="29552-135">В области **глобаладминс** щелкните **элементы**, а затем щелкните **Просмотр всех элементов и управление ими**.</span><span class="sxs-lookup"><span data-stu-id="29552-135">In the **GlobalAdmins** pane, click **Members**, and then click **View all and manage members**.</span></span>
9. <span data-ttu-id="29552-136">В области **глобаладминс** нажмите кнопку **Добавить участников**, выберите учетную запись **дедикатедадмин** и учетную запись глобального администратора, а затем нажмите кнопку **сохранить > закрыть > закрыть**.</span><span class="sxs-lookup"><span data-stu-id="29552-136">In the **GlobalAdmins** pane, click **Add members**, select the **DedicatedAdmin** account and your global admin account, and then click **Save > Close > Close**.</span></span>

<span data-ttu-id="29552-137">Затем создайте политики условного доступа, чтобы использовать многофакторную проверку подлинности для учетных записей глобального администратора, и запретите проверку подлинности, если риск входа в систему имеет средний или высокий уровень.</span><span class="sxs-lookup"><span data-stu-id="29552-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="29552-138">Эта первая политика требует, чтобы все учетные записи глобального администратора использовали MFA.</span><span class="sxs-lookup"><span data-stu-id="29552-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="29552-139">На новой вкладке браузера перейдите в раздел [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="29552-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="29552-140">Щелкните элемент **Azure Active Directory > безопасность > условный доступ**.</span><span class="sxs-lookup"><span data-stu-id="29552-140">Click **Azure Active Directory > Security > Conditional Access**.</span></span>
3. <span data-ttu-id="29552-141">В области **Условный доступ – политики** щелкните **Базовая политика: требовать MFA для администраторов (Предварительная версия)**.</span><span class="sxs-lookup"><span data-stu-id="29552-141">In the **Conditional access – Policies** pane, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="29552-142">В области **Базовая политика** выберите **параметр использовать политику сразу > сохранения**.</span><span class="sxs-lookup"><span data-stu-id="29552-142">In the **Baseline policy** pane, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="29552-143">Эта вторая политика блокирует доступ к проверке подлинности глобальной учетной записи администратора, если риск для входа имеет средний или высокий уровень.</span><span class="sxs-lookup"><span data-stu-id="29552-143">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="29552-144">В области **Условный доступ – политики** щелкните **создать политику**.</span><span class="sxs-lookup"><span data-stu-id="29552-144">In the **Conditional access – Policies** pane, click **New policy**.</span></span>
2. <span data-ttu-id="29552-145">В области **создать** в поле **имя**введите **Глобальные администраторы** .</span><span class="sxs-lookup"><span data-stu-id="29552-145">In the **New** pane, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="29552-146">В разделе **назначения** выберите **Пользователи и группы**.</span><span class="sxs-lookup"><span data-stu-id="29552-146">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="29552-147">На вкладке **включить** в области **Пользователи и группы** щелкните **Выбор пользователей и групп > пользователи и группы > выбрать**.</span><span class="sxs-lookup"><span data-stu-id="29552-147">On the **Include** tab of the **Users and groups** pane, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="29552-148">В области **Выбор** выберите группу **глобаладминс** и нажмите кнопку **выбрать > готово**.</span><span class="sxs-lookup"><span data-stu-id="29552-148">In the **Select** pane, click the **GlobalAdmins** group, and then click **Select > Done**.</span></span>
6. <span data-ttu-id="29552-149">В разделе **назначения** выберите пункт **условия**.</span><span class="sxs-lookup"><span data-stu-id="29552-149">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="29552-150">В области **условия** щелкните элемент **риск входа в систему**, нажмите кнопку **Да** для **настройки**, выберите **Высокая** и **Средняя**, а затем нажмите кнопку **выбрать** и **Готово**.</span><span class="sxs-lookup"><span data-stu-id="29552-150">In the **Conditions** pane, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="29552-151">В разделе **элементы управления доступом** в области **создать** нажмите кнопку **предоставить**.</span><span class="sxs-lookup"><span data-stu-id="29552-151">In the **Access controls** section of the **New** pane, click **Grant**.</span></span>
9. <span data-ttu-id="29552-152">В области **предоставление** щелкните **блокировать доступ**, а затем нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="29552-152">In the **Grant** pane, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="29552-153">В области **создать** выберите пункт **включить политику**, а **затем нажмите кнопку** **создать**.</span><span class="sxs-lookup"><span data-stu-id="29552-153">In the **New** pane, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="29552-154">Закройте вкладки **портал Azure** и **центр администрирования Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="29552-154">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="29552-155">Чтобы проверить первую политику, выйдите из учетной записи Дедикатедадмин и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="29552-155">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="29552-156">Вам будет предложено настроить MFA.</span><span class="sxs-lookup"><span data-stu-id="29552-156">You should be prompted to configure MFA.</span></span> <span data-ttu-id="29552-157">Это показывает, что применяется первая политика.</span><span class="sxs-lookup"><span data-stu-id="29552-157">This demonstrates that the first policy is being applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="29552-158">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="29552-158">Next step</span></span>

<span data-ttu-id="29552-159">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="29552-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="29552-160">См. также</span><span class="sxs-lookup"><span data-stu-id="29552-160">See also</span></span>

[<span data-ttu-id="29552-161">Схема удостоверений</span><span class="sxs-lookup"><span data-stu-id="29552-161">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="29552-162">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="29552-162">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="29552-163">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="29552-163">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="29552-164">Microsoft 365 для корпоративных документов</span><span class="sxs-lookup"><span data-stu-id="29552-164">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
