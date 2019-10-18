---
title: Синхронизация хэшей паролей для тестовой среды Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/13/2018
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
ms.assetid: ''
description: Сводка. Настройте и продемонстрируйте синхронизацию хэшей паролей и вход для тестовой среды Microsoft 365.
ms.openlocfilehash: 0c6f7ec4afdfaaca0c84ed33ea0c1b1f248a82f5
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073179"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="f83cd-103">Синхронизация хэшей паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f83cd-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="f83cd-104">Во многих организациях используются Azure AD Connect и синхронизация хэша паролей в целях синхронизации набора учетных записей в своем локальном лесу доменных служб Active Directory (AD DS) с набором учетных записей в клиенте Azure AD для своих подписок на Office 365 и EMS E5.</span><span class="sxs-lookup"><span data-stu-id="f83cd-104">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Office 365 and EMS E5 subscriptions.</span></span> <span data-ttu-id="f83cd-105">В этой статье описывается добавление синхронизации хэша паролей в тестовую среду Microsoft 365, в результате чего получается следующая конфигурация:</span><span class="sxs-lookup"><span data-stu-id="f83cd-105">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, resulting in the following configuration:</span></span>
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="f83cd-107">Настройка этой тестовой среды состоит из двух следующих этапов:</span><span class="sxs-lookup"><span data-stu-id="f83cd-107">There are two phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="f83cd-108">Создание тестовой среды "имитация предприятия Microsoft 365".</span><span class="sxs-lookup"><span data-stu-id="f83cd-108">Create the Microsoft 365 simulated enterprise test environment.</span></span>
2. <span data-ttu-id="f83cd-109">Установка и настройка Azure AD Connect на виртуальной машине APP1.</span><span class="sxs-lookup"><span data-stu-id="f83cd-109">Install and configure Azure AD Connect on APP1.</span></span>
    
> [!TIP]
> <span data-ttu-id="f83cd-110">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="f83cd-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="f83cd-111">Этап 1. Создание тестовой среды "имитация предприятия" для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f83cd-111">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="f83cd-p102">Следуйте инструкциям в статье о [базовой конфигурации "имитация предприятия" для Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Вот получившаяся конфигурация.</span><span class="sxs-lookup"><span data-stu-id="f83cd-p102">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md). Here is your resulting configuration.</span></span>
  
![Базовая конфигурация "имитация предприятия"](media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="f83cd-115">Конфигурация состоит из перечисленных ниже компонентов.</span><span class="sxs-lookup"><span data-stu-id="f83cd-115">This configuration consists of:</span></span> 
  
- <span data-ttu-id="f83cd-116">Пробные или платные подписки на Office 365 E5 и EMS E5.</span><span class="sxs-lookup"><span data-stu-id="f83cd-116">Office 365 E5 and EMS E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="f83cd-117">Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="f83cd-117">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="f83cd-118">DC1 — контроллер домена для домена testlab.\<имя вашего общедоступного домена> AD DS.</span><span class="sxs-lookup"><span data-stu-id="f83cd-118">DC1 is a domain controller for the testlab.\<your public domain name> Active Directory Domain Services (AD DS) domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="f83cd-119">Этап 2. Создание и регистрация домена testlab</span><span class="sxs-lookup"><span data-stu-id="f83cd-119">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="f83cd-120">На этом этапе создается и добавляется в подписку публичный домен DNS.</span><span class="sxs-lookup"><span data-stu-id="f83cd-120">In this phase you add a public DNS domain and add it to your subscription.</span></span>

<span data-ttu-id="f83cd-p104">Сначала под руководством регистратора создайте новое имя публичного домена DNS на основе текущего имени домена и добавьте его в подписку на Office 365. Рекомендуем использовать имя **testlab.**\<ваш публичный домен>. Например, если имя вашего публичного домена — <span>**contoso</span>.com**, добавьте имя **<span>testlab</span>.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="f83cd-p104">First, work with your public DNS registration provider to create a new public DNS domain name based on your current domain name and add it to your Office 365 subscription. We recommend using the name **testlab.**\<your public domain>. For example, if your public domain name is <span>**contoso</span>.com**, add the public domain name **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="f83cd-124">Затем добавьте домен **testlab.**\<общедоступный домен> в пробную или платную подписку на Office 365, пройдя процесс регистрации домена.</span><span class="sxs-lookup"><span data-stu-id="f83cd-124">Next, you add the **testlab.**\<your public domain> domain to your Office 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="f83cd-125">Он включает добавление записей DNS к домену **testlab.**\<общедоступный домен>.</span><span class="sxs-lookup"><span data-stu-id="f83cd-125">This consists of adding additional DNS records to the **testlab.**\<your public domain> domain.</span></span> <span data-ttu-id="f83cd-126">Дополнительные сведения см. в статье [Добавление пользователей и домена в Office 365](https://support.office.com/article/Add-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="f83cd-126">For more information, see [Add users and domain to Office 365](https://support.office.com/article/Add-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span> 

<span data-ttu-id="f83cd-127">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="f83cd-127">Here is your resulting configuration.</span></span>
  
![Регистрация доменного имени testlab](media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="f83cd-129">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="f83cd-129">This configuration consists of:</span></span>

- <span data-ttu-id="f83cd-130">Пробные или платные подписки на Office 365 E5 и EMS E5 с зарегистрированным доменом DNS testlab.\<имя общедоступного домена>.</span><span class="sxs-lookup"><span data-stu-id="f83cd-130">Office 365 E5 and EMS E5 trial or paid subscriptions with the DNS domain testlab.\<your public domain name> registered.</span></span>
- <span data-ttu-id="f83cd-131">Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure.</span><span class="sxs-lookup"><span data-stu-id="f83cd-131">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="f83cd-132">Обратите внимание, что testlab.\<имя вашего публичного домена> теперь:</span><span class="sxs-lookup"><span data-stu-id="f83cd-132">Notice how the testlab.\<your public domain name> is now:</span></span>

- <span data-ttu-id="f83cd-133">поддерживается общедоступными DNS-записями;</span><span class="sxs-lookup"><span data-stu-id="f83cd-133">Supported by public DNS records.</span></span>
- <span data-ttu-id="f83cd-134">зарегистрирован в подписках на Office 365 и EMS;</span><span class="sxs-lookup"><span data-stu-id="f83cd-134">Registered in your Office 365 and EMS subscriptions.</span></span>
- <span data-ttu-id="f83cd-135">Домен AD DS имитированной интрасети.</span><span class="sxs-lookup"><span data-stu-id="f83cd-135">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="f83cd-136">Этап 3. Установка Azure AD Connect на APP1</span><span class="sxs-lookup"><span data-stu-id="f83cd-136">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="f83cd-137">На этом этапе устанавливается и настраивается инструмент Azure AD Connect на APP1, а затем проверяется его работа.</span><span class="sxs-lookup"><span data-stu-id="f83cd-137">In this phase, you install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="f83cd-138">Сначала выполняется установка и настройка Azure AD Connect на APP1.</span><span class="sxs-lookup"><span data-stu-id="f83cd-138">First, you install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="f83cd-139">На [портале Azure](https://portal.azure.com) выполните вход с помощью учетной записи глобального администратора и подключитесь к виртуальной машине APP1 с помощью учетной записи TESTLAB\\User1.</span><span class="sxs-lookup"><span data-stu-id="f83cd-139">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="f83cd-140">На рабочем столе APP1 откройте командную строку Windows PowerShell с правами администратора и выполните указанные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="f83cd-140">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands:</span></span>
    
   ```
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="f83cd-141">На панели задач выберите **Internet Explorer** и перейдите по адресу [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span><span class="sxs-lookup"><span data-stu-id="f83cd-141">From the task bar, click **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="f83cd-142">На странице Microsoft Azure Active Directory Connect нажмите **Скачать**, а затем **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="f83cd-142">On the Microsoft Azure Active Directory Connect page, click **Download**, and then click **Run**.</span></span>
    
5. <span data-ttu-id="f83cd-143">На странице **Добро пожаловать в Azure AD Connect** установите флажок **Принимаю** и нажмите кнопку **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="f83cd-143">On the **Welcome to Azure AD Connect** page, click **I agree**, and then click **Continue**.</span></span>
    
6. <span data-ttu-id="f83cd-144">На странице **Стандартные параметры** выберите **Использовать стандартные параметры**.</span><span class="sxs-lookup"><span data-stu-id="f83cd-144">On the **Express Settings** page, click **Use express settings**.</span></span>
    
7. <span data-ttu-id="f83cd-145">На странице **Подключение к Azure AD** введите имя своей учетной записи глобального администратора Office 365 в поле **Имя пользователя**, введите пароль в поле **Пароль** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f83cd-145">On the **Connect to Azure AD** page, type your Office 365 global administrator account name in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="f83cd-146">На странице **Подключение к AD DS** введите **TESTLAB\\User1** в поле **Имя пользователя** и пароль в поле **Пароль**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="f83cd-146">On the **Connect to AD DS** page, type **TESTLAB\\User1** in **Username,** type its password in **Password**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="f83cd-147">На странице **Готово к настройке** нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="f83cd-147">On the **Ready to configure** page, click **Install**.</span></span>
    
10. <span data-ttu-id="f83cd-148">На странице **Настройка завершена** нажмите **Выход**.</span><span class="sxs-lookup"><span data-stu-id="f83cd-148">On the **Configuration complete** page, click **Exit**.</span></span>
    
11. <span data-ttu-id="f83cd-149">В браузере Internet Explorer перейдите в Центр администрирования Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="f83cd-149">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="f83cd-150">На панели навигации слева выберите элементы **Пользователи > Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="f83cd-150">In the left navigation, click **Users > Active users**.</span></span>
    
    <span data-ttu-id="f83cd-151">Обратите внимание на учетную запись **User1**.</span><span class="sxs-lookup"><span data-stu-id="f83cd-151">Note the account named **User1**.</span></span> <span data-ttu-id="f83cd-152">Эта учетная запись находится на домене AD DS TESTLAB. Это доказывает, что синхронизация службы каталогов выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="f83cd-152">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="f83cd-p107">Выберите учетную запись **User1**. Нажмите кнопку **Изменить** для лицензий на продукты.</span><span class="sxs-lookup"><span data-stu-id="f83cd-p107">Click the **User1** account. For product licenses, click **Edit**.</span></span>
    
14. <span data-ttu-id="f83cd-p108">На панели **Лицензии на продукты** выберите страну и переведите переключатель **Office 365 корпоративный E5** в положение **Вкл.** Выполните те же действия для лицензии **Enterprise Mobility + Security E5**.</span><span class="sxs-lookup"><span data-stu-id="f83cd-p108">In **Product licenses**, select your scountry, and then click the **Off** control for **Office 365 Enterprise E5** (switching it to **On**). Do the same for the **Enterprise Mobility + Security E5** license.</span></span> 

15. <span data-ttu-id="f83cd-157">Нажмите **Сохранить** в нижней части страницы, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="f83cd-157">Click **Save** at the bottom of the page, and then click **Close**.</span></span>
    
<span data-ttu-id="f83cd-158">Затем проверьте возможность входа в вашу подписку на Office 365 с использованием учетной записи <strong>user1@testlab.</strong>\<имя вашего домена> на имя пользователя User1.</span><span class="sxs-lookup"><span data-stu-id="f83cd-158">Next, you test the ability to sign in to your Office 365 subscription with the <strong>user1@testlab.</strong>\<your domain name> user name of the User1 account.</span></span>

1. <span data-ttu-id="f83cd-159">Выйдите из Office 365 на APP1 и повторно войдите, используя другую учетную запись.</span><span class="sxs-lookup"><span data-stu-id="f83cd-159">From APP1, sign out of Office 365, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="f83cd-p109">При появлении запроса имени пользователя и пароля, укажите <strong>user1@testlab.</strong>\<имя вашего домена> и пароль пользователя User1. Должен произойти успешный вход в качестве пользователя User1.</span><span class="sxs-lookup"><span data-stu-id="f83cd-p109">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your domain name> and the User1 password. You should successfully sign in as User1.</span></span> 
 
<span data-ttu-id="f83cd-162">Обратите внимание, что хотя у пользователя User1 есть разрешения администратора для домена AD DS TESTLAB, он не является глобальным администратором Office 365.</span><span class="sxs-lookup"><span data-stu-id="f83cd-162">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not an Office 365 global administrator.</span></span> <span data-ttu-id="f83cd-163">Следовательно, значок **Администратор** не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="f83cd-163">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="f83cd-164">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="f83cd-164">Here is your resulting configuration.</span></span>

![Тестовая среда "имитация предприятия с синхронизацией хэшей паролей"](media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="f83cd-166">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="f83cd-166">This configuration consists of:</span></span> 
  
- <span data-ttu-id="f83cd-167">Пробные или платные подписки на Office 365 E5 и EMS E5 с зарегистрированным доменом DNS TESTLAB.\<доменное имя>.</span><span class="sxs-lookup"><span data-stu-id="f83cd-167">Office 365 E5 and EMS E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="f83cd-168">Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure.</span><span class="sxs-lookup"><span data-stu-id="f83cd-168">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="f83cd-169">Azure AD Connect работает на APP1 для периодической синхронизации домена AD DS TESTLAB с клиентом Azure AD, связанным с подписками на Office 365 и EMS E5.</span><span class="sxs-lookup"><span data-stu-id="f83cd-169">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.</span></span>
- <span data-ttu-id="f83cd-170">Учетная запись User1 на домене AD DS TESTLAB синхронизирована с клиентом Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f83cd-170">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="f83cd-171">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="f83cd-171">Next step</span></span>

<span data-ttu-id="f83cd-172">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="f83cd-172">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="f83cd-173">См. также</span><span class="sxs-lookup"><span data-stu-id="f83cd-173">See also</span></span>

[<span data-ttu-id="f83cd-174">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="f83cd-174">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="f83cd-175">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="f83cd-175">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f83cd-176">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="f83cd-176">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


