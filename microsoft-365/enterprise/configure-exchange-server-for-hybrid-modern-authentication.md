---
title: Как настроить локальное развертывание Exchange Server для использования гибридной современной проверки подлинности
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Узнайте, как настроить локальное Exchange Server для использования гибридной современной проверки подлинности (HMA), предлагая более безопасную проверку подлинности и авторизацию пользователей.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f52b7c011b717c5dcb91270ab0a7dd2015131c0e
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694453"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="768f3-103">Как настроить локальное развертывание Exchange Server для использования гибридной современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="768f3-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="768f3-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="768f3-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="768f3-105">Гибридная современная проверка подлинности (HMA) — это метод управления удостоверениями, который обеспечивает более безопасную проверку подлинности и авторизацию пользователей и доступен для Exchange локального гибридного развертывания.</span><span class="sxs-lookup"><span data-stu-id="768f3-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="768f3-106">FYI</span><span class="sxs-lookup"><span data-stu-id="768f3-106">FYI</span></span>

<span data-ttu-id="768f3-107">Перед началом работы я вызываю:</span><span class="sxs-lookup"><span data-stu-id="768f3-107">Before we begin, I call:</span></span>

- <span data-ttu-id="768f3-108">Гибридная современная \> проверка подлинности HMA</span><span class="sxs-lookup"><span data-stu-id="768f3-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="768f3-109">Exchange \> локальной EXCH</span><span class="sxs-lookup"><span data-stu-id="768f3-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="768f3-110">\>Exchange Online EXO</span><span class="sxs-lookup"><span data-stu-id="768f3-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="768f3-111">Кроме того, если на рисунке в этой статье имеется объект с "серым" или "замутненым", это означает, что элемент, показанный в сером цвете, не входит в конфигурацию, определенную *HMA.*</span><span class="sxs-lookup"><span data-stu-id="768f3-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="768f3-112">Включение гибридной современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="768f3-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="768f3-113">Включение HMA означает:</span><span class="sxs-lookup"><span data-stu-id="768f3-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="768f3-114">Убедитесь, что перед началом работы вы встретите предварительные окрики.</span><span class="sxs-lookup"><span data-stu-id="768f3-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="768f3-115">Поскольку  для Skype для бизнеса и Exchange часто используется множество необходимых условий, обзор гибридной современной проверки подлинности и необходимые условия для его использования на локальном Skype для бизнеса [и Exchange серверах](hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="768f3-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="768f3-116">Сделайте это, прежде чем приступить к любым шагам в этой статье.</span><span class="sxs-lookup"><span data-stu-id="768f3-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="768f3-117">Добавление URL-адресов веб-служб локальной службы в качестве имен основных служб **(SPNs)** в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="768f3-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span> <span data-ttu-id="768f3-118">В том случае, если EXCH гибридна с несколькими клиентами, эти URL-адреса веб-службы локального уровня должны быть добавлены в качестве URL-адресов в Azure AD всех клиентов, которые находятся в гибридной связи с EXCH.</span><span class="sxs-lookup"><span data-stu-id="768f3-118">In case EXCH is in hybrid with **multiple tenants**, these on-premises web service URLs must be added as SPNs in the Azure AD of all the tenants which are in hybrid with EXCH.</span></span>

1. <span data-ttu-id="768f3-119">Обеспечение включения всех виртуальных каталогов для HMA</span><span class="sxs-lookup"><span data-stu-id="768f3-119">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="768f3-120">Проверка объекта Auth Server EvoSTS</span><span class="sxs-lookup"><span data-stu-id="768f3-120">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="768f3-121">Включение HMA в EXCH.</span><span class="sxs-lookup"><span data-stu-id="768f3-121">Enabling HMA in EXCH.</span></span>

> [!NOTE]
> <span data-ttu-id="768f3-122">Поддерживает ли ваша версия Office ma?</span><span class="sxs-lookup"><span data-stu-id="768f3-122">Does your version of Office support MA?</span></span> <span data-ttu-id="768f3-123">Узнайте, как работает современная [проверка подлинности для Office 2013 и Office 2016 г.](modern-auth-for-office-2013-and-2016.md)</span><span class="sxs-lookup"><span data-stu-id="768f3-123">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>


## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="768f3-124">Убедитесь, что вы соответствуете всем необходимым требованиям</span><span class="sxs-lookup"><span data-stu-id="768f3-124">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="768f3-125">Поскольку многие необходимые условия являются общими как для Skype для бизнеса, так и для Exchange, просмотрите обзор гибридной современной проверки подлинности и необходимые условия для ее использования на локальном Skype для бизнеса [и Exchange серверах](hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="768f3-125">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="768f3-126">Сделайте  *это,*  прежде чем приступить к любым шагам в этой статье.</span><span class="sxs-lookup"><span data-stu-id="768f3-126">Do this  *before*  you begin any of the steps in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="768f3-127">Outlook Web App и Exchange панель управления не работает с гибридной современной проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="768f3-127">Outlook Web App and Exchange Control Panel does not work with hybrid Modern Authentication.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="768f3-128">Добавление URL-адресов веб-службы на локальной основе в качестве SPNs в Azure AD</span><span class="sxs-lookup"><span data-stu-id="768f3-128">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="768f3-129">Запустите команды, которые назначают URL-адреса локальной веб-службы в качестве SPNs Azure AD.</span><span class="sxs-lookup"><span data-stu-id="768f3-129">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="768f3-130">SpNs используются клиентские машины и устройства во время проверки подлинности и авторизации.</span><span class="sxs-lookup"><span data-stu-id="768f3-130">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="768f3-131">Все URL-адреса, которые можно использовать для подключения из локального в Azure Active Directory (Azure AD), должны быть зарегистрированы в Azure AD (это включает как внутренние, так и внешние пространства имен).</span><span class="sxs-lookup"><span data-stu-id="768f3-131">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="768f3-132">Сначала соберйте все URL-адреса, которые необходимо добавить в AAD.</span><span class="sxs-lookup"><span data-stu-id="768f3-132">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="768f3-133">Запустите эти команды на месте:</span><span class="sxs-lookup"><span data-stu-id="768f3-133">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
```

<span data-ttu-id="768f3-134">Убедитесь, что клиенты URL-адресов могут подключаться к числу основных имен служб HTTPS в AAD.</span><span class="sxs-lookup"><span data-stu-id="768f3-134">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span> <span data-ttu-id="768f3-135">В случае, если EXCH гибридна с несколькими **арендаторами,** эти VPN HTTPS должны быть добавлены в AAD всех клиентов в гибриде с EXCH.</span><span class="sxs-lookup"><span data-stu-id="768f3-135">In case EXCH is in hybrid with **multiple tenants**, these HTTPS SPNs should be added in the AAD of all the tenants in hybrid with EXCH.</span></span>

1. <span data-ttu-id="768f3-136">Во-первых, подключите К AAD с [этими инструкциями.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="768f3-136">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="768f3-137">Чтобы использовать команду _ниже, необходимо использовать Подключение-MsolService_ на этой странице.</span><span class="sxs-lookup"><span data-stu-id="768f3-137">You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="768f3-138">Для URL Exchange связанных с Exchange, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="768f3-138">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="768f3-139">Обратите внимание (и снимок экрана для более позднего сравнения) вывода этой команды, которая должна включать URL-адрес https://  *autodiscover.yourdomain.com*  и https://  *mail.yourdomain.com,* но в основном состоит из SPNs, которые начинаются с 0000002-0000-0ff1-ce00-0000000000000/.</span><span class="sxs-lookup"><span data-stu-id="768f3-139">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="768f3-140">Если из локального https:// отсутствуют URL-адреса, нам потребуется добавить эти конкретные записи в этот список.</span><span class="sxs-lookup"><span data-stu-id="768f3-140">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="768f3-141">Если вы не видите в этом списке внутренние и внешние записи MAPI/HTTP, EWS, ActiveSync, OAB и Autodiscover, необходимо добавить их с помощью команд ниже (например URL-адреса в примере ' и ', но вы замените URL-адреса примера `mail.corp.contoso.com` `owa.contoso.com` собственными): </span><span class="sxs-lookup"><span data-stu-id="768f3-141">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="768f3-142">Убедитесь, что новые записи были добавлены, Get-MsolServicePrincipal команду из шага 2 и проверив выход.</span><span class="sxs-lookup"><span data-stu-id="768f3-142">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="768f3-143">Сравните список и снимок экрана до нового списка spNs.</span><span class="sxs-lookup"><span data-stu-id="768f3-143">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="768f3-144">Вы также можете сделать снимок экрана нового списка для записей.</span><span class="sxs-lookup"><span data-stu-id="768f3-144">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="768f3-145">Если вы были успешными, вы увидите два новых URL-адреса в списке.</span><span class="sxs-lookup"><span data-stu-id="768f3-145">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="768f3-146">В нашем примере список СНО теперь будет включать конкретные  `https://mail.corp.contoso.com`  URL-адреса и  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="768f3-146">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="768f3-147">Проверка правильной настройки виртуальных каталогов</span><span class="sxs-lookup"><span data-stu-id="768f3-147">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="768f3-148">Теперь убедитесь, что OAuth включен Exchange во всех виртуальных каталогах Outlook, которые можно использовать при запуске следующих команд:</span><span class="sxs-lookup"><span data-stu-id="768f3-148">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="768f3-149">Проверьте вывод, чтобы убедиться, что **OAuth** включен в каждом из этих VDirs, он будет выглядеть так (и главное, что нужно посмотреть, это OAuth):</span><span class="sxs-lookup"><span data-stu-id="768f3-149">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="768f3-150">Если OAuth отсутствует на любом сервере и любом из четырех виртуальных каталогов, его необходимо добавить с помощью соответствующих команд перед началом работы[(Set-MapiVirtualDirectory,](/powershell/module/exchange/set-mapivirtualdirectory) [Set-WebServicesVirtualDirectory,](/powershell/module/exchange/set-webservicesvirtualdirectory) [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)и [Set-AutodiscoverVirtualDirectory).](/powershell/module/exchange/set-autodiscovervirtualdirectory)</span><span class="sxs-lookup"><span data-stu-id="768f3-150">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="768f3-151">Подтверждение на наличие объекта Auth Server EvoSTS</span><span class="sxs-lookup"><span data-stu-id="768f3-151">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="768f3-152">Возвращайся к локальной Exchange командной оболочке для этой последней команды.</span><span class="sxs-lookup"><span data-stu-id="768f3-152">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="768f3-153">Теперь вы можете проверить, есть ли у локального поставщика проверки подлинности evoSTS запись:</span><span class="sxs-lookup"><span data-stu-id="768f3-153">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -like "EvoSts"}
```

<span data-ttu-id="768f3-154">На выходе должен быть показываться AuthServer имени EvoSts, а состояние "Включено" должно быть True.</span><span class="sxs-lookup"><span data-stu-id="768f3-154">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="768f3-155">Если этого не видно, следует скачать и запустить новейшую версию мастера гибридной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="768f3-155">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="768f3-156">В том случае, если EXCH гибридна с несколькими арендаторами, на выходе должен быть по одному AuthServer name EvoSts — {GUID} для каждого клиента в гибриде с EXCH, а состояние "Включено" должно быть true для всех этих объектов AuthServer.</span><span class="sxs-lookup"><span data-stu-id="768f3-156">In case EXCH is in hybrid with **multiple tenants**, your output should show one AuthServer of the Name EvoSts - {GUID} for each tenant in hybrid with EXCH and the 'Enabled' state should be True for all of these AuthServer objects.</span></span>

 <span data-ttu-id="768f3-157">**Важно** Если в среде Exchange 2010 г., поставщик проверки подлинности EvoSTS не будет создан.</span><span class="sxs-lookup"><span data-stu-id="768f3-157">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="768f3-158">Включить HMA</span><span class="sxs-lookup"><span data-stu-id="768f3-158">Enable HMA</span></span>

<span data-ttu-id="768f3-159">Запустите следующую команду в локальной Exchange командной оболочке:</span><span class="sxs-lookup"><span data-stu-id="768f3-159">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

<span data-ttu-id="768f3-160">Если версия EXCH Exchange 2016 (CU18 или выше) или Exchange 2019 (CU7 или выше) и гибридная была настроена с HCW, загруженным после сентября 2020 г., запустите следующую команду в локальной Exchange Management Shell:</span><span class="sxs-lookup"><span data-stu-id="768f3-160">If the EXCH version is Exchange 2016 (CU18 or higher) or Exchange 2019 (CU7 or higher) and hybrid was configured with HCW downloaded after September 2020, run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -DomainName "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> <span data-ttu-id="768f3-161">Если EXCH гибридна с несколькими арендаторами, в EXCH присутствует несколько объектов AuthServer с доменами, соответствующими каждому клиенту.</span><span class="sxs-lookup"><span data-stu-id="768f3-161">In case EXCH is in hybrid with **multiple tenants**, there are multiple AuthServer objects present in EXCH with domains corresponding to each tenant.</span></span>  <span data-ttu-id="768f3-162">Флаг **IsDefaultAuthorizationEndpoint** должен быть задан для true (с помощью **cmdlet IsDefaultAuthorizationEndpoint)** для любого из этих объектов AuthServer.</span><span class="sxs-lookup"><span data-stu-id="768f3-162">The **IsDefaultAuthorizationEndpoint** flag should be set to true (using the **IsDefaultAuthorizationEndpoint** cmdlet) for any one of these AuthServer objects.</span></span> <span data-ttu-id="768f3-163">Этот флаг не может быть задан для всех объектов Authserver и HMA будет включен, даже если один из этих объектов AuthServer **isDefaultAuthorizationEndpoint** флаг установлен для true.</span><span class="sxs-lookup"><span data-stu-id="768f3-163">This flag can't be set to true for all the Authserver objects and HMA would be enabled even if one of these AuthServer object's **IsDefaultAuthorizationEndpoint** flag is set to true.</span></span>

## <a name="verify"></a><span data-ttu-id="768f3-164">Проверка</span><span class="sxs-lookup"><span data-stu-id="768f3-164">Verify</span></span>

<span data-ttu-id="768f3-165">После встраив HMA, следующий вход клиента будет использовать новый поток auth.</span><span class="sxs-lookup"><span data-stu-id="768f3-165">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="768f3-166">Обратите внимание, что включение HMA не вызовет повторной оценки для любого клиента.</span><span class="sxs-lookup"><span data-stu-id="768f3-166">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="768f3-167">Клиенты повторно обнародуются в зависимости от срока службы маркеров auth и/или сертификатов, которые у них есть.</span><span class="sxs-lookup"><span data-stu-id="768f3-167">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="768f3-168">Кроме того, необходимо удерживать клавишу CTRL одновременно с правой кнопкой мыши значок для клиента Outlook (также в подносе Windows уведомлений) и нажмите кнопку "Состояние подключения".</span><span class="sxs-lookup"><span data-stu-id="768f3-168">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="768f3-169">Иском адрес SMTP клиента в отношении типа 'Authn' 'Bearer', который представляет маркер носители, используемый \* в OAuth.</span><span class="sxs-lookup"><span data-stu-id="768f3-169">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

> [!NOTE]
> <span data-ttu-id="768f3-170">Необходимо настроить Skype для бизнеса с HMA?</span><span class="sxs-lookup"><span data-stu-id="768f3-170">Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="768f3-171">Вам потребуется две статьи: одна из них, которая перечисляет поддерживаемые [топологии,](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)и одна, которая показывает, как [сделать конфигурацию.](configure-skype-for-business-for-hybrid-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="768f3-171">You'll need two articles: One that lists [supported topologies](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>


## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="768f3-172">Гибридная современная проверка подлинности в случае Outlook для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="768f3-172">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="768f3-173">Если вы — локальное клиент, использующее сервер Exchange TCP 443, обходить обработку трафика для следующих диапазонов IP-адресов:</span><span class="sxs-lookup"><span data-stu-id="768f3-173">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP address ranges:</span></span>

```
52.125.128.0/20
52.127.96.0/23
```

<span data-ttu-id="768f3-174">Приложение Outlook для iOS и Android разработано как лучший способ испытать Microsoft 365 или Office 365 на вашем мобильном устройстве с помощью службы Майкрософт для поиска, планирования и приоритетов вашей повседневной жизни и работы.</span><span class="sxs-lookup"><span data-stu-id="768f3-174">The Outlook app for iOS and Android is designed as the best way to experience Microsoft 365 or Office 365 on your mobile device by using Microsoft services to help find, plan, and prioritize your daily life and work.</span></span> <span data-ttu-id="768f3-175">Дополнительные сведения можно получить в ссылке Использование гибридной современной проверки подлинности [Outlook для iOS и Android.](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth?view=exchserver-2019)</span><span class="sxs-lookup"><span data-stu-id="768f3-175">For more information, please refer to [Using hybrid Modern Authentication with Outlook for iOS and Android](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth?view=exchserver-2019).</span></span>

## <a name="related-topics"></a><span data-ttu-id="768f3-176">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="768f3-176">Related topics</span></span>

[<span data-ttu-id="768f3-177">Современные требования к конфигурации проверки подлинности для перехода Office 365/ITAR на vNext</span><span class="sxs-lookup"><span data-stu-id="768f3-177">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
