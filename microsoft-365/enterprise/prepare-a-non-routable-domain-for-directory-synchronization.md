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
description: Узнайте, что делать, если у вас есть домен, не связанный с маршрутией, связанный с учетными записями локального пользователя, прежде чем синхронизировать их с клиентом Microsoft 365.
ms.openlocfilehash: dcd941bbae159afeb0cf6ef4f5acbaf409966295
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780336"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a><span data-ttu-id="b836c-103">Подготовка немаршрутизируемого домена к синхронизации службы каталогов</span><span class="sxs-lookup"><span data-stu-id="b836c-103">Prepare a non-routable domain for directory synchronization</span></span>

<span data-ttu-id="b836c-104">При синхронизации локального каталога с Microsoft 365 необходимо иметь проверенный домен в Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b836c-104">When you synchronize your on-premises directory with Microsoft 365, you have to have a verified domain in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="b836c-105">Синхронизируются только имена основных пользователей( UPNS), связанные с локального домена доменных служб Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="b836c-105">Only the User Principal Names (UPNs) that are associated with the on-premises Active Directory Domain Services (AD DS) domain are synchronized.</span></span> <span data-ttu-id="b836c-106">Однако любое имя upN, которое содержит нена маршрутизируемый домен, например ".local" (например, billa@contoso.local), будет синхронизировано с доменом .onmicrosoft.com (например: billa@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="b836c-106">However, any UPN that contains a non-routable domain, such as ".local" (example: billa@contoso.local), will be synchronized to an .onmicrosoft.com domain (example: billa@contoso.onmicrosoft.com).</span></span> 

<span data-ttu-id="b836c-107">Если в настоящее время вы используете "локальный" домен для учетных записей пользователей в доменных службах AD DS, рекомендуется изменить их на проверенный домен, например billa@contoso.com, для правильной синхронизации с доменом Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b836c-107">If you currently use a ".local" domain for your user accounts in AD DS, it's recommended that you change them to use a verified domain, such as billa@contoso.com, in order to properly synchronize with your Microsoft 365 domain.</span></span>
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a><span data-ttu-id="b836c-108">Что делать, если у меня есть только локальный домен .local?</span><span class="sxs-lookup"><span data-stu-id="b836c-108">What if I only have a ".local" on-premises domain?</span></span>

<span data-ttu-id="b836c-109">Azure AD Connect используется для синхронизации AD DS с клиентом Azure AD клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b836c-109">You use Azure AD Connect for synchronizing your AD DS to the Azure AD tenant of your Microsoft 365 tenant.</span></span> <span data-ttu-id="b836c-110">Дополнительные сведения см. в интеграции локальной идентификации [с Azure AD.](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad)</span><span class="sxs-lookup"><span data-stu-id="b836c-110">For more information, see [Integrating your on-premises identities with Azure AD](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad).</span></span>
  
<span data-ttu-id="b836c-111">Azure AD Connect синхронизирует upN и пароль пользователей, чтобы пользователи могли вводить те же учетные данные, что и локально.</span><span class="sxs-lookup"><span data-stu-id="b836c-111">Azure AD Connect synchronizes your users' UPN and password so that users can sign in with the same credentials they use on-premises.</span></span> <span data-ttu-id="b836c-112">Однако Azure AD Connect синхронизирует пользователей только с доменами, проверенными Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b836c-112">However, Azure AD Connect only synchronizes users to domains that are verified by Microsoft 365.</span></span> <span data-ttu-id="b836c-113">Это означает, что домен также проверяется Службой Azure AD, так как удостоверениями Microsoft 365 управляет Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b836c-113">This means that the domain also is verified by Azure AD because Microsoft 365 identities are managed by Azure AD.</span></span> <span data-ttu-id="b836c-114">Другими словами, домен должен быть допустимым доменом Интернета (например, .com, .org, .net, .us).</span><span class="sxs-lookup"><span data-stu-id="b836c-114">In other words, the domain has to be a valid Internet domain (such as, .com, .org, .net, .us).</span></span> <span data-ttu-id="b836c-115">Если внутренняя служба доменных служб AD DS использует только домен, который не является маршрутивируемым (например, ".local"), это может не совпадать с проверенным доменом, который у вас есть для клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b836c-115">If your internal AD DS only uses a non-routable domain (for example, ".local"), this can't possibly match the verified domain you have for your Microsoft 365 tenant.</span></span> <span data-ttu-id="b836c-116">Эту проблему можно устранить, изменив основной домен в локальной AD DS или добавив один или несколько суффиксов имени upN.</span><span class="sxs-lookup"><span data-stu-id="b836c-116">You can fix this issue by either changing your primary domain in your on-premises AD DS, or by adding one or more UPN suffixes.</span></span>
  
### <a name="change-your-primary-domain"></a><span data-ttu-id="b836c-117">Изменение основного домена</span><span class="sxs-lookup"><span data-stu-id="b836c-117">Change your primary domain</span></span>

<span data-ttu-id="b836c-118">Измените основной домен на домен, проверенный в Microsoft 365, например contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b836c-118">Change your primary domain to a domain you have verified in Microsoft 365, for example, contoso.com.</span></span> <span data-ttu-id="b836c-119">Каждый пользователь с доменом contoso.local затем обновляется до contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b836c-119">Every user that has the domain contoso.local is then updated to contoso.com.</span></span> <span data-ttu-id="b836c-120">Однако это очень сложный процесс, и более простое решение описано в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="b836c-120">This is a very involved process, however, and an easier solution is described in the following section.</span></span>
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a><span data-ttu-id="b836c-121">Добавление суффиксов upN и обновление пользователей</span><span class="sxs-lookup"><span data-stu-id="b836c-121">Add UPN suffixes and update your users to them</span></span>

<span data-ttu-id="b836c-122">Чтобы решить проблему ".local", необходимо зарегистрировать новый суффикс или суффикс имени upN в доменных службах AD DS в соответствие с доменом (или доменами), проверенными в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b836c-122">You can solve the ".local" problem by registering new UPN suffix or suffixes in AD DS to match the domain (or domains) you verified in Microsoft 365.</span></span> <span data-ttu-id="b836c-123">После регистрации нового суффикса имена пользователей обновляются, заменив имя ".local" новым именем домена, например, чтобы учетная запись пользователя выглядела billa@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b836c-123">After you register the new suffix, you update the user UPNs to replace the ".local" with the new domain name, for example, so that a user account looks like billa@contoso.com.</span></span>
  
<span data-ttu-id="b836c-124">После обновления имен upns для использования проверенного домена вы можете синхронизировать свои доменные службы AD DS с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b836c-124">After you have updated the UPNs to use the verified domain, you are ready to synchronize your on-premises AD DS with Microsoft 365.</span></span>
  
#### <a name="step-1-add-the-new-upn-suffix"></a><span data-ttu-id="b836c-125">Шаг 1. Добавление нового суффикса upN\*\*</span><span class="sxs-lookup"><span data-stu-id="b836c-125">Step 1: Add the new UPN suffix\*\*</span></span>
  
1. <span data-ttu-id="b836c-126">На контроллере домена AD DS  в диспетчере серверов выберите "Tools \> **Active Directory Domains and Trusts".**</span><span class="sxs-lookup"><span data-stu-id="b836c-126">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Domains and Trusts**.</span></span>
    
    <span data-ttu-id="b836c-127">**Или, если у вас нет Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="b836c-127">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="b836c-128">Нажмите **клавиши Windows + R,** чтобы открыть диалоговое окно **"Выполнить",** а затем введите Domain.msc и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="b836c-128">Press **Windows key + R** to open the **Run** dialog, and then type in Domain.msc, and then choose **OK**.</span></span>
    
    ![Выберите "Домены и доверие Active Directory".](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. <span data-ttu-id="b836c-130">В окне "Домены и доверие **Active Directory"** щелкните правой кнопкой мыши "Домены и доверие **Active Directory"** и выберите **"Свойства".**</span><span class="sxs-lookup"><span data-stu-id="b836c-130">In the **Active Directory Domains and Trusts** window, right-click **Active Directory Domains and Trusts**, and then choose **Properties**.</span></span>
    
    ![Щелкните правой кнопкой мыши домены и доверие Active Directory и выберите "Свойства"](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. <span data-ttu-id="b836c-132">На вкладке "Суффиксы upN" в поле "Альтернативные суффиксы **upN"** введите новый суффикс или суффикс **upN,** а затем выберите "Добавить  \> **применить".**</span><span class="sxs-lookup"><span data-stu-id="b836c-132">On the **UPN Suffixes** tab, in the **Alternative UPN Suffixes** box, type your new UPN suffix or suffixes, and then choose **Add** \> **Apply**.</span></span>
    
    ![Добавление нового суффикса upN](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    <span data-ttu-id="b836c-134">После **добавления** суффиксов выберите "ОК".</span><span class="sxs-lookup"><span data-stu-id="b836c-134">Choose **OK** when you're done adding suffixes.</span></span> 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a><span data-ttu-id="b836c-135">Шаг 2. Изменение суффикса upN для существующих пользователей</span><span class="sxs-lookup"><span data-stu-id="b836c-135">Step 2: Change the UPN suffix for existing users</span></span>
  
1. <span data-ttu-id="b836c-136">На контроллере домена AD DS  в диспетчере серверов выберите "Средства active Directory — пользователи \> **и компьютеры".**</span><span class="sxs-lookup"><span data-stu-id="b836c-136">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="b836c-137">**Или, если у вас нет Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="b836c-137">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="b836c-138">Нажмите **клавиши Windows + R,** чтобы открыть диалоговое окно **"Выполнить",** а затем введите Dsa.msc и нажмите кнопку **ОК**</span><span class="sxs-lookup"><span data-stu-id="b836c-138">Press **Windows key + R** to open the **Run** dialog, and then type in Dsa.msc, and then click **OK**</span></span>
    
2. <span data-ttu-id="b836c-139">Выберите пользователя, щелкните правой кнопкой мыши и выберите **"Свойства".**</span><span class="sxs-lookup"><span data-stu-id="b836c-139">Select a user, right-click, and then choose **Properties**.</span></span>
    
3. <span data-ttu-id="b836c-140">На **вкладке "Учетная** запись" в выпадаемом списке суффиксов upN выберите новый суффикс и выберите **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="b836c-140">On the **Account** tab, in the UPN suffix drop-down list, choose the new UPN suffix, and then choose **OK**.</span></span>
    
    ![Добавление нового суффикса upN для пользователя](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. <span data-ttu-id="b836c-142">Выполните эти действия для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="b836c-142">Complete these steps for every user.</span></span>
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a><span data-ttu-id="b836c-143">Использование PowerShell для изменения суффикса upN для всех пользователей</span><span class="sxs-lookup"><span data-stu-id="b836c-143">Use PowerShell to change the UPN suffix for all of your users</span></span>

<span data-ttu-id="b836c-144">Если у вас много учетных записей пользователей для обновления, проще использовать PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b836c-144">If you have a lot of user accounts to update, it's easier to use PowerShell.</span></span> <span data-ttu-id="b836c-145">В следующем примере для изменения всех суффиксов contoso.local на contoso.com AD DS используются contoso.com [Get-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624312) и [Set-ADUser.](https://go.microsoft.com/fwlink/p/?LinkId=624313)</span><span class="sxs-lookup"><span data-stu-id="b836c-145">The following example uses the cmdlets [Get-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624312) and [Set-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624313) to change all contoso.local suffixes to contoso.com in AD DS.</span></span> 

<span data-ttu-id="b836c-146">Например, можно выполнить следующие команды PowerShell, чтобы обновить все суффиксы contoso.local до contoso.com:</span><span class="sxs-lookup"><span data-stu-id="b836c-146">For example, you could run the following PowerShell commands to update all contoso.local suffixes to contoso.com:</span></span>
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

<span data-ttu-id="b836c-147">Дополнительные Windows PowerShell active [Directory](https://go.microsoft.com/fwlink/p/?LinkId=624314) см. в Windows PowerShell AD DS.</span><span class="sxs-lookup"><span data-stu-id="b836c-147">See [Active Directory Windows PowerShell module](https://go.microsoft.com/fwlink/p/?LinkId=624314) to learn more about using Windows PowerShell in AD DS.</span></span> 

