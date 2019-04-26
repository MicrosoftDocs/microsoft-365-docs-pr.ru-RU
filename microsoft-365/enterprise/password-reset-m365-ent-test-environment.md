---
title: Сброс пароля для тестовой среды Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
ms.audience: ITPro
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
ms.openlocfilehash: f5fc8d68493464d6b4a6ffdcda64ed9a0d8c7cdd
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289470"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="36061-103">Сброс пароля для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="36061-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="36061-104">Функция самостоятельного сброса паролей (SSPR) Azure AD позволяет пользователям сбрасывать пароли и разблокировать учетные записи.</span><span class="sxs-lookup"><span data-stu-id="36061-104">Azure AD self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="36061-105">В этой статье описано, как настроить и проверить сброс паролей в тестовой среде Microsoft 365 в два этапа:</span><span class="sxs-lookup"><span data-stu-id="36061-105">This article describes how you can configure and test password resets in your Microsoft 365 test environment in two phases:</span></span>

1.  <span data-ttu-id="36061-106">Создайте среду тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="36061-106">Create the Microsoft 365 simulated enterprise test environment.</span></span>
2.  <span data-ttu-id="36061-107">Настройте и проверьте сброс паролей для учетной записи "Пользователь 2".</span><span class="sxs-lookup"><span data-stu-id="36061-107">Configure and test password reset for the User 2 account.</span></span>
    
![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="36061-109">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="36061-109">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-password-hash-synchronization-and-password-writebback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="36061-110">Этап 1. Настройка синхронизации хэша паролей и обратной записи паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="36061-110">Phase 1: Configure password hash synchronization and password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="36061-p101">Сначала выполните инструкции из статьи [Синхронизация хэша паролей](password-hash-sync-m365-ent-test-environment.md). Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="36061-p101">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="36061-114">Конфигурация состоит из следующих компонентов: </span><span class="sxs-lookup"><span data-stu-id="36061-114">This configuration consists of:</span></span> 
  
- <span data-ttu-id="36061-115">Пробные или платные подписки на Office 365 E5 и EMS E5.</span><span class="sxs-lookup"><span data-stu-id="36061-115">Office 365 E5 and EMS E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="36061-116">Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure.</span><span class="sxs-lookup"><span data-stu-id="36061-116">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="36061-117">Azure AD Connect работает на APP1 для синхронизации домена AD DS TESTLAB с клиентом Azure AD, связанным с подписками на Office 365 и EMS E5.</span><span class="sxs-lookup"><span data-stu-id="36061-117">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

<span data-ttu-id="36061-118">Затем выполните инструкции [этапа 2 по обратной записи пароля](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) из руководства по лаборатории тестирования.</span><span class="sxs-lookup"><span data-stu-id="36061-118">Next, follow the instructions in [Phase 2 of the password reset](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) Test Lab Guide.</span></span>

<span data-ttu-id="36061-119">Чтобы использовать сброс пароля, необходимо включить обратную запись пароля.</span><span class="sxs-lookup"><span data-stu-id="36061-119">You must have password reset enabled to use password writeback.</span></span>
  
## <a name="phase-2-configure-and-test-password-reset"></a><span data-ttu-id="36061-120">Этап 2. Настройка и проверка сброса паролей</span><span class="sxs-lookup"><span data-stu-id="36061-120">Phase 2: Configure and test password reset</span></span>

<span data-ttu-id="36061-121">На этом этапе настраивается и проверяется сброс паролей в клиенте Azure AD благодаря членству в группе.</span><span class="sxs-lookup"><span data-stu-id="36061-121">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="36061-122">Сперва включите сброс паролей для учетных записей в определенной группе Azure AD.</span><span class="sxs-lookup"><span data-stu-id="36061-122">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="36061-123">Откройте браузер в приватном режиме, откройте [https://portal.azure.com](https://portal.azure.com), а затем выполните вход, используя учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="36061-123">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="36061-124">На портале Azure выберите **Azure Active Directory > Группы > Создать группу**.</span><span class="sxs-lookup"><span data-stu-id="36061-124">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="36061-p102">Для параметра **Тип группы** настройте значение **Безопасность**, для параметра **Имя группы** — значение **PWReset**, а для параметра **Тип членства** — значение **Назначено**. Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="36061-p102">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**. Click **Create**.</span></span>
5. <span data-ttu-id="36061-127">Выберите в списке группу **PWReset** и щелкните **Члены**.</span><span class="sxs-lookup"><span data-stu-id="36061-127">Click the **PWReset** group in the list, and then click **Members**.</span></span>
6. <span data-ttu-id="36061-p103">Последовательно щелкните **Добавить участников**, **Пользователь 2**, **Выбрать**. Закройте страницы **PWReset** и **Группа**.</span><span class="sxs-lookup"><span data-stu-id="36061-p103">Click **Add members**, click **User 2**, and then click **Select**. Close the **PWReset** and **Group** pages.</span></span>
7. <span data-ttu-id="36061-130">На странице Azure Active Directory выберите **Сброс пароля**.</span><span class="sxs-lookup"><span data-stu-id="36061-130">On the Azure Active Directory page, click **Password reset**.</span></span>
8. <span data-ttu-id="36061-131">На странице **Свойства** щелкните **Выбрано** в разделе **Разрешен самостоятельный сброс пароля**.</span><span class="sxs-lookup"><span data-stu-id="36061-131">From the **Properties** page, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
9. <span data-ttu-id="36061-132">В разделе **Выбор группы** выберите **PWReset** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="36061-132">From **Select group**, select **PWReset**, and then click **Save**.</span></span>
10. <span data-ttu-id="36061-133">Закройте браузер, открытый в приватном режиме.</span><span class="sxs-lookup"><span data-stu-id="36061-133">Close the private browser instance.</span></span>

<span data-ttu-id="36061-134">Далее проверьте сброс паролей для учетной записи "Пользователь 2".</span><span class="sxs-lookup"><span data-stu-id="36061-134">Next, you test password reset for the User 2 account.</span></span>

1. <span data-ttu-id="36061-135">Откройте новое окно браузера в приватном режиме и перейдите к [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="36061-135">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="36061-136">Войдите в учетную запись "Пользователь 2".</span><span class="sxs-lookup"><span data-stu-id="36061-136">Sign in with the User 2 account credentials.</span></span>
3. <span data-ttu-id="36061-137">В разделе **Не утратьте доступ к учетной записи** укажите в качестве телефона для проверки подлинности свой номер мобильного телефона, а в качестве электронной почты для проверки подлинности — личную учетную запись электронной почты.</span><span class="sxs-lookup"><span data-stu-id="36061-137">In **Don’t lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
4. <span data-ttu-id="36061-138">После проверки обоих параметров выберите **Все правильно** и закройте браузер, открытый в приватном режиме.</span><span class="sxs-lookup"><span data-stu-id="36061-138">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
5. <span data-ttu-id="36061-139">Откройте новое окно браузера в приватном режиме и перейдите к [https://aka.ms/sspr](https://aka.ms/sspr).</span><span class="sxs-lookup"><span data-stu-id="36061-139">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
6. <span data-ttu-id="36061-140">Войдите в учетную запись "Пользователь 2", введите символы CAPTCHA, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="36061-140">Sign in with the User 2 account credentials, type the characters from the CAPTCHA, and then click **Next**.</span></span>
8. <span data-ttu-id="36061-p104">Для параметра **Шаг проверки 1** укажите **Письмо на запасной адрес электронной почты** и выберите **Почта**. Когда получите такое сообщение, введите проверочный код и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="36061-p104">For **verification step 1**, click **Email my alternate email**, and then click **Email**. When you receive the email, type the verification code, and then click **Next**.</span></span>
9. <span data-ttu-id="36061-p105">В разделе **Возвращение в учетную запись** введите новый пароль для учетной записи "Пользователь 2" и нажмите кнопку **Готово**. Запишите измененный пароль для учетной записи "Пользователь 2" и сохраните в безопасном расположении.</span><span class="sxs-lookup"><span data-stu-id="36061-p105">In **Get back into your account**, type a new password for the User 2 account, and then click **Finish**. Note the changed password of the User 2 account and store it in a safe location.</span></span>
10. <span data-ttu-id="36061-p106">На отдельной вкладке того же браузера перейдите к [https://office.com](https://office.com), а затем выполните вход, используя новый пароль и имя учетной записи "Пользователь 2". Откроется страница **Домашняя страница Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="36061-p106">In a separate tab of the same browser, go to [https://office.com](https://office.com), and then sign in with the User 2 account name and its new password. You should see the **Office Home** page.</span></span>

<span data-ttu-id="36061-147">Информацию и ссылки для настройки сброса паролей в рабочей среде вы найдете в описании шага [Простой сброс паролей](identity-password-reset.md#identity-pw-reset) этапа "Идентификация".</span><span class="sxs-lookup"><span data-stu-id="36061-147">See the [Simplify password resets](identity-password-reset.md#identity-pw-reset) step in the Identity phase for information and links to configure password resets in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="36061-148">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="36061-148">Next step</span></span>

<span data-ttu-id="36061-149">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="36061-149">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="36061-150">См. также</span><span class="sxs-lookup"><span data-stu-id="36061-150">See also</span></span>

[<span data-ttu-id="36061-151">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="36061-151">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="36061-152">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="36061-152">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="36061-153">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="36061-153">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
