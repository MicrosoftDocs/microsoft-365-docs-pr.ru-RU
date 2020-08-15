---
title: Обратная запись пароля для тестовой среды Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
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
description: Сводка. Настройка обратной записи пароля для тестовой среды Microsoft 365
ms.openlocfilehash: b8c89ca7ef967c423b89db4559ef04f715a5f869
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686230"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="229e4-103">Обратная запись пароля для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="229e4-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="229e4-104">*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для тестовых сред предприятия.*</span><span class="sxs-lookup"><span data-stu-id="229e4-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="229e4-p101">Обратная запись пароля позволяет пользователям обновлять свои пароли с помощью Azure Active Directory (Azure AD), которые затем реплицируются в локальных доменных службах Active Directory (AD DS). Благодаря функции обратной записи паролей пользователям не нужно обновлять свои пароли в локальных службах AD DS, где хранятся исходные учетные записи пользователей. Это помогает удаленным пользователям и пользователям, находящимся в пути, у которых нет подключения для удаленного доступа к сети локальной среды.</span><span class="sxs-lookup"><span data-stu-id="229e4-p101">Password writeback allows users to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS). With password writeback, users don't need to update their passwords through the on-premises AD DS where their original user accounts are stored. This helps roaming or remote users who do not have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="229e4-108">В этой статье описывается, как настроить обратную запись паролей в тестовой среде Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="229e4-108">This article describes how you can configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="229e4-109">Эта настройка состоит из двух этапов.</span><span class="sxs-lookup"><span data-stu-id="229e4-109">There are two phases to setting this up:</span></span>

1.    <span data-ttu-id="229e4-110">Создание тестовой среды с синхронизацией хэшей паролей для имитации корпоративной среды Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="229e4-110">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.    <span data-ttu-id="229e4-111">Включение обратной записи паролей для домена AD DS TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="229e4-111">Enable password writeback for the TESTLAB AD DS domain.</span></span>
    
![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="229e4-113">Щелкните [здесь](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 для крупных предприятий.</span><span class="sxs-lookup"><span data-stu-id="229e4-113">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="229e4-114">Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="229e4-114">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="229e4-p102">Сначала выполните инструкции из статьи [Синхронизация хэша паролей](password-hash-sync-m365-ent-test-environment.md). Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="229e4-p102">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="229e4-118">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="229e4-118">This configuration consists of:</span></span> 
  
- <span data-ttu-id="229e4-119">Пробная или платная подписка Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="229e4-119">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="229e4-120">Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure.</span><span class="sxs-lookup"><span data-stu-id="229e4-120">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="229e4-121">Azure AD Connect работает на APP1 для синхронизации домена AD DS TESTLAB с клиентом Azure AD, связанным с подпиской Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="229e4-121">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="229e4-122">Этап 2. Включение обратной записи паролей для домена AD DS TESTLAB</span><span class="sxs-lookup"><span data-stu-id="229e4-122">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="229e4-123">Сначала настройте учетную запись User 1 с ролью глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="229e4-123">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="229e4-124">В [Центре администрирования Microsoft 365](https://portal.microsoft.com) выполните вход с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="229e4-124">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="229e4-125">Щелкните пункт **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="229e4-125">Click **Active users**.</span></span>
 
3. <span data-ttu-id="229e4-126">На странице **Активные пользователи** щелкните учетную запись **User1**.</span><span class="sxs-lookup"><span data-stu-id="229e4-126">On the **Active users** page, click the **user1** account,</span></span>

4. <span data-ttu-id="229e4-127">В области **User1** нажмите кнопку **Изменить** рядом с элементом **Роли**.</span><span class="sxs-lookup"><span data-stu-id="229e4-127">On the **user1** pane, click **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="229e4-p103">В области **Изменить роли пользователя** для User1 выберите пункт **Глобальный администратор**. Нажмите кнопку **Сохранить**, а затем — **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="229e4-p103">On the **Edit user roles** pane for user1, click **Global administrator**. Click **Save**, and then click **Close**.</span></span>

<span data-ttu-id="229e4-130">Затем настройте для учетной записи User 1 параметры безопасности, позволяющие изменять пароли от имени других пользователей в домене AD DS TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="229e4-130">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="229e4-131">На [портале Azure](https://portal.azure.com) выполните вход с помощью учетной записи глобального администратора и затем подключитесь к виртуальной машине APP1 с учетной записью TESTLAB\User1.</span><span class="sxs-lookup"><span data-stu-id="229e4-131">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="229e4-132">На рабочем столе виртуальной машины APP1 нажмите кнопку **Пуск**, введите **active**, а затем выберите **Пользователи и компьютеры Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="229e4-132">From the desktop of APP1, click **Start**, type **active**, and then click **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="229e4-p104">В строке меню выберите пункт **Вид**. Если **Расширенные функции** не включены, щелкните по ним, чтобы их включить.</span><span class="sxs-lookup"><span data-stu-id="229e4-p104">Click **View** in the menu bar. If **Advanced features** is not enabled, click it to enable it.</span></span>

4. <span data-ttu-id="229e4-135">В области дерева щелкните правой кнопкой мыши ваш домен, выберите пункт **Свойства** и щелкните вкладку **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="229e4-135">In the tree pane, right-click your domain, click **Properties**, and then click the **Security** tab.</span></span>

5. <span data-ttu-id="229e4-136">Нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="229e4-136">Click **Advanced**.</span></span>

6. <span data-ttu-id="229e4-137">На вкладке **Разрешения** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="229e4-137">On the **Permissions** tab, click **Add**.</span></span>

7. <span data-ttu-id="229e4-138">Щелкните **Выбрать субъект**, введите **User1** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="229e4-138">Click **Select a principal**, type **User1**, and then click **OK**.</span></span>

8. <span data-ttu-id="229e4-139">В поле **Применяется к** выберите **Потомки объектов пользователя**.</span><span class="sxs-lookup"><span data-stu-id="229e4-139">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="229e4-140">В разделе **Разрешения** выберите следующее:</span><span class="sxs-lookup"><span data-stu-id="229e4-140">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="229e4-141">Смена пароля</span><span class="sxs-lookup"><span data-stu-id="229e4-141">Change password</span></span>
    - <span data-ttu-id="229e4-142">Сброс пароля</span><span class="sxs-lookup"><span data-stu-id="229e4-142">Reset password</span></span>

10. <span data-ttu-id="229e4-143">В разделе **Свойства** выберите следующее:</span><span class="sxs-lookup"><span data-stu-id="229e4-143">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="229e4-144">Запись lockoutTime</span><span class="sxs-lookup"><span data-stu-id="229e4-144">Write lockoutTime</span></span>
    - <span data-ttu-id="229e4-145">Запись pwdLastSet</span><span class="sxs-lookup"><span data-stu-id="229e4-145">Write pwdLastSet</span></span>

11. <span data-ttu-id="229e4-146">Нажмите кнопку **ОК** три раза, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="229e4-146">Click **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="229e4-147">Закройте оснастку **Пользователи и компьютеры Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="229e4-147">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="229e4-148">Затем настройте Azure AD Connect на виртуальной машине APP1 для обратной записи пароля.</span><span class="sxs-lookup"><span data-stu-id="229e4-148">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="229e4-149">При необходимости подключитесь к виртуальной машине APP1 с помощью учетной записи TESTLAB\User1</span><span class="sxs-lookup"><span data-stu-id="229e4-149">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="229e4-150">На рабочем столе виртуальной машины APP1 дважды щелкните значок **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="229e4-150">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="229e4-151">На **странице приветствия** нажмите кнопку **Настроить**.</span><span class="sxs-lookup"><span data-stu-id="229e4-151">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="229e4-152">На странице **Дополнительные задачи** щелкните команду **Настроить параметры синхронизации** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="229e4-152">On the **Additional tasks** page, click **Customize synchronization options**, and then click **Next**.</span></span>

5. <span data-ttu-id="229e4-153">На странице **Подключение к Azure AD** введите учетные данные глобального администратора и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="229e4-153">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="229e4-154">На страницах **Подключение каталогов** и **Фильтрация домена/OU** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="229e4-154">On the **Connect directories** and **Domain/OU filtering** pages, click **Next**.</span></span>

7. <span data-ttu-id="229e4-155">На странице **Дополнительные возможности** выберите пункт **Обратная запись пароля** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="229e4-155">On the **Optional features** page, select **Password writeback** and click **Next**.</span></span> 

8. <span data-ttu-id="229e4-156">На странице **Готово к настройке** нажмите кнопку **Настроить** и дождитесь завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="229e4-156">On the **Ready to configure** page, click **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="229e4-157">После завершения настройки нажмите кнопку **Выход**.</span><span class="sxs-lookup"><span data-stu-id="229e4-157">When you see the configuration finish, click **Exit**.</span></span>

<span data-ttu-id="229e4-158">Теперь вы готовы к проверке обратной записи пароля для пользователей на компьютерах, которые не подключены к виртуальной сети имитированной интрасети.</span><span class="sxs-lookup"><span data-stu-id="229e4-158">You are now ready to test password writeback for users on computers that are not connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="229e4-159">Ниже показана итоговая конфигурация.</span><span class="sxs-lookup"><span data-stu-id="229e4-159">Here is your resulting configuration:</span></span>

![Смоделированная организации с тестовой средой сквозной проверки подлинности](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="229e4-161">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="229e4-161">This configuration consists of:</span></span>

- <span data-ttu-id="229e4-162">Пробную или платную подписку Microsoft 365 в формате TESTLAB с DNS-доменом.\<your domain name></span><span class="sxs-lookup"><span data-stu-id="229e4-162">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name></span></span> <span data-ttu-id="229e4-163">-</span><span class="sxs-lookup"><span data-stu-id="229e4-163">registered.</span></span>
- <span data-ttu-id="229e4-164">Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure.</span><span class="sxs-lookup"><span data-stu-id="229e4-164">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="229e4-165">Azure AD Connect работает на APP1 для синхронизации списка учетных записей и групп из клиента Azure AD, связанного с подпиской Microsoft 365, с доменом AD DS TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="229e4-165">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="229e4-166">Обратная запись паролей включена, поэтому пользователи могут сменить свои пароли через Azure AD без необходимости подключения к упрощенной интрасети.</span><span class="sxs-lookup"><span data-stu-id="229e4-166">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

## <a name="next-step"></a><span data-ttu-id="229e4-167">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="229e4-167">Next step</span></span>

<span data-ttu-id="229e4-168">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="229e4-168">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="229e4-169">См. также</span><span class="sxs-lookup"><span data-stu-id="229e4-169">See also</span></span>

[<span data-ttu-id="229e4-170">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="229e4-170">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="229e4-171">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="229e4-171">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="229e4-172">Microsoft 365 для корпоративных документов</span><span class="sxs-lookup"><span data-stu-id="229e4-172">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


