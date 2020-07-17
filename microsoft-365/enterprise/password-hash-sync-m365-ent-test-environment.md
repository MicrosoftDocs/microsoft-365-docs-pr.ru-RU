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
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: Сводка. Настройте и продемонстрируйте синхронизацию хэшей паролей и вход для тестовой среды Microsoft 365.
ms.openlocfilehash: 2d5fbd3ed2a2afb994fc36f5ba3a15a8c55a274e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819392"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="74dd1-103">Синхронизация хэшей паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="74dd1-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="74dd1-104">*Это руководство по лаборатории тестирования можно использовать для тестовых сред Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="74dd1-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="74dd1-105">Во многих организациях используются Azure AD Connect и синхронизация хэша паролей в целях синхронизации набора учетных записей в своем локальном лесу доменных служб Active Directory (AD DS) с набором учетных записей в клиенте Azure AD для подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74dd1-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> <span data-ttu-id="74dd1-106">В этой статье описывается добавление синхронизации хэша паролей в тестовую среду Microsoft 365, в результате чего получается следующая конфигурация:</span><span class="sxs-lookup"><span data-stu-id="74dd1-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, resulting in the following configuration:</span></span>
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="74dd1-108">Настройка этой тестовой среды состоит из двух следующих этапов:</span><span class="sxs-lookup"><span data-stu-id="74dd1-108">There are two phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="74dd1-109">Создание тестовой среды "имитация предприятия Microsoft 365".</span><span class="sxs-lookup"><span data-stu-id="74dd1-109">Create the Microsoft 365 simulated enterprise test environment.</span></span>
2. <span data-ttu-id="74dd1-110">Установка и настройка Azure AD Connect на виртуальной машине APP1.</span><span class="sxs-lookup"><span data-stu-id="74dd1-110">Install and configure Azure AD Connect on APP1.</span></span>
    
> [!TIP]
> <span data-ttu-id="74dd1-111">Перейдите в раздел [Руководства по лаборатории тестирования Microsoft 365 корпоративный](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к данной теме.</span><span class="sxs-lookup"><span data-stu-id="74dd1-111">Go to [Microsoft 365 Enterprise Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="74dd1-112">Этап 1. Создание тестовой среды "имитация предприятия" для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74dd1-112">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="74dd1-p102">Следуйте инструкциям в статье о [базовой конфигурации "имитация предприятия" для Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Вот получившаяся конфигурация.</span><span class="sxs-lookup"><span data-stu-id="74dd1-p102">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Here is your resulting configuration.</span></span>
  
![Базовая конфигурация "имитация предприятия"](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="74dd1-116">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="74dd1-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="74dd1-117">Пробные или платные подписки на Microsoft 365 E5 или Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="74dd1-117">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="74dd1-118">Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="74dd1-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="74dd1-119">DC1 — контроллер домена для testlab.\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="74dd1-119">DC1 is a domain controller for the testlab.\<your public domain name></span></span> <span data-ttu-id="74dd1-120">Домен AD DS.</span><span class="sxs-lookup"><span data-stu-id="74dd1-120">AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="74dd1-121">Этап 2. Создание и регистрация домена testlab</span><span class="sxs-lookup"><span data-stu-id="74dd1-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="74dd1-122">На этом этапе создается и добавляется в подписку публичный домен DNS.</span><span class="sxs-lookup"><span data-stu-id="74dd1-122">In this phase you add a public DNS domain and add it to your subscription.</span></span>

<span data-ttu-id="74dd1-123">Сначала обратитесь к своему поставщику услуг регистрации общедоступных записей DNS, чтобы создать новое имя общедоступного домена DNS на основе текущего доменного имени и добавить его в подписку.</span><span class="sxs-lookup"><span data-stu-id="74dd1-123">First, work with your public DNS registration provider to create a new public DNS domain name based on your current domain name and add it to your subscription.</span></span> <span data-ttu-id="74dd1-124">Рекомендуем использовать имя **testlab.**\<your public domain>.</span><span class="sxs-lookup"><span data-stu-id="74dd1-124">We recommend using the name **testlab.**\<your public domain>.</span></span> <span data-ttu-id="74dd1-125">Например, если имя вашего общедоступного домена — **<span>contoso</span>.com**, добавьте имя **<span>testlab</span>.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="74dd1-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="74dd1-126">Затем добавьте домен **testlab.**\<your public domain></span><span class="sxs-lookup"><span data-stu-id="74dd1-126">Next, you add the **testlab.**\<your public domain></span></span> <span data-ttu-id="74dd1-127">в пробную или платную подписку на Microsoft 365 или Office 365, пройдя процесс регистрации домена.</span><span class="sxs-lookup"><span data-stu-id="74dd1-127">domain to your Microsoft 365 or Office 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="74dd1-128">Он включает добавление дополнительных записей DNS к домену **testlab.**\<your public domain></span><span class="sxs-lookup"><span data-stu-id="74dd1-128">This consists of adding additional DNS records to the **testlab.**\<your public domain></span></span> <span data-ttu-id="74dd1-129">.</span><span class="sxs-lookup"><span data-stu-id="74dd1-129">domain.</span></span> <span data-ttu-id="74dd1-130">Дополнительные сведения см. в статье [Добавление домена в Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="74dd1-130">For more information, see [Add a domain to Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain).</span></span> 

<span data-ttu-id="74dd1-131">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="74dd1-131">Here is your resulting configuration.</span></span>
  
![Регистрация доменного имени testlab](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="74dd1-133">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="74dd1-133">This configuration consists of:</span></span>

- <span data-ttu-id="74dd1-134">Пробные или платные подписки на Microsoft 365 E5 или Office 365 E5 с зарегистрированным доменом DNS testlab.\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="74dd1-134">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your public domain name></span></span> <span data-ttu-id="74dd1-135">-</span><span class="sxs-lookup"><span data-stu-id="74dd1-135">registered.</span></span>
- <span data-ttu-id="74dd1-136">Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure.</span><span class="sxs-lookup"><span data-stu-id="74dd1-136">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="74dd1-137">Обратите внимание, как домен testlab.\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="74dd1-137">Notice how the testlab.\<your public domain name></span></span> <span data-ttu-id="74dd1-138">в настоящее время:</span><span class="sxs-lookup"><span data-stu-id="74dd1-138">is now:</span></span>

- <span data-ttu-id="74dd1-139">поддерживается общедоступными DNS-записями;</span><span class="sxs-lookup"><span data-stu-id="74dd1-139">Supported by public DNS records.</span></span>
- <span data-ttu-id="74dd1-140">зарегистрирован в подписках на Microsoft 365;</span><span class="sxs-lookup"><span data-stu-id="74dd1-140">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="74dd1-141">является доменом AD DS в имитации интрасети.</span><span class="sxs-lookup"><span data-stu-id="74dd1-141">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="74dd1-142">Этап 3. Установка Azure AD Connect на APP1</span><span class="sxs-lookup"><span data-stu-id="74dd1-142">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="74dd1-143">На этом этапе устанавливается и настраивается инструмент Azure AD Connect на APP1, а затем проверяется его работа.</span><span class="sxs-lookup"><span data-stu-id="74dd1-143">In this phase, you install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="74dd1-144">Сначала выполняется установка и настройка Azure AD Connect на APP1.</span><span class="sxs-lookup"><span data-stu-id="74dd1-144">First, you install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="74dd1-145">На [портале Azure](https://portal.azure.com) выполните вход с помощью учетной записи глобального администратора и подключитесь к виртуальной машине APP1 с помощью учетной записи TESTLAB\\User1.</span><span class="sxs-lookup"><span data-stu-id="74dd1-145">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="74dd1-146">На рабочем столе APP1 откройте командную строку Windows PowerShell с правами администратора и выполните указанные ниже команды, чтобы отключить усиленную безопасность Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="74dd1-146">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="74dd1-147">На панели задач выберите **Internet Explorer** и перейдите по адресу [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span><span class="sxs-lookup"><span data-stu-id="74dd1-147">From the task bar, click **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="74dd1-148">На странице Microsoft Azure Active Directory Connect нажмите **Скачать**, а затем **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="74dd1-148">On the Microsoft Azure Active Directory Connect page, click **Download**, and then click **Run**.</span></span>
    
5. <span data-ttu-id="74dd1-149">На странице **Добро пожаловать в Azure AD Connect** установите флажок **Принимаю** и нажмите кнопку **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="74dd1-149">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue**.</span></span>
    
6. <span data-ttu-id="74dd1-150">На странице **Стандартные параметры** выберите **Использовать стандартные параметры**.</span><span class="sxs-lookup"><span data-stu-id="74dd1-150">On the **Express Settings** page, click **Use express settings**.</span></span>
    
7. <span data-ttu-id="74dd1-151">На странице **Подключение к Azure AD** введите имя своей учетной записи глобального администратора в поле **Имя пользователя**, введите пароль в поле **Пароль** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="74dd1-151">On the **Connect to Azure AD** page, type your global administrator account name in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="74dd1-152">На странице **Подключение к AD DS** введите **TESTLAB\\User1** в поле **Имя пользователя** и пароль в поле **Пароль**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="74dd1-152">On the **Connect to AD DS** page, type **TESTLAB\\User1** in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="74dd1-153">На странице **Готово к настройке** нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="74dd1-153">On the **Ready to configure** page, click **Install**.</span></span>
    
10. <span data-ttu-id="74dd1-154">На странице **Настройка завершена** нажмите **Выход**.</span><span class="sxs-lookup"><span data-stu-id="74dd1-154">On the **Configuration complete** page, click **Exit**.</span></span>
    
11. <span data-ttu-id="74dd1-155">В браузере Internet Explorer перейдите в Центр администрирования Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="74dd1-155">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="74dd1-156">На панели навигации слева выберите элементы **Пользователи > Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="74dd1-156">In the left navigation, click **Users > Active users**.</span></span>
    
    <span data-ttu-id="74dd1-157">Обратите внимание на учетную запись **User1**.</span><span class="sxs-lookup"><span data-stu-id="74dd1-157">Note the account named **User1**.</span></span> <span data-ttu-id="74dd1-158">Эта учетная запись находится на домене AD DS TESTLAB. Это доказывает, что синхронизация службы каталогов выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="74dd1-158">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="74dd1-159">Щелкните учетную запись **User1** и выберите **Лицензии и приложения**.</span><span class="sxs-lookup"><span data-stu-id="74dd1-159">Click the **User1** account, and then click **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="74dd1-160">В разделе **Лицензии продуктов** выберите свое расположение (при необходимости), отключите лицензию на **Office 365 E5** и включите лицензию на **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="74dd1-160">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license and enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="74dd1-161">Нажмите **Сохранить** в нижней части страницы, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="74dd1-161">Click **Save** at the bottom of the page, and then click **Close**.</span></span>
    
<span data-ttu-id="74dd1-162">Затем проверьте возможность входа в вашу подписку с использованием учетной записи <strong>user1@testlab.</strong>\<your domain name></span><span class="sxs-lookup"><span data-stu-id="74dd1-162">Next, you test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your domain name></span></span> <span data-ttu-id="74dd1-163">на имя пользователя учетной записи User1.</span><span class="sxs-lookup"><span data-stu-id="74dd1-163">user name of the User1 account.</span></span>

1. <span data-ttu-id="74dd1-164">Находясь в APP1, выйдите и повторно войдите, используя другую учетную запись.</span><span class="sxs-lookup"><span data-stu-id="74dd1-164">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="74dd1-165">При появлении запроса имени пользователя и пароля, укажите <strong>user1@testlab.</strong>\<your domain name></span><span class="sxs-lookup"><span data-stu-id="74dd1-165">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your domain name></span></span> <span data-ttu-id="74dd1-166">и пароль пользователя User1.</span><span class="sxs-lookup"><span data-stu-id="74dd1-166">and the User1 password.</span></span> <span data-ttu-id="74dd1-167">Должен осуществиться успешный вход в качестве пользователя User1.</span><span class="sxs-lookup"><span data-stu-id="74dd1-167">You should successfully sign in as User1.</span></span> 
 
<span data-ttu-id="74dd1-168">Обратите внимание, что хотя у пользователя User1 есть разрешения администратора для домена AD DS TESTLAB, он не является глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="74dd1-168">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="74dd1-169">Следовательно, значок **Администратор** не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="74dd1-169">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="74dd1-170">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="74dd1-170">Here is your resulting configuration.</span></span>

![Тестовая среда "имитация предприятия с синхронизацией хэшей паролей"](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="74dd1-172">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="74dd1-172">This configuration consists of:</span></span> 
  
- <span data-ttu-id="74dd1-173">Пробные или платные подписки на Microsoft 365 E5 или Office 365 E5 с зарегистрированным доменом DNS TESTLAB.\<your domain name></span><span class="sxs-lookup"><span data-stu-id="74dd1-173">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name></span></span> <span data-ttu-id="74dd1-174">-</span><span class="sxs-lookup"><span data-stu-id="74dd1-174">registered.</span></span>
- <span data-ttu-id="74dd1-175">Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure.</span><span class="sxs-lookup"><span data-stu-id="74dd1-175">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="74dd1-176">Azure AD Connect работает на APP1 для периодической синхронизации домена AD DS TESTLAB с клиентом Azure AD, связанным с подпиской на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74dd1-176">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription periodically.</span></span>
- <span data-ttu-id="74dd1-177">Учетная запись User1 на домене AD DS TESTLAB синхронизирована с клиентом Azure AD.</span><span class="sxs-lookup"><span data-stu-id="74dd1-177">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="74dd1-178">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="74dd1-178">Next step</span></span>

<span data-ttu-id="74dd1-179">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="74dd1-179">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="74dd1-180">См. также</span><span class="sxs-lookup"><span data-stu-id="74dd1-180">See also</span></span>

[<span data-ttu-id="74dd1-181">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="74dd1-181">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="74dd1-182">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="74dd1-182">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="74dd1-183">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="74dd1-183">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


