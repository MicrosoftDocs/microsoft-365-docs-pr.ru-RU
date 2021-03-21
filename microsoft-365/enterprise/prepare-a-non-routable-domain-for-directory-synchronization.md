---
title: Подготовка немаршрутизируемого домена к синхронизации службы каталогов
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365E_SetupDirSyncLocalDir
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: e7968303-c234-46c4-b8b0-b5c93c6d57a7
description: Узнайте, что делать, если у вас есть неотъемлемый домен, связанный с учетными записями локального пользователя, прежде чем синхронизировать их с клиентом Microsoft 365.
ms.openlocfilehash: e4d0e020c5792c610d501c33e8f3d5131b7a1ff0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927400"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a><span data-ttu-id="76e7b-103">Подготовка немаршрутизируемого домена к синхронизации службы каталогов</span><span class="sxs-lookup"><span data-stu-id="76e7b-103">Prepare a non-routable domain for directory synchronization</span></span>

<span data-ttu-id="76e7b-104">При синхронизации локального каталога с Microsoft 365 необходимо иметь проверенный домен в Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="76e7b-104">When you synchronize your on-premises directory with Microsoft 365, you have to have a verified domain in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="76e7b-105">Синхронизируются только основные имена пользователей (UPNs), связанные с доменом Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="76e7b-105">Only the User Principal Names (UPNs) that are associated with the on-premises Active Directory Domain Services (AD DS) domain are synchronized.</span></span> <span data-ttu-id="76e7b-106">Однако любой домен upN, содержащий домен, который не является маршрутизируемым, например ".local" (пример: billa@contoso.local), будет синхронизирован с доменом .onmicrosoft.com (пример: billa@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="76e7b-106">However, any UPN that contains a non-routable domain, such as ".local" (example: billa@contoso.local), will be synchronized to an .onmicrosoft.com domain (example: billa@contoso.onmicrosoft.com).</span></span> 

<span data-ttu-id="76e7b-107">Если в настоящее время используется домен ".local" для учетных записей пользователей в AD DS, рекомендуется изменить их на использование проверенного домена, например billa@contoso.com, для правильной синхронизации с доменом Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76e7b-107">If you currently use a ".local" domain for your user accounts in AD DS, it's recommended that you change them to use a verified domain, such as billa@contoso.com, in order to properly synchronize with your Microsoft 365 domain.</span></span>
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a><span data-ttu-id="76e7b-108">Что делать, если у меня есть только локальный домен ".local"?</span><span class="sxs-lookup"><span data-stu-id="76e7b-108">What if I only have a ".local" on-premises domain?</span></span>

<span data-ttu-id="76e7b-109">Вы используете Azure AD Connect для синхронизации AD DS с клиентом Azure AD клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76e7b-109">You use Azure AD Connect for synchronizing your AD DS to the Azure AD tenant of your Microsoft 365 tenant.</span></span> <span data-ttu-id="76e7b-110">Дополнительные сведения см. в сайте Интеграция идентификаторов локальной системы [с Azure AD.](/azure/architecture/reference-architectures/identity/azure-ad)</span><span class="sxs-lookup"><span data-stu-id="76e7b-110">For more information, see [Integrating your on-premises identities with Azure AD](/azure/architecture/reference-architectures/identity/azure-ad).</span></span>
  
<span data-ttu-id="76e7b-111">Azure AD Connect синхронизирует upN и пароль пользователей, чтобы пользователи могли войти с одинаковыми учетными данными, которые они используют на месте.</span><span class="sxs-lookup"><span data-stu-id="76e7b-111">Azure AD Connect synchronizes your users' UPN and password so that users can sign in with the same credentials they use on-premises.</span></span> <span data-ttu-id="76e7b-112">Однако Azure AD Connect синхронизирует пользователей только с доменами, проверенными Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76e7b-112">However, Azure AD Connect only synchronizes users to domains that are verified by Microsoft 365.</span></span> <span data-ttu-id="76e7b-113">Это означает, что домен также проверяется Azure AD, так как идентификаторы Microsoft 365 управляются Azure AD.</span><span class="sxs-lookup"><span data-stu-id="76e7b-113">This means that the domain also is verified by Azure AD because Microsoft 365 identities are managed by Azure AD.</span></span> <span data-ttu-id="76e7b-114">Другими словами, домен должен быть допустимым доменом Интернета (например, .com, .org, .net, .us).</span><span class="sxs-lookup"><span data-stu-id="76e7b-114">In other words, the domain has to be a valid Internet domain (such as, .com, .org, .net, .us).</span></span> <span data-ttu-id="76e7b-115">Если во внутренней службе AD DS используется только нена маршрутируемый домен (например, ".local"), это не может совпадать с проверенным доменом, который у вас есть для клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76e7b-115">If your internal AD DS only uses a non-routable domain (for example, ".local"), this can't possibly match the verified domain you have for your Microsoft 365 tenant.</span></span> <span data-ttu-id="76e7b-116">Эту проблему можно устранить, изменив основной домен в локальной AD DS или добавив один или несколько суффиксов upN.</span><span class="sxs-lookup"><span data-stu-id="76e7b-116">You can fix this issue by either changing your primary domain in your on-premises AD DS, or by adding one or more UPN suffixes.</span></span>
  
### <a name="change-your-primary-domain"></a><span data-ttu-id="76e7b-117">Изменение основного домена</span><span class="sxs-lookup"><span data-stu-id="76e7b-117">Change your primary domain</span></span>

<span data-ttu-id="76e7b-118">Измените основной домен на проверенный в Microsoft 365 домен, например contoso.com.</span><span class="sxs-lookup"><span data-stu-id="76e7b-118">Change your primary domain to a domain you have verified in Microsoft 365, for example, contoso.com.</span></span> <span data-ttu-id="76e7b-119">Каждый пользователь с доменом contoso.local обновляется до contoso.com.</span><span class="sxs-lookup"><span data-stu-id="76e7b-119">Every user that has the domain contoso.local is then updated to contoso.com.</span></span> <span data-ttu-id="76e7b-120">Однако это очень сложный процесс, и более простое решение описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="76e7b-120">This is a very involved process, however, and an easier solution is described in the following section.</span></span>
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a><span data-ttu-id="76e7b-121">Добавление суффиксов upN и обновление пользователей к ним</span><span class="sxs-lookup"><span data-stu-id="76e7b-121">Add UPN suffixes and update your users to them</span></span>

<span data-ttu-id="76e7b-122">Проблему ".local" можно решить, зарегистрировав в AD DS новый суффикс или суффиксы upN, чтобы соответствовать домену (или доменам), проверенным в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76e7b-122">You can solve the ".local" problem by registering new UPN suffix or suffixes in AD DS to match the domain (or domains) you verified in Microsoft 365.</span></span> <span data-ttu-id="76e7b-123">После регистрации нового суффикса обновляются пользовательские ИБН, чтобы заменить ".local" новым доменным именем, например, чтобы учетная запись пользователя выглядела как billa@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="76e7b-123">After you register the new suffix, you update the user UPNs to replace the ".local" with the new domain name, for example, so that a user account looks like billa@contoso.com.</span></span>
  
<span data-ttu-id="76e7b-124">После обновления upNs для использования проверенного домена вы готовы синхронизировать локальное AD DS с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76e7b-124">After you have updated the UPNs to use the verified domain, you are ready to synchronize your on-premises AD DS with Microsoft 365.</span></span>
  
#### <a name="step-1-add-the-new-upn-suffix"></a><span data-ttu-id="76e7b-125">Шаг 1. Добавление нового суффикса upN\*\*</span><span class="sxs-lookup"><span data-stu-id="76e7b-125">Step 1: Add the new UPN suffix\*\*</span></span>
  
1. <span data-ttu-id="76e7b-126">На контроллере домена AD DS в диспетчере серверов выберите **Средства** \> **Active Directory Domains и Trusts.**</span><span class="sxs-lookup"><span data-stu-id="76e7b-126">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Domains and Trusts**.</span></span>
    
    <span data-ttu-id="76e7b-127">**Или, если у вас нет Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="76e7b-127">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="76e7b-128">Нажмите **клавишу Windows + R,** чтобы открыть диалоговое окно **Run,** а затем введите домен.msc, а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="76e7b-128">Press **Windows key + R** to open the **Run** dialog, and then type in Domain.msc, and then choose **OK**.</span></span>
    
    ![Выберите домены Active Directory и трасты.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. <span data-ttu-id="76e7b-130">В **окне Active Directory Domains and Trusts** щелкните правой кнопкой мыши **Active Directory Domains and Trusts** и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="76e7b-130">In the **Active Directory Domains and Trusts** window, right-click **Active Directory Domains and Trusts**, and then choose **Properties**.</span></span>
    
    ![Щелкните правой кнопкой мыши Домены и трасты Active Directory и выберите свойства](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. <span data-ttu-id="76e7b-132">На вкладке **UpN Suffixes** в поле Альтернативные Суффиксы UPN введите новый суффикс или суффиксЫ **upN,** а затем выберите **Добавить** \> **Применить**.</span><span class="sxs-lookup"><span data-stu-id="76e7b-132">On the **UPN Suffixes** tab, in the **Alternative UPN Suffixes** box, type your new UPN suffix or suffixes, and then choose **Add** \> **Apply**.</span></span>
    
    ![Добавление нового суффикса upN](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    <span data-ttu-id="76e7b-134">Выберите **ОК,** когда вы закончили добавление суффиксов.</span><span class="sxs-lookup"><span data-stu-id="76e7b-134">Choose **OK** when you're done adding suffixes.</span></span> 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a><span data-ttu-id="76e7b-135">Шаг 2. Изменение суффикса UPN для существующих пользователей</span><span class="sxs-lookup"><span data-stu-id="76e7b-135">Step 2: Change the UPN suffix for existing users</span></span>
  
1. <span data-ttu-id="76e7b-136">На контроллере домена AD DS в диспетчере серверов выберите **средства** \> **Active Directory Users and Computers.**</span><span class="sxs-lookup"><span data-stu-id="76e7b-136">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="76e7b-137">**Или, если у вас нет Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="76e7b-137">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="76e7b-138">Нажмите **клавишу Windows + R,** чтобы открыть диалоговое окно **Run,** а затем введите в Dsa.msc и нажмите **кнопку ОК**</span><span class="sxs-lookup"><span data-stu-id="76e7b-138">Press **Windows key + R** to open the **Run** dialog, and then type in Dsa.msc, and then click **OK**</span></span>
    
2. <span data-ttu-id="76e7b-139">Выберите пользователя правой кнопкой мыши и выберите **Свойства.**</span><span class="sxs-lookup"><span data-stu-id="76e7b-139">Select a user, right-click, and then choose **Properties**.</span></span>
    
3. <span data-ttu-id="76e7b-140">На **вкладке Учетная** запись в списке суффикса upN выберите новый суффикс upN, а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="76e7b-140">On the **Account** tab, in the UPN suffix drop-down list, choose the new UPN suffix, and then choose **OK**.</span></span>
    
    ![Добавление нового суффикса upN для пользователя](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. <span data-ttu-id="76e7b-142">Выполните эти действия для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="76e7b-142">Complete these steps for every user.</span></span>
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a><span data-ttu-id="76e7b-143">Использование PowerShell для изменения суффикса UPN для всех пользователей</span><span class="sxs-lookup"><span data-stu-id="76e7b-143">Use PowerShell to change the UPN suffix for all of your users</span></span>

<span data-ttu-id="76e7b-144">Если у вас много учетных записей пользователей для обновления, проще использовать PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76e7b-144">If you have a lot of user accounts to update, it's easier to use PowerShell.</span></span> <span data-ttu-id="76e7b-145">В следующем примере для изменения всех суффиксов contoso.local на contoso.com AD DS используются cmdlets [Get-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617241(v=technet.10)) и [Set-ADUser.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617215(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="76e7b-145">The following example uses the cmdlets [Get-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617241(v=technet.10)) and [Set-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617215(v=technet.10)) to change all contoso.local suffixes to contoso.com in AD DS.</span></span> 

<span data-ttu-id="76e7b-146">Например, можно выполнить следующие команды PowerShell, чтобы обновить все суффиксы contoso.local до contoso.com:</span><span class="sxs-lookup"><span data-stu-id="76e7b-146">For example, you could run the following PowerShell commands to update all contoso.local suffixes to contoso.com:</span></span>
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

<span data-ttu-id="76e7b-147">Дополнительные Windows PowerShell active [Directory](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617195(v=technet.10)) см. в Windows PowerShell AD DS.</span><span class="sxs-lookup"><span data-stu-id="76e7b-147">See [Active Directory Windows PowerShell module](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617195(v=technet.10)) to learn more about using Windows PowerShell in AD DS.</span></span>