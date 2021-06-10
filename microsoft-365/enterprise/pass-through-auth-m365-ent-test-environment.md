---
title: Сквозная проверка подлинности для тестовой среды Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
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
ms.assetid: ''
description: Сводка. Настройка сквозной проверки подлинности для тестовой среды Microsoft 365
ms.openlocfilehash: cdbb6927fb8ca0001e3089c7169ce9046208e8f8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921532"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a><span data-ttu-id="2a660-103">Сквозная проверка подлинности для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2a660-103">Pass-through authentication for your Microsoft 365 test environment</span></span>

<span data-ttu-id="2a660-104">*Это руководство по тестовой лаборатории можно использовать как для Microsoft 365, так и для Office 365 корпоративный среды тестирования.*</span><span class="sxs-lookup"><span data-stu-id="2a660-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="2a660-105">Организации, которые хотят напрямую использовать свою локальную инфраструктуру доменных служб Active Directory (AD DS) при проверке подлинности для приложений и облачных служб Майкрософт, могут использовать сквозную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="2a660-105">Organizations that want to directly use their on-premises Active Directory Domain Services (AD DS) infrastructure for authentication to Microsoft cloud-based services and applications can use pass-through authentication.</span></span> <span data-ttu-id="2a660-106">В этой статье описывается, как можно настроить тестовую среду Microsoft 365 для сквозной проверки подлинности с созданием следующей конфигурации:</span><span class="sxs-lookup"><span data-stu-id="2a660-106">This article describes how you can configure your Microsoft 365 test environment for pass-through authentication, resulting in the following configuration:</span></span>
  
![Смоделированная организация с тестовой средой сквозной проверки подлинности](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="2a660-108">Процесс настройки этой тестовой среды состоит из двух указанных ниже основных этапов.</span><span class="sxs-lookup"><span data-stu-id="2a660-108">There are two phases to setting up this test environment:</span></span>

1.    <span data-ttu-id="2a660-109">Создание тестовой среды смоделированной организации Microsoft 365 с синхронизацией хэша паролей.</span><span class="sxs-lookup"><span data-stu-id="2a660-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.    <span data-ttu-id="2a660-110">Настройка Azure AD Connect на виртуальной машине APP1 для сквозной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="2a660-110">Configure Azure AD Connect on APP1 for pass-through authentication.</span></span>
    
![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="2a660-112">Щелкните [здесь](../downloads/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 для крупных предприятий.</span><span class="sxs-lookup"><span data-stu-id="2a660-112">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="2a660-113">Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2a660-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="2a660-p102">Следуйте инструкциям в статье [Синхронизация хэша паролей для Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="2a660-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="2a660-117">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="2a660-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="2a660-118">Microsoft 365 E5 пробную или платную подписку.</span><span class="sxs-lookup"><span data-stu-id="2a660-118">Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="2a660-119">Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure.</span><span class="sxs-lookup"><span data-stu-id="2a660-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="2a660-120">Azure AD Connect работает на APP1 для периодической синхронизации домена AD DS TESTLAB с клиентом Azure AD, связанным с подпиской на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2a660-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a><span data-ttu-id="2a660-121">Этап 2. Настройка Azure AD Connect на виртуальной машине APP1 для сквозной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="2a660-121">Phase 2: Configure Azure AD Connect on APP1 for pass-through authentication</span></span>

<span data-ttu-id="2a660-122">На этом этапе нужно выполнить настройку Azure AD Connect на виртуальной машине APP1 для использования сквозной проверки подлинности и затем убедиться в ее работоспособности.</span><span class="sxs-lookup"><span data-stu-id="2a660-122">In this phase, you configure Azure AD Connect on APP1 to use pass-through authentication, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="2a660-123">Настройка Azure AD Connect на виртуальной машине APP1</span><span class="sxs-lookup"><span data-stu-id="2a660-123">Configure Azure AD Connect on APP1</span></span>

1.    <span data-ttu-id="2a660-124">На [портале Azure](https://portal.azure.com) выполните вход с помощью учетной записи глобального администратора и затем подключитесь к виртуальной машине APP1 с учетной записью TESTLAB\User1.</span><span class="sxs-lookup"><span data-stu-id="2a660-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.    <span data-ttu-id="2a660-125">На рабочем столе виртуальной машины APP1 запустите Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="2a660-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3.    <span data-ttu-id="2a660-126">На **странице приветствия** нажмите кнопку **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="2a660-126">On the **Welcome page**, click **Configure**.</span></span>

4.    <span data-ttu-id="2a660-127">На странице дополнительных задач выберите **Смена имени пользователя для входа** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2a660-127">On the Additional tasks page, click **Change user sign-in**, and then click **Next**.</span></span>

5.    <span data-ttu-id="2a660-128">На странице **Подключение к Azure AD** введите учетные данные глобального администратора и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2a660-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6.    <span data-ttu-id="2a660-129">На странице **Вход пользователя** щелкните пункт **Сквозная проверка подлинности**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="2a660-129">On the **User sign-in** page, click **Pass-through authentication**, and then click **Next**.</span></span>

7.    <span data-ttu-id="2a660-130">На странице **Готово к настройке** нажмите кнопку **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="2a660-130">On the **Ready to configure** page, click **Configure**.</span></span>

8.    <span data-ttu-id="2a660-131">На странице **Настройка завершена** нажмите **Выход**.</span><span class="sxs-lookup"><span data-stu-id="2a660-131">On the **Configuration complete** page, click **Exit**.</span></span>

9.    <span data-ttu-id="2a660-p104">На портале Azure, в области слева, выберите **Azure Active Directory > Azure AD Connect**. Убедитесь, что функция **Сквозная проверка подлинности** **включена**.</span><span class="sxs-lookup"><span data-stu-id="2a660-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Pass-through authentication** feature appears as **Enabled**.</span></span>

10.    <span data-ttu-id="2a660-p105">Выберите пункт **Сквозная проверка подлинности**. На панели **Сквозная проверка подлинности** перечислены серверы, где установлены агенты проверки подлинности. Виртуальная машина APP1 должна отображаться в списке. Закройте панель **Сквозная проверка подлинности**.</span><span class="sxs-lookup"><span data-stu-id="2a660-p105">Click **Pass-through authentication**. The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed. You should see APP1 in the list. Close the **Pass-through authentication** pane.</span></span>

<span data-ttu-id="2a660-138">Далее проверьте возможность войти в подписку с помощью <strong>user1@testlab.</strong>\<your public domain></span><span class="sxs-lookup"><span data-stu-id="2a660-138">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="2a660-139">на имя пользователя учетной записи User1.</span><span class="sxs-lookup"><span data-stu-id="2a660-139">user name of the User1 account.</span></span>

1. <span data-ttu-id="2a660-140">Находясь в APP1, выйдите и повторно войдите, используя другую учетную запись.</span><span class="sxs-lookup"><span data-stu-id="2a660-140">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="2a660-141">При появлении запроса имени пользователя и пароля, укажите <strong>user1@testlab.</strong>\<your public domain></span><span class="sxs-lookup"><span data-stu-id="2a660-141">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="2a660-142">и пароль пользователя User1.</span><span class="sxs-lookup"><span data-stu-id="2a660-142">and the User1 password.</span></span> <span data-ttu-id="2a660-143">Должен осуществиться успешный вход в качестве пользователя User1.</span><span class="sxs-lookup"><span data-stu-id="2a660-143">You should successfully sign in as User1.</span></span>

<span data-ttu-id="2a660-144">Обратите внимание, что хотя у пользователя User1 есть разрешения администратора для домена AD DS TESTLAB, он не является глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="2a660-144">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="2a660-145">Следовательно, значок **Администратор** не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="2a660-145">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="2a660-146">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="2a660-146">Here is your resulting configuration:</span></span>

![Смоделированная организации с тестовой средой сквозной проверки подлинности](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
<span data-ttu-id="2a660-148">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="2a660-148">This configuration consists of:</span></span>

- <span data-ttu-id="2a660-149">Пробная Microsoft 365 E5 или платная подписка с тестовой плитой домена DNS.\<your domain name></span><span class="sxs-lookup"><span data-stu-id="2a660-149">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name></span></span> <span data-ttu-id="2a660-150">-</span><span class="sxs-lookup"><span data-stu-id="2a660-150">registered.</span></span>
- <span data-ttu-id="2a660-p110">Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure. Агент проверки подлинности работает на компьютере APP1 для обработки запросов сквозной проверки подлинности от клиента Azure AD, связанного с подпиской на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2a660-p110">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="next-step"></a><span data-ttu-id="2a660-153">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="2a660-153">Next step</span></span>

<span data-ttu-id="2a660-154">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="2a660-154">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a660-155">См. также</span><span class="sxs-lookup"><span data-stu-id="2a660-155">See also</span></span>

[<span data-ttu-id="2a660-156">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="2a660-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2a660-157">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="2a660-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="2a660-158">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="2a660-158">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)