---
title: Сброс пароля для тестовой среды Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Сводка: сведения о том, как настроить и проверить сброс пароля для тестовой среды Microsoft 365.'
ms.openlocfilehash: 98e6b8d8432c86e9d1c432128ed6d223da83610e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686540"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="0aba7-103">Сброс пароля для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0aba7-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="0aba7-104">*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для тестовых сред предприятия.*</span><span class="sxs-lookup"><span data-stu-id="0aba7-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="0aba7-105">Функция самостоятельного сброса паролей (SSPR) Azure Active Directory (Azure AD) позволяет пользователям сбрасывать пароли и разблокировать учетные записи.</span><span class="sxs-lookup"><span data-stu-id="0aba7-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> 

<span data-ttu-id="0aba7-106">В этой статье описано, как настроить и проверить сброс паролей в тестовой среде Microsoft 365 в три этапа:</span><span class="sxs-lookup"><span data-stu-id="0aba7-106">This article describes how you can configure and test password resets in your Microsoft 365 test environment in three phases:</span></span>

1.    <span data-ttu-id="0aba7-107">Создайте тестовую среду Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="0aba7-107">Create the Microsoft 365 for enterprise test environment.</span></span>
2.  <span data-ttu-id="0aba7-108">Включите обратную запись пароля.</span><span class="sxs-lookup"><span data-stu-id="0aba7-108">Enable password writeback.</span></span>
3.    <span data-ttu-id="0aba7-109">Настройте и проверьте сброс паролей для учетной записи "Пользователь 3".</span><span class="sxs-lookup"><span data-stu-id="0aba7-109">Configure and test password reset for the User 3 account.</span></span>
    
![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="0aba7-111">Щелкните [здесь](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 для крупных предприятий.</span><span class="sxs-lookup"><span data-stu-id="0aba7-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="0aba7-112">Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0aba7-112">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="0aba7-p101">Сначала выполните инструкции из статьи [Синхронизация хэша паролей](password-hash-sync-m365-ent-test-environment.md). Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="0aba7-p101">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="0aba7-116">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="0aba7-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="0aba7-117">Пробная или платная подписка Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="0aba7-117">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="0aba7-118">Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure.</span><span class="sxs-lookup"><span data-stu-id="0aba7-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="0aba7-119">Azure AD Connect работает на APP1 для синхронизации домена TESTLAB доменных служб Active Directory (AD DS) с клиентом Azure AD, связанным с подпиской Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0aba7-119">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="0aba7-120">Этап 2. Включений обратной записи паролей</span><span class="sxs-lookup"><span data-stu-id="0aba7-120">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="0aba7-121">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для обратной записи пароля](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="0aba7-121">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="0aba7-122">Чтобы использовать сброс пароля, необходимо включить обратную запись пароля.</span><span class="sxs-lookup"><span data-stu-id="0aba7-122">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="0aba7-123">Этап 3. Настройка и проверка сброса паролей</span><span class="sxs-lookup"><span data-stu-id="0aba7-123">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="0aba7-124">На этом этапе настраивается и проверяется сброс паролей в клиенте Azure AD благодаря членству в группе.</span><span class="sxs-lookup"><span data-stu-id="0aba7-124">In this phase, you configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="0aba7-125">Сперва включите сброс паролей для учетных записей в определенной группе Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0aba7-125">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="0aba7-126">Откройте браузер в приватном режиме, откройте [https://portal.azure.com](https://portal.azure.com), а затем выполните вход, используя учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="0aba7-126">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="0aba7-127">На портале Azure выберите **Azure Active Directory > Группы > Создать группу**.</span><span class="sxs-lookup"><span data-stu-id="0aba7-127">In the Azure portal, click **Azure Active Directory > Groups > New group**.</span></span>
3. <span data-ttu-id="0aba7-128">Для параметра **Тип группы** настройте значение **Безопасность**, для параметра **Имя группы** — значение **PWReset**, а для параметра **Тип членства** — значение **Назначено**.</span><span class="sxs-lookup"><span data-stu-id="0aba7-128">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span> 
4. <span data-ttu-id="0aba7-129">Нажмите кнопку **Участники**, найдите и выберите **Пользователь 3**, а затем щелкните **Выбрать**и **Создать**.</span><span class="sxs-lookup"><span data-stu-id="0aba7-129">Click **Members**, find and select **User 3**, and then click **Select**, and then click **Create**.</span></span>
5. <span data-ttu-id="0aba7-130">Закройте панель **Группы**.</span><span class="sxs-lookup"><span data-stu-id="0aba7-130">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="0aba7-131">На панели Azure Active Directory щелкните**Сброс пароля** в панели навигации слева.</span><span class="sxs-lookup"><span data-stu-id="0aba7-131">In the Azure Active Directory pane, click **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="0aba7-132">На панели **Сброс пароля - Свойства** щелкните **Выбрано** в разделе **Разрешен самостоятельный сброс пароля**.</span><span class="sxs-lookup"><span data-stu-id="0aba7-132">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="0aba7-133">Нажмите **Выбрать группу**, выберите группу **PWReset**, а затем щелкните **Выбрать > Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0aba7-133">Click **Select group**, select the **PWReset** group, and then click **Select > Save**.</span></span>
9. <span data-ttu-id="0aba7-134">Закройте браузер, открытый в приватном режиме.</span><span class="sxs-lookup"><span data-stu-id="0aba7-134">Close the private browser instance.</span></span>

<span data-ttu-id="0aba7-135">Далее проверьте сброс паролей для учетной записи "Пользователь 3".</span><span class="sxs-lookup"><span data-stu-id="0aba7-135">Next, you test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="0aba7-136">Откройте новое окно браузера в приватном режиме и перейдите к [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="0aba7-136">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
2. <span data-ttu-id="0aba7-137">Войдите с помощью учетной записи "Пользователь 3".</span><span class="sxs-lookup"><span data-stu-id="0aba7-137">Sign in with the User 3 account credentials.</span></span>
3. <span data-ttu-id="0aba7-138">В окне **Требуются дополнительные сведения** щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0aba7-138">In **More information required**, click **Next**.</span></span> 
5. <span data-ttu-id="0aba7-139">В разделе **Не утратьте доступ к учетной записи** укажите в качестве телефона для проверки подлинности свой номер мобильного телефона, а в качестве электронной почты для проверки подлинности — свою личную учетную запись электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0aba7-139">In **Don't lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
7. <span data-ttu-id="0aba7-140">После проверки обоих параметров выберите **Все правильно** и закройте браузер, открытый в приватном режиме.</span><span class="sxs-lookup"><span data-stu-id="0aba7-140">After both are verified, click **Looks good** and close the private instance of the browser.</span></span>
8. <span data-ttu-id="0aba7-141">Откройте новое окно браузера в приватном режиме и перейдите к [https://aka.ms/sspr](https://aka.ms/sspr).</span><span class="sxs-lookup"><span data-stu-id="0aba7-141">Open a new private browser instance and go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
9. <span data-ttu-id="0aba7-142">Введите имя учетной записи "Пользователь 3", введите символы CAPTCHA, нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0aba7-142">Type the User 3 account name, type the characters from the CAPTCHA, and then click **Next**.</span></span>
10. <span data-ttu-id="0aba7-p102">Для параметра **Шаг проверки 1** укажите **Письмо на запасной адрес электронной почты** и выберите **Почта**. Когда получите такое сообщение, введите проверочный код и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0aba7-p102">For **verification step 1**, click **Email my alternate email**, and then click **Email**. When you receive the email, type the verification code, and then click **Next**.</span></span>
11. <span data-ttu-id="0aba7-145">В окне **Вернуться в свою учетную запись** введите новый пароль учетной записи для пользователя 3 и нажмите кнопку **Завершить**.</span><span class="sxs-lookup"><span data-stu-id="0aba7-145">In **Get back into your account**, type a new password for the User 3 account, and then click **Finish**.</span></span> <span data-ttu-id="0aba7-146">Запишите измененный пароль учетной записи пользователя 3 и храните его в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="0aba7-146">Note the changed password of the User 3 account and store it in a safe location.</span></span>
12. <span data-ttu-id="0aba7-147">На отдельной вкладке того же браузера перейдите к [https://portal.office.com](https://portal.office.com), а затем выполните вход, используя новый пароль и имя учетной записи "Пользователь 3".</span><span class="sxs-lookup"><span data-stu-id="0aba7-147">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="0aba7-148">Откроется **Домашняя страница Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="0aba7-148">You should see the **Microsoft Office Home** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="0aba7-149">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="0aba7-149">Next step</span></span>

<span data-ttu-id="0aba7-150">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="0aba7-150">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="0aba7-151">См. также</span><span class="sxs-lookup"><span data-stu-id="0aba7-151">See also</span></span>

[<span data-ttu-id="0aba7-152">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="0aba7-152">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="0aba7-153">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="0aba7-153">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="0aba7-154">Microsoft 365 для корпоративных документов</span><span class="sxs-lookup"><span data-stu-id="0aba7-154">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
