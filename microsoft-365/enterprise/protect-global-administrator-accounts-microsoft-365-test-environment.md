---
title: Защита учетных записей глобального администратора в тестовой среде Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Используйте следующие действия для защиты учетных записей глобального администратора в тестовой среде Microsoft 365 Enterprise.
ms.openlocfilehash: cded424188447f96e5614f31d3e207bb541d438e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290862"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="8451b-103">Защита учетных записей глобального администратора в тестовой среде Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8451b-103">Protect global administrator accounts in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="8451b-104">Вы можете предотвратить цифровые атаки в Организации, убедившись, что учетные записи администраторов максимально надежны.</span><span class="sxs-lookup"><span data-stu-id="8451b-104">You can prevent digital attacks on your organization by ensuring that your administrator accounts are as secure as possible.</span></span> <span data-ttu-id="8451b-105">В этой статье описывается, как использовать Office 365 Cloud App Security and политики условного доступа Azure AD для защиты учетных записей глобальных администраторов.</span><span class="sxs-lookup"><span data-stu-id="8451b-105">This article describes how to use Office 365 Cloud App Security and Azure AD conditional access policies to protect global administrator accounts.</span></span>

<span data-ttu-id="8451b-106">Существует два этапа защиты учетных записей глобального администратора в тестовой среде Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="8451b-106">There are two phases to protecting global administrator accounts in your Microsoft 365 Enterprise test environment:</span></span>

1.  <span data-ttu-id="8451b-107">Создайте корпоративную тестовую среду Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8451b-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="8451b-108">Защитите выделенную учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="8451b-108">Protect your dedicated global administrator account.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="8451b-110">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="8451b-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

> [!NOTE]
> <span data-ttu-id="8451b-111">В тестовой среде Microsoft 365 Enterprise используется версия Office 365 и управление предприятием + Security + Security (EMS).</span><span class="sxs-lookup"><span data-stu-id="8451b-111">The Microsoft 365 Enterprise test environment uses E5 versions of Office 365 and Enterprise Management + Security (EMS).</span></span> <span data-ttu-id="8451b-112">Функция Cloud App Security (Office 365) доступна только в версии "только для Office 365".</span><span class="sxs-lookup"><span data-stu-id="8451b-112">The Office 365 Cloud App Security feature is only available in the E5 version Office 365.</span></span> 

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="8451b-113">Этап 1: создание тестовой среды Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8451b-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="8451b-114">Если вы хотите просто протестировать защиту учетной записи глобального администратора в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="8451b-114">If you just want to test global administrator account protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="8451b-115">Если вы хотите протестировать защиту учетной записи глобального администратора на имитации предприятия, следуйте инструкциям в [сквозной проверке](pass-through-auth-m365-ent-test-environment.md)подлинности.</span><span class="sxs-lookup"><span data-stu-id="8451b-115">If you want to test global administrator account protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>

  
> [!NOTE]
> <span data-ttu-id="8451b-116">Для тестирования защиты учетной записи глобального администратора не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету, и синхронизацию каталогов для доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="8451b-116">Testing global administrator account protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="8451b-117">Он предоставляется в качестве параметра, чтобы можно было тестировать защиту учетной записи глобального администратора и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="8451b-117">It is provided here as an option so that you can test global administrator account protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a><span data-ttu-id="8451b-118">Этап 2: Настройка безопасности облачных приложений и политик условного доступа</span><span class="sxs-lookup"><span data-stu-id="8451b-118">Phase 2: Configure Cloud App Security and conditional access policies</span></span>

<span data-ttu-id="8451b-119">Сначала создайте политику безопасности облачных приложений Office 365, чтобы отслеживать действия с учетной записью глобального администратора и отправлять оповещения на адрес электронной почты учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="8451b-119">First, create an Office 365 Cloud App Security policy to monitor global administrator account activity and send alerts to the email address of your global administrator account.</span></span> 

1. <span data-ttu-id="8451b-120">Войдите на [портал Office 365 Security _амп_](https://protection.office.com/) , используя учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="8451b-120">Sign in to the [Office 365 Security & Compliance portal](https://protection.office.com/) using your global administrator account.</span></span>
2. <span data-ttu-id="8451b-121">В области навигации слева выберите **Оповещения > Управление расширенными оповещениями**.</span><span class="sxs-lookup"><span data-stu-id="8451b-121">In the left navigation pane, click **Alerts > Manage advanced alerts**.</span></span>
3. <span data-ttu-id="8451b-122">На странице **Управление расширенными оповещениями** нажмите **Включить Office 365 Cloud App Security**, а затем выберите **Перейти к Office 365 Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="8451b-122">On the **Manage advanced alerts** page, click **Turn on Office 365 Cloud App Security**, and then click **Go to Office 365 Cloud App Security**.</span></span>
4. <span data-ttu-id="8451b-123">На вкладке **Панель мониторинга** выберите **Элемент управления > Политики**.</span><span class="sxs-lookup"><span data-stu-id="8451b-123">On the new **Dashboard** tab, click **Control > Policies**.</span></span>
5. <span data-ttu-id="8451b-124">На странице **Политики** нажмите **Создание политики** и выберите элемент **Политика действий**.</span><span class="sxs-lookup"><span data-stu-id="8451b-124">On the **Policy** page, click **Create policy**, and then click **Activity policy**.</span></span>
6. <span data-ttu-id="8451b-125">В поле **Имя политики** введите **Административное действие**.</span><span class="sxs-lookup"><span data-stu-id="8451b-125">In **Policy name**, type **Administrative activity**.</span></span>
7. <span data-ttu-id="8451b-126">В разделе **Серьезность политики** выберите **Высокая**.</span><span class="sxs-lookup"><span data-stu-id="8451b-126">In **Policy severity**, click **High**.</span></span>
8. <span data-ttu-id="8451b-127">В разделе **Категория** выберите элемент **Привилегированные учетные записи**.</span><span class="sxs-lookup"><span data-stu-id="8451b-127">In **Category**, click **Privileged accounts**.</span></span>
9. <span data-ttu-id="8451b-128">В разделе **Создать фильтры для политики** для элемента **Действия, соответствующие всем следующим условиям** задайте значение **Административное действие**.</span><span class="sxs-lookup"><span data-stu-id="8451b-128">In **Create filters for the policy**, in **Activities matching all of the following**, click **Administrative activity**.</span></span>
10. <span data-ttu-id="8451b-p104">В разделе **Оповещения** выберите **Отправлять оповещение по электронной почте**. В поле **Кому** введите адрес электронной почты учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="8451b-p104">In **Alerts**, click **Send alert as email**. In **To**, type the email address of your global administrator account.</span></span>
11. <span data-ttu-id="8451b-131">В нижней части страницы нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="8451b-131">At the bottom of the page, click **Create**.</span></span>
12. <span data-ttu-id="8451b-132">Закройте вкладку **Dashboard (панель мониторинга** ).</span><span class="sxs-lookup"><span data-stu-id="8451b-132">Close the **Dashboard** tab.</span></span>
    
<span data-ttu-id="8451b-133">Затем создайте новую учетную запись пользователя в качестве выделенного глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="8451b-133">Next, create a new user account as a dedicated global administrator.</span></span>

1. <span data-ttu-id="8451b-134">На отдельной вкладке откройте [центр администрирования Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="8451b-134">On a separate tab, open the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span>
2. <span data-ttu-id="8451b-135">В разделе **Активные пользователи**нажмите кнопку **Добавить пользователя**.</span><span class="sxs-lookup"><span data-stu-id="8451b-135">Under **Active users**, click **Add a user**.</span></span>
3. <span data-ttu-id="8451b-136">На странице **Новый пользователь** введите **дедикатедадмин** в поле **имя**, отображаемое **имя**и **имя пользователя**.</span><span class="sxs-lookup"><span data-stu-id="8451b-136">On the **New user** page, type **DedicatedAdmin** in **First name**, **Display name**, and **Username**.</span></span>
4. <span data-ttu-id="8451b-137">Нажмите **пароль**, выберите пункт **создать пароль**, а затем введите надежный пароль.</span><span class="sxs-lookup"><span data-stu-id="8451b-137">Click **Password**, click **Let me create the password**, and then type a strong password.</span></span> <span data-ttu-id="8451b-138">ЗаПишите пароль для новой учетной записи в надежном расположении.</span><span class="sxs-lookup"><span data-stu-id="8451b-138">Record the password for this new account in a secure location.</span></span>
5. <span data-ttu-id="8451b-139">Снимите флажок сделать так, **чтобы пользователь изменил свой пароль при первом входе в систему**.</span><span class="sxs-lookup"><span data-stu-id="8451b-139">Clear **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="8451b-140">Щелкните **роли**, а затем — **глобальный администратор**.</span><span class="sxs-lookup"><span data-stu-id="8451b-140">Click **Roles**, and then click **Global administrator**.</span></span>
7. <span data-ttu-id="8451b-141">Выберите пункт **лицензии на продукты**, а затем отключите **Enterprise Mobility + Security/Security** , а также лицензии на **Office 365 Корпоративная** .</span><span class="sxs-lookup"><span data-stu-id="8451b-141">Click **Product licenses**, and then turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5 licenses** on.</span></span>
8. <span data-ttu-id="8451b-142">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8451b-142">Click **Add**.</span></span>
9. <span data-ttu-id="8451b-143">На **странице "пользователь добавлен**" снимите флажок **Отправить пароль в сообщении электронной почты**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="8451b-143">On the **User was added page**, clear **Send password in email**, and then click **Close**.</span></span>

<span data-ttu-id="8451b-144">Затем создайте группу с именем Глобаладминс и добавьте в нее учетную запись Дедикатедадмин.</span><span class="sxs-lookup"><span data-stu-id="8451b-144">Next, create a new group named GlobalAdmins and add the DedicatedAdmin account to it.</span></span>

1. <span data-ttu-id="8451b-145">На вкладке **центра администрирования Microsoft 365** щелкните значок группы в левой области навигации, а затем выберите пункт **группы**.</span><span class="sxs-lookup"><span data-stu-id="8451b-145">On the **Microsoft 365 admin center** tab, click the groups icon in the left navigation, and then click **Groups**.</span></span>
2. <span data-ttu-id="8451b-146">Нажмите кнопку **Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="8451b-146">Click **Add a group**.</span></span>
3. <span data-ttu-id="8451b-147">На странице " **Новая группа** " введите **глобаладминс**.</span><span class="sxs-lookup"><span data-stu-id="8451b-147">On the **New Group** page, type **GlobalAdmins**.</span></span>
4. <span data-ttu-id="8451b-148">Нажмите кнопку **Выбрать владельца** , выберите свою учетную запись глобального администратора и нажмите кнопку **Добавить _гт_ закрыть**.</span><span class="sxs-lookup"><span data-stu-id="8451b-148">Click **Select owner** click your global administrator account, and then click **Add > Close**.</span></span>
5. <span data-ttu-id="8451b-149">В списке групп выберите группу **глобаладминс** .</span><span class="sxs-lookup"><span data-stu-id="8451b-149">In the list of groups, click the **GlobalAdmins** group.</span></span>
6. <span data-ttu-id="8451b-150">На странице **глобаладминс** щелкните **изменить для элемента**, а затем нажмите кнопку **Добавить участников**.</span><span class="sxs-lookup"><span data-stu-id="8451b-150">On the **GlobalAdmins** page, click **Edit for Member**, and then click **Add members**.</span></span>
7. <span data-ttu-id="8451b-151">В списке выберите учетную запись **дедикатедадмин** , а затем нажмите кнопку **сохранить _Гт_ закрыть _гт_ закрыть _гт_ центра администрирования**.</span><span class="sxs-lookup"><span data-stu-id="8451b-151">In the list, click the **DedicatedAdmin** account, and then click **Save > Close > Close > Admin center**.</span></span>

<span data-ttu-id="8451b-152">Затем создайте политики условного доступа, чтобы использовать многофакторную проверку подлинности для учетных записей глобального администратора, и запретите проверку подлинности, если риск входа в систему имеет средний или высокий уровень.</span><span class="sxs-lookup"><span data-stu-id="8451b-152">Next, create conditional access policies to require multifactor authentication for global administrator accounts and to deny authentication if the sign-in risk is medium or high.</span></span>

<span data-ttu-id="8451b-153">Эта первая политика требует, чтобы все учетные записи глобального администратора использовали MFA.</span><span class="sxs-lookup"><span data-stu-id="8451b-153">This first policy requires that all global administrator accounts use MFA.</span></span>

1. <span data-ttu-id="8451b-154">На новой вкладке браузера перейдите в [https://portal.azure.com](https://portal.azure.com)раздел.</span><span class="sxs-lookup"><span data-stu-id="8451b-154">In a new tab of your browser, go to [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="8451b-155">Выберите **Azure Active Directory _Гт_ условный доступ**.</span><span class="sxs-lookup"><span data-stu-id="8451b-155">Click **Azure Active Directory > Conditional access**.</span></span>
3. <span data-ttu-id="8451b-156">В колонке **Условный доступ — политики** выберите пункт **Базовая политика: требовать MFA для администраторов (Предварительная версия)**.</span><span class="sxs-lookup"><span data-stu-id="8451b-156">On the **Conditional access – Policies** blade, click **Baseline policy: Require MFA for admins (preview)**.</span></span>
4. <span data-ttu-id="8451b-157">В **базовых политиках...**</span><span class="sxs-lookup"><span data-stu-id="8451b-157">On the **Baseline policies…**</span></span> <span data-ttu-id="8451b-158">колонка, щелкните **использовать политику сразу _Гт_ сохранения**.</span><span class="sxs-lookup"><span data-stu-id="8451b-158">blade, click **Use policy immediately > Save**.</span></span>

<span data-ttu-id="8451b-159">Эта вторая политика блокирует доступ к проверке подлинности глобальной учетной записи администратора, если риск для входа имеет средний или высокий уровень.</span><span class="sxs-lookup"><span data-stu-id="8451b-159">This second policy blocks access to global administrator account authentication when the sign-in risk is medium or high.</span></span>

1. <span data-ttu-id="8451b-160">В колонке **Условный доступ – политики** щелкните **создать политику**.</span><span class="sxs-lookup"><span data-stu-id="8451b-160">On the **Conditional access – Policies** blade, click **New policy**.</span></span>
2. <span data-ttu-id="8451b-161">В **новой** колонке введите **имя**в поле **Глобальные администраторы** .</span><span class="sxs-lookup"><span data-stu-id="8451b-161">On the **New** blade, type **Global administrators** in **Name**.</span></span>
3. <span data-ttu-id="8451b-162">В разделе **назначения** выберите **Пользователи и группы**.</span><span class="sxs-lookup"><span data-stu-id="8451b-162">In the **Assignments** section, click **Users and groups**.</span></span>
4. <span data-ttu-id="8451b-163">На вкладке **включить** в колонке **Пользователи и группы** нажмите **выбрать пользователей и группы _Гт_ пользователи и группы _гт_ выбрать**.</span><span class="sxs-lookup"><span data-stu-id="8451b-163">On the **Include** tab of the **Users and groups** blade, click **Select users and groups > Users and groups > Select**.</span></span>
5. <span data-ttu-id="8451b-164">В колонке **Выбор** выберите **Глобаладминс _Гт_ выберите _гт_ готово**.</span><span class="sxs-lookup"><span data-stu-id="8451b-164">On the **Select** blade, click the **GlobalAdmins > Select > Done**.</span></span>
6. <span data-ttu-id="8451b-165">В разделе **назначения** выберите пункт **условия**.</span><span class="sxs-lookup"><span data-stu-id="8451b-165">In the **Assignments** section, click **Conditions**.</span></span>
7. <span data-ttu-id="8451b-166">В колонке **условия** щелкните элемент **риск входа в**систему, нажмите кнопку **Да** для **настройки**, **выберите Высокая** и **Средняя**, а затем нажмите кнопку **выбрать** и **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8451b-166">On the **Conditions** blade, click **Sign-in risk**, click **Yes** for **Configure**, click **High** and **Medium**, and then click **Select** and **Done**.</span></span>
8. <span data-ttu-id="8451b-167">В разделе **элементы управления доступом** **нового** блейд-сервера нажмите кнопку **предоставить**.</span><span class="sxs-lookup"><span data-stu-id="8451b-167">In the **Access controls** section of the **New** blade, click **Grant**.</span></span>
9. <span data-ttu-id="8451b-168">В колонке **предоставление** выберите пункт **блокировать доступ**, а затем нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="8451b-168">On the **Grant** blade, click **Block access**, and then click **Select**.</span></span>
10. <span data-ttu-id="8451b-169">На **новой** колонке щелкните Включить \*\*\*\* , чтобы **включить политику**, а затем нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="8451b-169">On the **New** blade, click **On** for **Enable policy**, and then click **Create**.</span></span>
11. <span data-ttu-id="8451b-170">Закройте вкладки **портал Azure** и **центр администрирования Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="8451b-170">Close the **Azure portal** and **Microsoft 365 admin center** tabs.</span></span>

<span data-ttu-id="8451b-171">Чтобы проверить первую политику, выйдите из учетной записи Дедикатедадмин и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="8451b-171">To test the first policy, sign out and sign in with the DedicatedAdmin account.</span></span> <span data-ttu-id="8451b-172">Вам будет предложено настроить MFA для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="8451b-172">You should be prompted to configure MFA on the user account.</span></span> <span data-ttu-id="8451b-173">Это показывает, что применяется первая политика.</span><span class="sxs-lookup"><span data-stu-id="8451b-173">This demonstrates that the first policy is being applied.</span></span>

<span data-ttu-id="8451b-174">Сведения и ссылки для защиты учетных записей глобального администратора в рабочей среде приведены в статье [Защита учетных записей глобальных администраторов](identity-designate-protect-admin-accounts.md#identity-global-admin) на этапе идентификации.</span><span class="sxs-lookup"><span data-stu-id="8451b-174">See the [Protect global administrator accounts](identity-designate-protect-admin-accounts.md#identity-global-admin) step in the Identity phase for information and links to protect your global administrator accounts in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="8451b-175">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="8451b-175">Next step</span></span>

<span data-ttu-id="8451b-176">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="8451b-176">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="8451b-177">См. также</span><span class="sxs-lookup"><span data-stu-id="8451b-177">See also</span></span>

[<span data-ttu-id="8451b-178">Шаг 2. Идентификация</span><span class="sxs-lookup"><span data-stu-id="8451b-178">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="8451b-179">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="8451b-179">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="8451b-180">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="8451b-180">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="8451b-181">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="8451b-181">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
