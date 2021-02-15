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
ms.openlocfilehash: 5d98dcc50f16bc08da787a928beeeacf825201c9
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487428"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="e0789-103">Сброс пароля для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0789-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="e0789-104">*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для корпоративных тестовых сред.*</span><span class="sxs-lookup"><span data-stu-id="e0789-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="e0789-105">Функция самостоятельного сброса паролей (SSPR) Azure Active Directory (Azure AD) позволяет пользователям сбрасывать пароли и разблокировать учетные записи.</span><span class="sxs-lookup"><span data-stu-id="e0789-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span>

<span data-ttu-id="e0789-106">В этой статье описывается настройка и проверка сброса паролей в тестовой среде Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0789-106">This article describes how to configure and test password resets in your Microsoft 365 test environment.</span></span>

<span data-ttu-id="e0789-107">Настройка SSPR состоит из трех этапов:</span><span class="sxs-lookup"><span data-stu-id="e0789-107">Setting up SSPR involves three phases:</span></span>
- [<span data-ttu-id="e0789-108">Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0789-108">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="e0789-109">Этап 2. Включений обратной записи паролей</span><span class="sxs-lookup"><span data-stu-id="e0789-109">Phase 2: Enable password writeback</span></span>](#phase-2-enable-password-writeback)
- [<span data-ttu-id="e0789-110">Этап 3. Настройка и проверка сброса паролей</span><span class="sxs-lookup"><span data-stu-id="e0789-110">Phase 3: Configure and test password reset</span></span>](#phase-3-configure-and-test-password-reset)
    
![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="e0789-112">Чтобы получить визуальную карту со всеми статьями в руководстве по лаборатории тестирования Microsoft 365 для предприятий, перейдите в стек руководств по лаборатории тестирования [Microsoft 365 для предприятий.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="e0789-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="e0789-113">Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e0789-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="e0789-114">Сначала следуйте инструкциям в синхронизации [паролей.](password-hash-sync-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="e0789-114">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="e0789-115">Итоговая конфигурация выглядит так:</span><span class="sxs-lookup"><span data-stu-id="e0789-115">Your resulting configuration looks like this:</span></span>
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="e0789-117">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="e0789-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="e0789-118">Пробная или платная подписка Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e0789-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="e0789-119">Упрощенная интрасеть организации, подключенная к Интернету, состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="e0789-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="e0789-120">Azure AD Connect работает на APP1 для синхронизации домена TESTLAB доменных служб Active Directory (AD DS) с клиентом Azure AD, связанным с подпиской Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0789-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="e0789-121">Этап 2. Включений обратной записи паролей</span><span class="sxs-lookup"><span data-stu-id="e0789-121">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="e0789-122">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для обратной записи пароля](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="e0789-122">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="e0789-123">Чтобы использовать сброс пароля, необходимо включить обратную запись пароля.</span><span class="sxs-lookup"><span data-stu-id="e0789-123">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="e0789-124">Этап 3. Настройка и проверка сброса паролей</span><span class="sxs-lookup"><span data-stu-id="e0789-124">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="e0789-125">На этом этапе настройте сброс пароля в клиенте Azure AD с помощью членства в группах, а затем убедитесь, что он работает.</span><span class="sxs-lookup"><span data-stu-id="e0789-125">In this phase, configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="e0789-126">Сперва включите сброс паролей для учетных записей в определенной группе Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e0789-126">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="e0789-127">Откройте браузер в приватном режиме, откройте [https://portal.azure.com](https://portal.azure.com), а затем выполните вход, используя учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="e0789-127">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="e0789-128">На портале Azure выберите новую **группу групп Azure Active Directory.**  >    >  </span><span class="sxs-lookup"><span data-stu-id="e0789-128">In the Azure portal, select **Azure Active Directory** > **Groups** > **New group**.</span></span>
3. <span data-ttu-id="e0789-129">Для параметра **Тип группы** настройте значение **Безопасность**, для параметра **Имя группы** — значение **PWReset**, а для параметра **Тип членства** — значение **Назначено**.</span><span class="sxs-lookup"><span data-stu-id="e0789-129">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span>
4. <span data-ttu-id="e0789-130">Select **Members**, find and select **User 3,** select **Select**, and then select **Create**.</span><span class="sxs-lookup"><span data-stu-id="e0789-130">Select **Members**, find and select **User 3**, select **Select**, and then select **Create**.</span></span>
5. <span data-ttu-id="e0789-131">Закройте панель **Группы**.</span><span class="sxs-lookup"><span data-stu-id="e0789-131">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="e0789-132">В области Azure Active Directory выберите сброс пароля **в** области навигации слева.</span><span class="sxs-lookup"><span data-stu-id="e0789-132">In the Azure Active Directory pane, select **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="e0789-133">На панели **Сброс пароля - Свойства** щелкните **Выбрано** в разделе **Разрешен самостоятельный сброс пароля**.</span><span class="sxs-lookup"><span data-stu-id="e0789-133">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="e0789-134">Выберите **"Выбрать группу",** выберите группу **PWReset** и выберите **"Сохранить".**  >  </span><span class="sxs-lookup"><span data-stu-id="e0789-134">Select **Select group**, select the **PWReset** group, and then select **Select** > **Save**.</span></span>
9. <span data-ttu-id="e0789-135">Закройте браузер, открытый в приватном режиме.</span><span class="sxs-lookup"><span data-stu-id="e0789-135">Close the private browser instance.</span></span>

<span data-ttu-id="e0789-136">Затем протестировать сброс пароля для учетной записи User 3.</span><span class="sxs-lookup"><span data-stu-id="e0789-136">Next, test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="e0789-137">Откройте новое окно браузера в приватном режиме и перейдите к [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="e0789-137">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
1. <span data-ttu-id="e0789-138">Войдите с помощью учетной записи "Пользователь 3".</span><span class="sxs-lookup"><span data-stu-id="e0789-138">Sign in with the User 3 account credentials.</span></span>
1. <span data-ttu-id="e0789-139">In **More information required,** select **Next**.</span><span class="sxs-lookup"><span data-stu-id="e0789-139">In **More information required**, select **Next**.</span></span> 
1. <span data-ttu-id="e0789-140">В разделе **Не утратьте доступ к учетной записи** укажите в качестве телефона для проверки подлинности свой номер мобильного телефона, а в качестве электронной почты для проверки подлинности — свою личную учетную запись электронной почты.</span><span class="sxs-lookup"><span data-stu-id="e0789-140">In **Don't lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
1. <span data-ttu-id="e0789-141">После проверки обоих окей выберите **"Выглядит хорошо"** и закроет частный экземпляр браузера.</span><span class="sxs-lookup"><span data-stu-id="e0789-141">After both are verified, select **Looks good**, and then close the private instance of the browser.</span></span>
1. <span data-ttu-id="e0789-142">В новом экземпляре частного браузера перейдите к [https://aka.ms/sspr](https://aka.ms/sspr) .</span><span class="sxs-lookup"><span data-stu-id="e0789-142">In a new private browser instance, go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
1. <span data-ttu-id="e0789-143">Введите имя учетной записи User 3, введите символы из CAPTCHA и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="e0789-143">Enter the User 3 account name, enter the characters from the CAPTCHA, and then select **Next**.</span></span>
1. <span data-ttu-id="e0789-144">Для **проверки на шаге 1** выберите "Отправить по **электронной почте"** альтернативное сообщение электронной почты, а затем выберите "Электронная **почта".**</span><span class="sxs-lookup"><span data-stu-id="e0789-144">For **verification step 1**, select **Email my alternate email**, and then select **Email**.</span></span> <span data-ttu-id="e0789-145">Когда вы получите сообщение электронной почты, введите код проверки и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="e0789-145">When you receive the email, enter the verification code, and then select **Next**.</span></span>
1. <span data-ttu-id="e0789-146">In **Get back into your account,** enter a new password for the User 3 account, and then select **Finish**.</span><span class="sxs-lookup"><span data-stu-id="e0789-146">In **Get back into your account**, enter a new password for the User 3 account, and then select **Finish**.</span></span> <span data-ttu-id="e0789-147">Запишите измененный пароль учетной записи пользователя 3 и храните его в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="e0789-147">Note the changed password of the User 3 account and store it in a safe location.</span></span>
1. <span data-ttu-id="e0789-148">На отдельной вкладке того же браузера перейдите к [https://portal.office.com](https://portal.office.com), а затем выполните вход, используя новый пароль и имя учетной записи "Пользователь 3".</span><span class="sxs-lookup"><span data-stu-id="e0789-148">In a separate tab of the same browser, go to [https://portal.office.com](https://portal.office.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="e0789-149">Откроется **Домашняя страница Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="e0789-149">You should see the **Microsoft Office Home** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="e0789-150">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="e0789-150">Next step</span></span>

<span data-ttu-id="e0789-151">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="e0789-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0789-152">См. также</span><span class="sxs-lookup"><span data-stu-id="e0789-152">See also</span></span>

[<span data-ttu-id="e0789-153">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="e0789-153">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e0789-154">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="e0789-154">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e0789-155">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="e0789-155">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
