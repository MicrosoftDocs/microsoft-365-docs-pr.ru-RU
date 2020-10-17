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
ms.openlocfilehash: 3c20d1997be2ff47f0b449cbba3afb1e6edcd59a
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487462"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="34cc2-103">Синхронизация хэшей паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="34cc2-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="34cc2-104">*Это руководство по лаборатории тестирования можно использовать как для Microsoft 365 Enterprise, так и для корпоративных тестовых сред Office 365.*</span><span class="sxs-lookup"><span data-stu-id="34cc2-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="34cc2-105">Во многих организациях используются Azure AD Connect и синхронизация хэша паролей в целях синхронизации набора учетных записей в своем локальном лесу доменных служб Active Directory (AD DS) с набором учетных записей в клиенте Azure AD для подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34cc2-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> 

<span data-ttu-id="34cc2-106">В этой статье описывается, как добавить синхронизацию хэша паролей в тестовую среду Microsoft 365, что приведет к следующей настройке:</span><span class="sxs-lookup"><span data-stu-id="34cc2-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, which results in this configuration:</span></span>
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="34cc2-108">Настройка этой тестовой среды состоит из трех этапов:</span><span class="sxs-lookup"><span data-stu-id="34cc2-108">Setting up this test environment involves three phases:</span></span>
- [<span data-ttu-id="34cc2-109">Этап 1. Создание тестовой среды "имитация предприятия" для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34cc2-109">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [<span data-ttu-id="34cc2-110">Этап 2. Создание и регистрация домена testlab</span><span class="sxs-lookup"><span data-stu-id="34cc2-110">Phase 2: Create and register the testlab domain</span></span>](#phase-2-create-and-register-the-testlab-domain)
- [<span data-ttu-id="34cc2-111">Этап 3. Установка Azure AD Connect на APP1</span><span class="sxs-lookup"><span data-stu-id="34cc2-111">Phase 3: Install Azure AD Connect on APP1</span></span>](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> <span data-ttu-id="34cc2-112">Для отображения всех статей, посвященных руководству по лаборатории тестирования Microsoft 365 для предприятий, перейдите к разделу [руководство по лаборатории тестирования microsoft 365 для предприятия](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="34cc2-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="34cc2-113">Этап 1. Создание тестовой среды "имитация предприятия" для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34cc2-113">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="34cc2-114">Следуйте инструкциям в разделе [смоделированная конфигурация предприятия для Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="34cc2-114">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span></span> <span data-ttu-id="34cc2-115">Результирующая конфигурация выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="34cc2-115">Your resulting configuration looks like this:</span></span>
  
![Базовая конфигурация "имитация предприятия"](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="34cc2-117">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="34cc2-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="34cc2-118">Пробная или платная подписка Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="34cc2-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="34cc2-119">Упрощенная интрасеть Организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="34cc2-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="34cc2-120">DC1 — контроллер домена для testlab. <*имя вашего общедоступного домена*> домене доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="34cc2-120">DC1 is a domain controller for the testlab.<*your public domain name*> AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="34cc2-121">Этап 2. Создание и регистрация домена testlab</span><span class="sxs-lookup"><span data-stu-id="34cc2-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="34cc2-122">На этом этапе добавьте общедоступный домен DNS и добавьте его в подписку.</span><span class="sxs-lookup"><span data-stu-id="34cc2-122">In this phase, add a public DNS domain, and then add it to your subscription.</span></span>

<span data-ttu-id="34cc2-123">Для начала выполните действия с поставщиком услуг общедоступной службы DNS для создания нового общедоступного доменного имени DNS, основанного на текущем доменном имени, а затем добавьте его в подписку.</span><span class="sxs-lookup"><span data-stu-id="34cc2-123">First, work with your public DNS registration provider to create a new public DNS domain name that's based on your current domain name, and then add it to your subscription.</span></span> <span data-ttu-id="34cc2-124">Рекомендуем использовать имя \**testlab. <*общедоступного домена\* > \*\*.</span><span class="sxs-lookup"><span data-stu-id="34cc2-124">We recommend using the name **testlab.<*your public domain*>**.</span></span> <span data-ttu-id="34cc2-125">Например, если имя общедоступного домена — \*\* <span>contoso</span>. com**, добавьте имя общедоступного домена: \*\* <span>testlab</span>. contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="34cc2-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name: **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="34cc2-126">Затем добавьте \**testlab. <*ваш общедоступный\* > \*\* домен в пробную или платную подписку на Microsoft 365, прополнив процесс регистрации домена.</span><span class="sxs-lookup"><span data-stu-id="34cc2-126">Next, add the **testlab.<*your public domain*>** domain to your Microsoft 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="34cc2-127">Это состоит в добавлении дополнительных записей DNS в \*\*testlab. <домен *общедоступного домена* > \*\* .</span><span class="sxs-lookup"><span data-stu-id="34cc2-127">This consists of adding additional DNS records to the **testlab.<*your public domain*>** domain.</span></span> <span data-ttu-id="34cc2-128">Дополнительные сведения см. [в статье Добавление домена в Microsoft 365](../admin/setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="34cc2-128">For more information, see [Add a domain to Microsoft 365](../admin/setup/add-domain.md).</span></span>

<span data-ttu-id="34cc2-129">Результирующая конфигурация выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="34cc2-129">Your resulting configuration looks like this:</span></span>
  
![Регистрация доменного имени testlab](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="34cc2-131">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="34cc2-131">This configuration consists of:</span></span>

- <span data-ttu-id="34cc2-132">Пробная или платная подписка Microsoft 365 в testlab. <*имя вашего общедоступного домена*> зарегистрировано.</span><span class="sxs-lookup"><span data-stu-id="34cc2-132">A Microsoft 365 E5 trial or paid subscription with the DNS domain testlab.<*your public domain name*> registered.</span></span>
- <span data-ttu-id="34cc2-133">Упрощенная интрасеть Организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="34cc2-133">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="34cc2-134">Обратите внимание на то, что testlab. <*имя общедоступного домена*> теперь:</span><span class="sxs-lookup"><span data-stu-id="34cc2-134">Notice how the testlab.<*your public domain name*> is now:</span></span>

- <span data-ttu-id="34cc2-135">поддерживается общедоступными DNS-записями;</span><span class="sxs-lookup"><span data-stu-id="34cc2-135">Supported by public DNS records.</span></span>
- <span data-ttu-id="34cc2-136">зарегистрирован в подписках на Microsoft 365;</span><span class="sxs-lookup"><span data-stu-id="34cc2-136">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="34cc2-137">является доменом AD DS в имитации интрасети.</span><span class="sxs-lookup"><span data-stu-id="34cc2-137">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="34cc2-138">Этап 3. Установка Azure AD Connect на APP1</span><span class="sxs-lookup"><span data-stu-id="34cc2-138">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="34cc2-139">На этом этапе установите и настройте средство Azure AD Connect на APP1, а затем убедитесь, что оно работает.</span><span class="sxs-lookup"><span data-stu-id="34cc2-139">In this phase, install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="34cc2-140">Сначала установите и настройте Azure AD Connect на APP1.</span><span class="sxs-lookup"><span data-stu-id="34cc2-140">First, install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="34cc2-141">На [портале Azure](https://portal.azure.com) выполните вход с помощью учетной записи глобального администратора и подключитесь к виртуальной машине APP1 с помощью учетной записи TESTLAB\\User1.</span><span class="sxs-lookup"><span data-stu-id="34cc2-141">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="34cc2-142">На рабочем столе APP1 откройте командную строку Windows PowerShell с правами администратора и выполните указанные ниже команды, чтобы отключить усиленную безопасность Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="34cc2-142">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="34cc2-143">На панели задач выберите **Internet Explorer** и перейдите к [https://aka.ms/aadconnect](https://aka.ms/aadconnect) .</span><span class="sxs-lookup"><span data-stu-id="34cc2-143">From the taskbar, select **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="34cc2-144">На странице Microsoft Azure Active Directory Connect нажмите кнопку **скачать**, а затем выберите команду **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="34cc2-144">On the Microsoft Azure Active Directory Connect page, select **Download**, and then select **Run**.</span></span>
    
5. <span data-ttu-id="34cc2-145">На странице **Добро пожаловать в Azure AD Connect** установите флажок **принимаю**и нажмите кнопку **продолжить**.</span><span class="sxs-lookup"><span data-stu-id="34cc2-145">On the **Welcome to Azure AD Connect** page, select **I agree**, and then select **Continue**.</span></span>
    
6. <span data-ttu-id="34cc2-146">На странице " **Экспресс-параметры** " выберите **использовать Экспресс-параметры**.</span><span class="sxs-lookup"><span data-stu-id="34cc2-146">On the **Express Settings** page, select **Use express settings**.</span></span>
    
7. <span data-ttu-id="34cc2-147">На странице **Подключение к Azure AD** введите имя учетной записи глобального администратора в поле **имя пользователя,** введите пароль в поле **пароль**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="34cc2-147">On the **Connect to Azure AD** page, enter your global administrator account name in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
8. <span data-ttu-id="34cc2-148">На странице **Подключение к AD DS** введите **TESTLAB \\ User1** в поле **имя пользователя,** введите пароль в поле **пароль**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="34cc2-148">On the **Connect to AD DS** page, enter **TESTLAB\\User1** in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="34cc2-149">На странице **Готово к настройке** нажмите кнопку **установить**.</span><span class="sxs-lookup"><span data-stu-id="34cc2-149">On the **Ready to configure** page, select **Install**.</span></span>
    
10. <span data-ttu-id="34cc2-150">На странице **Завершение настройки** нажмите кнопку **выход**.</span><span class="sxs-lookup"><span data-stu-id="34cc2-150">On the **Configuration complete** page, select **Exit**.</span></span>
    
11. <span data-ttu-id="34cc2-151">В браузере Internet Explorer перейдите в Центр администрирования Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="34cc2-151">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="34cc2-152">В левой области навигации выберите **пользователи > активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="34cc2-152">In the left navigation pane, select **Users > Active users**.</span></span>
    
    <span data-ttu-id="34cc2-153">Обратите внимание на учетную запись **User1**.</span><span class="sxs-lookup"><span data-stu-id="34cc2-153">Note the account named **User1**.</span></span> <span data-ttu-id="34cc2-154">Эта учетная запись находится на домене AD DS TESTLAB. Это доказывает, что синхронизация службы каталогов выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="34cc2-154">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="34cc2-155">Выберите учетную запись **Пользователь1** , а затем выберите пункт **лицензии и приложения**.</span><span class="sxs-lookup"><span data-stu-id="34cc2-155">Select the **User1** account, and then select **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="34cc2-156">В разделе **лицензии на продукты**выберите свое местоположение (при необходимости), отключите лицензию **Office 365** и затем включите лицензию **Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="34cc2-156">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license, and then enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="34cc2-157">Нажмите кнопку **сохранить** в нижней части страницы, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="34cc2-157">Select **Save** at the bottom of the page, and then select **Close**.</span></span>
    
<span data-ttu-id="34cc2-158">Затем проверьте возможность входа в вашу подписку с помощью \**User1@testlab. <*доменное\* > \*\* имя пользователя учетной записи User1:</span><span class="sxs-lookup"><span data-stu-id="34cc2-158">Next, test the ability to sign in to your subscription with the **user1@testlab.<*your domain name*>** user name of the User1 account:</span></span>

1. <span data-ttu-id="34cc2-159">Находясь в APP1, выйдите и повторно войдите, используя другую учетную запись.</span><span class="sxs-lookup"><span data-stu-id="34cc2-159">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="34cc2-160">При запросе имени пользователя и пароля укажите \**User1@testlab. <*доменное имя\* > \*\* и пароль User1.</span><span class="sxs-lookup"><span data-stu-id="34cc2-160">When prompted for a user name and password, specify **user1@testlab.<*your domain name*>** and the User1 password.</span></span> <span data-ttu-id="34cc2-161">Должен осуществиться успешный вход в качестве пользователя User1.</span><span class="sxs-lookup"><span data-stu-id="34cc2-161">You should successfully sign in as User1.</span></span>
 
<span data-ttu-id="34cc2-162">Обратите внимание, что хотя у пользователя User1 есть разрешения администратора для домена AD DS TESTLAB, он не является глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="34cc2-162">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="34cc2-163">Следовательно, значок **Администратор** не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="34cc2-163">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="34cc2-164">Результирующая конфигурация выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="34cc2-164">Your resulting configuration looks like this:</span></span>

![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="34cc2-166">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="34cc2-166">This configuration consists of:</span></span> 
  
- <span data-ttu-id="34cc2-167">Microsoft 365 а также пробные или платные подписки Office 365 в TESTLAB. <*доменное имя*> зарегистрировано.</span><span class="sxs-lookup"><span data-stu-id="34cc2-167">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.<*your domain name*> registered.</span></span>
- <span data-ttu-id="34cc2-168">Упрощенная интрасеть Организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="34cc2-168">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="34cc2-169">Azure AD Connect работает на APP1 для периодической синхронизации домена AD DS TESTLAB с клиентом Azure AD вашей подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34cc2-169">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>
- <span data-ttu-id="34cc2-170">Учетная запись User1 на домене AD DS TESTLAB синхронизирована с клиентом Azure AD.</span><span class="sxs-lookup"><span data-stu-id="34cc2-170">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="34cc2-171">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="34cc2-171">Next step</span></span>

<span data-ttu-id="34cc2-172">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="34cc2-172">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="34cc2-173">См. также</span><span class="sxs-lookup"><span data-stu-id="34cc2-173">See also</span></span>

[<span data-ttu-id="34cc2-174">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="34cc2-174">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="34cc2-175">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="34cc2-175">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="34cc2-176">Microsoft 365 для корпоративных документов</span><span class="sxs-lookup"><span data-stu-id="34cc2-176">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
