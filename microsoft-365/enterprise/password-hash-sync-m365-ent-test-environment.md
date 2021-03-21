---
title: Синхронизация хэшей паролей для тестовой среды Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: Сводка. Настройте и продемонстрируйте синхронизацию хэшей паролей и вход для тестовой среды Microsoft 365.
ms.openlocfilehash: 9c61745fe322dce4cb2b537b18963634a97c697a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921508"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="97ab3-103">Синхронизация хэшей паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="97ab3-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="97ab3-104">*Это руководство по тестовой лаборатории можно использовать для microsoft 365 для корпоративных и корпоративных тестовых сред Office 365.*</span><span class="sxs-lookup"><span data-stu-id="97ab3-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="97ab3-105">Во многих организациях используются Azure AD Connect и синхронизация хэша паролей в целях синхронизации набора учетных записей в своем локальном лесу доменных служб Active Directory (AD DS) с набором учетных записей в клиенте Azure AD для подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="97ab3-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> 

<span data-ttu-id="97ab3-106">В этой статье описывается, как можно добавить синхронизацию хаширования паролей в тестовую среду Microsoft 365, что приводит к такой конфигурации:</span><span class="sxs-lookup"><span data-stu-id="97ab3-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, which results in this configuration:</span></span>
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="97ab3-108">Настройка этой тестовой среды включает три этапа:</span><span class="sxs-lookup"><span data-stu-id="97ab3-108">Setting up this test environment involves three phases:</span></span>
- [<span data-ttu-id="97ab3-109">Этап 1. Создание тестовой среды "имитация предприятия" для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="97ab3-109">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [<span data-ttu-id="97ab3-110">Этап 2. Создание и регистрация домена testlab</span><span class="sxs-lookup"><span data-stu-id="97ab3-110">Phase 2: Create and register the testlab domain</span></span>](#phase-2-create-and-register-the-testlab-domain)
- [<span data-ttu-id="97ab3-111">Этап 3. Установка Azure AD Connect на APP1</span><span class="sxs-lookup"><span data-stu-id="97ab3-111">Phase 3: Install Azure AD Connect on APP1</span></span>](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> <span data-ttu-id="97ab3-112">Чтобы получить визуальную карту для всех статей в стеке Руководство по корпоративной тестовой лаборатории Microsoft 365, перейдите в [Microsoft 365 для](../downloads/Microsoft365EnterpriseTLGStack.pdf)корпоративного руководства по тестовой лаборатории.</span><span class="sxs-lookup"><span data-stu-id="97ab3-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="97ab3-113">Этап 1. Создание тестовой среды "имитация предприятия" для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="97ab3-113">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="97ab3-114">Следуйте инструкциям в [моделируемой корпоративной базовой конфигурации для Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="97ab3-114">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span></span> <span data-ttu-id="97ab3-115">В результате конфигурация выглядит так:</span><span class="sxs-lookup"><span data-stu-id="97ab3-115">Your resulting configuration looks like this:</span></span>
  
![Базовая конфигурация "имитация предприятия"](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="97ab3-117">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="97ab3-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="97ab3-118">Пробная или платная подписка Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="97ab3-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="97ab3-119">Упрощенная интрасеть организации, подключенная к Интернету, состоящая из виртуальных машин DC1, APP1 и CLIENT1 в виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="97ab3-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="97ab3-120">DC1 — контроллер домена для testlab.<домена> AD DS. </span><span class="sxs-lookup"><span data-stu-id="97ab3-120">DC1 is a domain controller for the testlab.<*your public domain name*> AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="97ab3-121">Этап 2. Создание и регистрация домена testlab</span><span class="sxs-lookup"><span data-stu-id="97ab3-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="97ab3-122">На этом этапе добавьте общедоступный домен DNS и добавьте его в подписку.</span><span class="sxs-lookup"><span data-stu-id="97ab3-122">In this phase, add a public DNS domain, and then add it to your subscription.</span></span>

<span data-ttu-id="97ab3-123">Сначала работайте с общедоступным поставщиком регистрации DNS для создания нового общего доменного имени DNS, основанного на текущем доменном имени, а затем добавьте его в подписку.</span><span class="sxs-lookup"><span data-stu-id="97ab3-123">First, work with your public DNS registration provider to create a new public DNS domain name that's based on your current domain name, and then add it to your subscription.</span></span> <span data-ttu-id="97ab3-124">Мы рекомендуем использовать имя **testlab.<*общедоступным доменом.\* >*\*</span><span class="sxs-lookup"><span data-stu-id="97ab3-124">We recommend using the name **testlab.<*your public domain*>**.</span></span> <span data-ttu-id="97ab3-125">Например, если ваше имя общего домена **<span>— contoso</span>.com,** добавьте имя общего домена: **<span>testlab</span>.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="97ab3-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name: **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="97ab3-126">Далее добавьте **testlab.< >** домена общественного достояния в пробную или платную подписку Microsoft 365, проехав процесс регистрации домена.</span><span class="sxs-lookup"><span data-stu-id="97ab3-126">Next, add the **testlab.<*your public domain*>** domain to your Microsoft 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="97ab3-127">Это включает добавление дополнительных записей DNS в **testlab.<*домена общественного\* >*\* достояния.</span><span class="sxs-lookup"><span data-stu-id="97ab3-127">This consists of adding additional DNS records to the **testlab.<*your public domain*>** domain.</span></span> <span data-ttu-id="97ab3-128">Дополнительные сведения см. в [добавлении домена в Microsoft 365.](../admin/setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="97ab3-128">For more information, see [Add a domain to Microsoft 365](../admin/setup/add-domain.md).</span></span>

<span data-ttu-id="97ab3-129">В результате конфигурация выглядит так:</span><span class="sxs-lookup"><span data-stu-id="97ab3-129">Your resulting configuration looks like this:</span></span>
  
![Регистрация доменного имени testlab](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="97ab3-131">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="97ab3-131">This configuration consists of:</span></span>

- <span data-ttu-id="97ab3-132">Пробная версия microsoft 365 E5 или платная подписка с  помощью testlab.<домена DNS> зарегистрирована.</span><span class="sxs-lookup"><span data-stu-id="97ab3-132">A Microsoft 365 E5 trial or paid subscription with the DNS domain testlab.<*your public domain name*> registered.</span></span>
- <span data-ttu-id="97ab3-133">Упрощенная интрасеть организации, подключенная к Интернету, состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="97ab3-133">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="97ab3-134">Обратите внимание, как testlab.<*имя* вашего> домена теперь:</span><span class="sxs-lookup"><span data-stu-id="97ab3-134">Notice how the testlab.<*your public domain name*> is now:</span></span>

- <span data-ttu-id="97ab3-135">поддерживается общедоступными DNS-записями;</span><span class="sxs-lookup"><span data-stu-id="97ab3-135">Supported by public DNS records.</span></span>
- <span data-ttu-id="97ab3-136">зарегистрирован в подписках на Microsoft 365;</span><span class="sxs-lookup"><span data-stu-id="97ab3-136">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="97ab3-137">является доменом AD DS в имитации интрасети.</span><span class="sxs-lookup"><span data-stu-id="97ab3-137">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="97ab3-138">Этап 3. Установка Azure AD Connect на APP1</span><span class="sxs-lookup"><span data-stu-id="97ab3-138">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="97ab3-139">На этом этапе установите и настройте средство Azure AD Connect в APP1, а затем убедитесь, что он работает.</span><span class="sxs-lookup"><span data-stu-id="97ab3-139">In this phase, install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="97ab3-140">Сначала установите и настройте Azure AD Connect в APP1.</span><span class="sxs-lookup"><span data-stu-id="97ab3-140">First, install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="97ab3-141">На [портале Azure](https://portal.azure.com) выполните вход с помощью учетной записи глобального администратора и подключитесь к виртуальной машине APP1 с помощью учетной записи TESTLAB\\User1.</span><span class="sxs-lookup"><span data-stu-id="97ab3-141">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="97ab3-142">На рабочем столе APP1 откройте командную строку Windows PowerShell с правами администратора и выполните указанные ниже команды, чтобы отключить усиленную безопасность Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="97ab3-142">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="97ab3-143">Из панели задач выберите **Internet Explorer** и перейдите в [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .</span><span class="sxs-lookup"><span data-stu-id="97ab3-143">From the taskbar, select **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="97ab3-144">На странице Microsoft Azure Active Directory Connect выберите **Скачать** и затем выберите **Run**.</span><span class="sxs-lookup"><span data-stu-id="97ab3-144">On the Microsoft Azure Active Directory Connect page, select **Download**, and then select **Run**.</span></span>
    
5. <span data-ttu-id="97ab3-145">На странице **Добро пожаловать в Azure AD Connect** выберите я **согласен,** а затем выберите **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="97ab3-145">On the **Welcome to Azure AD Connect** page, select **I agree**, and then select **Continue**.</span></span>
    
6. <span data-ttu-id="97ab3-146">На странице **Express Settings** выберите **Использование параметров express.**</span><span class="sxs-lookup"><span data-stu-id="97ab3-146">On the **Express Settings** page, select **Use express settings**.</span></span>
    
7. <span data-ttu-id="97ab3-147">На странице **Подключение к Azure AD** введите имя глобальной учетной записи администратора в **имени пользователя,** введите пароль в **Password** и выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="97ab3-147">On the **Connect to Azure AD** page, enter your global administrator account name in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
8. <span data-ttu-id="97ab3-148">На странице **Подключение к AD DS** введите **TESTLAB \\ User1** в **имени пользователя,** введите пароль в **пароль,** а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="97ab3-148">On the **Connect to AD DS** page, enter **TESTLAB\\User1** in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="97ab3-149">На странице **Готово к настройке** выберите **Установите**.</span><span class="sxs-lookup"><span data-stu-id="97ab3-149">On the **Ready to configure** page, select **Install**.</span></span>
    
10. <span data-ttu-id="97ab3-150">На странице **Полная конфигурация** выберите **Exit**.</span><span class="sxs-lookup"><span data-stu-id="97ab3-150">On the **Configuration complete** page, select **Exit**.</span></span>
    
11. <span data-ttu-id="97ab3-151">В браузере Internet Explorer перейдите в Центр администрирования Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="97ab3-151">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="97ab3-152">В левой области навигации выберите **Пользователи > активных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="97ab3-152">In the left navigation pane, select **Users > Active users**.</span></span>
    
    <span data-ttu-id="97ab3-153">Обратите внимание на учетную запись **User1**.</span><span class="sxs-lookup"><span data-stu-id="97ab3-153">Note the account named **User1**.</span></span> <span data-ttu-id="97ab3-154">Эта учетная запись находится на домене AD DS TESTLAB. Это доказывает, что синхронизация службы каталогов выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="97ab3-154">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="97ab3-155">Выберите **учетную запись User1,** а затем выберите **лицензии и приложения.**</span><span class="sxs-lookup"><span data-stu-id="97ab3-155">Select the **User1** account, and then select **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="97ab3-156">В **лицензиях** на продукт выберите свое расположение (при необходимости), отключите лицензию **Office 365 E5** и включите лицензию **Microsoft 365 E5.**</span><span class="sxs-lookup"><span data-stu-id="97ab3-156">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license, and then enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="97ab3-157">Выберите **Сохранить** в нижней части страницы, а затем выберите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="97ab3-157">Select **Save** at the bottom of the page, and then select **Close**.</span></span>
    
<span data-ttu-id="97ab3-158">Далее проверьте возможность войти в подписку с **помощью  > user1@testlab.<** имя пользователя доменного имени учетной записи User1:</span><span class="sxs-lookup"><span data-stu-id="97ab3-158">Next, test the ability to sign in to your subscription with the **user1@testlab.<*your domain name*>** user name of the User1 account:</span></span>

1. <span data-ttu-id="97ab3-159">Находясь в APP1, выйдите и повторно войдите, используя другую учетную запись.</span><span class="sxs-lookup"><span data-stu-id="97ab3-159">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="97ab3-160">При запросе имени пользователя и пароля укажите **user1@testlab.< >** имя домена и пароль User1.</span><span class="sxs-lookup"><span data-stu-id="97ab3-160">When prompted for a user name and password, specify **user1@testlab.<*your domain name*>** and the User1 password.</span></span> <span data-ttu-id="97ab3-161">Должен осуществиться успешный вход в качестве пользователя User1.</span><span class="sxs-lookup"><span data-stu-id="97ab3-161">You should successfully sign in as User1.</span></span>
 
<span data-ttu-id="97ab3-162">Обратите внимание, что хотя у пользователя User1 есть разрешения администратора для домена AD DS TESTLAB, он не является глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="97ab3-162">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="97ab3-163">Следовательно, значок **Администратор** не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="97ab3-163">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="97ab3-164">В результате конфигурация выглядит так:</span><span class="sxs-lookup"><span data-stu-id="97ab3-164">Your resulting configuration looks like this:</span></span>

![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="97ab3-166">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="97ab3-166">This configuration consists of:</span></span> 
  
- <span data-ttu-id="97ab3-167">Microsoft 365 E5 или Office 365 E5 пробные или платные подписки  с доменом DNS TESTLAB.<доменного имени> зарегистрированы.</span><span class="sxs-lookup"><span data-stu-id="97ab3-167">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.<*your domain name*> registered.</span></span>
- <span data-ttu-id="97ab3-168">Упрощенная интрасеть организации, подключенная к Интернету, состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="97ab3-168">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="97ab3-169">Azure AD Connect выполняется в APP1, чтобы периодически синхронизировать домен TESTLAB AD DS с клиентом Azure AD подписки Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="97ab3-169">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>
- <span data-ttu-id="97ab3-170">Учетная запись User1 на домене AD DS TESTLAB синхронизирована с клиентом Azure AD.</span><span class="sxs-lookup"><span data-stu-id="97ab3-170">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="97ab3-171">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="97ab3-171">Next step</span></span>

<span data-ttu-id="97ab3-172">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="97ab3-172">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="97ab3-173">См. также</span><span class="sxs-lookup"><span data-stu-id="97ab3-173">See also</span></span>

[<span data-ttu-id="97ab3-174">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="97ab3-174">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="97ab3-175">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="97ab3-175">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="97ab3-176">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="97ab3-176">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)