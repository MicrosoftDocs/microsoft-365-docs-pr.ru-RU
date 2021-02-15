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
description: Узнайте, как администрировать параметры Exchange Online с несколькими геообъегами в среде Microsoft 365 с помощью PowerShell.
ms.openlocfilehash: 63eb1957611fd57e216012435188a6ddd1b232d3
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2020
ms.locfileid: "49552011"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="78eb2-103">Администрирование почтовых ящиков Exchange Online в среде с поддержкой нескольких регионов</span><span class="sxs-lookup"><span data-stu-id="78eb2-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="78eb2-104">Exchange Online PowerShell необходим для просмотра и настройки свойств нескольких геообзоров в среде Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78eb2-104">Exchange Online PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="78eb2-105">Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="78eb2-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="78eb2-106">Вам потребуется [модуль Microsoft Azure Active Directory PowerShell](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) версии 1.1.166.0 или более поздней в версии 1.x, чтобы просматривать свойство **PreferredDataLocation** пользовательских объектов.</span><span class="sxs-lookup"><span data-stu-id="78eb2-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="78eb2-107">Для пользовательских объектов, синхронизированных с помощью AAD Connect с AAD, нельзя изменить значение **PreferredDataLocation** непосредственно через AAD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78eb2-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="78eb2-108">Через AAD PowerShell можно изменять объекты облачных пользователей.</span><span class="sxs-lookup"><span data-stu-id="78eb2-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="78eb2-109">Сведения о подключении к Azure AD PowerShell см. в статье [Подключение к PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="78eb2-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="78eb2-110">Прямое подключение к географическому расположению с помощью Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="78eb2-110">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="78eb2-111">Обычно Exchange Online PowerShell подключается к центральному географическому расположению.</span><span class="sxs-lookup"><span data-stu-id="78eb2-111">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="78eb2-112">Но вы также можете подключиться непосредственно к периферийному географическому расположению.</span><span class="sxs-lookup"><span data-stu-id="78eb2-112">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="78eb2-113">В связи с повышением производительности рекомендуется подключаться непосредственно к периферийному географическому расположению, если вы управляете пользователями только в этом расположении.</span><span class="sxs-lookup"><span data-stu-id="78eb2-113">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="78eb2-114">Требования для установки и использования модуля EXO V2 описаны в статье [Установка и обслуживание модуля EXO V2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span><span class="sxs-lookup"><span data-stu-id="78eb2-114">The requirements for installing and using the EXO V2 module are described in [Install and maintain the EXO V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

<span data-ttu-id="78eb2-115">Чтобы подключить Exchange Online PowerShell к определенному географическому расположению, параметр *ConnectionUri* отличается от инструкций по обычному подключению.</span><span class="sxs-lookup"><span data-stu-id="78eb2-115">To connect Exchange Online PowerShell to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="78eb2-116">Остальные команды и значения совпадают.</span><span class="sxs-lookup"><span data-stu-id="78eb2-116">The rest of the commands and values are the same.</span></span>

<span data-ttu-id="78eb2-117">В частности, необходимо добавить значение `?email=<emailaddress>` в конец _значения ConnectionUri._</span><span class="sxs-lookup"><span data-stu-id="78eb2-117">Specifically, you need to add the `?email=<emailaddress>` value to end of the _ConnectionUri_ value.</span></span> <span data-ttu-id="78eb2-118">`<emailaddress>` — это адрес электронной почты **любого почтового** ящика в целевом географическом расположении.</span><span class="sxs-lookup"><span data-stu-id="78eb2-118">`<emailaddress>` is the email address of **any** mailbox in the target geo location.</span></span> <span data-ttu-id="78eb2-119">Ваши разрешения на доступ к этому почтовому ящику или связь с учетными данными не являются фактором; Адрес электронной почты просто сообщает Exchange Online PowerShell, где необходимо подключиться.</span><span class="sxs-lookup"><span data-stu-id="78eb2-119">Your permissions to that mailbox or the relationship to your credentials are not a factor; the email address simply tells Exchange Online PowerShell where to connect.</span></span>

<span data-ttu-id="78eb2-120">Как правило, пользователям Microsoft 365 или Microsoft 365 GCC не нужно использовать параметр _ConnectionUri_ для подключения к Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78eb2-120">Microsoft 365 or Microsoft 365 GCC customers typically don't need to use the _ConnectionUri_ parameter to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="78eb2-121">Но для подключения к определенному географическому расположению необходимо использовать параметр _ConnectionUri,_ чтобы использовать `?email=<emailaddress>` его в значении.</span><span class="sxs-lookup"><span data-stu-id="78eb2-121">But, to connect to a specific geo location, you do need to use _ConnectionUri_ parameter so you can use `?email=<emailaddress>` in the value.</span></span>

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a><span data-ttu-id="78eb2-122">Подключение к географическому расположению в Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="78eb2-122">Connect to a geo location in Exchange Online PowerShell</span></span>

<span data-ttu-id="78eb2-123">Следующие инструкции по подключению работают для учетных записей, которые настроены или не настроены для многофакторной проверки подлинности (MFA).</span><span class="sxs-lookup"><span data-stu-id="78eb2-123">The following connection instructions work for accounts that are or aren't configured for multi-factor authentication (MFA).</span></span>

1. <span data-ttu-id="78eb2-124">В окне Windows PowerShell загрузите модуль EXO V2, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="78eb2-124">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="78eb2-125">В следующем примере admin@contoso.onmicrosoft.com учетной записью администратора, а в целевом географическом расположении находится почтовый olga@contoso.onmicrosoft.com почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="78eb2-125">In the following example, admin@contoso.onmicrosoft.com is the admin account, and the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. <span data-ttu-id="78eb2-126">Введите пароль для admin@contoso.onmicrosoft.com в от всей подсказке.</span><span class="sxs-lookup"><span data-stu-id="78eb2-126">Enter the password for the admin@contoso.onmicrosoft.com in the prompt that appears.</span></span> <span data-ttu-id="78eb2-127">Если учетная запись настроена для MFA, необходимо также ввести код безопасности.</span><span class="sxs-lookup"><span data-stu-id="78eb2-127">If the account is configured for MFA, you also need to enter the security code.</span></span>

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="78eb2-128">Просмотр доступных географических расположений, настроенных в организации Exchange Online</span><span class="sxs-lookup"><span data-stu-id="78eb2-128">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="78eb2-129">Чтобы просмотреть список настроенных географических расположений в Microsoft 365 Multi-Geo, выполните следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="78eb2-129">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="78eb2-130">Просмотр центрального географического расположения для организации Exchange Online</span><span class="sxs-lookup"><span data-stu-id="78eb2-130">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="78eb2-131">Чтобы просмотреть центральное географическое расположение клиента, выполните следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="78eb2-131">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="78eb2-132">Поиск географического расположения почтового ящика</span><span class="sxs-lookup"><span data-stu-id="78eb2-132">Find the geo location of a mailbox</span></span>

<span data-ttu-id="78eb2-133">Командлет **Get-Mailbox** в Exchange Online PowerShell отображает следующие свойства, связанные с поддержкой нескольких регионов, для почтовых ящиков:</span><span class="sxs-lookup"><span data-stu-id="78eb2-133">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="78eb2-134">**Database**. Первые 3 буквы имени базы данных соответствуют коду региона, указывающему текущее расположение почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="78eb2-134">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="78eb2-135">Для сетевых архивных почтовых ящиков следует использовать свойство **ArchiveDatabase**.</span><span class="sxs-lookup"><span data-stu-id="78eb2-135">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="78eb2-136">**MailboxRegion**. Указывает код географического расположения, установленный администратором (синхронизируется из параметра **PreferredDataLocation** в Azure AD).</span><span class="sxs-lookup"><span data-stu-id="78eb2-136">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="78eb2-137">**MailboxRegionLastUpdateTime**. Указывает время последнего обновления MailboxRegion (автоматического или ручного).</span><span class="sxs-lookup"><span data-stu-id="78eb2-137">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="78eb2-138">Чтобы просмотреть эти свойства для почтового ящика, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="78eb2-138">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="78eb2-139">Например, чтобы просмотреть сведения о географическом расположении для почтового ящика chris@contoso.onmicrosoft.com, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="78eb2-139">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="78eb2-140">Выходные данные команды выглядят так:</span><span class="sxs-lookup"><span data-stu-id="78eb2-140">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="78eb2-141">Если код географического расположения в имени базы данных не соответствует значению **MailboxRegion,** почтовый ящик будет автоматически помещаться в очередь перемещения и перемещен в географическое расположение, указанное значением **MailboxRegion (Exchange** Online ищет несоответствие между этими значениями свойств).</span><span class="sxs-lookup"><span data-stu-id="78eb2-141">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="78eb2-142">Перемещение существующего облачного почтового ящика в определенное географическое расположение</span><span class="sxs-lookup"><span data-stu-id="78eb2-142">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="78eb2-143">Облачный пользователь — это пользователь, не синхронизированный с клиентом посредством AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="78eb2-143">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="78eb2-144">Этот пользователь был создан непосредственно в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="78eb2-144">This user was created directly in Azure AD.</span></span> <span data-ttu-id="78eb2-145">Используйте командлеты **Get-MsolUser** и **Set-MsolUser** модуля Azure AD для Windows PowerShell, чтобы просмотреть или указать географическое расположение для хранения почтового ящика облачного пользователя.</span><span class="sxs-lookup"><span data-stu-id="78eb2-145">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="78eb2-146">Чтобы просмотреть значение **PreferredDataLocation** для пользователя, используйте следующий синтаксис в Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="78eb2-146">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="78eb2-147">Например, чтобы посмотреть значение **PreferredDataLocation** для пользователя michelle@contoso.onmicrosoft.com, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="78eb2-147">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="78eb2-148">Чтобы изменить значение **PreferredDataLocation** для объекта облачного пользователя, используйте следующий синтаксис в Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="78eb2-148">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="78eb2-149">Например, чтобы присвоить значению **PreferredDataLocation** регион Европейского Союза (EUR) для пользователя michelle@contoso.onmicrosoft.com, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="78eb2-149">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - <span data-ttu-id="78eb2-150">Как упоминалось ранее, эту процедуру нельзя использовать для синхронизированных объектов пользователей из локальной службы Active Directory.</span><span class="sxs-lookup"><span data-stu-id="78eb2-150">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="78eb2-151">Нужно изменить значение **PreferredDataLocation** в Active Directory и синхронизировать его с помощью AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="78eb2-151">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="78eb2-152">Дополнительные сведения см. в статье [Синхронизация Azure Active Directory Connect: настройка предпочтительного расположения данных для ресурсов Microsoft 365](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span><span class="sxs-lookup"><span data-stu-id="78eb2-152">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
>
> - <span data-ttu-id="78eb2-153">Продолжительность перемещения почтового ящика в новое географическое расположение зависит от нескольких факторов:</span><span class="sxs-lookup"><span data-stu-id="78eb2-153">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
>
>   - <span data-ttu-id="78eb2-154">Размер и тип почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="78eb2-154">The size and type of mailbox.</span></span>
>   - <span data-ttu-id="78eb2-155">Число перемещаемых почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="78eb2-155">The number of mailboxes being moved.</span></span>
>   - <span data-ttu-id="78eb2-156">Доступность ресурсов перемещения.</span><span class="sxs-lookup"><span data-stu-id="78eb2-156">The availability of move resources.</span></span>

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a><span data-ttu-id="78eb2-157">Перемещение неактивного почтового ящика в определенный геообназ</span><span class="sxs-lookup"><span data-stu-id="78eb2-157">Move an inactive mailbox to a specific geo</span></span>

<span data-ttu-id="78eb2-158">Неактивные почтовые ящики, которые сохраняются в целях соответствия требованиям (например, почтовые ящики, для судебного удержания), нельзя перемещать, изменяя их значение **PreferredDataLocation.**</span><span class="sxs-lookup"><span data-stu-id="78eb2-158">You can't move inactive mailboxes that are preserved for compliance purposes (for example, mailboxes on Litigation Hold) by changing their **PreferredDataLocation** value.</span></span> <span data-ttu-id="78eb2-159">Чтобы переместить неактивный почтовый ящик в другой геообназ, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="78eb2-159">To move an inactive mailbox to a different geo, do the following steps:</span></span>

1. <span data-ttu-id="78eb2-160">Восстановите неактивный почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="78eb2-160">Recover the inactive mailbox.</span></span> <span data-ttu-id="78eb2-161">Инструкции см. в инструкциях [по восстановлению неактивного почтового ящика.](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox)</span><span class="sxs-lookup"><span data-stu-id="78eb2-161">For instructions, see [Recover an inactive mailbox](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox).</span></span>

2. <span data-ttu-id="78eb2-162">Запретить помощнику по работе с управляемыми папками обрабатывать восстановленный почтовый ящик, заменяя имя, псевдоним, учетную запись или адрес электронной почты почтового ящика и выступая в \<MailboxIdentity\> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="78eb2-162">Prevent the Managed Folder Assistant from processing the recovered mailbox by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. <span data-ttu-id="78eb2-163">**Назначьте лицензию Exchange Online (план 2)** для восстановленного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="78eb2-163">Assign an **Exchange Online Plan 2** license to the recovered mailbox.</span></span> <span data-ttu-id="78eb2-164">Это необходимо для того, чтобы вернуть почтовый ящик на удержание для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="78eb2-164">This step is required to place the mailbox back on Litigation Hold.</span></span> <span data-ttu-id="78eb2-165">Инструкции см. в [подсети "Назначение лицензий пользователям".](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="78eb2-165">For instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

4. <span data-ttu-id="78eb2-166">Настройте значение **PreferredDataLocation** для почтового ящика, как описано в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="78eb2-166">Configure the **PreferredDataLocation** value on the mailbox as described in the previous section.</span></span>

5. <span data-ttu-id="78eb2-167">После подтверждения того, что почтовый ящик перемещен в новое географическое расположение, поместите восстановленный почтовый ящик на удержание для судебного разбирательства.</span><span class="sxs-lookup"><span data-stu-id="78eb2-167">After you've confirmed that the mailbox has moved to the new geo location, place the recovered mailbox back on Litigation Hold.</span></span> <span data-ttu-id="78eb2-168">Инструкции см. в инструкциях по удержанию [почтового ящика для судебного разбирательства.](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold)</span><span class="sxs-lookup"><span data-stu-id="78eb2-168">For instructions, see [Place a mailbox on Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold).</span></span>

6. <span data-ttu-id="78eb2-169">После проверки на месте удержания для судебного разбирательства позвольте помощнику для управляемых папок повторно обработать почтовый ящик, заменив имя, псевдоним, учетную запись или адрес электронной почты почтового ящика и выступая в \<MailboxIdentity\> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)следующую команду:</span><span class="sxs-lookup"><span data-stu-id="78eb2-169">After verifying that the Litigation Hold is in place, allow the Managed Folder Assistant to process the mailbox again by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. <span data-ttu-id="78eb2-170">Снова деактивировать почтовый ящик, удалив учетную запись пользователя, связанную с почтовым ящиком.</span><span class="sxs-lookup"><span data-stu-id="78eb2-170">Make the mailbox inactive again by removing the user account that's associated with the mailbox.</span></span> <span data-ttu-id="78eb2-171">Инструкции см. в [инструкциях по удалению пользователя из организации.](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="78eb2-171">For instructions, see [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user).</span></span> <span data-ttu-id="78eb2-172">На этом этапе также будет высвобрована лицензия на Exchange Online (план 2) для других видов использования.</span><span class="sxs-lookup"><span data-stu-id="78eb2-172">This step also releases the Exchange Online Plan 2 license for other uses.</span></span>

<span data-ttu-id="78eb2-173">**Примечание.** Перемещение неактивного почтового ящика в другое географическое расположение может повлиять на результаты поиска контента или возможность поиска в почтовом ящике из прежнего географического расположения.</span><span class="sxs-lookup"><span data-stu-id="78eb2-173">**Note**: When you move an inactive mailbox to a different geo location, you might affect content search results or the ability to search the mailbox from the former geo location.</span></span> <span data-ttu-id="78eb2-174">Дополнительные сведения [см. в поиске и экспорте контента в средах с несколькими географическими средами.](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments)</span><span class="sxs-lookup"><span data-stu-id="78eb2-174">For more information, see [Searching and exporting content in Multi-Geo environments](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments).</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="78eb2-175">Создание новых облачных почтовых ящиков в определенном географическом расположении</span><span class="sxs-lookup"><span data-stu-id="78eb2-175">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="78eb2-176">Чтобы создать почтовый ящик в определенном географическом расположении, нужно выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="78eb2-176">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="78eb2-177">Настройте значение **PreferredDataLocation,** как описано в предыдущем разделе, перед созданием  почтового ящика в Exchange Online переместите существующий облачный почтовый ящик в определенный раздел географического расположения. [](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location)</span><span class="sxs-lookup"><span data-stu-id="78eb2-177">Configure the **PreferredDataLocation** value as described in the previous [Move an existing cloud-only mailbox to a specific geo location](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) section *before* you create the mailbox in Exchange Online.</span></span> <span data-ttu-id="78eb2-178">Например, настройте значение **PreferredDataLocation** для пользователя перед назначением лицензии.</span><span class="sxs-lookup"><span data-stu-id="78eb2-178">For example, configure the **PreferredDataLocation** value on a user before you assign a license.</span></span>

- <span data-ttu-id="78eb2-179">Назначьте лицензию одновременно с настройкой значения **PreferredDataLocation**.</span><span class="sxs-lookup"><span data-stu-id="78eb2-179">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="78eb2-180">Чтобы создать облачного лицензированного пользователя (не синхронизированного с помощью AAD Connect) в определенном географическом расположении, используйте следующий синтаксис в Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="78eb2-180">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="78eb2-181">В этом примере создается новая учетная запись пользователя Elizabeth Brunner со следующими значениями:</span><span class="sxs-lookup"><span data-stu-id="78eb2-181">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="78eb2-182">Имя участника-пользователя: ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="78eb2-182">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>
- <span data-ttu-id="78eb2-183">Имя: Elizabeth</span><span class="sxs-lookup"><span data-stu-id="78eb2-183">First name: Elizabeth</span></span>
- <span data-ttu-id="78eb2-184">Фамилия: Brunner</span><span class="sxs-lookup"><span data-stu-id="78eb2-184">Last name: Brunner</span></span>
- <span data-ttu-id="78eb2-185">Отображаемое имя: Elizabeth Brunner</span><span class="sxs-lookup"><span data-stu-id="78eb2-185">Display name: Elizabeth Brunner</span></span>
- <span data-ttu-id="78eb2-186">Пароль: создается случайным образом и отображается в результатах команды (так как не используется параметр *Password*)</span><span class="sxs-lookup"><span data-stu-id="78eb2-186">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>
- <span data-ttu-id="78eb2-187">Лицензия: `contoso:ENTERPRISEPREMIUM` (E5)</span><span class="sxs-lookup"><span data-stu-id="78eb2-187">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>
- <span data-ttu-id="78eb2-188">Расположение: Австралия (AUS)</span><span class="sxs-lookup"><span data-stu-id="78eb2-188">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="78eb2-189">Дополнительные сведения о создании учетных записей пользователей и поиске значений LicenseAssignment в Azure AD PowerShell см. в статьях [Создание учетных записей пользователей с помощью PowerShell](create-user-accounts-with-microsoft-365-powershell.md) и [Просмотр лицензий и служб с помощью PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="78eb2-189">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="78eb2-190">Если вы используете Exchange Online PowerShell, чтобы включить почтовый ящик, и вам нужно создать почтовый ящик непосредственно в географическом расположении, указанном в параметре **PreferredDataLocation**, необходимо использовать командлет Exchange Online, например, **Enable-Mailbox** или **New-Mailbox**, прямо в облачной службе.</span><span class="sxs-lookup"><span data-stu-id="78eb2-190">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="78eb2-191">Если вы используете командлет **Enable-RemoteMailbox** в локальной среде Exchange PowerShell, почтовый ящик будет создан в центральном географическом расположении.</span><span class="sxs-lookup"><span data-stu-id="78eb2-191">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="78eb2-192">Перенос существующих локальных почтовых ящиков в определенное географическое расположение</span><span class="sxs-lookup"><span data-stu-id="78eb2-192">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="78eb2-193">Можно использовать стандартные средства и процедуры переноса для перемещения почтового ящика из локальной организации Exchange в Exchange Online, включая [информационную панель миграции в Центре администрирования Exchange](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331) и командлет [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78eb2-193">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="78eb2-194">Сначала нужно подтвердить, что объект пользователя существует для каждого переносимого почтового ящика, и проверить правильность значения **PreferredDataLocation**, настроенного в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="78eb2-194">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="78eb2-195">Средства переноса учитывают значение **PreferredDataLocation** и переносят почтовые ящики непосредственно в указанное географическое расположение.</span><span class="sxs-lookup"><span data-stu-id="78eb2-195">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="78eb2-196">Или можно использовать указанные ниже действия для переноса почтовых ящиков непосредственно в определенное географическое расположение с помощью командлета [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) в Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78eb2-196">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="78eb2-197">Убедитесь в наличии объекта пользователя для каждого переносимого почтового ящика и в установке нужного значения **PreferredDataLocation** в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="78eb2-197">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="78eb2-198">Значение **PreferredDataLocation** синхронизируется с атрибутом **MailboxRegion** соответствующего объекта пользователя почты в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="78eb2-198">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="78eb2-199">Напрямую подключитесь к определенному периферийному географическому расположению, следуя инструкциям по подключению, указанным выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="78eb2-199">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="78eb2-200">В Exchange Online PowerShell сохраните учетные данные локального администратора, использующиеся для выполнения переноса почтового ящика, в переменной, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="78eb2-200">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="78eb2-201">В Exchange Online PowerShell, создайте новый командлет **New-MoveRequest**, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="78eb2-201">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="78eb2-202">Повторите шаг 4 для каждого почтового ящика, требующего переноса из локальной среды Exchange в периферийное географическое расположение, к которому вы в настоящее время подключены.</span><span class="sxs-lookup"><span data-stu-id="78eb2-202">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="78eb2-203">Если нужно перенести дополнительные почтовые ящики в другое периферийное географическое расположение, повторите шаги 2–4 для каждого определенного периферийного расположения.</span><span class="sxs-lookup"><span data-stu-id="78eb2-203">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="78eb2-204">Отчеты об использовании нескольких регионов</span><span class="sxs-lookup"><span data-stu-id="78eb2-204">Multi-geo reporting</span></span>

<span data-ttu-id="78eb2-205">**Отчеты об использовании нескольких регионов** в Центре администрирования Microsoft 365 отображают число пользователей по географическим расположениям.</span><span class="sxs-lookup"><span data-stu-id="78eb2-205">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="78eb2-206">Отчет отображает распределение пользователей в текущем месяце и представляет ретроспективные данные за последние 6 месяцев.</span><span class="sxs-lookup"><span data-stu-id="78eb2-206">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="78eb2-207">См. также</span><span class="sxs-lookup"><span data-stu-id="78eb2-207">See also</span></span>

[<span data-ttu-id="78eb2-208">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="78eb2-208">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
