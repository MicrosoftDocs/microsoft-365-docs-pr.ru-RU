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
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="6d0e7-103">Обратная запись пароля для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d0e7-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="6d0e7-104">*Это руководство по лаборатории тестирования можно использовать только для Microsoft 365 для корпоративных тестовых сред.*</span><span class="sxs-lookup"><span data-stu-id="6d0e7-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="6d0e7-p101">Пользователи могут использовать возможность записи паролей для обновления паролей с помощью Azure Active Directory (Azure AD), которая затем реплицируется в локальные доменные службы Active Directory (AD DS). При этом пользователям не нужно обновлять свои пароли с помощью локальной AD DS, в которой хранятся их исходные учетные записи пользователей. Это помогает перемещаемым или удаленным пользователям, у которых нет подключения к локальной сети с удаленным доступом.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-p101">Users can use password writeback to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS). With password writeback, users don't have to update their passwords through the on-premises AD DS where their original user accounts are stored. This helps roaming or remote users who don't have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="6d0e7-108">В этой статье описывается настройка тестовой среды Microsoft 365 для записи паролей.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-108">This article describes how to configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="6d0e7-109">Настройка тестовой среды для записи паролей состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="6d0e7-109">Configuring your test environment for password writeback involves two phases:</span></span>
- [<span data-ttu-id="6d0e7-110">Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d0e7-110">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="6d0e7-111">Этап 2. Включение обратной записи паролей для домена AD DS TESTLAB</span><span class="sxs-lookup"><span data-stu-id="6d0e7-111">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="6d0e7-113">Чтобы получить визуальную карту всех статей в руководстве по лаборатории тестирования Microsoft 365 для предприятий, перейдите в стек руководств по лаборатории тестирования [Microsoft 365 для предприятий.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="6d0e7-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="6d0e7-114">Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d0e7-114">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="6d0e7-p102">Сначала следуйте инструкциям в синхронизации [с паролем.](password-hash-sync-m365-ent-test-environment.md) Итоговая конфигурация выглядит так:</span><span class="sxs-lookup"><span data-stu-id="6d0e7-p102">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Your resulting configuration looks like this:</span></span>
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="6d0e7-118">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="6d0e7-118">This configuration consists of:</span></span>
  
- <span data-ttu-id="6d0e7-119">Пробная или платная подписка Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="6d0e7-119">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="6d0e7-120">Упрощенная интрасеть организации, подключенная к Интернету, состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-120">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="6d0e7-121">Azure AD Connect работает на APP1 для синхронизации домена AD DS TESTLAB с клиентом Azure AD, связанным с подпиской Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-121">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="6d0e7-122">Этап 2. Включение обратной записи паролей для домена AD DS TESTLAB</span><span class="sxs-lookup"><span data-stu-id="6d0e7-122">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="6d0e7-123">Сначала настройте учетную запись User 1 с ролью глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-123">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="6d0e7-124">В [Центре администрирования Microsoft 365](https://portal.microsoft.com) выполните вход с помощью учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-124">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="6d0e7-125">Выберите **активных пользователей.**</span><span class="sxs-lookup"><span data-stu-id="6d0e7-125">Select **Active users**.</span></span>
 
3. <span data-ttu-id="6d0e7-126">На странице **"Активные пользователи"** выберите учетную **запись user1.**</span><span class="sxs-lookup"><span data-stu-id="6d0e7-126">On the **Active users** page, select the **user1** account,</span></span>

4. <span data-ttu-id="6d0e7-127">На области **user1** выберите "Изменить **рядом** с **ролями".**</span><span class="sxs-lookup"><span data-stu-id="6d0e7-127">On the **user1** pane, select **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="6d0e7-128">В области **"Изменение ролей пользователя"** для пользователя user1 выберите "Глобальный **администратор",**"Сохранить" **и** **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="6d0e7-128">On the **Edit user roles** pane for user1, select **Global administrator**, select **Save**, and then select **Close**.</span></span>

<span data-ttu-id="6d0e7-129">Затем настройте для учетной записи User 1 параметры безопасности, позволяющие изменять пароли от имени других пользователей в домене AD DS TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-129">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="6d0e7-130">На [портале Azure](https://portal.azure.com) выполните вход с помощью учетной записи глобального администратора и затем подключитесь к виртуальной машине APP1 с учетной записью TESTLAB\User1.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-130">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="6d0e7-131">На рабочем столе APP1 выберите **"Начните",** введите **"Активные",** а затем выберите "Пользователи и компьютеры **Active Directory".**</span><span class="sxs-lookup"><span data-stu-id="6d0e7-131">From the desktop of APP1, select **Start**, enter **active**, and then select **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="6d0e7-132">В панели меню выберите **"Вид".**</span><span class="sxs-lookup"><span data-stu-id="6d0e7-132">On the menu bar, select **View**.</span></span> <span data-ttu-id="6d0e7-133">Если **расширенные функции** не включены, выберите его, чтобы включить его.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-133">If **Advanced features** is not enabled, select it to enable it.</span></span>

4. <span data-ttu-id="6d0e7-134">В области дерева выберите и удерживайте (или щелкните правой кнопкой мыши) домен, выберите "Свойства" **и** перейдите на вкладку **"Безопасность".**</span><span class="sxs-lookup"><span data-stu-id="6d0e7-134">In the tree pane, select and hold (or right-click) your domain, select **Properties**, and then select the **Security** tab.</span></span>

5. <span data-ttu-id="6d0e7-135">Выберите **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-135">Select **Advanced**.</span></span>

6. <span data-ttu-id="6d0e7-136">На **вкладке "Разрешения"** выберите **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="6d0e7-136">On the **Permissions** tab, select **Add**.</span></span>

7. <span data-ttu-id="6d0e7-137">Select **Select a principal,** enter **User1**, and then select **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-137">Select **Select a principal**, enter **User1**, and then select **OK**.</span></span>

8. <span data-ttu-id="6d0e7-138">В поле **Применяется к** выберите **Потомки объектов пользователя**.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-138">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="6d0e7-139">В разделе **Разрешения** выберите следующее:</span><span class="sxs-lookup"><span data-stu-id="6d0e7-139">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="6d0e7-140">**Смена пароля**</span><span class="sxs-lookup"><span data-stu-id="6d0e7-140">**Change password**</span></span>
    - <span data-ttu-id="6d0e7-141">**Сброс пароля**</span><span class="sxs-lookup"><span data-stu-id="6d0e7-141">**Reset password**</span></span>

10. <span data-ttu-id="6d0e7-142">В разделе **Свойства** выберите следующее:</span><span class="sxs-lookup"><span data-stu-id="6d0e7-142">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="6d0e7-143">**Запись lockoutTime**</span><span class="sxs-lookup"><span data-stu-id="6d0e7-143">**Write lockoutTime**</span></span>
    - <span data-ttu-id="6d0e7-144">**Запись pwdLastSet**</span><span class="sxs-lookup"><span data-stu-id="6d0e7-144">**Write pwdLastSet**</span></span>

11. <span data-ttu-id="6d0e7-145">Чтобы **сохранить** изменения, три раза выберите "ОК".</span><span class="sxs-lookup"><span data-stu-id="6d0e7-145">Select **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="6d0e7-146">Закройте оснастку **Пользователи и компьютеры Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-146">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="6d0e7-147">Затем настройте Azure AD Connect на виртуальной машине APP1 для обратной записи пароля.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-147">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="6d0e7-148">При необходимости подключитесь к виртуальной машине APP1 с помощью учетной записи TESTLAB\User1</span><span class="sxs-lookup"><span data-stu-id="6d0e7-148">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="6d0e7-149">На рабочем столе виртуальной машины APP1 дважды щелкните значок **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-149">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="6d0e7-150">На странице **приветствия выберите** **"Настроить".**</span><span class="sxs-lookup"><span data-stu-id="6d0e7-150">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="6d0e7-151">На странице **"Дополнительные задачи"** выберите **"Настройка параметров** синхронизации", а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="6d0e7-151">On the **Additional tasks** page, select **Customize synchronization options**, and then select **Next**.</span></span>

5. <span data-ttu-id="6d0e7-152">На странице **"Подключение к Azure AD"** введите учетные данные глобального администратора и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="6d0e7-152">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="6d0e7-153">On the **Connect directories** and **Domain/OU filtering** pages, select **Next**.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-153">On the **Connect directories** and **Domain/OU filtering** pages, select **Next**.</span></span>

7. <span data-ttu-id="6d0e7-154">На странице **"Необязательные функции"** выберите функцию "Перезаписка **пароля"** и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="6d0e7-154">On the **Optional features** page, select **Password writeback**, and then select **Next**.</span></span>

8. <span data-ttu-id="6d0e7-155">На странице  **"Готово к настройке"** выберите "Настройка" и дождитесь завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-155">On the **Ready to configure** page, select **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="6d0e7-156">После завершения настройки выберите **"Выход".**</span><span class="sxs-lookup"><span data-stu-id="6d0e7-156">When you see the configuration finish, select **Exit**.</span></span>

<span data-ttu-id="6d0e7-157">Теперь вы можете проверить возможность записи паролей для пользователей на компьютерах, которые не подключены к виртуальной сети имитированной интрасети.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-157">You are now ready to test password writeback for users on computers that aren't connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="6d0e7-158">Итоговая конфигурация выглядит так:</span><span class="sxs-lookup"><span data-stu-id="6d0e7-158">Your resulting configuration looks like this:</span></span>

![Смоделированная организации с тестовой средой сквозной проверки подлинности](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="6d0e7-160">Конфигурация состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="6d0e7-160">This configuration consists of:</span></span>

- <span data-ttu-id="6d0e7-161">Пробная или платная подписка Microsoft 365 E5 с доменом DNS TESTLAB.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="6d0e7-161">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<*your domain name*></span></span> <span data-ttu-id="6d0e7-162">-</span><span class="sxs-lookup"><span data-stu-id="6d0e7-162">registered.</span></span>
- <span data-ttu-id="6d0e7-163">Упрощенная интрасеть организации, подключенная к Интернету, состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети виртуальной сети Azure.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-163">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="6d0e7-164">Azure AD Connect работает на APP1 для синхронизации списка учетных записей и групп из клиента Azure AD, связанного с подпиской Microsoft 365, с доменом AD DS TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-164">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="6d0e7-165">Обратная запись паролей включена, поэтому пользователи могут сменить свои пароли через Azure AD без необходимости подключения к упрощенной интрасети.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-165">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

## <a name="next-step"></a><span data-ttu-id="6d0e7-166">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="6d0e7-166">Next step</span></span>

<span data-ttu-id="6d0e7-167">Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="6d0e7-167">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d0e7-168">См. также</span><span class="sxs-lookup"><span data-stu-id="6d0e7-168">See also</span></span>

[<span data-ttu-id="6d0e7-169">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="6d0e7-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6d0e7-170">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="6d0e7-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="6d0e7-171">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="6d0e7-171">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


