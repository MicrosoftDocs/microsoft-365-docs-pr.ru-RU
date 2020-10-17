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
ms.openlocfilehash: b999d50b0e98b11638199327bd7ffe7269b261ce
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487132"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="6052b-103">Обратная запись пароля для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6052b-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="6052b-104">*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для тестовых сред предприятия.*</span><span class="sxs-lookup"><span data-stu-id="6052b-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="6052b-p101">Пользователи могут использовать обратную запись пароля для обновления своих паролей с помощью Azure Active Directory (Azure AD), которая затем реплицируется в локальные доменные службы Active Directory (AD DS). При обратной записи паролей пользователям не нужно обновлять свои пароли с помощью локальных доменных служб Active Directory, в которых хранятся исходные учетные записи пользователей. Это помогает перемещать или удаленным пользователям, у которых нет подключения удаленного доступа к своей локальной сети.</span><span class="sxs-lookup"><span data-stu-id="6052b-p101">Users can use password writeback to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS). With password writeback, users don't have to update their passwords through the on-premises AD DS where their original user accounts are stored. This helps roaming or remote users who don't have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="6052b-108">В этой статье описывается настройка тестовой среды Microsoft 365 для обратной записи пароля.</span><span class="sxs-lookup"><span data-stu-id="6052b-108">This article describes how to configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="6052b-109">Настройка тестовой среды для обратной записи паролей состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="6052b-109">Configuring your test environment for password writeback involves two phases:</span></span>
- [<span data-ttu-id="6052b-110">Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6052b-110">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="6052b-111">Этап 2. Включение обратной записи паролей для домена AD DS TESTLAB</span><span class="sxs-lookup"><span data-stu-id="6052b-111">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="6052b-113">Для отображения всех статей, посвященных руководству по лаборатории тестирования Microsoft 365 для предприятий, перейдите к разделу [руководство по лаборатории тестирования microsoft 365 для предприятия](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="6052b-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="6052b-114">Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6052b-114">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="6052b-p102">Сначала следуйте инструкциям в статье [Синхронизация хэша пароля](password-hash-sync-m365-ent-test-environment.md). Результирующая конфигурация выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6052b-p102">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Your resulting configuration looks like this:</span></span>
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="6052b-118">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="6052b-118">This configuration consists of:</span></span>
  
- <span data-ttu-id="6052b-119">Пробная или платная подписка Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="6052b-119">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="6052b-120">Упрощенная интрасеть Организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="6052b-120">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="6052b-121">Azure AD Connect работает на APP1 для синхронизации домена AD DS TESTLAB с клиентом Azure AD, связанным с подпиской Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6052b-121">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="6052b-122">Этап 2. Включение обратной записи паролей для домена AD DS TESTLAB</span><span class="sxs-lookup"><span data-stu-id="6052b-122">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="6052b-123">Сначала настройте учетную запись User 1 с ролью глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="6052b-123">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="6052b-124">В [Центре администрирования Microsoft 365](https://portal.microsoft.com) выполните вход с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="6052b-124">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="6052b-125">Выберите пункт **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="6052b-125">Select **Active users**.</span></span>
 
3. <span data-ttu-id="6052b-126">На странице **Активные пользователи** выберите учетную запись **User1** ,</span><span class="sxs-lookup"><span data-stu-id="6052b-126">On the **Active users** page, select the **user1** account,</span></span>

4. <span data-ttu-id="6052b-127">В области **Пользователь1** нажмите кнопку **изменить** рядом с элементом **роли**.</span><span class="sxs-lookup"><span data-stu-id="6052b-127">On the **user1** pane, select **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="6052b-128">В области **изменение ролей пользователей для пользователя** User1 выберите **глобальный администратор**, нажмите кнопку **сохранить**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="6052b-128">On the **Edit user roles** pane for user1, select **Global administrator**, select **Save**, and then select **Close**.</span></span>

<span data-ttu-id="6052b-129">Затем настройте для учетной записи User 1 параметры безопасности, позволяющие изменять пароли от имени других пользователей в домене AD DS TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="6052b-129">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="6052b-130">На [портале Azure](https://portal.azure.com) выполните вход с помощью учетной записи глобального администратора и затем подключитесь к виртуальной машине APP1 с учетной записью TESTLAB\User1.</span><span class="sxs-lookup"><span data-stu-id="6052b-130">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="6052b-131">На рабочем столе приложения APP1 нажмите кнопку **Пуск**, введите **Активная**, а затем выберите пункт **Active Directory — пользователи и компьютеры**.</span><span class="sxs-lookup"><span data-stu-id="6052b-131">From the desktop of APP1, select **Start**, enter **active**, and then select **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="6052b-132">В строке меню выберите пункт **Просмотр**.</span><span class="sxs-lookup"><span data-stu-id="6052b-132">On the menu bar, select **View**.</span></span> <span data-ttu-id="6052b-133">Если **Дополнительные функции** отключены, выберите ее, чтобы включить.</span><span class="sxs-lookup"><span data-stu-id="6052b-133">If **Advanced features** is not enabled, select it to enable it.</span></span>

4. <span data-ttu-id="6052b-134">В области дерева выберите и удерживайте (или щелкните правой кнопкой мыши) ваш домен, выберите пункт **Свойства**, а затем перейдите на вкладку **Безопасность** .</span><span class="sxs-lookup"><span data-stu-id="6052b-134">In the tree pane, select and hold (or right-click) your domain, select **Properties**, and then select the **Security** tab.</span></span>

5. <span data-ttu-id="6052b-135">Выберите **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="6052b-135">Select **Advanced**.</span></span>

6. <span data-ttu-id="6052b-136">На вкладке **разрешения** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="6052b-136">On the **Permissions** tab, select **Add**.</span></span>

7. <span data-ttu-id="6052b-137">Выберите **пункт выбрать участника**, введите **Пользователь1**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6052b-137">Select **Select a principal**, enter **User1**, and then select **OK**.</span></span>

8. <span data-ttu-id="6052b-138">В поле **Применяется к** выберите **Потомки объектов пользователя**.</span><span class="sxs-lookup"><span data-stu-id="6052b-138">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="6052b-139">В разделе **Разрешения** выберите следующее:</span><span class="sxs-lookup"><span data-stu-id="6052b-139">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="6052b-140">**Смена пароля**</span><span class="sxs-lookup"><span data-stu-id="6052b-140">**Change password**</span></span>
    - <span data-ttu-id="6052b-141">**Сброс пароля**</span><span class="sxs-lookup"><span data-stu-id="6052b-141">**Reset password**</span></span>

10. <span data-ttu-id="6052b-142">В разделе **Свойства** выберите следующее:</span><span class="sxs-lookup"><span data-stu-id="6052b-142">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="6052b-143">**Запись lockoutTime**</span><span class="sxs-lookup"><span data-stu-id="6052b-143">**Write lockoutTime**</span></span>
    - <span data-ttu-id="6052b-144">**Запись pwdLastSet**</span><span class="sxs-lookup"><span data-stu-id="6052b-144">**Write pwdLastSet**</span></span>

11. <span data-ttu-id="6052b-145">Нажмите кнопку **ОК** три раза, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="6052b-145">Select **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="6052b-146">Закройте оснастку **Пользователи и компьютеры Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="6052b-146">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="6052b-147">Затем настройте Azure AD Connect на виртуальной машине APP1 для обратной записи пароля.</span><span class="sxs-lookup"><span data-stu-id="6052b-147">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="6052b-148">При необходимости подключитесь к виртуальной машине APP1 с помощью учетной записи TESTLAB\User1</span><span class="sxs-lookup"><span data-stu-id="6052b-148">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="6052b-149">На рабочем столе виртуальной машины APP1 дважды щелкните значок **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="6052b-149">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="6052b-150">На **странице приветствия**нажмите кнопку **настроить**.</span><span class="sxs-lookup"><span data-stu-id="6052b-150">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="6052b-151">На странице **Дополнительные задачи** выберите пункт **Настройка параметров синхронизации**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6052b-151">On the **Additional tasks** page, select **Customize synchronization options**, and then select **Next**.</span></span>

5. <span data-ttu-id="6052b-152">На странице **Подключение к Azure AD** введите учетные данные глобального администратора, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6052b-152">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="6052b-153">На страницах **подключения каталогов** и **фильтрации доменов/подразделений** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6052b-153">On the **Connect directories** and **Domain/OU filtering** pages, select **Next**.</span></span>

7. <span data-ttu-id="6052b-154">На странице **Дополнительные функции** выберите **обратная запись пароля**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="6052b-154">On the **Optional features** page, select **Password writeback**, and then select **Next**.</span></span>

8. <span data-ttu-id="6052b-155">На странице **Готово к настройке** нажмите кнопку **настроить** и дождитесь завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="6052b-155">On the **Ready to configure** page, select **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="6052b-156">Когда появится окно завершения настройки, нажмите кнопку **выход**.</span><span class="sxs-lookup"><span data-stu-id="6052b-156">When you see the configuration finish, select **Exit**.</span></span>

<span data-ttu-id="6052b-157">Теперь вы можете протестировать обратную запись пароля для пользователей на компьютерах, которые не подключены к виртуальной сети имитируемой интрасети.</span><span class="sxs-lookup"><span data-stu-id="6052b-157">You are now ready to test password writeback for users on computers that aren't connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="6052b-158">Результирующая конфигурация выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6052b-158">Your resulting configuration looks like this:</span></span>

![Смоделированная организации с тестовой средой сквозной проверки подлинности](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="6052b-160">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="6052b-160">This configuration consists of:</span></span>

- <span data-ttu-id="6052b-161">Пробную или платную подписку Microsoft 365 в формате TESTLAB с DNS-доменом.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="6052b-161">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<*your domain name*></span></span> <span data-ttu-id="6052b-162">-</span><span class="sxs-lookup"><span data-stu-id="6052b-162">registered.</span></span>
- <span data-ttu-id="6052b-163">Упрощенная интрасеть Организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="6052b-163">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="6052b-164">Azure AD Connect работает на APP1 для синхронизации списка учетных записей и групп из клиента Azure AD, связанного с подпиской Microsoft 365, с доменом AD DS TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="6052b-164">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="6052b-165">Обратная запись паролей включена, поэтому пользователи могут сменить свои пароли через Azure AD без необходимости подключения к упрощенной интрасети.</span><span class="sxs-lookup"><span data-stu-id="6052b-165">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

## <a name="next-step"></a><span data-ttu-id="6052b-166">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="6052b-166">Next step</span></span>

<span data-ttu-id="6052b-167">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="6052b-167">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6052b-168">См. также</span><span class="sxs-lookup"><span data-stu-id="6052b-168">See also</span></span>

[<span data-ttu-id="6052b-169">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="6052b-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6052b-170">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="6052b-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="6052b-171">Microsoft 365 для корпоративных документов</span><span class="sxs-lookup"><span data-stu-id="6052b-171">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


