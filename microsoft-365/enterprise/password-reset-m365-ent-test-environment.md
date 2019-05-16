---
title: Сброс пароля для тестовой среды Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Сводка: сведения о том, как настроить и проверить сброс пароля для тестовой среды Microsoft 365.'
ms.openlocfilehash: de025d6b54b3cc1b69c8e50fec428f58d7754dcb
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073119"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="004cf-103">Сброс пароля для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="004cf-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="004cf-104">Функция самостоятельного сброса паролей (SSPR) Azure Active Directory (Azure AD) позволяет пользователям сбрасывать пароли и разблокировать учетные записи.</span><span class="sxs-lookup"><span data-stu-id="004cf-104">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="004cf-105">В этой статье описано, как настроить и проверить сброс паролей в тестовой среде Microsoft 365 в три этапа:</span><span class="sxs-lookup"><span data-stu-id="004cf-105">This article describes how you can configure and test password resets in your Microsoft 365 test environment in three phases:</span></span>

1.  <span data-ttu-id="004cf-106">Создайте среду тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="004cf-106">Create the Microsoft 365 Enterprise test environment.</span></span>
2.  <span data-ttu-id="004cf-107">Включите обратную запись пароля.</span><span class="sxs-lookup"><span data-stu-id="004cf-107">Enable password writeback.</span></span>
3.  <span data-ttu-id="004cf-108">Настройте и проверьте сброс паролей для учетной записи "Пользователь 2".</span><span class="sxs-lookup"><span data-stu-id="004cf-108">Configure and test password reset for the User 2 account.</span></span>
    
![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="004cf-110">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="004cf-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="004cf-111">Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="004cf-111">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="004cf-p101">Сначала выполните инструкции из статьи [Синхронизация хэша паролей](password-hash-sync-m365-ent-test-environment.md). Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="004cf-p101">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="004cf-115">Конфигурация состоит из следующих компонентов: </span><span class="sxs-lookup"><span data-stu-id="004cf-115">This configuration consists of:</span></span> 
  
- <span data-ttu-id="004cf-116">Пробные или платные подписки на Office 365 E5 и EMS E5.</span><span class="sxs-lookup"><span data-stu-id="004cf-116">Office 365 E5 and EMS E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="004cf-117">Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure.</span><span class="sxs-lookup"><span data-stu-id="004cf-117">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="004cf-118">Azure AD Connect работает на APP1 для синхронизации домена TESTLAB доменных служб Active Directory (AD DS) с клиентом Azure AD, связанным с подписками на Office 365 и EMS E5.</span><span class="sxs-lookup"><span data-stu-id="004cf-118">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>


## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="004cf-119">Этап 2. Включений обратной записи паролей</span><span class="sxs-lookup"><span data-stu-id="004cf-119">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="004cf-120">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для обратной записи пароля](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="004cf-120">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="004cf-121">Чтобы использовать сброс пароля, необходимо включить обратную запись пароля.</span><span class="sxs-lookup"><span data-stu-id="004cf-121">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="004cf-122">Этап 3. Настройка и проверка сброса паролей</span><span class="sxs-lookup"><span data-stu-id="004cf-122">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="004cf-123">На этом этапе настраивается и проверяется сброс паролей в клиенте Azure AD благодаря членству в группе.</span><span class="sxs-lookup"><span data-stu-id="004cf-123">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="004cf-124">Сперва включите сброс паролей для учетных записей в определенной группе Azure AD.</span><span class="sxs-lookup"><span data-stu-id="004cf-124">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="004cf-125">Откройте браузер в приватном режиме, откройте [https://portal.azure.com](https://portal.azure.com), а затем выполните вход, используя учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="004cf-125">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="004cf-126">На портале Azure выберите **Azure Active Directory > Группы > Создать группу**.</span><span class="sxs-lookup"><span data-stu-id="004cf-126">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="004cf-p102">Для параметра **Тип группы** настройте значение **Безопасность**, для параметра **Имя группы** — значение **PWReset**, а для параметра **Тип членства** — значение **Назначено**. Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="004cf-p102">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**. Click **Create**.</span></span>
5. <span data-ttu-id="004cf-129">Выберите в списке группу **PWReset** и щелкните **Члены**.</span><span class="sxs-lookup"><span data-stu-id="004cf-129">Click the **PWReset** group in the list, and then click **Members**.</span></span>
6. <span data-ttu-id="004cf-p103">Последовательно щелкните **Добавить участников**, **Пользователь 2**, **Выбрать**. Закройте страницы **PWReset** и **Группа**.</span><span class="sxs-lookup"><span data-stu-id="004cf-p103">Click **Add members**, click **User 2**, and then click **Select**. Close the **PWReset** and **Group** pages.</span></span>
7. <span data-ttu-id="004cf-132">На странице Azure Active Directory выберите **Сброс пароля**.</span><span class="sxs-lookup"><span data-stu-id="004cf-132">On the Azure Active Directory page, click **Password reset**.</span></span>
8. <span data-ttu-id="004cf-133">На странице **Свойства** щелкните **Выбрано** в разделе **Разрешен самостоятельный сброс пароля**.</span><span class="sxs-lookup"><span data-stu-id="004cf-133">From the **Properties** page, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
9. <span data-ttu-id="004cf-134">В разделе **Выбор группы** выберите **PWReset** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="004cf-134">From **Select group**, select **PWReset**, and then click **Save**.</span></span>
10. <span data-ttu-id="004cf-135">Закройте браузер, открытый в приватном режиме.</span><span class="sxs-lookup"><span data-stu-id="004cf-135">Close the private browser instance.</span></span>

<span data-ttu-id="004cf-136">Далее проверьте сброс паролей для учетной записи "Пользователь 2".</span><span class="sxs-lookup"><span data-stu-id="004cf-136">Next, you test password reset for the User 2 account.</span></span>

1. <span data-ttu-id="004cf-137">Откройте новое окно браузера в приватном режиме и перейдите к [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="004cf-137">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="004cf-138">Войдите в учетную запись "Пользователь 2".</span><span class="sxs-lookup"><span data-stu-id="004cf-138">Sign in with the User 2 account credentials.</span></span>
3. <span data-ttu-id="004cf-139">В разделе **Не утратьте доступ к учетной записи** укажите в качестве телефона для проверки подлинности свой номер мобильного телефона, а в качестве электронной почты для проверки подлинности — личную учетную запись электронной почты.</span><span class="sxs-lookup"><span data-stu-id="004cf-139">In **Don’t lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
4. <span data-ttu-id="004cf-140">После проверки обоих параметров выберите **Все правильно** и закройте браузер, открытый в приватном режиме.</span><span class="sxs-lookup"><span data-stu-id="004cf-140">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
5. <span data-ttu-id="004cf-141">Откройте новое окно браузера в приватном режиме и перейдите к [https://aka.ms/sspr](https://aka.ms/sspr).</span><span class="sxs-lookup"><span data-stu-id="004cf-141">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
6. <span data-ttu-id="004cf-142">Войдите в учетную запись "Пользователь 2", введите символы CAPTCHA, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="004cf-142">Sign in with the User 2 account credentials, type the characters from the CAPTCHA, and then click **Next**.</span></span>
8. <span data-ttu-id="004cf-p104">Для параметра **Шаг проверки 1** укажите **Письмо на запасной адрес электронной почты** и выберите **Почта**. Когда получите такое сообщение, введите проверочный код и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="004cf-p104">For **verification step 1**, click **Email my alternate email**, and then click **Email**. When you receive the email, type the verification code, and then click **Next**.</span></span>
9. <span data-ttu-id="004cf-p105">В разделе **Возвращение в учетную запись** введите новый пароль для учетной записи "Пользователь 2" и нажмите кнопку **Готово**. Запишите измененный пароль для учетной записи "Пользователь 2" и сохраните в безопасном расположении.</span><span class="sxs-lookup"><span data-stu-id="004cf-p105">In **Get back into your account**, type a new password for the User 2 account, and then click **Finish**. Note the changed password of the User 2 account and store it in a safe location.</span></span>
10. <span data-ttu-id="004cf-147">На отдельной вкладке того же браузера перейдите к [https://portal.office.com](https://portal.office.com), а затем выполните вход, используя новый пароль и имя учетной записи "Пользователь 2".</span><span class="sxs-lookup"><span data-stu-id="004cf-147">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 2 account name and its new password.</span></span> <span data-ttu-id="004cf-148">Откроется **Домашняя страница Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="004cf-148">You should see the **Microsoft Office Home** page.</span></span>

<span data-ttu-id="004cf-149">Информацию и ссылки для настройки сброса паролей в рабочей среде вы найдете в описании шага [Простой сброс паролей](identity-password-reset.md#identity-pw-reset) этапа "Идентификация".</span><span class="sxs-lookup"><span data-stu-id="004cf-149">See the [Simplify password resets](identity-password-reset.md#identity-pw-reset) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="004cf-150">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="004cf-150">Next step</span></span>

<span data-ttu-id="004cf-151">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="004cf-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="004cf-152">См. также</span><span class="sxs-lookup"><span data-stu-id="004cf-152">See also</span></span>

[<span data-ttu-id="004cf-153">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="004cf-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="004cf-154">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="004cf-154">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="004cf-155">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="004cf-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
