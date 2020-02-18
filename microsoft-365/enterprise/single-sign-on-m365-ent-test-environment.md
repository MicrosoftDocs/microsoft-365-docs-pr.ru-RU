---
title: Эффективный единый вход Azure AD для тестовой среды Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
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
description: Сводка. Настройте и протестируйте эффективный единый вход Azure AD для тестовой среды Microsoft 365.
ms.openlocfilehash: d2b17acb2b57e379fe204e3ea4402b3f00ef7d6c
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083808"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="8eefd-103">Эффективный единый вход Azure AD для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8eefd-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="8eefd-104">*Это руководство по лаборатории тестирования можно использовать для тестовых сред Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="8eefd-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="8eefd-p101">Эффективный единый вход Azure AD обеспечивает автоматический вход пользователей на компьютерах или устройствах, подключенных к сети организации. Эффективный единый вход Azure AD обеспечивает легкий доступ к облачным приложениям без использования дополнительных локальных компонентов.</span><span class="sxs-lookup"><span data-stu-id="8eefd-p101">Azure AD Seamless Single Sign-On (SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network. Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="8eefd-107">В этой статье описывается, как настроить эффективный единый вход Azure AD для тестовой среды Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8eefd-107">This article describes how you can configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="8eefd-108">Эта настройка состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="8eefd-108">There are two phases to setting this up:</span></span>

1.  <span data-ttu-id="8eefd-109">Создание тестовой среды с синхронизацией хэшей паролей для имитации корпоративной среды Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8eefd-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="8eefd-110">Настройка эффективного единого входа Azure AD через Azure AD Connect на APP1.</span><span class="sxs-lookup"><span data-stu-id="8eefd-110">Configure Azure AD Connect on APP1 for Azure AD Seamless SSO.</span></span>
    
![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="8eefd-112">Щелкните [здесь](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="8eefd-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="8eefd-113">Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8eefd-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="8eefd-p102">Следуйте инструкциям в статье [Синхронизация хэша паролей для Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="8eefd-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="8eefd-117">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="8eefd-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="8eefd-118">Пробные или платные подписки на Microsoft 365 E5 или Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="8eefd-118">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="8eefd-119">Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure.</span><span class="sxs-lookup"><span data-stu-id="8eefd-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="8eefd-120">Azure AD Connect работает на APP1 для периодической синхронизации домена TESTLAB доменных служб Active Directory (AD DS) с клиентом Azure AD, связанным с подпиской на Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="8eefd-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 or Office 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="8eefd-121">Этап 2. Настройка эффективного единого входа Azure AD через Azure AD Connect на APP1</span><span class="sxs-lookup"><span data-stu-id="8eefd-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="8eefd-122">На этом этапе вы настраиваете эффективный единый вход Azure AD, используя Azure AD Connect на APP1, а затем проверяете его работу.</span><span class="sxs-lookup"><span data-stu-id="8eefd-122">In this phase, you configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="8eefd-123">Настройка Azure AD Connect на виртуальной машине APP1</span><span class="sxs-lookup"><span data-stu-id="8eefd-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="8eefd-124">На [портале Azure](https://portal.azure.com) выполните вход с помощью учетной записи глобального администратора и затем подключитесь к виртуальной машине APP1 с учетной записью TESTLAB\User1.</span><span class="sxs-lookup"><span data-stu-id="8eefd-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="8eefd-125">На рабочем столе виртуальной машины APP1 запустите Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="8eefd-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3. <span data-ttu-id="8eefd-126">На **странице приветствия** нажмите кнопку **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="8eefd-126">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="8eefd-127">На странице **Дополнительные задачи** выберите **Смена имени пользователя для входа** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8eefd-127">On the **Additional tasks** page, click **Change user sign-in**, and then click **Next**.</span></span>

5. <span data-ttu-id="8eefd-128">На странице **Подключение к Azure AD** введите учетные данные глобального администратора и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8eefd-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="8eefd-129">На странице **Вход пользователя** выберите **Включить единый вход** и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8eefd-129">On the **User sign-in** page, select **Enable single sign-on**, and then click **Next**.</span></span>

7. <span data-ttu-id="8eefd-130">На странице **Включить единый вход** щелкните **Ввести учетные данные**.</span><span class="sxs-lookup"><span data-stu-id="8eefd-130">On the **Enable single sign-on** page, click **Enter credentials**.</span></span>

8. <span data-ttu-id="8eefd-p103">В диалоговом окне **Безопасность Windows** введите **user1** и пароль учетной записи user1, а затем нажмите **ОК**. Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8eefd-p103">In the **Windows Security** dialog box, type **user1** and the password of the user1 account, and then click **OK**. Click **Next**.</span></span>

9. <span data-ttu-id="8eefd-133">На странице **Готово к настройке** нажмите **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="8eefd-133">On the **Ready to Configure** page, click **Configure**.</span></span>

10. <span data-ttu-id="8eefd-134">На странице **Настройка завершена** нажмите **Выход**.</span><span class="sxs-lookup"><span data-stu-id="8eefd-134">On the **Configuration complete** page, click **Exit**.</span></span>

11. <span data-ttu-id="8eefd-p104">На портале Azure, в области слева, выберите **Azure Active Directory > Azure AD Connect**. Убедитесь, что функция **Эффективный единый вход** **включена**.</span><span class="sxs-lookup"><span data-stu-id="8eefd-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="8eefd-137">Затем проверьте возможность входа в вашу подписку с помощью учетной записи <strong>user1@testlab.</strong>\<общедоступный домен> на имя пользователя User1.</span><span class="sxs-lookup"><span data-stu-id="8eefd-137">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="8eefd-138">В Internet Explorer на APP1 щелкните значок настроек и выберите **Свойства браузера**.</span><span class="sxs-lookup"><span data-stu-id="8eefd-138">From Internet Explorer on APP1, click the settings icon, and then click **Internet Options**.</span></span>
 
2. <span data-ttu-id="8eefd-139">В окне **Свойства обозревателя** перейдите на вкладку **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="8eefd-139">In **Internet Options**, click the **Security** tab.</span></span>

3. <span data-ttu-id="8eefd-140">Выберите **Местная интрасеть** и нажмите кнопку **Сайты**.</span><span class="sxs-lookup"><span data-stu-id="8eefd-140">Click **Local intranet**, and then click **Sites**.</span></span>

4. <span data-ttu-id="8eefd-141">В окне **Местная интрасеть** нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="8eefd-141">In **Local intranet**, click **Advanced**.</span></span>

5. <span data-ttu-id="8eefd-142">В поле **Добавить в зону следующий узел** введите **https<span>://</span>autologon.microsoftazuread-sso.com** и нажмите **Добавить > Закрыть > ОК > ОК**.</span><span class="sxs-lookup"><span data-stu-id="8eefd-142">In **Add this website to the zone**, type **https<span>://</span>autologon.microsoftazuread-sso.com**, click **Add > Close > OK > OK**.</span></span>

6. <span data-ttu-id="8eefd-143">Выйдите и повторно войдите, используя другую учетную запись.</span><span class="sxs-lookup"><span data-stu-id="8eefd-143">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="8eefd-144">Укажите имя <strong>user1@testlab.</strong>\<общедоступный домен> и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8eefd-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<your public domain> name, and then click **Next**.</span></span> <span data-ttu-id="8eefd-145">Вход в учетную запись User1 будет выполнен без запроса пароля.</span><span class="sxs-lookup"><span data-stu-id="8eefd-145">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="8eefd-146">Это доказывает, что эффективный единый вход работает.</span><span class="sxs-lookup"><span data-stu-id="8eefd-146">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="8eefd-147">Обратите внимание, что хотя у пользователя User1 есть разрешения администратора для домена AD DS TESTLAB, он не является глобальным администратором для Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8eefd-147">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="8eefd-148">Следовательно, значок **Администратор** не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="8eefd-148">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="8eefd-149">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="8eefd-149">Here is your resulting configuration:</span></span>

![Смоделированная организации с тестовой средой сквозной проверки подлинности](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
<span data-ttu-id="8eefd-151">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="8eefd-151">This configuration consists of:</span></span>

- <span data-ttu-id="8eefd-152">Пробные или платные подписки на Microsoft 365 E5 или Office 365 E5 с зарегистрированным доменом DNS testlab.\<доменное имя>.</span><span class="sxs-lookup"><span data-stu-id="8eefd-152">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name> registered.</span></span>
- <span data-ttu-id="8eefd-153">Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure.</span><span class="sxs-lookup"><span data-stu-id="8eefd-153">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="8eefd-154">Azure AD Connect работает на APP1 для синхронизации списка учетных записей и групп из клиента Azure AD, связанного с подпиской на Microsoft 365 или Office 365, с доменом AD DS TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="8eefd-154">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 or Office 365 subscription to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="8eefd-155">Эффективный единый вход Azure AD включен, поэтому при входе в облачные ресурсы Microsoft 365 с компьютеров в моделируемой интрасети не требуется указывать пароль учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="8eefd-155">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifing a user account password.</span></span>

<span data-ttu-id="8eefd-156">Информацию и ссылки для настройки эффективного единого входа Azure AD в эксплуатационной среде вы найдете в описании шага [Упрощение входа пользователей](identity-secure-your-passwords.md#identity-sso) этапа "Идентификация".</span><span class="sxs-lookup"><span data-stu-id="8eefd-156">See the [Simplify user sign-in](identity-secure-your-passwords.md#identity-sso) step in the Identity phase for information and links to configure Azure AD Seamless SSO in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="8eefd-157">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="8eefd-157">Next step</span></span>

<span data-ttu-id="8eefd-158">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="8eefd-158">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="8eefd-159">См. также</span><span class="sxs-lookup"><span data-stu-id="8eefd-159">See also</span></span>

[<span data-ttu-id="8eefd-160">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="8eefd-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="8eefd-161">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="8eefd-161">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="8eefd-162">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="8eefd-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


