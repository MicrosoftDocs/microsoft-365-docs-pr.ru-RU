---
title: Защита учетных записей глобального администратора в тестовой среде Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Используйте следующие действия для защиты учетных записей глобального администратора в тестовой среде Microsoft 365 Enterprise.
ms.openlocfilehash: 5447177c6581b69d48272ceef7718552ea84dc9d
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "39202230"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="55847-103">Защита учетных записей глобального администратора в тестовой среде Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="55847-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="55847-104">*Это руководство по лаборатории тестирования можно использовать только для тестовых сред Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="55847-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="55847-105">Вы можете предотвратить цифровые атаки в Организации, убедившись, что учетные записи администраторов максимально надежны.</span><span class="sxs-lookup"><span data-stu-id="55847-105">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="55847-106">В этой статье описывается, как использовать политики условного доступа Azure Active Directory (Azure AD) для защиты учетных записей глобальных администраторов.</span><span class="sxs-lookup"><span data-stu-id="55847-106">This article describes how to use Azure Active Directory (Azure AD) conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="55847-107">Существует два этапа защиты учетных записей глобального администратора в тестовой среде Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="55847-107">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="55847-108">Создайте среду тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="55847-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="55847-109">Защитите выделенную учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="55847-109">Protect your dedicated global administrator account.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="55847-111">Щелкните [здесь](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="55847-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="55847-112">Этап 1. Создание собственной тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="55847-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="55847-113">Если вы хотите просто протестировать защиту учетной записи глобального администратора в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="55847-113">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="55847-114">Если вы хотите протестировать защиту учетной записи глобального администратора на имитации предприятия, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="55847-114">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

  
> [!NOTE]
> <span data-ttu-id="55847-115">Для тестирования защиты учетной записи глобального администратора не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету, и синхронизацию каталогов для доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="55847-115">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="55847-116">Он предоставляется в качестве параметра, чтобы можно было тестировать защиту учетной записи глобального администратора и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="55847-116">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-conditional-access-policies"></a><span data-ttu-id="55847-117">Этап 2: Настройка политик условного доступа</span><span class="sxs-lookup"><span data-stu-id="55847-117">Phase 2: Configure conditional access policies</span></span>

<span data-ttu-id="55847-118">Сначала создайте новую учетную запись пользователя в качестве выделенного глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="55847-118">First, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="55847-119">На отдельной вкладке откройте [центр администрирования Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="55847-119">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="55847-120">В разделе **Активные пользователи**нажмите кнопку **Добавить пользователя**.</span><span class="sxs-lookup"><span data-stu-id="55847-120">Under **Active users**, click **Add a user**.</span></span>
3. <span data-ttu-id="55847-121">На странице **Новый пользователь** введите **дедикатедадмин** в поле **имя**, **Отображаемое имя**и **имя пользователя**.</span><span class="sxs-lookup"><span data-stu-id="55847-121">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="55847-122">Нажмите **пароль**, выберите пункт **создать пароль**, а затем введите надежный пароль.</span><span class="sxs-lookup"><span data-stu-id="55847-122">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="55847-123">Запишите пароль для новой учетной записи в надежном расположении.</span><span class="sxs-lookup"><span data-stu-id="55847-123">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="55847-124">Снимите флажок сделать так, **чтобы пользователь изменил свой пароль при первом входе в систему**.</span><span class="sxs-lookup"><span data-stu-id="55847-124">Clear **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="55847-125">Щелкните **роли**, а затем — **глобальный администратор**.</span><span class="sxs-lookup"><span data-stu-id="55847-125">Click **Roles**, and then click **Global administrator**.</span></span>
7. <span data-ttu-id="55847-126">Щелкните **лицензии на продукты**, а затем включите лицензию **Microsoft 365 в систему Microsoft** .</span><span class="sxs-lookup"><span data-stu-id="55847-126">Click **Product licenses**, and then turn the **Microsoft 365 E5** license on.</span></span>
8. <span data-ttu-id="55847-127">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="55847-127">Click **Add**.</span></span>
9. <span data-ttu-id="55847-128">На **странице "пользователь добавлен**" снимите флажок **Отправить пароль в сообщении электронной почты**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="55847-128">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="55847-129">Затем создайте группу с именем Глобаладминс и добавьте в нее учетную запись Дедикатедадмин.</span><span class="sxs-lookup"><span data-stu-id="55847-129">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="55847-130">На вкладке **центра администрирования Microsoft 365** щелкните значок группы в левой области навигации, а затем выберите пункт **группы**.</span><span class="sxs-lookup"><span data-stu-id="55847-130">On the **Microsoft 365 admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="55847-131">Нажмите кнопку **Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="55847-131">Click **Add a group**.</span></span>
3. <span data-ttu-id="55847-132">На странице " **Новая группа** " введите **глобаладминс**.</span><span class="sxs-lookup"><span data-stu-id="55847-132">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="55847-133">Нажмите кнопку **Выбрать владельца** , выберите свою учетную запись глобального администратора и нажмите кнопку **Добавить > закрыть**.</span><span class="sxs-lookup"><span data-stu-id="55847-133">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="55847-134">В списке групп выберите группу **глобаладминс** .</span><span class="sxs-lookup"><span data-stu-id="55847-134">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="55847-135">На странице **глобаладминс** щелкните **изменить для элемента**, а затем нажмите кнопку **Добавить участников**.</span><span class="sxs-lookup"><span data-stu-id="55847-135">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="55847-136">В списке выберите учетную запись **дедикатедадмин** , а затем нажмите кнопку **сохранить > закрыть > закрыть > центр администрирования**.</span><span class="sxs-lookup"><span data-stu-id="55847-136">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="55847-137">Затем создайте политики условного доступа, чтобы использовать многофакторную проверку подлинности для учетных записей глобального администратора, и запретите проверку подлинности, если риск входа в систему имеет средний или высокий уровень.</span><span class="sxs-lookup"><span data-stu-id="55847-137">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="55847-138">Эта первая политика требует, чтобы все учетные записи глобального администратора использовали MFA.</span><span class="sxs-lookup"><span data-stu-id="55847-138">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="55847-139">На новой вкладке браузера перейдите в [https://portal.azure.com](https://portal.azure.com)раздел.</span><span class="sxs-lookup"><span data-stu-id="55847-139">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="55847-140">Выберите **Azure Active Directory > условный доступ**.</span><span class="sxs-lookup"><span data-stu-id="55847-140">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="55847-141">В колонке **Условный доступ — политики** выберите пункт **Базовая политика: требовать MFA для администраторов (Предварительная версия)**.</span><span class="sxs-lookup"><span data-stu-id="55847-141">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="55847-142">В **базовых политиках...**</span><span class="sxs-lookup"><span data-stu-id="55847-142">On the **Baseline policies…**</span></span> <span data-ttu-id="55847-143">Блейд, щелкните **использовать политику сразу > сохранения**.</span><span class="sxs-lookup"><span data-stu-id="55847-143">blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="55847-144">Эта вторая политика блокирует доступ к проверке подлинности глобальной учетной записи администратора, если риск для входа имеет средний или высокий уровень.</span><span class="sxs-lookup"><span data-stu-id="55847-144">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="55847-145">В колонке **Условный доступ – политики** щелкните **создать политику**.</span><span class="sxs-lookup"><span data-stu-id="55847-145">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="55847-146">В **новой** колонке введите **имя**в поле **Глобальные администраторы** .</span><span class="sxs-lookup"><span data-stu-id="55847-146">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="55847-147">В разделе **назначения** выберите **Пользователи и группы**.</span><span class="sxs-lookup"><span data-stu-id="55847-147">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="55847-148">На вкладке **включить** в колонке **Пользователи и группы** щелкните **Выбор пользователей и групп > пользователи и группы > выбрать**.</span><span class="sxs-lookup"><span data-stu-id="55847-148">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="55847-149">В разделе **Выбор** блейд-меню выберите **глобаладминс > выберите > готово**.</span><span class="sxs-lookup"><span data-stu-id="55847-149">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="55847-150">В разделе **назначения** выберите пункт **условия**.</span><span class="sxs-lookup"><span data-stu-id="55847-150">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="55847-151">В колонке **условия** щелкните элемент **риск входа в**систему, нажмите кнопку **Да** для **настройки**, **выберите Высокая** и **Средняя**, а затем нажмите кнопку **выбрать** и **Готово**.</span><span class="sxs-lookup"><span data-stu-id="55847-151">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="55847-152">В разделе **элементы управления доступом** **нового** блейд-сервера нажмите кнопку **предоставить**.</span><span class="sxs-lookup"><span data-stu-id="55847-152">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="55847-153">В колонке **предоставление** выберите пункт **блокировать доступ**, а затем нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="55847-153">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="55847-154">На **новой** колонке щелкните Включить, чтобы **включить политику**, а **затем нажмите кнопку** **создать**.</span><span class="sxs-lookup"><span data-stu-id="55847-154">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="55847-155">Закройте вкладки **портал Azure** и **центр администрирования Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="55847-155">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="55847-156">Чтобы проверить первую политику, выйдите из учетной записи Дедикатедадмин и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="55847-156">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="55847-157">Вам будет предложено настроить MFA для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="55847-157">You should be prompted to configure MFA on the user account.</span></span> <span data-ttu-id="55847-158">Это показывает, что применяется первая политика.</span><span class="sxs-lookup"><span data-stu-id="55847-158">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="55847-159">Сведения и ссылки для защиты учетных записей глобального администратора в рабочей среде приведены в статье [Защита учетных записей глобальных администраторов](identity-create-protect-global-admins.md#identity-global-admin) на этапе идентификации.</span><span class="sxs-lookup"><span data-stu-id="55847-159">See the [Protect global administrator accounts](identity-create-protect-global-admins.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="55847-160">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="55847-160">Next step</span></span>

<span data-ttu-id="55847-161">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="55847-161">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="55847-162">См. также</span><span class="sxs-lookup"><span data-stu-id="55847-162">See also</span></span>

[<span data-ttu-id="55847-163">Шаг 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="55847-163">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="55847-164">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="55847-164">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="55847-165">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="55847-165">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="55847-166">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="55847-166">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
