---
title: Включение управления устройствами с Windows 10, подключенными к домену, в Microsoft 365 для бизнеса
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Сведения о том, как включить Microsoft 365 для защиты локальных подключенных к Active Directory устройств с Windows 10 в всего несколько этапов.
ms.openlocfilehash: 857651081fb10856d28dd419333ebef655388407
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "44564960"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="d01d1-103">Управление устройствами с Windows 10, подключенными к домену, с помощью Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="d01d1-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="d01d1-104">Если ваша организация использует локальную службу Windows Server Active Directory, вы можете настроить Microsoft 365 Business Premium для защиты устройств Windows 10, сохраняя доступ к локальным ресурсам, требующим локальной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d01d1-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="d01d1-105">Чтобы настроить эту защиту, можно внедрить **гибридные подключенные устройства Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="d01d1-106">Эти устройства присоединяются как к локальной службе Active Directory, так и к Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d01d1-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="d01d1-107">В этом видеоролике описаны действия, которые необходимо выполнить для наиболее распространенного сценария, который также содержит подробные инструкции.</span><span class="sxs-lookup"><span data-stu-id="d01d1-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="d01d1-108">Прежде чем приступить к работе, убедитесь, что выполнены следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d01d1-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="d01d1-109">Синхронизация пользователей с Azure AD с помощью Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="d01d1-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="d01d1-110">Выполните синхронизацию подразделения Azure AD Connect (OU).</span><span class="sxs-lookup"><span data-stu-id="d01d1-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="d01d1-111">Убедитесь, что у всех пользователей домена, которые вы синхронизируете, есть лицензии на Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="d01d1-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="d01d1-112">В этой статье приведены инструкции по [синхронизации пользователей домена с корпорацией Майкрософт](manage-domain-users.md) .</span><span class="sxs-lookup"><span data-stu-id="d01d1-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="d01d1-113">1. Проверка полномочий MDM в Intune</span><span class="sxs-lookup"><span data-stu-id="d01d1-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="d01d1-114">Перейдите в portal.azure.com и в верхней части страницы поиска для Intune.</span><span class="sxs-lookup"><span data-stu-id="d01d1-114">Go to portal.azure.com and on the top of the page search for Intune.</span></span>
<span data-ttu-id="d01d1-115">На странице Microsoft Intune выберите элемент **Регистрация устройств** и на странице **Обзор** убедитесь, что **центр MDM** является **Intune**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-115">On the Microsoft Intune page, select **Device enrollment** and on the **Overview** page make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="d01d1-116">Если для **MDM Authority** задано значение **None (нет**), щелкните **центр MDM** , чтобы задать для него значение **Intune**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-116">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="d01d1-117">Если в качестве **шлюза** **MDM** используется **Microsoft Office 365**, перейдите на страницу  >  **Регистрация устройств** и воспользуйтесь диалоговым окном **Добавление центра MDM** справа для добавления центра **Intune MDM** (диалоговое окно **Add MDM Authority** доступно только в том случае, если для шлюза **MDM** установлено значение Microsoft Office 365).</span><span class="sxs-lookup"><span data-stu-id="d01d1-117">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="d01d1-118">2. Убедитесь, что служба Azure AD включена для присоединения компьютеров</span><span class="sxs-lookup"><span data-stu-id="d01d1-118">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="d01d1-119">Перейдите в центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> и выберите **Azure Active Directory** (выберите Показать все, если Azure Active Directory не отображается) в списке **центры администрирования** .</span><span class="sxs-lookup"><span data-stu-id="d01d1-119">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="d01d1-120">В **центре администрирования Azure Active Directory**откройте **Azure Active Directory** , выберите пункт **устройства** и затем **Параметры устройства**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-120">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="d01d1-121">Проверка того, что**пользователи могут присоединяться к устройствам для Azure AD** .</span><span class="sxs-lookup"><span data-stu-id="d01d1-121">Verify**Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="d01d1-122">Чтобы включить всех пользователей, задайте значение **ALL**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-122">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="d01d1-123">Чтобы включить определенных пользователей, установите **флажок** разрешить определенную группу пользователей.</span><span class="sxs-lookup"><span data-stu-id="d01d1-123">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="d01d1-124">Добавьте в [группу безопасности](../admin/create-groups/create-groups.md)требуемых пользователей домена, синхронизированных в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d01d1-124">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="d01d1-125">Выберите **пункт Выбрать группы** , чтобы включить область пользователя MDM для этой группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="d01d1-125">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="d01d1-126">3. Убедитесь, что служба Azure AD включена для MDM</span><span class="sxs-lookup"><span data-stu-id="d01d1-126">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="d01d1-127">Перейдите в центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> и выберите пункт выбрать **конечную точку манажемен**t (выберите **Показать все** , если **Диспетчер конечных точек** не отображается).</span><span class="sxs-lookup"><span data-stu-id="d01d1-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen**t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="d01d1-128">В **центре администрирования Microsoft Endpoint Manager**перейдите к разделу **устройства**, подаче заявки на  >  **Windows**  >  **регистрацию Windows Windows**для  >  **автоматической регистрации**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-128">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="d01d1-129">Убедитесь, что область пользователя MDM включена.</span><span class="sxs-lookup"><span data-stu-id="d01d1-129">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="d01d1-130">Чтобы зарегистрировать все компьютеры, установите для параметра **ALL** значение автоматическая регистрация всех пользовательских компьютеров, присоединенных к Azure AD и новым компьютерам, когда пользователи добавляют рабочую учетную запись в Windows.</span><span class="sxs-lookup"><span data-stu-id="d01d1-130">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="d01d1-131">Установите значение **, чтобы** зарегистрировать компьютеры определенной группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="d01d1-131">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="d01d1-132">Добавьте в [группу безопасности](../admin/create-groups/create-groups.md)требуемых пользователей домена, синхронизированных в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d01d1-132">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="d01d1-133">Выберите **пункт Выбрать группы** , чтобы включить область пользователя MDM для этой группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="d01d1-133">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-set-up-service-connection-point-scp"></a><span data-ttu-id="d01d1-134">4. Настройка точки подключения службы (SCP)</span><span class="sxs-lookup"><span data-stu-id="d01d1-134">4. Set up Service connection point (SCP)</span></span>

<span data-ttu-id="d01d1-135">Эти действия упрощают [настройку гибридного подключения Azure AD](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span><span class="sxs-lookup"><span data-stu-id="d01d1-135">These steps are simplified from [configure hybrid azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="d01d1-136">Для выполнения действий, необходимых для использования Azure AD Connect, а также паролей администратора Microsoft 365 Business Premium Global и Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d01d1-136">To complete the steps you need to use Azure AD Connect and your Microsoft 365 Business Premium global admin and Active Directory admin passwords.</span></span>

1.  <span data-ttu-id="d01d1-137">Запустите Azure AD Connect, а затем выберите пункт **настроить**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-137">Start Azure AD Connect, and then select **Configure**.</span></span>
2.  <span data-ttu-id="d01d1-138">На странице **Дополнительные задачи** выберите пункт **Настройка параметров устройства**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-138">On the **Additional tasks**  page, select **Configure device options**, and then select **Next**.</span></span>
3.  <span data-ttu-id="d01d1-139">На странице **Обзор** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-139">On the **Overview** page, select **Next**.</span></span>
4.  <span data-ttu-id="d01d1-140">На странице **Подключение к Azure AD** введите учетные данные глобального администратора для Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="d01d1-140">On the **Connect to Azure AD** page, enter the credentials of a global administrator for Microsoft 365 Business Premium.</span></span>
5.  <span data-ttu-id="d01d1-141">На странице **Параметры устройства** выберите **Настройка гибридного подключения Azure AD**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-141">On the **Device options** page, select **Configure Hybrid Azure AD join**, and then select **Next**.</span></span>
6.  <span data-ttu-id="d01d1-142">На странице **точка подключения службы (SCP** ) для каждого леса, в котором служба Azure AD Connect должна быть настроена для настройки SCP, выполните следующие действия, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-142">On the **SCP** page, for each forest where you want Azure AD Connect to configure the SCP, complete the following steps, and then select **Next**:</span></span>
    - <span data-ttu-id="d01d1-143">Установите флажок рядом с именем леса.</span><span class="sxs-lookup"><span data-stu-id="d01d1-143">Check the box beside the forest name.</span></span> <span data-ttu-id="d01d1-144">Лес должен быть именем домена AD.</span><span class="sxs-lookup"><span data-stu-id="d01d1-144">The forest should be your AD domain name.</span></span>
    - <span data-ttu-id="d01d1-145">В столбце **Служба проверки подлинности** откройте раскрывающееся меню и выберите совпадающее доменное имя (должен быть только один параметр).</span><span class="sxs-lookup"><span data-stu-id="d01d1-145">Under the **Authentication Service** column, open the dropdown and select matching domain name (there should only be one only option).</span></span>
    - <span data-ttu-id="d01d1-146">Нажмите кнопку **Добавить** , чтобы ввести учетные данные администратора домена.</span><span class="sxs-lookup"><span data-stu-id="d01d1-146">Select **Add** to enter the domain administrator credentials.</span></span>  
7.  <span data-ttu-id="d01d1-147">На странице " **операционные системы устройств** " выберите только устройства, присоединенные к домену Windows 10 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="d01d1-147">On the **Device operating systems** page, select Windows 10 or later domain-joined devices only.</span></span>
8.  <span data-ttu-id="d01d1-148">На странице **Готово к настройке** нажмите кнопку **настроить**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-148">On the **Ready to configure** page, select **Configure**.</span></span>
9.  <span data-ttu-id="d01d1-149">На странице **Завершение настройки** нажмите кнопку **выход**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-149">On the **Configuration complete** page, select **Exit**.</span></span>


## <a name="5-create-a-gpo-for-intune-enrollment--admx-method"></a><span data-ttu-id="d01d1-150">5. Создание объекта групповой политики для регистрации в Intune — метод ADMX</span><span class="sxs-lookup"><span data-stu-id="d01d1-150">5. Create a GPO for Intune Enrollment – ADMX method</span></span>

<span data-ttu-id="d01d1-151">Используйте. Файл шаблона ADMX.</span><span class="sxs-lookup"><span data-stu-id="d01d1-151">Use .ADMX template file.</span></span>

1.  <span data-ttu-id="d01d1-152">Выполните вход на сервер Active Directory, найдите и **Server Manager**откройте компонент "  >  **Tools**  >  **Управление групповыми политиками**" средств диспетчера серверов.</span><span class="sxs-lookup"><span data-stu-id="d01d1-152">Log on to AD server, search and open **Server Manager** > **Tools** > **Group Policy Management**.</span></span>
2.  <span data-ttu-id="d01d1-153">Выберите имя домена в разделе **домены** , а затем щелкните правой кнопкой мыши пункт **объекты групповой политики** , чтобы выбрать пункт **создать**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-153">Select your domain name under **Domains** and right-click **Group Policy Objects** to select **New**.</span></span>
3.  <span data-ttu-id="d01d1-154">Присвойте новому объекту групповой политики имя, например "*Cloud_Enrollment*", а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-154">Give the new GPO an name, for example “*Cloud_Enrollment*” and then select **OK**.</span></span>
4.  <span data-ttu-id="d01d1-155">Щелкните правой кнопкой мыши новый объект групповой **политики в разделе объекты групповой политики** и выберите **изменить**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-155">Right-click the new GPO under **Group Policy Objects** and select **Edit**.</span></span>
5.  <span data-ttu-id="d01d1-156">В **редакторе управления групповыми политиками**перейдите к разделу политики **конфигурации компьютера**  >  **Policies**  >  **Административные шаблоны**  >  **компонентов Windows**  >  **MDM**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-156">In the **Group Policy Management Editor**, go to **Computer Configuration** > **Policies** > **Administrative Templates** > **Windows Components** > **MDM**.</span></span>
6. <span data-ttu-id="d01d1-157">Щелкните правой кнопкой мыши **включить автоматическую регистрацию MDM, используя учетные данные Azure AD по умолчанию** , а затем выберите **включено**  >  **OK**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-157">Right-click **Enable automatic MDM enrollment using default Azure AD credentials** and then select **Enabled** > **OK**.</span></span> <span data-ttu-id="d01d1-158">Закройте окно редактора.</span><span class="sxs-lookup"><span data-stu-id="d01d1-158">Close the editor window.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d01d1-159">Если вы не видите политику **включения автоматической регистрации MDM с использованием учетных данных Azure AD по умолчанию**, ознакомьтесь [со статьей получение последних административных шаблонов](#get-the-latest-administrative-templates).</span><span class="sxs-lookup"><span data-stu-id="d01d1-159">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, see [Get the latest Administrative Templates](#get-the-latest-administrative-templates).</span></span>

## <a name="6-deploy-the-group-policy"></a><span data-ttu-id="d01d1-160">6. Разверните групповую политику.</span><span class="sxs-lookup"><span data-stu-id="d01d1-160">6. Deploy the Group Policy</span></span>

1.  <span data-ttu-id="d01d1-161">В диспетчере серверов в разделе **домены** > объекты групповой политики выберите объект групповой политики, описанный на шаге 3, например, "Cloud_Enrollment".</span><span class="sxs-lookup"><span data-stu-id="d01d1-161">In the Server Manager, under **Domains** > Group Policy objects, select the GPO from Step 3 above, for example “Cloud_Enrollment”.</span></span>
2.  <span data-ttu-id="d01d1-162">Перейдите на вкладку **область** для объекта групповой политики.</span><span class="sxs-lookup"><span data-stu-id="d01d1-162">Select the **Scope** tab for your GPO.</span></span>
3.  <span data-ttu-id="d01d1-163">На вкладке Область применения GPO щелкните правой кнопкой мыши ссылку на домен в разделе **ссылки**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-163">In the GPO’s Scope tab, right-click the link to the domain under **Links**.</span></span>
4.  <span data-ttu-id="d01d1-164">Выберите **принудительно применить** , чтобы развернуть объект групповой политики, а затем нажмите **кнопку ОК** в окне подтверждения.</span><span class="sxs-lookup"><span data-stu-id="d01d1-164">Select **Enforced** to deploy the GPO and then **OK** in the confirmation screen.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="d01d1-165">Получение последних административных шаблонов</span><span class="sxs-lookup"><span data-stu-id="d01d1-165">Get the latest Administrative Templates</span></span>

<span data-ttu-id="d01d1-166">Если вы не видите политику **включения автоматической регистрации MDM с использованием учетных данных Azure AD по умолчанию**, возможно, у вас нет ADMX, установленного для Windows 10, версии 1803, версии 1809 или версии 1903.</span><span class="sxs-lookup"><span data-stu-id="d01d1-166">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="d01d1-167">Чтобы устранить эту проблему, выполните указанные ниже действия (Примечание: последние версии MDM. ADMX совместимы с предыдущими).</span><span class="sxs-lookup"><span data-stu-id="d01d1-167">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="d01d1-168">Загрузка: [Административные шаблоны (ADMX) для Windows 10 май 2019 обновление (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span><span class="sxs-lookup"><span data-stu-id="d01d1-168">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="d01d1-169">Установите пакет на основном контроллере домена (PDC).</span><span class="sxs-lookup"><span data-stu-id="d01d1-169">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="d01d1-170">Навигация в зависимости от версии папки: **C:\Program Files (x86) \Microsoft Group полици\виндовс 10 май 2019 обновление (1903) v3**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-170">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="d01d1-171">Переименуйте папку " **определения политик** " в указанном выше пути в **Папка PolicyDefinitions**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-171">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="d01d1-172">Скопируйте папку **Папка PolicyDefinitions** в **к:\виндовс\сисвол\домаин\полиЦиес**.</span><span class="sxs-lookup"><span data-stu-id="d01d1-172">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="d01d1-173">Если вы планируете использовать централизованное хранилище политик для всего домена, добавьте в него содержимое папка PolicyDefinitions.</span><span class="sxs-lookup"><span data-stu-id="d01d1-173">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="d01d1-174">Чтобы политика была доступна, перезапустите основной контроллер домена.</span><span class="sxs-lookup"><span data-stu-id="d01d1-174">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="d01d1-175">Эта процедура будет работать и для всех последующих версий.</span><span class="sxs-lookup"><span data-stu-id="d01d1-175">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="d01d1-176">На этом шаге вы увидите, что политика **включает автоматическую регистрацию MDM, используя доступные учетные данные Azure AD по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="d01d1-176">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>

