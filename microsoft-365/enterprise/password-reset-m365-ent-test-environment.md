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
ms.openlocfilehash: 13169824866e91c1a09d412a875d2f4ce4391fa8
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339386"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="4de0d-103">Сброс пароля для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4de0d-103">Password reset for your Microsoft 365 test environment</span></span>

<span data-ttu-id="4de0d-104">*Это руководство по тестовой лаборатории можно использовать только для Microsoft 365 для корпоративных тестовых сред.*</span><span class="sxs-lookup"><span data-stu-id="4de0d-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="4de0d-105">Функция самостоятельного сброса паролей (SSPR) Azure Active Directory (Azure AD) позволяет пользователям сбрасывать пароли и разблокировать учетные записи.</span><span class="sxs-lookup"><span data-stu-id="4de0d-105">Azure Active Directory (Azure AD) self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span>

<span data-ttu-id="4de0d-106">В этой статье описывается настройка и тестирование сброса пароля в Microsoft 365 тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="4de0d-106">This article describes how to configure and test password resets in your Microsoft 365 test environment.</span></span>

<span data-ttu-id="4de0d-107">Настройка SSPR включает три этапа:</span><span class="sxs-lookup"><span data-stu-id="4de0d-107">Setting up SSPR involves three phases:</span></span>
- [<span data-ttu-id="4de0d-108">Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4de0d-108">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="4de0d-109">Этап 2. Включений обратной записи паролей</span><span class="sxs-lookup"><span data-stu-id="4de0d-109">Phase 2: Enable password writeback</span></span>](#phase-2-enable-password-writeback)
- [<span data-ttu-id="4de0d-110">Этап 3. Настройка и проверка сброса паролей</span><span class="sxs-lookup"><span data-stu-id="4de0d-110">Phase 3: Configure and test password reset</span></span>](#phase-3-configure-and-test-password-reset)
    
![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="4de0d-112">Чтобы получить визуальную карту для всех статей в стеке руководства по Microsoft 365 для корпоративной лаборатории тестирования, перейдите Microsoft 365 для корпоративного руководства по [лаборатории тестирования.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="4de0d-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="4de0d-113">Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4de0d-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="4de0d-114">Во-первых, следуйте инструкциям в [синхронизации с hash паролем](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="4de0d-114">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="4de0d-115">В результате конфигурация выглядит так:</span><span class="sxs-lookup"><span data-stu-id="4de0d-115">Your resulting configuration looks like this:</span></span>
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="4de0d-117">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="4de0d-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="4de0d-118">Пробная или платная подписка Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4de0d-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="4de0d-119">Упрощенная интрасеть организации, подключенная к Интернету, состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="4de0d-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="4de0d-120">Azure AD Connect работает на APP1 для синхронизации домена TESTLAB доменных служб Active Directory (AD DS) с клиентом Azure AD, связанным с подпиской Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4de0d-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback"></a><span data-ttu-id="4de0d-121">Этап 2. Включений обратной записи паролей</span><span class="sxs-lookup"><span data-stu-id="4de0d-121">Phase 2: Enable password writeback</span></span>

<span data-ttu-id="4de0d-122">Выполните инструкции [этапа 2 руководства по лаборатории тестирования для обратной записи пароля](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span><span class="sxs-lookup"><span data-stu-id="4de0d-122">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

<span data-ttu-id="4de0d-123">Чтобы использовать сброс пароля, необходимо включить обратную запись пароля.</span><span class="sxs-lookup"><span data-stu-id="4de0d-123">You must have password writeback enabled to use password reset.</span></span>
  
## <a name="phase-3-configure-and-test-password-reset"></a><span data-ttu-id="4de0d-124">Этап 3. Настройка и проверка сброса паролей</span><span class="sxs-lookup"><span data-stu-id="4de0d-124">Phase 3: Configure and test password reset</span></span>

<span data-ttu-id="4de0d-125">На этом этапе настройте сброс пароля в клиенте Azure AD с помощью членства в группе, а затем убедитесь, что он работает.</span><span class="sxs-lookup"><span data-stu-id="4de0d-125">In this phase, configure password reset in the Azure AD tenant through group membership, and then verify that it works.</span></span>

<span data-ttu-id="4de0d-126">Сперва включите сброс паролей для учетных записей в определенной группе Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4de0d-126">First, enable password reset for the accounts in a specific Azure AD group.</span></span>

1. <span data-ttu-id="4de0d-127">Откройте браузер в приватном режиме, откройте [https://portal.azure.com](https://portal.azure.com), а затем выполните вход, используя учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="4de0d-127">From a private instance of your browser, open [https://portal.azure.com](https://portal.azure.com), and then sign in with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="4de0d-128">На портале Azure выберите **группу Azure Active Directory**  >    >  **группы .**</span><span class="sxs-lookup"><span data-stu-id="4de0d-128">In the Azure portal, select **Azure Active Directory** > **Groups** > **New group**.</span></span>
3. <span data-ttu-id="4de0d-129">Для параметра **Тип группы** настройте значение **Безопасность**, для параметра **Имя группы** — значение **PWReset**, а для параметра **Тип членства** — значение **Назначено**.</span><span class="sxs-lookup"><span data-stu-id="4de0d-129">Set the **Group type** to **Security**, **Group name** to **PWReset**, and the **Membership type** to **Assigned**.</span></span>
4. <span data-ttu-id="4de0d-130">Выберите **участников,** найдите и выберите **Пользователь 3,** **выберите Выберите**, а затем выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="4de0d-130">Select **Members**, find and select **User 3**, select **Select**, and then select **Create**.</span></span>
5. <span data-ttu-id="4de0d-131">Закройте панель **Группы**.</span><span class="sxs-lookup"><span data-stu-id="4de0d-131">Close the **Groups** pane.</span></span>
6. <span data-ttu-id="4de0d-132">В области Azure Active Directory выберите сброс **пароля** в левой навигации.</span><span class="sxs-lookup"><span data-stu-id="4de0d-132">In the Azure Active Directory pane, select **Password reset** in the left navigation.</span></span>
7. <span data-ttu-id="4de0d-133">На панели **Сброс пароля - Свойства** щелкните **Выбрано** в разделе **Разрешен самостоятельный сброс пароля**.</span><span class="sxs-lookup"><span data-stu-id="4de0d-133">In the **Password reset-Properties** pane, under the option **Self Service Password Reset Enabled**, choose **Selected**.</span></span>
8. <span data-ttu-id="4de0d-134">Выберите **группу Выберите,** выберите **группу PWReset** и выберите **Выберите**  >  **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4de0d-134">Select **Select group**, select the **PWReset** group, and then select **Select** > **Save**.</span></span>
9. <span data-ttu-id="4de0d-135">Закройте браузер, открытый в приватном режиме.</span><span class="sxs-lookup"><span data-stu-id="4de0d-135">Close the private browser instance.</span></span>

<span data-ttu-id="4de0d-136">Затем проверьте сброс пароля для учетной записи Пользователя 3.</span><span class="sxs-lookup"><span data-stu-id="4de0d-136">Next, test password reset for the User 3 account.</span></span>

1. <span data-ttu-id="4de0d-137">Откройте новое окно браузера в приватном режиме и перейдите к [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span><span class="sxs-lookup"><span data-stu-id="4de0d-137">Open a new private browser instance and browse to [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).</span></span>
1. <span data-ttu-id="4de0d-138">Войдите с помощью учетной записи "Пользователь 3".</span><span class="sxs-lookup"><span data-stu-id="4de0d-138">Sign in with the User 3 account credentials.</span></span>
1. <span data-ttu-id="4de0d-139">Дополнительные **сведения, необходимые,** выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4de0d-139">In **More information required**, select **Next**.</span></span> 
1. <span data-ttu-id="4de0d-140">В разделе **Не утратьте доступ к учетной записи** укажите в качестве телефона для проверки подлинности свой номер мобильного телефона, а в качестве электронной почты для проверки подлинности — свою личную учетную запись электронной почты.</span><span class="sxs-lookup"><span data-stu-id="4de0d-140">In **Don't lose access to your account**, set the authentication phone to your mobile phone number and the authentication email to your work or personal email account.</span></span>
1. <span data-ttu-id="4de0d-141">После проверки обоих выберите **"Выглядит хорошо",** а затем закроем частный экземпляр браузера.</span><span class="sxs-lookup"><span data-stu-id="4de0d-141">After both are verified, select **Looks good**, and then close the private instance of the browser.</span></span>
1. <span data-ttu-id="4de0d-142">В новом экземпляре частного браузера перейдите к [https://aka.ms/sspr](https://aka.ms/sspr) .</span><span class="sxs-lookup"><span data-stu-id="4de0d-142">In a new private browser instance, go to [https://aka.ms/sspr](https://aka.ms/sspr).</span></span>
1. <span data-ttu-id="4de0d-143">Введите имя учетной записи Пользователя 3, введите символы из CAPTCHA и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4de0d-143">Enter the User 3 account name, enter the characters from the CAPTCHA, and then select **Next**.</span></span>
1. <span data-ttu-id="4de0d-144">Для **проверки шаг 1,** выберите электронную почту **моей альтернативной** электронной почты, а затем выберите **электронную почту**.</span><span class="sxs-lookup"><span data-stu-id="4de0d-144">For **verification step 1**, select **Email my alternate email**, and then select **Email**.</span></span> <span data-ttu-id="4de0d-145">При приеме электронной почты введите код проверки и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4de0d-145">When you receive the email, enter the verification code, and then select **Next**.</span></span>
1. <span data-ttu-id="4de0d-146">В **"Возвращайся в свою учетную запись"** введите новый пароль для учетной записи Пользователя 3, а затем выберите **Finish**.</span><span class="sxs-lookup"><span data-stu-id="4de0d-146">In **Get back into your account**, enter a new password for the User 3 account, and then select **Finish**.</span></span> <span data-ttu-id="4de0d-147">Запишите измененный пароль учетной записи пользователя 3 и храните его в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="4de0d-147">Note the changed password of the User 3 account and store it in a safe location.</span></span>
1. <span data-ttu-id="4de0d-148">На отдельной вкладке того же браузера перейдите к [https://admin.microsoft.com](https://admin.microsoft.com), а затем выполните вход, используя новый пароль и имя учетной записи "Пользователь 3".</span><span class="sxs-lookup"><span data-stu-id="4de0d-148">In a separate tab of the same browser, go to [https://admin.microsoft.com](https://admin.microsoft.com), and then sign in with the User 3 account name and its new password.</span></span> <span data-ttu-id="4de0d-149">Откроется **Домашняя страница Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="4de0d-149">You should see the **Microsoft Office Home** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="4de0d-150">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="4de0d-150">Next step</span></span>

<span data-ttu-id="4de0d-151">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="4de0d-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4de0d-152">См. также</span><span class="sxs-lookup"><span data-stu-id="4de0d-152">See also</span></span>

[<span data-ttu-id="4de0d-153">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="4de0d-153">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4de0d-154">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="4de0d-154">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="4de0d-155">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="4de0d-155">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)