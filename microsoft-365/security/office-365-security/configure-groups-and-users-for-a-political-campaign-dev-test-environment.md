---
title: Настройка групп и пользователей в среде разработки и тестирования для политической кампании
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 0e22bcf3-bad3-42a4-b44f-276e0cf4790f
description: Сводка. Сведения о создании пробных подписок на Office 365 и Enterprise Mobility + Security (EMS) с пользователями и группами в случае среды разработки и тестирования для политической кампании.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 80454477bc55ab54ae7edf14ded5b4fa49fe1530
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203363"
---
# <a name="configure-groups-and-users-for-a-political-campaign-devtest-environment"></a><span data-ttu-id="0fb95-103">Настройка групп и пользователей в случае среды разработки и тестирования для политической кампании</span><span class="sxs-lookup"><span data-stu-id="0fb95-103">Configure groups and users for a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="0fb95-104">**Сводка.** Сведения о создании пробных подписок на Office 365 и Enterprise Mobility + Security (EMS) с пользователями и группами в случае среды разработки и тестирования для политической кампании.</span><span class="sxs-lookup"><span data-stu-id="0fb95-104">**Summary:** Create Office 365 and Enterprise Mobility + Security (EMS) trial subscriptions with users and groups for a political campaign dev/test environment.</span></span>

<span data-ttu-id="0fb95-105">Инструкции из этой статьи помогут создать среду разработки и тестирования, которая включает упрощенные учетные записи пользователей и группы. Она необходима для решения, упомянутого в статье [Руководство по безопасности (Майкрософт) для политических кампаний, некоммерческих и других динамических организаций](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md).</span><span class="sxs-lookup"><span data-stu-id="0fb95-105">Use the instructions in this article to create a dev/test environment that includes simplified user accounts and groups for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution.</span></span>

## <a name="phase-1-create-your-office-365-devtest-environment"></a><span data-ttu-id="0fb95-106">Этап 1. Создание среды разработки и тестирования Office 365</span><span class="sxs-lookup"><span data-stu-id="0fb95-106">Phase 1: Create your Office 365 dev/test environment</span></span>

<span data-ttu-id="0fb95-107">На этом этапе вы получите пробные подписки на Office 365 E5 и Enterprise Mobility + Security (EMS) E5 для вымышленной организации, которая проводит политическую кампанию.</span><span class="sxs-lookup"><span data-stu-id="0fb95-107">In this phase, you obtain trial subscriptions for Office 365 E5 and Enterprise Mobility + Security (EMS) E5 for a fictional organization that represents a political campaign.</span></span>

<span data-ttu-id="0fb95-108">Сначала выполните инструкции для **этапа 2** из статьи [Простая базовая конфигурация](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="0fb95-108">First, follow the instructions in **Phase 2** of [The lightweight base configuration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span></span>

<span data-ttu-id="0fb95-109">Затем оформите пробную подписку EMS E5 и добавьте ее для той же организации, что и пробную подписку.</span><span class="sxs-lookup"><span data-stu-id="0fb95-109">Next, sign up for the EMS E5 trial subscription and add it to the same organization as your trial subscription.</span></span>

1. <span data-ttu-id="0fb95-110">При необходимости войдите в Центр администрирования, используя учетные данные глобального администратора пробной подписки.</span><span class="sxs-lookup"><span data-stu-id="0fb95-110">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="0fb95-111">Дополнительные сведения см. в статье [Вход](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="0fb95-111">For help, see [Where to sign in](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="0fb95-112">Выберите плитку **Администрирование**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-112">Click the **Admin** tile.</span></span>

3. <span data-ttu-id="0fb95-113">На вкладке **Центр администрирования Microsoft 365** в браузере, в области навигации слева, щелкните **Выставление счетов > Приобретение служб**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-113">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Billing > Purchase services**.</span></span>

4. <span data-ttu-id="0fb95-p102">На странице **Приобретение служб** найдите элемент **Enterprise Mobility + Security E5**. Наведите на него указатель мыши и выберите **Начать бесплатный пробный период**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-p102">On the **Purchase services** page, find the **Enterprise Mobility + Security E5** item. Hover your mouse pointer over it and click **Start free trial**.</span></span>

5. <span data-ttu-id="0fb95-116">На странице **Подтверждение заказа** нажмите кнопку **Попробовать**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-116">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="0fb95-117">На странице **Получение заказа** нажмите кнопку **Продолжить**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-117">On the **Order receipt** page, click **Continue**.</span></span>

<span data-ttu-id="0fb95-118">Затем включите лицензию на EMS E5 для своей учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="0fb95-118">Next, enable the EMS E5 license for your global administrator account.</span></span>

1. <span data-ttu-id="0fb95-119">Открыв вкладку браузера **Центр администрирования Microsoft 365**, на панели навигации слева выберите **Пользователи > Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-119">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Users > Active users**.</span></span>

2. <span data-ttu-id="0fb95-120">Выберите свою учетную запись глобального администратора и щелкните ссылку **Изменить** для параметра **Лицензии на продукты**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-120">Click your global administrator account, and then click **Edit** for **Product licenses**.</span></span>

3. <span data-ttu-id="0fb95-121">На панели **Лицензии на продукты** переведите переключатель **Enterprise Mobility + Security E5** в положение **Вкл.**, нажмите **Сохранить**, а затем дважды **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-121">On the **Product licenses** pane, turn the product license for **Enterprise Mobility + Security E5** to **On**, click **Save,** and then click **Close** twice.</span></span>

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups"></a><span data-ttu-id="0fb95-122">Этап 2. Создание и настройка групп Azure Active Directory (AD)</span><span class="sxs-lookup"><span data-stu-id="0fb95-122">Phase 2: Create and configure your Azure Active Directory (AD) groups</span></span>

<span data-ttu-id="0fb95-123">На этом этапе создаются и настраиваются группы Azure AD для кампании.</span><span class="sxs-lookup"><span data-stu-id="0fb95-123">In this phase, you create and configure the Azure AD groups for your campaign.</span></span>

<span data-ttu-id="0fb95-124">Сначала создайте набор групп для обычной политической кампании на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="0fb95-124">First, create a set of groups for a typical political campaign with the Azure portal.</span></span>

1. <span data-ttu-id="0fb95-p103">Откройте портал Azure ([https://portal.azure.com](https://portal.azure.com)) на отдельной вкладке браузера. Если необходимо, выполните вход, используя данные учетной записи глобального администратора для пробной подписки на Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="0fb95-p103">On a separate tab in your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com). If needed, sign in with the credentials of the global administrator account for your Office 365 E5 trial subscription.</span></span>

2. <span data-ttu-id="0fb95-127">На портале Azure последовательно выберите **Azure Active Directory > Пользователи и группы > Все группы**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-127">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>

3. <span data-ttu-id="0fb95-128">Выполните приведенные ниже шаги для каждой группы из этого списка:</span><span class="sxs-lookup"><span data-stu-id="0fb95-128">Do the following steps for each group name in this list:</span></span>

   - <span data-ttu-id="0fb95-129">"Старший и стратегический персонал";</span><span class="sxs-lookup"><span data-stu-id="0fb95-129">Senior and strategic staff</span></span>

   - <span data-ttu-id="0fb95-130">"ИТ-персонал";</span><span class="sxs-lookup"><span data-stu-id="0fb95-130">IT staff</span></span>

   - <span data-ttu-id="0fb95-131">"Специалисты по аналитике";</span><span class="sxs-lookup"><span data-stu-id="0fb95-131">Analytics staff</span></span>

   - <span data-ttu-id="0fb95-132">"Основной штат сотрудников";</span><span class="sxs-lookup"><span data-stu-id="0fb95-132">Regular core staff</span></span>

   - <span data-ttu-id="0fb95-133">"Операционный персонал";</span><span class="sxs-lookup"><span data-stu-id="0fb95-133">Operations staff</span></span>

   - <span data-ttu-id="0fb95-134">"Выездной персонал".</span><span class="sxs-lookup"><span data-stu-id="0fb95-134">Field staff</span></span>

1. <span data-ttu-id="0fb95-135">В колонке **Все группы** выберите пункт **+ Новая группа**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-135">On the **All groups** blade, click **+ New group**.</span></span>

2. <span data-ttu-id="0fb95-136">Введите имя группы из списка в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-136">Type the group name from the list in **Name**.</span></span>

3. <span data-ttu-id="0fb95-137">Выберите **Динамический пользователь** для параметра **Членство**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-137">Select **Dynamic user** in **Membership**.</span></span>

4. <span data-ttu-id="0fb95-138">Выберите вариант **Да** для параметра **Включить функции Office**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-138">Click **Yes** for **Enable Office features**.</span></span>

5. <span data-ttu-id="0fb95-139">Выберите **Добавить динамический запрос**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-139">Click **Add dynamic query**.</span></span>

6. <span data-ttu-id="0fb95-140">В поле **Место добавления пользователей** выберите **Отдел**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-140">In **Add users where**, select **department**.</span></span>

7. <span data-ttu-id="0fb95-141">В следующем поле выберите **Равно**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-141">In the next field, select **Equals**.</span></span>

8. <span data-ttu-id="0fb95-142">В следующем поле введите имя группы из списка.</span><span class="sxs-lookup"><span data-stu-id="0fb95-142">In the next field, type the group name from the list.</span></span>

9. <span data-ttu-id="0fb95-143">Выберите **Добавить запрос** > **Создать**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-143">Click **Add query**, and then click **Create**.</span></span>

10. <span data-ttu-id="0fb95-144">Выберите **Пользователи и группы — Все группы**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-144">Click **Users and groups - All groups**.</span></span>

<span data-ttu-id="0fb95-145">Затем настройте группы так, чтобы их членам автоматически назначались лицензии на Office 365 E5 и EMS E5.</span><span class="sxs-lookup"><span data-stu-id="0fb95-145">Next, you configure the groups so that members are automatically assigned Office 365 E5 and EMS E5 licenses.</span></span>

1. <span data-ttu-id="0fb95-146">На портале Azure последовательно выберите **Azure Active Directory > Лицензии > Все продукты**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-146">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>

2. <span data-ttu-id="0fb95-147">В списке выберите **Enterprise Mobility + Security E5** и **Office 365 корпоративный E5**, затем нажмите **+ Назначить**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-147">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **+ Assign**.</span></span>

3. <span data-ttu-id="0fb95-148">В колонке **Назначение лицензии** щелкните **Пользователи и группы**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-148">In the **Assign license** blade, click **Users and groups**.</span></span>

4. <span data-ttu-id="0fb95-149">В списке выберите следующие группы:</span><span class="sxs-lookup"><span data-stu-id="0fb95-149">In the list of groups, select the following:</span></span>

   - <span data-ttu-id="0fb95-150">Специалисты по аналитике</span><span class="sxs-lookup"><span data-stu-id="0fb95-150">Analytics staff</span></span>

   - <span data-ttu-id="0fb95-151">Выездной персонал</span><span class="sxs-lookup"><span data-stu-id="0fb95-151">Field staff</span></span>

   - <span data-ttu-id="0fb95-152">ИТ-персонал</span><span class="sxs-lookup"><span data-stu-id="0fb95-152">IT staff</span></span>

   - <span data-ttu-id="0fb95-153">Операционный персонал</span><span class="sxs-lookup"><span data-stu-id="0fb95-153">Operations staff</span></span>

   - <span data-ttu-id="0fb95-154">Основной штат сотрудников</span><span class="sxs-lookup"><span data-stu-id="0fb95-154">Regular core staff</span></span>

   - <span data-ttu-id="0fb95-155">Старший и стратегический персонал</span><span class="sxs-lookup"><span data-stu-id="0fb95-155">Senior and strategic staff</span></span>

5. <span data-ttu-id="0fb95-156">Выберите **Выбрать** > **Назначить**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-156">Click **Select**, and then click **Assign**.</span></span>

6. <span data-ttu-id="0fb95-157">Закройте вкладку портала Azure в браузере.</span><span class="sxs-lookup"><span data-stu-id="0fb95-157">Close the Azure portal tab in your browser.</span></span>

## <a name="phase-3-add-your-user-accounts"></a><span data-ttu-id="0fb95-158">Этап 3. Добавление учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="0fb95-158">Phase 3: Add your user accounts</span></span>

<span data-ttu-id="0fb95-159">На этом этапе добавляются демонстрационные учетные записи пользователей для политической кампании.</span><span class="sxs-lookup"><span data-stu-id="0fb95-159">In this phase, you add the example user accounts for your political campaign.</span></span>

<span data-ttu-id="0fb95-160">Прежде всего [подключитесь к модулю PowerShell Azure Active Directory для Graph](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="0fb95-160">First, you [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell).</span></span>

<span data-ttu-id="0fb95-161">Затем введите название организации, адрес и общий пароль и выполните эти команды в командной строке PowerShell или интегрированной среде сценариев (ISE):</span><span class="sxs-lookup"><span data-stu-id="0fb95-161">Next, you fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE):</span></span>

```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$deptName="Senior and strategic staff"
$userNames=@("Candidate","ChiefOfStaff","Strategic1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Analytics staff"
$userNames=@("DataScientist1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Regular core staff"
$userNames=@("Regular1","Regular2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Operations staff"
$userNames=@("Operations1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Field staff"
$userNames=@("FieldConsultant1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
```

> [!IMPORTANT]
> <span data-ttu-id="0fb95-p104">Общий пароль используется для автоматизации и упрощения настройки среды разработки и тестирования. Не рекомендуется для рабочих подписок. При входе в каждую из этих новых учетных записей пользователя вам будут показаны запросы на изменение пароля.</span><span class="sxs-lookup"><span data-stu-id="0fb95-p104">The use of a common password here is for automation and ease of configuration for a dev/test environment. This is not recommended for production subscriptions. As you sign in with each of these new user accounts, you will be prompted to change the password.</span></span>

<span data-ttu-id="0fb95-165">Чтобы проверить динамическое членство в группах и групповое лицензирование:</span><span class="sxs-lookup"><span data-stu-id="0fb95-165">Use these steps to verify that dynamic group membership and group-based licensing are working correctly.</span></span>

1. <span data-ttu-id="0fb95-166">На вкладке браузера **Домашняя страница Microsoft Office** щелкните плитку **Администрирование**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-166">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>

2. <span data-ttu-id="0fb95-167">На новой вкладке браузера**Центр администрирования Microsoft 365** щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-167">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>

3. <span data-ttu-id="0fb95-168">В списке пользователей выберите **Кандидат**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-168">In the list of users, click **Candidate**.</span></span>

4. <span data-ttu-id="0fb95-169">В области свойств учетной записи **Кандидат** убедитесь, что:</span><span class="sxs-lookup"><span data-stu-id="0fb95-169">In the pane that lists the properties of the **Candidate** user account, verify that:</span></span>

   - <span data-ttu-id="0fb95-170">она входит в состав группы **Старший и стратегический персонал** (в разделе **Членство в группах**);</span><span class="sxs-lookup"><span data-stu-id="0fb95-170">It is a member of the **Senior and strategic staff** group (in **Group memberships**).</span></span>

   - <span data-ttu-id="0fb95-171">ей назначены лицензии на **Enterprise Mobility + Security E5** и **Office 365 корпоративный E5** (в разделе **Лицензии на продукты**).</span><span class="sxs-lookup"><span data-stu-id="0fb95-171">It has been assigned the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses (in **Product licenses**).</span></span>

5. <span data-ttu-id="0fb95-172">Закройте область учетной записи пользователя **Кандидат**.</span><span class="sxs-lookup"><span data-stu-id="0fb95-172">Close the **Candidate** user account pane.</span></span>

## <a name="record-values-for-future-reference"></a><span data-ttu-id="0fb95-173">Запишите значения для дальнейшего использования</span><span class="sxs-lookup"><span data-stu-id="0fb95-173">Record values for future reference</span></span>

<span data-ttu-id="0fb95-174">Запишите эти значения для работы с пробными подписками Office 365 и EMS для этой среды разработки и тестирования:</span><span class="sxs-lookup"><span data-stu-id="0fb95-174">Record these values for working with the Office 365 and EMS trial subscriptions for this dev/test environment:</span></span>

- <span data-ttu-id="0fb95-175">Название вашей организации:</span><span class="sxs-lookup"><span data-stu-id="0fb95-175">Your trial subscription organization name:</span></span> ![Подчеркнутый](../../media/Common-Images/TableLine.png)

  <span data-ttu-id="0fb95-177">Например, для доменного имени contoso.onmicrosoft.com название организации — "contoso".</span><span class="sxs-lookup"><span data-stu-id="0fb95-177">For example, for the trial subscription domain name of contoso.onmicrosoft.com, the organization name is "contoso".</span></span>

- <span data-ttu-id="0fb95-178">Имя глобального администратора:</span><span class="sxs-lookup"><span data-stu-id="0fb95-178">The global administrator name:</span></span> ![Подчеркнутый](../../media/Common-Images/TableLine.png)<span data-ttu-id="0fb95-180">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="0fb95-180">.onmicrosoft.com</span></span>

  <span data-ttu-id="0fb95-181">Запишите пароль для этой учетной записи и общий первоначальный пароль для других учетных записей пользователей в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="0fb95-181">Record the password for this account and the common initial password for the other user accounts in a secure location.</span></span>

## <a name="next-step"></a><span data-ttu-id="0fb95-182">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="0fb95-182">Next step</span></span>

<span data-ttu-id="0fb95-183">Создайте четыре типа для сайтов группы SharePoint Online в этой среде разработки и тестирования, следуя инструкциям из статьи [Создание сайтов группы в среде разработки и тестирования для политической кампании](create-team-sites-in-a-political-campaign-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="0fb95-183">Build the four different types of SharePoint Online team sites in this dev/test environment with [Create team sites in a political campaign dev/test environment](create-team-sites-in-a-political-campaign-dev-test-environment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0fb95-184">См. также</span><span class="sxs-lookup"><span data-stu-id="0fb95-184">See also</span></span>

[<span data-ttu-id="0fb95-185">Руководство по безопасности (Майкрософт) для политических кампаний, некоммерческих и других динамических организаций</span><span class="sxs-lookup"><span data-stu-id="0fb95-185">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="0fb95-186">Создание сайтов группы в среде разработки и тестирования для политической кампании</span><span class="sxs-lookup"><span data-stu-id="0fb95-186">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="0fb95-187">Руководства по лаборатории тестирования для облачных решений</span><span class="sxs-lookup"><span data-stu-id="0fb95-187">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[<span data-ttu-id="0fb95-188">Освоение облака и гибридные решения</span><span class="sxs-lookup"><span data-stu-id="0fb95-188">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
