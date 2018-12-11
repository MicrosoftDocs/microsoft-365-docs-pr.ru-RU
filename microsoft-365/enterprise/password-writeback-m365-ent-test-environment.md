---
title: Обратная запись пароля для тестовой среды Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: Сводка. Настройка обратной записи пароля для тестовой среды Microsoft 365
ms.openlocfilehash: 748ccaf8601d9e9564d176f2368e3cc71f926208
ms.sourcegitcommit: fec2c756121006069dc3e5b8dbd6c4abe7a3c63c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "27214437"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="88969-103">Обратная запись пароля для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="88969-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="88969-p101">Обратная запись пароля позволяет пользователям обновлять их пароли с помощью Azure Active Directory (AD), которые затем будут реплицированы в ваш локальный Windows Server Active Directory (AD). Благодаря функции обратной записи паролей пользователям не нужно обновлять свои пароли на локальном Windows Server AD, где хранятся исходные учетные записи пользователей. Это помогает удаленным пользователям и пользователям, находящимся в пути, у которых нет подключения для удаленного доступа к сети локальной среды.</span><span class="sxs-lookup"><span data-stu-id="88969-p101">Password writeback allows users to update their passwords through Azure Active Directory (AD), which is then replicated to your local Windows Server Active Directory (AD). With password writeback, users don’t need to update their passwords through the on-premises Windows Server AD where their original user accounts are stored. This helps roaming or remote users who do not have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="88969-107">В этой статье описывается, как настроить обратную запись паролей в тестовой среде Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="88969-107">This article describes how you can configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="88969-108">Эта настройка состоит из двух этапов.</span><span class="sxs-lookup"><span data-stu-id="88969-108">There are two phases to setting this up:</span></span>

1.  <span data-ttu-id="88969-109">Создание тестовой среды с синхронизацией хэшей паролей для имитации корпоративной среды Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="88969-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="88969-110">Включение обратной записи паролей для домена Windows Server AD TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="88969-110">Enable password writeback for the TESTLAB Windows Server AD domain.</span></span>
    
![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="88969-112">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="88969-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="88969-113">Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="88969-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="88969-p102">Следуйте инструкциям в статье [Синхронизация хэша паролей для Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="88969-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="88969-117">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="88969-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="88969-118">Пробные или постоянные подписки на Office 365 E5 и EMS E5.</span><span class="sxs-lookup"><span data-stu-id="88969-118">Office 365 E5 and EMS E5 trial or permanent subscriptions.</span></span>
- <span data-ttu-id="88969-119">Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure.</span><span class="sxs-lookup"><span data-stu-id="88969-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="88969-120">Azure AD Connect работает на APP1 для синхронизации домена Windows Server AD TESTLAB с клиентом Azure AD, связанным с подписками на Office 365 и EMS E5.</span><span class="sxs-lookup"><span data-stu-id="88969-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-windows-server-ad-domain"></a><span data-ttu-id="88969-121">Этап 2. Включение обратной записи паролей для домена Windows Server AD TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="88969-121">Phase 2: Enable password writeback for the TESTLAB Windows Server AD domain</span></span>

<span data-ttu-id="88969-122">Сначала настройте учетную запись User 1 с ролью глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="88969-122">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="88969-123">На [портале Office](https://office.com) выполните вход с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="88969-123">From the [Office portal](https://office.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="88969-p103">Щелкните плитку **Администрирование**. На новой вкладке браузера **Центр администрирования Microsoft 365** щелкните **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="88969-p103">Click the **Admin** tile. From the new **Microsoft 365 admin center** tab of your browser, click **Active users**.</span></span>
 
3. <span data-ttu-id="88969-126">На странице **Активные пользователи** щелкните учетную запись **User1**.</span><span class="sxs-lookup"><span data-stu-id="88969-126">On the **Active users** page, click the **user1** account,</span></span>

4. <span data-ttu-id="88969-127">В области **User1** нажмите кнопку **Изменить** рядом с элементом **Роли**.</span><span class="sxs-lookup"><span data-stu-id="88969-127">On the **user1** pane, click **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="88969-p104">В области **Изменить роли пользователя** для User1 выберите пункт **Глобальный администратор**. Нажмите кнопку **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="88969-p104">On the **Edit user roles** pane for user1, click **Global administrator**. Click **Save**, and then click **Close**.</span></span>

<span data-ttu-id="88969-130">Затем настройте для учетной записи User 1 параметры безопасности, позволяющие изменять пароли от имени других пользователей в домене Windows Server AD TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="88969-130">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB Windows Server AD domain.</span></span>

1. <span data-ttu-id="88969-131">На [портале Azure](https://portal.azure.com) выполните вход с помощью учетной записи глобального администратора и затем подключитесь к виртуальной машине APP1 с учетной записью TESTLAB\User1.</span><span class="sxs-lookup"><span data-stu-id="88969-131">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="88969-132">На рабочем столе виртуальной машины APP1 нажмите кнопку **Пуск**, введите **active**, а затем выберите **Пользователи и компьютеры Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="88969-132">From the desktop of APP1, click **Start**, type **active**, and then click **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="88969-p105">В строке меню выберите пункт **Вид**. Если **Расширенные функции** не включены, щелкните по ним, чтобы их включить.</span><span class="sxs-lookup"><span data-stu-id="88969-p105">Click **View** in the menu bar. If **Advanced features** is not enabled, click it to enable it.</span></span>

4. <span data-ttu-id="88969-135">В области дерева щелкните правой кнопкой мыши ваш домен, выберите пункт **Свойства** и щелкните вкладку **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="88969-135">In the tree pane, right-click your domain, click **Properties**, and then click the **Security** tab.</span></span>

5. <span data-ttu-id="88969-136">Нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="88969-136">Click **Advanced**.</span></span>

6. <span data-ttu-id="88969-137">На вкладке **Разрешения** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="88969-137">On the **Permissions** tab, click **Add**.</span></span>

7. <span data-ttu-id="88969-138">Щелкните **Выбрать субъект**, введите **User1** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="88969-138">Click **Select a principal**, type **User1**, and then click **OK**.</span></span>

8. <span data-ttu-id="88969-139">В поле **Применяется к** выберите **Потомки объектов пользователя**.</span><span class="sxs-lookup"><span data-stu-id="88969-139">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="88969-140">В разделе **Разрешения** выберите следующее:</span><span class="sxs-lookup"><span data-stu-id="88969-140">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="88969-141">Смена пароля</span><span class="sxs-lookup"><span data-stu-id="88969-141">Change password</span></span>
    - <span data-ttu-id="88969-142">Сброс пароля</span><span class="sxs-lookup"><span data-stu-id="88969-142">Reset password</span></span>

10. <span data-ttu-id="88969-143">В разделе **Свойства** выберите следующее:</span><span class="sxs-lookup"><span data-stu-id="88969-143">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="88969-144">Запись lockoutTime</span><span class="sxs-lookup"><span data-stu-id="88969-144">Write lockoutTime</span></span>
    - <span data-ttu-id="88969-145">Запись pwdLastSet</span><span class="sxs-lookup"><span data-stu-id="88969-145">Write pwdLastSet</span></span>

11. <span data-ttu-id="88969-146">Нажмите кнопку **ОК** три раза, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="88969-146">Click **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="88969-147">Закройте оснастку **Пользователи и компьютеры Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="88969-147">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="88969-148">Затем настройте Azure AD Connect на виртуальной машине APP1 для обратной записи пароля.</span><span class="sxs-lookup"><span data-stu-id="88969-148">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="88969-149">При необходимости подключитесь к виртуальной машине APP1 с помощью учетной записи TESTLAB\User1</span><span class="sxs-lookup"><span data-stu-id="88969-149">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="88969-150">На рабочем столе виртуальной машины APP1 дважды щелкните значок **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="88969-150">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="88969-151">На **странице приветствия** нажмите кнопку **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="88969-151">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="88969-152">На странице **Дополнительные задачи** щелкните команду **Настроить параметры синхронизации** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="88969-152">On the **Additional tasks** page, click **Customize synchronization options**, and then click **Next**.</span></span>

5. <span data-ttu-id="88969-153">На странице **Подключение к Azure AD** введите учетные данные пользователя User 1 и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="88969-153">On the **Connect to Azure AD** page, type the User 1 account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="88969-154">На страницах **Подключение каталогов** и **Фильтрация домена/OU** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="88969-154">On the **Connect directories** and **Domain/OU filtering** pages, click **Next**.</span></span>

7. <span data-ttu-id="88969-155">На странице **Дополнительные возможности** выберите пункт **Обратная запись пароля** и нажмите кнопку "Далее".</span><span class="sxs-lookup"><span data-stu-id="88969-155">On the **Optional features** page, select **Password writeback** and click Next.</span></span> 

8. <span data-ttu-id="88969-156">На странице **Готово к настройке** нажмите кнопку **Настроить** и дождитесь завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="88969-156">On the **Ready to configure** page, click **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="88969-157">После завершения настройки нажмите кнопку **Выход**.</span><span class="sxs-lookup"><span data-stu-id="88969-157">When you see the configuration finish, click **Exit**.</span></span>

<span data-ttu-id="88969-158">Теперь вы готовы к проверке обратной записи пароля для пользователей на компьютерах, которые не подключены к виртуальной сети имитированной интрасети.</span><span class="sxs-lookup"><span data-stu-id="88969-158">You are now ready to test password writeback for users on computers that are not connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="88969-159">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="88969-159">Here is your resulting configuration:</span></span>

![Смоделированная организации с тестовой средой сквозной проверки подлинности](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="88969-161">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="88969-161">This configuration consists of:</span></span>

- <span data-ttu-id="88969-162">Пробные или постоянные подписки на Office 365 E5 и EMS E5 с зарегистрированным доменом DNS TESTLAB.\<доменное имя>.</span><span class="sxs-lookup"><span data-stu-id="88969-162">Office 365 E5 and EMS E5 trial or permanent subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="88969-163">Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure.</span><span class="sxs-lookup"><span data-stu-id="88969-163">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="88969-164">Azure AD Connect работает на APP1 для синхронизации списка учетных записей и групп из клиента Azure AD, связанного с подпиской на Office 365 и EMS E5, с доменом Windows Server AD TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="88969-164">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Office 365 and EMS E5 subscriptions to the TESTLAB Windows Server AD domain.</span></span> 
- <span data-ttu-id="88969-165">Обратная запись паролей включена, поэтому пользователи могут сменить свои пароли через Azure AD без необходимости подключения к упрощенной интрасети.</span><span class="sxs-lookup"><span data-stu-id="88969-165">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

<span data-ttu-id="88969-166">Информацию и ссылки для настройки обратной записи паролей в рабочей среде вы найдете в описании шага [Упрощение процедуры обновления паролей](identity-password-writeback.md) этапа "Идентификация".</span><span class="sxs-lookup"><span data-stu-id="88969-166">See the [Simplify password updates](identity-password-writeback.md) step in the Identity phase for information and links to configure password writeback in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="88969-167">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="88969-167">Next step</span></span>

<span data-ttu-id="88969-168">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="88969-168">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="88969-169">См. также</span><span class="sxs-lookup"><span data-stu-id="88969-169">See also</span></span>

[<span data-ttu-id="88969-170">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="88969-170">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="88969-171">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="88969-171">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="88969-172">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="88969-172">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


