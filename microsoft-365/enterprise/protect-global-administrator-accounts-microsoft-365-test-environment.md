---
title: Защита учетных записей глобального администратора в тестовой среде Microsoft 365 для предприятия
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
description: Используйте следующие действия для защиты учетных записей глобального администратора в тестовой среде Microsoft 365 для предприятия.
ms.openlocfilehash: 233e2178b060df4950c340e034d5f51216fac8fb
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870462"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="8c0cb-103">Защита учетных записей глобального администратора в тестовой среде Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="8c0cb-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="8c0cb-p101">Можно запретить цифровой атак на вашей организации, чтобы убедиться, что учетные записи администратора безопасности. В этой статье описывается, как использовать политики условного доступа приложения облаке Безопасность в Office 365 и Azure AD для защиты учетных записей глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-p101">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible. This article describes how to use Office 365 Cloud App Security and Azure AD conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="8c0cb-106">Существует два этапа защита учетные записи глобального администратора в тестовой среде Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-106">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="8c0cb-107">Создание тестовой среды Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="8c0cb-108">Защита учетной записи выделенного глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-108">Protect your dedicated global administrator account.</span></span>

![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="8c0cb-110">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="8c0cb-111">Этап 1: Создание масштабирование тестовой среды Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="8c0cb-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="8c0cb-112">Если необходимо проверить защиты учетной записи глобального администратора в облегченный путь с минимальным требованиям, следуйте инструкциям в [упрощенной базовой конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="8c0cb-112">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="8c0cb-113">Если вы хотите проверить защиты учетной записи глобального администратора в имитации enterprise, следуйте инструкциям в [сквозная проверка подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="8c0cb-113">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8c0cb-p102">Проверка учетной записи глобального администратора защиты не требует имитации enterprise тестовой среды, который включает имитации интрасети подключен к Интернету и синхронизации каталогов для леса Windows Server AD. Предоставляется здесь как вариант, чтобы проверить защиты учетной записи глобального администратора и экспериментировать с его в среде, которая представляет типичное организации.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-p102">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a><span data-ttu-id="8c0cb-116">Этап 2: Настройка безопасности облаке приложения и политик условного доступа</span><span class="sxs-lookup"><span data-stu-id="8c0cb-116">Phase 2: Configure Cloud App Security and conditional access policies</span></span>

<span data-ttu-id="8c0cb-117">Во-первых создайте политику безопасности Office 365 облаке приложения для контроля активности учетной записи глобального администратора и отправлять оповещения на адрес электронной почты учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-117">First, create an Office 365 Cloud App Security policy to monitor global administrator account activity and send alerts to the email address of your global administrator account.</span></span> 

1. <span data-ttu-id="8c0cb-118">Войдите в портал Office 365 по [http://portal.office.com](http://portal.office.com) с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-118">Sign in to the Office 365 portal at [http://portal.office.com](http://portal.office.com) using your global administrator account.</span></span>
2. <span data-ttu-id="8c0cb-p103">Щелкните плитку **администрирования** . На вкладке **центра администрирования Office** щелкните **центры администрирования > Безопасность и соответствие требованиям**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-p103">Click the **Admin** tile. On the **Office Admin center** tab, click **Admin centers > Security & Compliance**.</span></span>
3. <span data-ttu-id="8c0cb-121">В области навигации слева выберите **Оповещения > Управление расширенными оповещениями**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-121">In the left navigation pane, click **Alerts > Manage advanced alerts**.</span></span>
4. <span data-ttu-id="8c0cb-122">На странице **Управление расширенными оповещениями** нажмите **Включить Office 365 Cloud App Security**, а затем выберите **Перейти к Office 365 Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-122">On the **Manage advanced alerts** page, click **Turn on Office 365 Cloud App Security**, and then click **Go to Office 365 Cloud App Security**.</span></span>
5. <span data-ttu-id="8c0cb-123">На вкладке **Панель мониторинга** выберите **Элемент управления > Политики**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-123">On the new **Dashboard** tab, click **Control > Policies**.</span></span>
6. <span data-ttu-id="8c0cb-124">На странице **Политики** нажмите **Создание политики** и выберите элемент **Политика действий**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-124">On the **Policy** page, click **Create policy**, and then click **Activity policy**.</span></span>
7. <span data-ttu-id="8c0cb-125">В поле **Имя политики** введите **Административное действие**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-125">In **Policy name**, type **Administrative activity**.</span></span>
8. <span data-ttu-id="8c0cb-126">В разделе **Серьезность политики** выберите **Высокая**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-126">In **Policy severity**, click **High**.</span></span>
9. <span data-ttu-id="8c0cb-127">В разделе **Категория** выберите элемент **Привилегированные учетные записи**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-127">In **Category**, click **Privileged accounts**.</span></span>
10. <span data-ttu-id="8c0cb-128">В разделе **Создать фильтры для политики** для элемента **Действия, соответствующие всем следующим условиям** задайте значение **Административное действие**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-128">In **Create filters for the policy**, in **Activities matching all of the following**, click **Administrative activity**.</span></span>
11. <span data-ttu-id="8c0cb-p104">В разделе **Оповещения** выберите **Отправлять оповещение по электронной почте**. В поле **Кому** введите адрес электронной почты учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-p104">In **Alerts**, click **Send alert as email**. In **To**, type the email address of your global administrator account.</span></span>
12. <span data-ttu-id="8c0cb-131">В нижней части страницы нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-131">At the bottom of the page, click **Create**.</span></span>
13. <span data-ttu-id="8c0cb-132">Закройте вкладку **панели мониторинга** .</span><span class="sxs-lookup"><span data-stu-id="8c0cb-132">Close the **Dashboard** tab.</span></span>
    
<span data-ttu-id="8c0cb-133">Создайте новую учетную запись пользователя, как выделенный глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-133">Next, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="8c0cb-134">На вкладке **центра администрирования Office** в разделе **активных пользователей**, нажмите кнопку **Добавить пользователя**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-134">On the **Office Admin center** tab, under **Active users**, click **Add a user**.</span></span>
2. <span data-ttu-id="8c0cb-135">На странице " **Новый пользователь** " введите **DedicatedAdmin** в **имя**, **отображаемое имя**и **имя пользователя**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-135">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
3. <span data-ttu-id="8c0cb-p105">Нажмите кнопку **пароль**, щелкните **Самостоятельное создание пароль**и затем введите надежный пароль. Запишите пароль для учетной записи в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-p105">Click **Password**, click **Let me create the password**, and then type a strong password. Record the password for this new account in a secure location.</span></span>
4. <span data-ttu-id="8c0cb-138">Снимите флажок **пользователь изменить пароль при первом входе в**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-138">Clear **Make this user change their password when they first sign in**.</span></span>
5. <span data-ttu-id="8c0cb-139">Выберите **роли**и нажмите кнопку **глобального администратора**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-139">Click **Roles**, and then click **Global administrator**.</span></span>
6. <span data-ttu-id="8c0cb-140">Нажмите кнопку **лицензий на продукт**и включите **мобильности Enterprise + E5 безопасности** и **лицензиями Office 365 корпоративный E5** .</span><span class="sxs-lookup"><span data-stu-id="8c0cb-140">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
7. <span data-ttu-id="8c0cb-141">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-141">Click **Add**.</span></span>
8. <span data-ttu-id="8c0cb-142">На, **пользователь был добавлен страницы**снимите флажок **отправить пароль по электронной почте**и нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-142">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="8c0cb-143">Затем создайте новую группу с именем GlobalAdmins и добавьте учетную запись DedicatedAdmin к нему.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-143">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="8c0cb-144">На вкладке **центра администрирования Office** щелкните значок группы в левой области навигации и щелкните элемент **группы**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-144">On the **Office Admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="8c0cb-145">Нажмите кнопку **Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-145">Click **Add a group**.</span></span>
3. <span data-ttu-id="8c0cb-146">На странице **Новая группа** введите **GlobalAdmins**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-146">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="8c0cb-147">Щелкните **выбрать владелец** щелкните свою учетную запись глобального администратора и нажмите кнопку **Добавить > Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-147">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="8c0cb-148">В списке группы выберите группу **GlobalAdmins** .</span><span class="sxs-lookup"><span data-stu-id="8c0cb-148">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="8c0cb-149">На странице " **GlobalAdmins** " нажмите кнопку **изменить для элемента**и нажмите кнопку **Добавить элементы**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-149">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="8c0cb-150">В списке, щелкните учетную запись **DedicatedAdmin** и нажмите кнопку **Сохранить > Закрыть > Закрыть > Центр администрирования**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-150">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="8c0cb-151">Создайте политики условного доступа для поддержки требования многофакторной проверки подлинности для глобального администратора учетных записей и для запрета проверки подлинности, если риск входа в средней или высокой.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-151">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="8c0cb-152">В этом первый политики требуется, что все учетные записи глобального администратора многофакторной проверкой Подлинности.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-152">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="8c0cb-153">На новой вкладке браузера перейдите к [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="8c0cb-153">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="8c0cb-154">Нажмите кнопку **Azure Active Directory > условного доступа**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-154">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="8c0cb-155">На blade **условного доступа – политик** , щелкните **базовой политики: требовать многофакторной проверкой Подлинности для "Администраторы" (preview)**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-155">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="8c0cb-p106">На blade **... базового политик** , щелкните **с помощью политики сразу же > Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-p106">On the **Baseline policies…** blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="8c0cb-158">В этом второй политики блокирует доступ к глобальным администратором учетной записи проверки подлинности при риск входа в средних и высокой.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-158">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="8c0cb-159">На blade **условного доступа, политики** выберите **новую политику**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-159">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="8c0cb-160">На blade **New** введите в поле **имя** **глобальных администраторов** .</span><span class="sxs-lookup"><span data-stu-id="8c0cb-160">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="8c0cb-161">В разделе **назначения** щелкните **пользователи и группы**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-161">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="8c0cb-162">На вкладке **Include** blade **пользователей и групп** нажмите кнопку **выберите пользователи и группы > пользователи и группы > выберите**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-162">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="8c0cb-163">На blade **выберите** пункт **GlobalAdmins > выберите > выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-163">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="8c0cb-164">В разделе **назначения** выберите **условия**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-164">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="8c0cb-165">На blade **условия** нажмите кнопку **Вход риск**, нажмите кнопку **Да** для **настройки**, нажмите кнопку **Высокая** и **средние**и нажмите кнопку **выберите** и **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-165">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="8c0cb-166">В разделе **Управление доступом** **New** blade щелкните **право**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-166">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="8c0cb-167">На blade **Grant** щелкните **заблокировать доступ**и нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-167">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="8c0cb-168">На blade **New** \*\*выберите команду для \*\*включения политики\*\*\*\* и затем нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-168">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="8c0cb-169">Закройте вкладки **Azure портала** и **Центр администрирования Office** .</span><span class="sxs-lookup"><span data-stu-id="8c0cb-169">Close the **Azure portal** and **Office Admin center** tabs.</span></span>

<span data-ttu-id="8c0cb-p107">Чтобы проверить первой политики, выйти и вход с помощью учетной записи DedicatedAdmin. Вы должны запрос Настройка многофакторной проверкой Подлинности учетной записи пользователя. Этот пример демонстрирует применения первого политики.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-p107">To test the first policy, sign out and sign in with the DedicatedAdmin account. You should be prompted to configure MFA on the user account. This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="8c0cb-173">См. [учетные записи глобального администратора защитить](identity-designate-protect-admin-accounts.md) действие на этапе Identity сведения и ссылки для защиты учетных записей глобального администратора в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-173">See the [Protect global administrator accounts](identity-designate-protect-admin-accounts.md) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="8c0cb-174">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="8c0cb-174">Next step</span></span>

<span data-ttu-id="8c0cb-175">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="8c0cb-175">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c0cb-176">См. также</span><span class="sxs-lookup"><span data-stu-id="8c0cb-176">See also</span></span>

[<span data-ttu-id="8c0cb-177">Этап 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="8c0cb-177">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="8c0cb-178">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="8c0cb-178">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="8c0cb-179">Развертывание Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="8c0cb-179">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="8c0cb-180">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="8c0cb-180">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
