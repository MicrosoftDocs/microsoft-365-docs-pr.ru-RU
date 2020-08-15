---
title: Администрирование почтовых ящиков Exchange Online в среде с поддержкой нескольких регионов
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
localization_priority: normal
description: Сведения о том, как администрировать параметры Multi-Geo Exchange Online в среде Microsoft 365 с помощью PowerShell.
ms.openlocfilehash: 645d48066ca02dbf3480e20ae30dc187f84293cf
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692953"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="a40c6-103">Администрирование почтовых ящиков Exchange Online в среде с поддержкой нескольких регионов</span><span class="sxs-lookup"><span data-stu-id="a40c6-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="a40c6-104">Для просмотра и настройки свойств поддержки нескольких регионов в среде Microsoft 365 требуется удаленная оболочка PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a40c6-104">Remote PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="a40c6-105">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a40c6-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="a40c6-106">Вам потребуется [модуль Microsoft Azure Active Directory PowerShell](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) версии 1.1.166.0 или более поздней в версии 1.x, чтобы просматривать свойство **PreferredDataLocation** пользовательских объектов.</span><span class="sxs-lookup"><span data-stu-id="a40c6-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="a40c6-107">Для пользовательских объектов, синхронизированных с помощью AAD Connect с AAD, нельзя изменить значение **PreferredDataLocation** непосредственно через AAD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a40c6-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="a40c6-108">Через AAD PowerShell можно изменять объекты облачных пользователей.</span><span class="sxs-lookup"><span data-stu-id="a40c6-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="a40c6-109">Сведения о подключении к Azure AD PowerShell см. в статье [Подключение к PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a40c6-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="a40c6-110">Прямое подключение к географическому расположению с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="a40c6-110">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="a40c6-111">Обычно Exchange Online PowerShell подключается к центральному географическому расположению.</span><span class="sxs-lookup"><span data-stu-id="a40c6-111">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="a40c6-112">Но вы также можете подключиться непосредственно к периферийному географическому расположению.</span><span class="sxs-lookup"><span data-stu-id="a40c6-112">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="a40c6-113">В связи с повышением производительности рекомендуется подключаться непосредственно к периферийному географическому расположению, если вы управляете пользователями только в этом расположении.</span><span class="sxs-lookup"><span data-stu-id="a40c6-113">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="a40c6-114">При подключении к определенным географическим расположениям параметр *ConnectionUri* отличается от указанного в инструкциях для обычного подключения.</span><span class="sxs-lookup"><span data-stu-id="a40c6-114">To connect to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="a40c6-115">Остальные команды и значения совпадают.</span><span class="sxs-lookup"><span data-stu-id="a40c6-115">The rest of the commands and values are the same.</span></span> <span data-ttu-id="a40c6-116">Ниже описана последовательность действий.</span><span class="sxs-lookup"><span data-stu-id="a40c6-116">The steps are:</span></span>

1. <span data-ttu-id="a40c6-117">На локальном компьютере откройте Windows PowerShell и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a40c6-117">On your local computer, open Windows PowerShell and run the following command:</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

   <span data-ttu-id="a40c6-118">В диалоговом окне **Запрос учетных данных Windows PowerShell** введите свою рабочую или учебную учетную запись и пароль, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a40c6-118">In the **Windows PowerShell Credential Request** dialog box, type your work or school account and password, and then click **OK**.</span></span>

2. <span data-ttu-id="a40c6-119">Замените `<emailaddress>` адресом электронной почты **любого** почтового ящика в целевом географическом расположении и выполните указанную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="a40c6-119">Replace `<emailaddress>` with the email address of **any** mailbox in the target geo location and run the following command.</span></span> <span data-ttu-id="a40c6-120">Ваши разрешения для почтового ящика и связи с учетными данными из шага 1 не оказывают влияния; адрес электронной почты просто сообщает Exchange Online место подключения.</span><span class="sxs-lookup"><span data-stu-id="a40c6-120">Your permissions on the mailbox and the relationship to your credentials in Step 1 are not a factor; the email address simply tells Exchange Online where to connect.</span></span>
  
   ```powershell
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell?email=<emailaddress> -Credential $UserCredential -Authentication  Basic -AllowRedirection
   ```

   <span data-ttu-id="a40c6-121">Например, если olga@contoso.onmicrosoft.com — это адрес электронной почты действительного почтового ящика в географическом расположении, к которому нужно подключиться, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a40c6-121">For example, if olga@contoso.onmicrosoft.com is the email address of a valid mailbox in the geo location where you want to connect, run the following command:</span></span>

   ```powershell
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com -Credential $UserCredential -Authentication  Basic -AllowRedirection
   ```

3. <span data-ttu-id="a40c6-122">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="a40c6-122">Run the following command:</span></span>

    ```powershell
    Import-PSSession $Session
    ```

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="a40c6-123">Просмотр доступных географических расположений, настроенных в организации Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a40c6-123">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="a40c6-124">Чтобы просмотреть список настроенных географических расположений в Microsoft 365 Multi-Geo, выполните следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a40c6-124">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="a40c6-125">Просмотр центрального географического расположения для организации Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a40c6-125">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="a40c6-126">Чтобы просмотреть центральное географическое расположение клиента, выполните следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a40c6-126">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="a40c6-127">Поиск географического расположения почтового ящика</span><span class="sxs-lookup"><span data-stu-id="a40c6-127">Find the geo location of a mailbox</span></span>

<span data-ttu-id="a40c6-128">Командлет **Get-Mailbox** в Exchange Online PowerShell отображает следующие свойства, связанные с поддержкой нескольких регионов, для почтовых ящиков:</span><span class="sxs-lookup"><span data-stu-id="a40c6-128">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="a40c6-129">**Database**. Первые 3 буквы имени базы данных соответствуют коду региона, указывающему текущее расположение почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="a40c6-129">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="a40c6-130">Для сетевых архивных почтовых ящиков следует использовать свойство **ArchiveDatabase**.</span><span class="sxs-lookup"><span data-stu-id="a40c6-130">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="a40c6-131">**MailboxRegion**. Указывает код географического расположения, установленный администратором (синхронизируется из параметра **PreferredDataLocation** в Azure AD).</span><span class="sxs-lookup"><span data-stu-id="a40c6-131">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="a40c6-132">**MailboxRegionLastUpdateTime**. Указывает время последнего обновления MailboxRegion (автоматического или ручного).</span><span class="sxs-lookup"><span data-stu-id="a40c6-132">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="a40c6-133">Чтобы просмотреть эти свойства для почтового ящика, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="a40c6-133">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="a40c6-134">Например, чтобы просмотреть сведения о географическом расположении для почтового ящика chris@contoso.onmicrosoft.com, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a40c6-134">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="a40c6-135">Выходные данные команды выглядят так:</span><span class="sxs-lookup"><span data-stu-id="a40c6-135">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="a40c6-136">Если код географического расположения в имени базы данных не совпадает со значением **маилбоксрегион** , почтовый ящик будет автоматически помещен в очередь перемещения и перемещен в географическое расположение, заданное значением **Маилбоксрегион** (Exchange Online ищет несоответствие между этими значениями свойств).</span><span class="sxs-lookup"><span data-stu-id="a40c6-136">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="a40c6-137">Перемещение существующего облачного почтового ящика в определенное географическое расположение</span><span class="sxs-lookup"><span data-stu-id="a40c6-137">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="a40c6-138">Облачный пользователь — это пользователь, не синхронизированный с клиентом посредством AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="a40c6-138">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="a40c6-139">Этот пользователь был создан непосредственно в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a40c6-139">This user was created directly in Azure AD.</span></span> <span data-ttu-id="a40c6-140">Используйте командлеты **Get-MsolUser** и **Set-MsolUser** модуля Azure AD для Windows PowerShell, чтобы просмотреть или указать географическое расположение для хранения почтового ящика облачного пользователя.</span><span class="sxs-lookup"><span data-stu-id="a40c6-140">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="a40c6-141">Чтобы просмотреть значение **PreferredDataLocation** для пользователя, используйте следующий синтаксис в Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a40c6-141">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="a40c6-142">Например, чтобы посмотреть значение **PreferredDataLocation** для пользователя michelle@contoso.onmicrosoft.com, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a40c6-142">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="a40c6-143">Чтобы изменить значение **PreferredDataLocation** для объекта облачного пользователя, используйте следующий синтаксис в Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a40c6-143">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="a40c6-144">Например, чтобы присвоить значению **PreferredDataLocation** регион Европейского Союза (EUR) для пользователя michelle@contoso.onmicrosoft.com, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a40c6-144">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
> - <span data-ttu-id="a40c6-145">Как упоминалось ранее, эту процедуру нельзя использовать для синхронизированных объектов пользователей из локальной службы Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a40c6-145">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="a40c6-146">Нужно изменить значение **PreferredDataLocation** в Active Directory и синхронизировать его с помощью AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="a40c6-146">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="a40c6-147">Дополнительные сведения см. в статье [Синхронизация Azure Active Directory Connect: настройка предпочтительного расположения данных для ресурсов Microsoft 365](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span><span class="sxs-lookup"><span data-stu-id="a40c6-147">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
> 
> - <span data-ttu-id="a40c6-148">Продолжительность перемещения почтового ящика в новое географическое расположение зависит от нескольких факторов:</span><span class="sxs-lookup"><span data-stu-id="a40c6-148">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
> 
>   - <span data-ttu-id="a40c6-149">Размер и тип почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="a40c6-149">The size and type of mailbox.</span></span>
> 
>   - <span data-ttu-id="a40c6-150">Число перемещаемых почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="a40c6-150">The number of mailboxes being moved.</span></span>
> 
>   - <span data-ttu-id="a40c6-151">Доступность ресурсов перемещения.</span><span class="sxs-lookup"><span data-stu-id="a40c6-151">The availability of move resources.</span></span>

### <a name="move-disabled-mailboxes-that-are-on-litigation-hold"></a><span data-ttu-id="a40c6-152">Перемещение отключенных почтовых ящиков, находящихся на судебном удержании</span><span class="sxs-lookup"><span data-stu-id="a40c6-152">Move disabled mailboxes that are on Litigation Hold</span></span>

<span data-ttu-id="a40c6-153">Отключенные почтовые ящики на судебном удержании, сохраненные для целей обнаружения электронных данных, невозможно переместить путем изменения их значения **PreferredDataLocation** в отключенном состоянии.</span><span class="sxs-lookup"><span data-stu-id="a40c6-153">Disabled mailboxes on Litigation Hold that are preserved for eDiscovery purposes cannot be moved by changing their **PreferredDataLocation** value in their disabled state.</span></span> <span data-ttu-id="a40c6-154">Чтобы переместить отключенный почтовый ящик на судебном удержании:</span><span class="sxs-lookup"><span data-stu-id="a40c6-154">To move a disabled mailbox on litigation hold:</span></span>

1. <span data-ttu-id="a40c6-155">Временно назначьте лицензию для почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="a40c6-155">Temporarily assign a license to the mailbox.</span></span>

2. <span data-ttu-id="a40c6-156">Измените значение **PreferredDataLocation**.</span><span class="sxs-lookup"><span data-stu-id="a40c6-156">Change the **PreferredDataLocation**.</span></span>

3. <span data-ttu-id="a40c6-157">Удалите лицензию из почтового ящика после его перемещения в выбранное географическое расположение, чтобы вернуть его в отключенное состояние.</span><span class="sxs-lookup"><span data-stu-id="a40c6-157">Remove the license from the mailbox after it has been moved to the selected geo location to put it back into the disabled state.</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="a40c6-158">Создание новых облачных почтовых ящиков в определенном географическом расположении</span><span class="sxs-lookup"><span data-stu-id="a40c6-158">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="a40c6-159">Чтобы создать почтовый ящик в определенном географическом расположении, нужно выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="a40c6-159">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="a40c6-160">Настройте значение **PreferredDataLocation**, как описано в предыдущем разделе, *перед* созданием почтового ящика в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a40c6-160">Configure the **PreferredDataLocation** value as described in the previous section *before* the mailbox is created in Exchange Online.</span></span> <span data-ttu-id="a40c6-161">Например, настройте значение **PreferredDataLocation** для пользователя перед назначением лицензии.</span><span class="sxs-lookup"><span data-stu-id="a40c6-161">For example, configure the **PreferredDataLocation** value on a user before assigning a license.</span></span>

- <span data-ttu-id="a40c6-162">Назначьте лицензию одновременно с настройкой значения **PreferredDataLocation**.</span><span class="sxs-lookup"><span data-stu-id="a40c6-162">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="a40c6-163">Чтобы создать облачного лицензированного пользователя (не синхронизированного с помощью AAD Connect) в определенном географическом расположении, используйте следующий синтаксис в Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a40c6-163">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="a40c6-164">В этом примере создается новая учетная запись пользователя Elizabeth Brunner со следующими значениями:</span><span class="sxs-lookup"><span data-stu-id="a40c6-164">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="a40c6-165">Имя участника-пользователя: ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="a40c6-165">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>

- <span data-ttu-id="a40c6-166">Имя: Elizabeth</span><span class="sxs-lookup"><span data-stu-id="a40c6-166">First name: Elizabeth</span></span>

- <span data-ttu-id="a40c6-167">Фамилия: Brunner</span><span class="sxs-lookup"><span data-stu-id="a40c6-167">Last name: Brunner</span></span>

- <span data-ttu-id="a40c6-168">Отображаемое имя: Elizabeth Brunner</span><span class="sxs-lookup"><span data-stu-id="a40c6-168">Display name: Elizabeth Brunner</span></span>

- <span data-ttu-id="a40c6-169">Пароль: создается случайным образом и отображается в результатах команды (так как не используется параметр *Password*)</span><span class="sxs-lookup"><span data-stu-id="a40c6-169">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>

- <span data-ttu-id="a40c6-170">Лицензия: `contoso:ENTERPRISEPREMIUM` (E5)</span><span class="sxs-lookup"><span data-stu-id="a40c6-170">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>

- <span data-ttu-id="a40c6-171">Расположение: Австралия (AUS)</span><span class="sxs-lookup"><span data-stu-id="a40c6-171">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="a40c6-172">Дополнительные сведения о создании учетных записей пользователей и поиске значений LicenseAssignment в Azure AD PowerShell см. в статьях [Создание учетных записей пользователей с помощью PowerShell](create-user-accounts-with-microsoft-365-powershell.md) и [Просмотр лицензий и служб с помощью PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a40c6-172">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a40c6-173">Если вы используете Exchange Online PowerShell, чтобы включить почтовый ящик, и вам нужно создать почтовый ящик непосредственно в географическом расположении, указанном в параметре **PreferredDataLocation**, необходимо использовать командлет Exchange Online, например, **Enable-Mailbox** или **New-Mailbox**, прямо в облачной службе.</span><span class="sxs-lookup"><span data-stu-id="a40c6-173">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="a40c6-174">Если вы используете командлет **Enable-RemoteMailbox** в локальной среде Exchange PowerShell, почтовый ящик будет создан в центральном географическом расположении.</span><span class="sxs-lookup"><span data-stu-id="a40c6-174">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="a40c6-175">Перенос существующих локальных почтовых ящиков в определенное географическое расположение</span><span class="sxs-lookup"><span data-stu-id="a40c6-175">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="a40c6-176">Можно использовать стандартные средства и процедуры переноса для перемещения почтового ящика из локальной организации Exchange в Exchange Online, включая [информационную панель миграции в Центре администрирования Exchange](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331) и командлет [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a40c6-176">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="a40c6-177">Сначала нужно подтвердить, что объект пользователя существует для каждого переносимого почтового ящика, и проверить правильность значения **PreferredDataLocation**, настроенного в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a40c6-177">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="a40c6-178">Средства переноса учитывают значение **PreferredDataLocation** и переносят почтовые ящики непосредственно в указанное географическое расположение.</span><span class="sxs-lookup"><span data-stu-id="a40c6-178">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="a40c6-179">Или можно использовать указанные ниже действия для переноса почтовых ящиков непосредственно в определенное географическое расположение с помощью командлета [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a40c6-179">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="a40c6-180">Убедитесь в наличии объекта пользователя для каждого переносимого почтового ящика и в установке нужного значения **PreferredDataLocation** в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a40c6-180">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="a40c6-181">Значение **PreferredDataLocation** синхронизируется с атрибутом **MailboxRegion** соответствующего объекта пользователя почты в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a40c6-181">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="a40c6-182">Напрямую подключитесь к определенному периферийному географическому расположению, следуя инструкциям по подключению, указанным выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="a40c6-182">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="a40c6-183">В Exchange Online PowerShell сохраните учетные данные локального администратора, использующиеся для выполнения переноса почтового ящика, в переменной, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a40c6-183">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="a40c6-184">В Exchange Online PowerShell, создайте новый командлет **New-MoveRequest**, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a40c6-184">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="a40c6-185">Повторите шаг 4 для каждого почтового ящика, требующего переноса из локальной среды Exchange в периферийное географическое расположение, к которому вы в настоящее время подключены.</span><span class="sxs-lookup"><span data-stu-id="a40c6-185">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="a40c6-186">Если нужно перенести дополнительные почтовые ящики в другое периферийное географическое расположение, повторите шаги 2–4 для каждого определенного периферийного расположения.</span><span class="sxs-lookup"><span data-stu-id="a40c6-186">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="a40c6-187">Отчеты об использовании нескольких регионов</span><span class="sxs-lookup"><span data-stu-id="a40c6-187">Multi-geo reporting</span></span>

<span data-ttu-id="a40c6-188">**Отчеты об использовании нескольких регионов** в Центре администрирования Microsoft 365 отображают число пользователей по географическим расположениям.</span><span class="sxs-lookup"><span data-stu-id="a40c6-188">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="a40c6-189">Отчет отображает распределение пользователей в текущем месяце и представляет ретроспективные данные за последние 6 месяцев.</span><span class="sxs-lookup"><span data-stu-id="a40c6-189">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="a40c6-190">См. также</span><span class="sxs-lookup"><span data-stu-id="a40c6-190">See also</span></span>

[<span data-ttu-id="a40c6-191">Управление Microsoft 365 и Exchange Online с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a40c6-191">Managing Microsoft 365 and Exchange Online with Windows PowerShell</span></span>](https://support.office.com//article/06a743bb-ceb6-49a9-a61d-db4ffdf54fa6)
