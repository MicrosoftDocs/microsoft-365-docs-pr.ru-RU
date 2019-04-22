---
title: Обратная запись пароля для тестовой среды Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
ms.audience: ITPro
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
description: Сводка. Настройка обратной записи пароля для тестовой среды Microsoft 365
ms.openlocfilehash: 11a0efbae09c36098a19725187cd43b53850f4fc
ms.sourcegitcommit: db52a11eb192a28dbec827c565e36ad4a81d8e3f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2019
ms.locfileid: "31901223"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="03d7d-103">Обратная запись пароля для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="03d7d-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="03d7d-p101">Обратная запись пароля позволяет пользователям обновлять их пароли с помощью Azure Active Directory (Azure AD), которые затем реплицируются в локальных доменных службах Active Directory (AD DS). Благодаря функции обратной записи паролей пользователям не нужно обновлять свои пароли в локальных доменных службах Active Directory (AD DS), где хранятся исходные учетные записи пользователей. Это помогает удаленным пользователям и пользователям, находящимся в пути, у которых нет подключения для удаленного доступа к сети локальной среды.</span><span class="sxs-lookup"><span data-stu-id="03d7d-p101">Password writeback allows users to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS). With password writeback, users don’t need to update their passwords through the on-premises Windows Server AD where their original user accounts are stored. This helps roaming or remote users who do not have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="03d7d-107">В этой статье описывается, как настроить обратную запись паролей в тестовой среде Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="03d7d-107">This article describes how you can configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="03d7d-108">Эта настройка состоит из двух этапов.</span><span class="sxs-lookup"><span data-stu-id="03d7d-108">There are two phases to setting this up:</span></span>

1.  <span data-ttu-id="03d7d-109">Создание тестовой среды с синхронизацией хэшей паролей для имитации корпоративной среды Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="03d7d-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="03d7d-110">Включение обратной записи паролей для домена AD DS TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="03d7d-110">Enable password writeback for the TESTLAB Windows Server AD domain.</span></span>
    
![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="03d7d-112">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="03d7d-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-and-password-reset-for-your-microsoft-365-test-environment"></a><span data-ttu-id="03d7d-113">Этап 1. Настройка синхронизации хэша паролей и сброса паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="03d7d-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="03d7d-p102">Сначала выполните инструкции из статьи [Синхронизация хэша паролей](password-hash-sync-m365-ent-test-environment.md). Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="03d7d-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="03d7d-117">Конфигурация состоит из следующих компонентов: </span><span class="sxs-lookup"><span data-stu-id="03d7d-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="03d7d-118">Пробные или платные подписки на Office 365 E5 и EMS E5.</span><span class="sxs-lookup"><span data-stu-id="03d7d-118">Office 365 E5 and EMS E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="03d7d-119">Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure.</span><span class="sxs-lookup"><span data-stu-id="03d7d-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="03d7d-120">Azure AD Connect работает на APP1 для синхронизации домена AD DS TESTLAB с клиентом Azure AD, связанным с подписками на Office 365 и EMS E5.</span><span class="sxs-lookup"><span data-stu-id="03d7d-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

<span data-ttu-id="03d7d-121">Затем выполните инструкции [этапа 2 по сбросу пароля](password-reset-m365-ent-test-environment.md#phase-2-configure-and-test-password-reset) из руководства по лаборатории тестирования.</span><span class="sxs-lookup"><span data-stu-id="03d7d-121">Next, follow the instructions in [Phase 2 of the password reset](password-reset-m365-ent-test-environment.md#phase-2-configure-and-test-password-reset) Test Lab Guide.</span></span>

<span data-ttu-id="03d7d-122">Чтобы использовать обратную запись пароля, необходимо включить сброс пароля.</span><span class="sxs-lookup"><span data-stu-id="03d7d-122">You must have password reset enabled to use password writeback.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="03d7d-123">Этап 2. Включение обратной записи паролей для домена AD DS TESTLAB</span><span class="sxs-lookup"><span data-stu-id="03d7d-123">Phase 2: Enable password writeback for the TESTLAB Windows Server AD domain</span></span>

<span data-ttu-id="03d7d-124">Сначала настройте учетную запись User 1 с ролью глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="03d7d-124">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="03d7d-125">На [портале Office](https://office.com) выполните вход с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="03d7d-125">From the [Office portal](https://office.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="03d7d-p103">Щелкните плитку **Администрирование**. На новой вкладке браузера **Центр администрирования Microsoft 365** щелкните **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="03d7d-p103">Click the **Admin** tile. From the new **Microsoft 365 admin center** tab of your browser, click **Active users**.</span></span>
 
3. <span data-ttu-id="03d7d-128">На странице **Активные пользователи** щелкните учетную запись **User1**.</span><span class="sxs-lookup"><span data-stu-id="03d7d-128">On the **Active users** page, click the **user1** account,</span></span>

4. <span data-ttu-id="03d7d-129">В области **User1** нажмите кнопку **Изменить** рядом с элементом **Роли**.</span><span class="sxs-lookup"><span data-stu-id="03d7d-129">On the **user1** pane, click **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="03d7d-p104">В области **Изменить роли пользователя** для User1 выберите пункт **Глобальный администратор**. Нажмите кнопку **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="03d7d-p104">On the **Edit user roles** pane for user1, click **Global administrator**. Click **Save**, and then click **Close**.</span></span>

<span data-ttu-id="03d7d-132">Затем настройте для учетной записи User 1 параметры безопасности, позволяющие изменять пароли от имени других пользователей в домене AD DS TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="03d7d-132">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB Windows Server AD domain.</span></span>

1. <span data-ttu-id="03d7d-133">На [портале Azure](https://portal.azure.com) выполните вход с помощью учетной записи глобального администратора и затем подключитесь к виртуальной машине APP1 с учетной записью TESTLAB\User1.</span><span class="sxs-lookup"><span data-stu-id="03d7d-133">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="03d7d-134">На рабочем столе виртуальной машины APP1 нажмите кнопку **Пуск**, введите **active**, а затем выберите **Пользователи и компьютеры Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="03d7d-134">From the desktop of APP1, click **Start**, type **active**, and then click **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="03d7d-p105">В строке меню выберите пункт **Вид**. Если **Расширенные функции** не включены, щелкните по ним, чтобы их включить.</span><span class="sxs-lookup"><span data-stu-id="03d7d-p105">Click **View** in the menu bar. If **Advanced features** is not enabled, click it to enable it.</span></span>

4. <span data-ttu-id="03d7d-137">В области дерева щелкните правой кнопкой мыши ваш домен, выберите пункт **Свойства** и щелкните вкладку **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="03d7d-137">In the tree pane, right-click your domain, click **Properties**, and then click the **Security** tab.</span></span>

5. <span data-ttu-id="03d7d-138">Нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="03d7d-138">Click **Advanced**.</span></span>

6. <span data-ttu-id="03d7d-139">На вкладке **Разрешения** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="03d7d-139">On the **Permissions** tab, click **Add**.</span></span>

7. <span data-ttu-id="03d7d-140">Щелкните **Выбрать субъект**, введите **User1** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="03d7d-140">Click **Select a principal**, type **User1**, and then click **OK**.</span></span>

8. <span data-ttu-id="03d7d-141">В поле **Применяется к** выберите **Потомки объектов пользователя**.</span><span class="sxs-lookup"><span data-stu-id="03d7d-141">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="03d7d-142">В разделе **Разрешения** выберите следующее:</span><span class="sxs-lookup"><span data-stu-id="03d7d-142">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="03d7d-143">Смена пароля</span><span class="sxs-lookup"><span data-stu-id="03d7d-143">Change password</span></span>
    - <span data-ttu-id="03d7d-144">Сброс пароля</span><span class="sxs-lookup"><span data-stu-id="03d7d-144">Reset password</span></span>

10. <span data-ttu-id="03d7d-145">В разделе **Свойства** выберите следующее:</span><span class="sxs-lookup"><span data-stu-id="03d7d-145">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="03d7d-146">Запись lockoutTime</span><span class="sxs-lookup"><span data-stu-id="03d7d-146">Write lockoutTime</span></span>
    - <span data-ttu-id="03d7d-147">Запись pwdLastSet</span><span class="sxs-lookup"><span data-stu-id="03d7d-147">Write pwdLastSet</span></span>

11. <span data-ttu-id="03d7d-148">Нажмите кнопку **ОК** три раза, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="03d7d-148">Click **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="03d7d-149">Закройте оснастку **Пользователи и компьютеры Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="03d7d-149">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="03d7d-150">Затем настройте Azure AD Connect на виртуальной машине APP1 для обратной записи пароля.</span><span class="sxs-lookup"><span data-stu-id="03d7d-150">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="03d7d-151">При необходимости подключитесь к виртуальной машине APP1 с помощью учетной записи TESTLAB\User1</span><span class="sxs-lookup"><span data-stu-id="03d7d-151">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="03d7d-152">На рабочем столе виртуальной машины APP1 дважды щелкните значок **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="03d7d-152">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="03d7d-153">На **странице приветствия** нажмите кнопку **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="03d7d-153">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="03d7d-154">На странице **Дополнительные задачи** щелкните команду **Настроить параметры синхронизации** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="03d7d-154">On the **Additional tasks** page, click **Customize synchronization options**, and then click **Next**.</span></span>

5. <span data-ttu-id="03d7d-155">На странице **Подключение к Azure AD** введите учетные данные глобального администратора и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="03d7d-155">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="03d7d-156">На страницах **Подключение каталогов** и **Фильтрация домена/OU** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="03d7d-156">On the **Connect directories** and **Domain/OU filtering** pages, click **Next**.</span></span>

7. <span data-ttu-id="03d7d-157">На странице **Дополнительные возможности** выберите пункт **Обратная запись пароля** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="03d7d-157">On the **Optional features** page, select **Password writeback** and click **Next**.</span></span> 

8. <span data-ttu-id="03d7d-158">На странице **Готово к настройке** нажмите кнопку **Настроить** и дождитесь завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="03d7d-158">On the **Ready to configure** page, click **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="03d7d-159">После завершения настройки нажмите кнопку **Выход**.</span><span class="sxs-lookup"><span data-stu-id="03d7d-159">When you see the configuration finish, click **Exit**.</span></span>

<span data-ttu-id="03d7d-160">Теперь вы готовы к проверке обратной записи пароля для пользователей на компьютерах, которые не подключены к виртуальной сети имитированной интрасети.</span><span class="sxs-lookup"><span data-stu-id="03d7d-160">You are now ready to test password writeback for users on computers that are not connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="03d7d-161">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="03d7d-161">Here is your resulting configuration:</span></span>

![Смоделированная организации с тестовой средой сквозной проверки подлинности](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="03d7d-163">Конфигурация состоит из следующих компонентов: </span><span class="sxs-lookup"><span data-stu-id="03d7d-163">This configuration consists of:</span></span>

- <span data-ttu-id="03d7d-164">Пробные или платные подписки на Office 365 E5 и EMS E5 с зарегистрированным доменом DNS TESTLAB.\<доменное имя>.</span><span class="sxs-lookup"><span data-stu-id="03d7d-164">Office 365 E5 and EMS E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="03d7d-165">Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure.</span><span class="sxs-lookup"><span data-stu-id="03d7d-165">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="03d7d-166">Azure AD Connect работает на APP1 для синхронизации списка учетных записей и групп из клиента Azure AD, связанного с подпиской на Office 365 и EMS E5, с доменом AD DS TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="03d7d-166">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Office 365 and EMS E5 subscriptions to the TESTLAB Windows Server AD domain.</span></span> 
- <span data-ttu-id="03d7d-167">Обратная запись паролей включена, поэтому пользователи могут сменить свои пароли через Azure AD без необходимости подключения к упрощенной интрасети.</span><span class="sxs-lookup"><span data-stu-id="03d7d-167">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

<span data-ttu-id="03d7d-168">Информацию и ссылки для настройки обратной записи паролей в рабочей среде вы найдете в описании шага [Упрощение процедуры обновления паролей](identity-password-reset.md#identity-pw-writeback) этапа "Идентификация".</span><span class="sxs-lookup"><span data-stu-id="03d7d-168">See the [Simplify password updates](identity-password-reset.md#identity-pw-writeback) step in the Identity phase for information and links to configure password writeback in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="03d7d-169">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="03d7d-169">Next step</span></span>

<span data-ttu-id="03d7d-170">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="03d7d-170">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="03d7d-171">См. также</span><span class="sxs-lookup"><span data-stu-id="03d7d-171">See also</span></span>

[<span data-ttu-id="03d7d-172">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="03d7d-172">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="03d7d-173">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="03d7d-173">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="03d7d-174">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="03d7d-174">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


