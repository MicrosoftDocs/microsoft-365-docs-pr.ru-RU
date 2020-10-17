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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: Сводка. Настройте и протестируйте эффективный единый вход Azure AD для тестовой среды Microsoft 365.
ms.openlocfilehash: f98f82de50feb2a9f92d1ecc4775c5307b314a72
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487610"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="3cf9c-103">Эффективный единый вход Azure AD для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3cf9c-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="3cf9c-104">*Это руководство по лаборатории тестирования можно использовать как для Microsoft 365 Enterprise, так и для корпоративных тестовых сред Office 365.*</span><span class="sxs-lookup"><span data-stu-id="3cf9c-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="3cf9c-p101">Единая одноSign-Onная служба Azure AD позволяет автоматически подключаться к пользователям, если они находятся на компьютерах или устройствах, подключенных к сети Организации. Единый единый вход в Azure AD обеспечивает пользователям легкий доступ к облачным приложениям, не требуя дополнительных компонентов локальной сети.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-p101">Azure AD Seamless Single Sign-On (Seamless SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network. Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="3cf9c-107">В этой статье описывается настройка тестовой среды Microsoft 365 для беспрепятственного единого входа Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-107">This article describes how to configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="3cf9c-108">Настройка беспрепятственного единого входа Azure AD состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="3cf9c-108">Setting up Azure AD Seamless SSO involves two phases:</span></span>
- [<span data-ttu-id="3cf9c-109">Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3cf9c-109">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="3cf9c-110">Этап 2. Настройка эффективного единого входа Azure AD через Azure AD Connect на APP1</span><span class="sxs-lookup"><span data-stu-id="3cf9c-110">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="3cf9c-112">Для отображения всех статей, посвященных руководству по лаборатории тестирования Microsoft 365 для предприятий, перейдите к разделу [руководство по лаборатории тестирования microsoft 365 для предприятия](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="3cf9c-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="3cf9c-113">Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3cf9c-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="3cf9c-114">Следуйте инструкциям в статье [Синхронизация хэша паролей для Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="3cf9c-114">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="3cf9c-115">Результирующая конфигурация выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3cf9c-115">Your resulting configuration looks like this:</span></span>
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="3cf9c-117">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="3cf9c-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="3cf9c-118">Пробная или платная подписка Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="3cf9c-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="3cf9c-119">Упрощенная интрасеть Организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="3cf9c-120">Azure AD Connect работает на APP1 для периодической синхронизации домена доменных служб Active Directory TESTLAB (AD DS) с клиентом Azure AD вашей подписки на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-120">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="3cf9c-121">Этап 2. Настройка эффективного единого входа Azure AD через Azure AD Connect на APP1</span><span class="sxs-lookup"><span data-stu-id="3cf9c-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="3cf9c-122">На этом этапе настройте Azure AD Connect на APP1 для беспрепятственного единого входа Azure AD, а затем убедитесь, что она работает.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-122">In this phase, configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="3cf9c-123">Настройка Azure AD Connect на виртуальной машине APP1</span><span class="sxs-lookup"><span data-stu-id="3cf9c-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="3cf9c-124">На [портале Azure](https://portal.azure.com) выполните вход с помощью учетной записи глобального администратора и затем подключитесь к виртуальной машине APP1 с учетной записью TESTLAB\User1.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="3cf9c-125">На настольном компьютере APP1 запустите Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-125">From the APP1 desktop, run Azure AD Connect.</span></span>

3. <span data-ttu-id="3cf9c-126">На **странице приветствия**нажмите кнопку **настроить**.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-126">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="3cf9c-127">На странице **Дополнительные задачи** выберите **изменить вход пользователя**и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-127">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>

5. <span data-ttu-id="3cf9c-128">На странице **Подключение к Azure AD** введите учетные данные глобального администратора, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-128">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="3cf9c-129">На странице **входа пользователя** выберите **включить единый вход**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-129">On the **User sign-in** page, select **Enable single sign-on**, and then select **Next**.</span></span>

7. <span data-ttu-id="3cf9c-130">На странице **Включение единого входа** нажмите кнопку **Ввод учетных данных**.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-130">On the **Enable single sign-on** page, select **Enter credentials**.</span></span>

8. <span data-ttu-id="3cf9c-131">В диалоговом окне " **Безопасность Windows** " введите **Пользователь1** и пароль учетной записи User1, нажмите кнопку **ОК**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-131">In the **Windows Security** dialog box, enter **user1** and the password of the user1 account, select **OK**, and then select **Next**.</span></span>

9. <span data-ttu-id="3cf9c-132">На странице **Готово к настройке** нажмите кнопку **настроить**.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-132">On the **Ready to Configure** page, select **Configure**.</span></span>

10. <span data-ttu-id="3cf9c-133">На странице **Завершение настройки** нажмите кнопку **выход**.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-133">On the **Configuration complete** page, select **Exit**.</span></span>

11. <span data-ttu-id="3cf9c-134">В левой области портала Azure выберите **Azure Active Directory**  >  **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-134">From the Azure portal, in the left pane, select **Azure Active Directory** > **Azure AD Connect**.</span></span> <span data-ttu-id="3cf9c-135">Убедитесь, что функция **единого входа** **включена**.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-135">Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="3cf9c-136">Затем проверьте возможность входа в подписку с помощью <strong>User1@testlab.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="3cf9c-136">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="3cf9c-137">на имя пользователя учетной записи User1.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-137">user name of the User1 account.</span></span>

1. <span data-ttu-id="3cf9c-138">В Internet Explorer на APP1 нажмите значок Параметры, а затем выберите **Свойства браузера**.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-138">From Internet Explorer on APP1, select the settings icon, and then select **Internet Options**.</span></span>
 
2. <span data-ttu-id="3cf9c-139">В окне **Свойства обозревателя**перейдите на вкладку **Безопасность** .</span><span class="sxs-lookup"><span data-stu-id="3cf9c-139">In **Internet Options**, select the **Security** tab.</span></span>

3. <span data-ttu-id="3cf9c-140">Выберите **Местная интрасеть**и нажмите кнопку **сайты**.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-140">Select **Local intranet**, and then select **Sites**.</span></span>

4. <span data-ttu-id="3cf9c-141">В **локальной интрасети**выберите **Advanced (дополнительно**).</span><span class="sxs-lookup"><span data-stu-id="3cf9c-141">In **Local intranet**, select **Advanced**.</span></span>

5. <span data-ttu-id="3cf9c-142">В разделе **Добавление этого веб-сайта в зону**введите **HTTPS<span>://</span>Autologon.microsoftazuread-SSO.com**, нажмите кнопку **Добавить**  >  **Закрыть**  >  **ОК**  >  **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-142">In **Add this website to the zone**, enter **https<span>://</span>autologon.microsoftazuread-sso.com**, select **Add** > **Close** > **OK** > **OK**.</span></span>

6. <span data-ttu-id="3cf9c-143">Выйдите и повторно войдите, используя другую учетную запись.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-143">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="3cf9c-144">Когда вам будет предложено выполнить вход, укажите <strong>User1@testlab.</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="3cf9c-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="3cf9c-145">имя, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-145">name, and then select **Next**.</span></span> <span data-ttu-id="3cf9c-146">Вход в учетную запись User1 будет выполнен без запроса пароля.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-146">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="3cf9c-147">Это доказывает, что эффективный единый вход работает.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-147">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="3cf9c-148">Обратите внимание, что хотя у пользователя User1 есть разрешения администратора для домена AD DS TESTLAB, он не является глобальным администратором для Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-148">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="3cf9c-149">Следовательно, значок **Администратор** не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-149">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="3cf9c-150">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-150">Here is your resulting configuration:</span></span>

![Смоделированная организации с тестовой средой сквозной проверки подлинности](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="3cf9c-152">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="3cf9c-152">This configuration consists of:</span></span>

- <span data-ttu-id="3cf9c-153">Пробную или платную подписку Microsoft 365 в формате testlab с DNS-доменом.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="3cf9c-153">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<*your domain name*></span></span> <span data-ttu-id="3cf9c-154">-</span><span class="sxs-lookup"><span data-stu-id="3cf9c-154">registered.</span></span>
- <span data-ttu-id="3cf9c-155">Упрощенная интрасеть Организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-155">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="3cf9c-156">Azure AD Connect работает на APP1 для синхронизации списка учетных записей и групп из клиента Azure AD, связанного с подпиской на Microsoft 365, с доменом AD DS TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-156">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="3cf9c-157">Единый единый вход в Azure AD включается, чтобы компьютеры в имитируемой интрасети могли входить в облачные ресурсы Microsoft 365 без указания пароля учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-157">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifying a user account password.</span></span>

## <a name="next-step"></a><span data-ttu-id="3cf9c-158">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="3cf9c-158">Next step</span></span>

<span data-ttu-id="3cf9c-159">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="3cf9c-160">См. также</span><span class="sxs-lookup"><span data-stu-id="3cf9c-160">See also</span></span>

[<span data-ttu-id="3cf9c-161">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="3cf9c-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="3cf9c-162">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="3cf9c-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="3cf9c-163">Microsoft 365 для корпоративных документов</span><span class="sxs-lookup"><span data-stu-id="3cf9c-163">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
