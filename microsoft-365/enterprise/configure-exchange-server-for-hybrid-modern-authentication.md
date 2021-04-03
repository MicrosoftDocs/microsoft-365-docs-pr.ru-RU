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
ms.openlocfilehash: 9393b457c219fb03ae2e8a35c3f795c324919f27
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579726"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="d56cc-103">Как настроить локальное развертывание Exchange Server для использования гибридной современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="d56cc-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="d56cc-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="d56cc-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d56cc-105">Гибридная современная проверка подлинности (HMA) — это метод управления удостоверениями, который обеспечивает более безопасную проверку подлинности и авторизацию пользователей и доступен для локального гибридного развертывания сервера Exchange.</span><span class="sxs-lookup"><span data-stu-id="d56cc-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="d56cc-106">FYI</span><span class="sxs-lookup"><span data-stu-id="d56cc-106">FYI</span></span>

<span data-ttu-id="d56cc-107">Перед началом работы я вызываю:</span><span class="sxs-lookup"><span data-stu-id="d56cc-107">Before we begin, I call:</span></span>

- <span data-ttu-id="d56cc-108">Гибридная современная \> проверка подлинности HMA</span><span class="sxs-lookup"><span data-stu-id="d56cc-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="d56cc-109">Exchange на локальной \> основе EXCH</span><span class="sxs-lookup"><span data-stu-id="d56cc-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="d56cc-110">Exchange Online \> EXO</span><span class="sxs-lookup"><span data-stu-id="d56cc-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="d56cc-111">Кроме того, если на рисунке в этой статье имеется объект с "серым" или "замутненым", это означает, что элемент, показанный в сером цвете, не входит в конфигурацию, определенную *HMA.*</span><span class="sxs-lookup"><span data-stu-id="d56cc-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="d56cc-112">Включение гибридной современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="d56cc-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="d56cc-113">Включение HMA означает:</span><span class="sxs-lookup"><span data-stu-id="d56cc-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="d56cc-114">Убедитесь, что перед началом работы вы встретите предварительные окрики.</span><span class="sxs-lookup"><span data-stu-id="d56cc-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="d56cc-115">Так **как** для Skype для бизнеса и Exchange используется множество необходимых условий, обзор гибридной современной проверки подлинности и необходимые условия для его использования на локальном сервере Skype для бизнеса и [Exchange.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d56cc-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="d56cc-116">Сделайте это, прежде чем приступить к любым шагам в этой статье.</span><span class="sxs-lookup"><span data-stu-id="d56cc-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="d56cc-117">Добавление URL-адресов веб-служб локальной службы в качестве имен основных служб **(SPNs)** в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d56cc-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span> <span data-ttu-id="d56cc-118">В том случае, если EXCH гибридна с несколькими клиентами, эти URL-адреса веб-службы локального уровня должны быть добавлены в качестве URL-адресов в Azure AD всех клиентов, которые находятся в гибридной связи с EXCH.</span><span class="sxs-lookup"><span data-stu-id="d56cc-118">In case EXCH is in hybrid with **multiple tenants**, these on-premises web service URLs must be added as SPNs in the Azure AD of all the tenants which are in hybrid with EXCH.</span></span>

1. <span data-ttu-id="d56cc-119">Обеспечение включения всех виртуальных каталогов для HMA</span><span class="sxs-lookup"><span data-stu-id="d56cc-119">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="d56cc-120">Проверка объекта Auth Server EvoSTS</span><span class="sxs-lookup"><span data-stu-id="d56cc-120">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="d56cc-121">Включение HMA в EXCH.</span><span class="sxs-lookup"><span data-stu-id="d56cc-121">Enabling HMA in EXCH.</span></span>

> [!NOTE]
> <span data-ttu-id="d56cc-122">Поддерживает ли ваша версия Ma Office?</span><span class="sxs-lookup"><span data-stu-id="d56cc-122">Does your version of Office support MA?</span></span> <span data-ttu-id="d56cc-123">Узнайте, как работает современная проверка подлинности для клиентских приложений [Office 2013 и Office 2016.](modern-auth-for-office-2013-and-2016.md)</span><span class="sxs-lookup"><span data-stu-id="d56cc-123">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>


## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="d56cc-124">Убедитесь, что вы соответствуете всем необходимым требованиям</span><span class="sxs-lookup"><span data-stu-id="d56cc-124">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="d56cc-125">Так как для Skype для бизнеса и Exchange используется множество необходимых условий, просмотрите обзор гибридной современной проверки подлинности и необходимые условия для его использования на локальном сервере Skype для бизнеса и [Exchange.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d56cc-125">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="d56cc-126">Сделайте  *это,*  прежде чем приступить к любым шагам в этой статье.</span><span class="sxs-lookup"><span data-stu-id="d56cc-126">Do this  *before*  you begin any of the steps in this article.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="d56cc-127">Добавление URL-адресов веб-службы на локальной основе в качестве SPNs в Azure AD</span><span class="sxs-lookup"><span data-stu-id="d56cc-127">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="d56cc-128">Запустите команды, которые назначают URL-адреса локальной веб-службы в качестве SPNs Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d56cc-128">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="d56cc-129">SpNs используются клиентские машины и устройства во время проверки подлинности и авторизации.</span><span class="sxs-lookup"><span data-stu-id="d56cc-129">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="d56cc-130">Все URL-адреса, которые можно использовать для подключения из локального в Azure Active Directory (Azure AD), должны быть зарегистрированы в Azure AD (это включает внутренние и внешние пространства имен).</span><span class="sxs-lookup"><span data-stu-id="d56cc-130">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="d56cc-131">Сначала соберйте все URL-адреса, которые необходимо добавить в AAD.</span><span class="sxs-lookup"><span data-stu-id="d56cc-131">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="d56cc-132">Запустите эти команды на месте:</span><span class="sxs-lookup"><span data-stu-id="d56cc-132">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

<span data-ttu-id="d56cc-133">Убедитесь, что клиенты URL-адресов могут подключаться к числу основных имен служб HTTPS в AAD.</span><span class="sxs-lookup"><span data-stu-id="d56cc-133">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span> <span data-ttu-id="d56cc-134">В случае, если EXCH гибридна с несколькими **арендаторами,** эти VPN HTTPS должны быть добавлены в AAD всех клиентов в гибриде с EXCH.</span><span class="sxs-lookup"><span data-stu-id="d56cc-134">In case EXCH is in hybrid with **multiple tenants**, these HTTPS SPNs should be added in the AAD of all the tenants in hybrid with EXCH.</span></span>

1. <span data-ttu-id="d56cc-135">Во-первых, подключите К AAD с [этими инструкциями.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="d56cc-135">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="d56cc-136">Чтобы использовать приведенную ниже команду, необходимо использовать параметр _Connect-MsolService_ на этой странице.</span><span class="sxs-lookup"><span data-stu-id="d56cc-136">You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="d56cc-137">Для URL-адресов, связанных с Exchange, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d56cc-137">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="d56cc-138">Обратите внимание (и снимок экрана для более позднего сравнения) вывода этой команды, которая должна включать URL-адрес https://  *autodiscover.yourdomain.com*  и https://  *mail.yourdomain.com,* но в основном состоит из SPNs, которые начинаются с 0000002-0000-0ff1-ce00-0000000000000/.</span><span class="sxs-lookup"><span data-stu-id="d56cc-138">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="d56cc-139">Если из локального https:// отсутствуют URL-адреса, нам потребуется добавить эти конкретные записи в этот список.</span><span class="sxs-lookup"><span data-stu-id="d56cc-139">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="d56cc-140">Если вы не видите в этом списке внутренние и внешние записи MAPI/HTTP, EWS, ActiveSync, OAB и Autodiscover, необходимо добавить их с помощью команд ниже (например URL-адреса в примере ' и ', но вы замените URL-адреса примера `mail.corp.contoso.com` `owa.contoso.com` собственными): </span><span class="sxs-lookup"><span data-stu-id="d56cc-140">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="d56cc-141">Убедитесь, что новые записи были добавлены, Get-MsolServicePrincipal команду из шага 2 и проверив выход.</span><span class="sxs-lookup"><span data-stu-id="d56cc-141">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="d56cc-142">Сравните список и снимок экрана до нового списка spNs.</span><span class="sxs-lookup"><span data-stu-id="d56cc-142">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="d56cc-143">Вы также можете сделать снимок экрана нового списка для записей.</span><span class="sxs-lookup"><span data-stu-id="d56cc-143">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="d56cc-144">Если вы были успешными, вы увидите два новых URL-адреса в списке.</span><span class="sxs-lookup"><span data-stu-id="d56cc-144">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="d56cc-145">В нашем примере список СНО теперь будет включать конкретные  `https://mail.corp.contoso.com`  URL-адреса и  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="d56cc-145">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="d56cc-146">Проверка правильной настройки виртуальных каталогов</span><span class="sxs-lookup"><span data-stu-id="d56cc-146">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="d56cc-147">Теперь убедитесь, что OAuth включен должным образом в Exchange во всех виртуальных каталогах Outlook, которые можно использовать при запуске следующих команд:</span><span class="sxs-lookup"><span data-stu-id="d56cc-147">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="d56cc-148">Проверьте вывод, чтобы убедиться, что **OAuth** включен в каждом из этих VDirs, он будет выглядеть так (и главное, что нужно посмотреть, это OAuth):</span><span class="sxs-lookup"><span data-stu-id="d56cc-148">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="d56cc-149">Если OAuth отсутствует на любом сервере и любом из четырех виртуальных каталогов, его необходимо добавить с помощью соответствующих команд перед началом работы[(Set-MapiVirtualDirectory,](/powershell/module/exchange/set-mapivirtualdirectory) [Set-WebServicesVirtualDirectory,](/powershell/module/exchange/set-webservicesvirtualdirectory) [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)и [Set-AutodiscoverVirtualDirectory).](/powershell/module/exchange/set-autodiscovervirtualdirectory)</span><span class="sxs-lookup"><span data-stu-id="d56cc-149">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="d56cc-150">Подтверждение на наличие объекта Auth Server EvoSTS</span><span class="sxs-lookup"><span data-stu-id="d56cc-150">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="d56cc-151">Возвращайся к локальной командной оболочке Exchange для последней команды.</span><span class="sxs-lookup"><span data-stu-id="d56cc-151">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="d56cc-152">Теперь вы можете проверить, есть ли у локального поставщика проверки подлинности evoSTS запись:</span><span class="sxs-lookup"><span data-stu-id="d56cc-152">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="d56cc-153">На выходе должен быть показываться AuthServer имени EvoSts, а состояние "Включено" должно быть True.</span><span class="sxs-lookup"><span data-stu-id="d56cc-153">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="d56cc-154">Если этого не видно, следует скачать и запустить новейшую версию мастера гибридной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d56cc-154">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="d56cc-155">В том случае, если EXCH гибридна с несколькими арендаторами, на выходе должен быть по одному AuthServer name EvoSts — {GUID} для каждого клиента в гибриде с EXCH, а состояние "Включено" должно быть true для всех этих объектов AuthServer.</span><span class="sxs-lookup"><span data-stu-id="d56cc-155">In case EXCH is in hybrid with **multiple tenants**, your output should show one AuthServer of the Name EvoSts - {GUID} for each tenant in hybrid with EXCH and the 'Enabled' state should be True for all of these AuthServer objects.</span></span>

 <span data-ttu-id="d56cc-156">**Важно** Если вы работаете в среде Exchange 2010, поставщик проверки подлинности EvoSTS не будет создан.</span><span class="sxs-lookup"><span data-stu-id="d56cc-156">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="d56cc-157">Включить HMA</span><span class="sxs-lookup"><span data-stu-id="d56cc-157">Enable HMA</span></span>

<span data-ttu-id="d56cc-158">Запустите следующую команду в локальной командной оболочке Exchange:</span><span class="sxs-lookup"><span data-stu-id="d56cc-158">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

<span data-ttu-id="d56cc-159">Если версия EXCH exchange 2016 (CU18 или выше) или Exchange 2019 (CU7 или выше) и гибридная настроена с HCW, загруженным после сентября 2020 г., запустите следующую команду в командной оболочке Exchange, локально:</span><span class="sxs-lookup"><span data-stu-id="d56cc-159">If the EXCH version is Exchange 2016 (CU18 or higher) or Exchange 2019 (CU7 or higher) and hybrid was configured with HCW downloaded after September 2020, run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -Domain "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> <span data-ttu-id="d56cc-160">Если EXCH гибридна с несколькими арендаторами, в EXCH присутствует несколько объектов AuthServer с доменами, соответствующими каждому клиенту.</span><span class="sxs-lookup"><span data-stu-id="d56cc-160">In case EXCH is in hybrid with **multiple tenants**, there are multiple AuthServer objects present in EXCH with domains corresponding to each tenant.</span></span>  <span data-ttu-id="d56cc-161">Флаг **IsDefaultAuthorizationEndpoint** должен быть задан для true (с помощью **cmdlet IsDefaultAuthorizationEndpoint)** для любого из этих объектов AuthServer.</span><span class="sxs-lookup"><span data-stu-id="d56cc-161">The **IsDefaultAuthorizationEndpoint** flag should be set to true (using the **IsDefaultAuthorizationEndpoint** cmdlet) for any one of these AuthServer objects.</span></span> <span data-ttu-id="d56cc-162">Этот флаг не может быть задан для всех объектов Authserver и HMA будет включен, даже если один из этих объектов AuthServer **isDefaultAuthorizationEndpoint** флаг установлен для true.</span><span class="sxs-lookup"><span data-stu-id="d56cc-162">This flag can't be set to true for all the Authserver objects and HMA would be enabled even if one of these AuthServer object's **IsDefaultAuthorizationEndpoint** flag is set to true.</span></span>

## <a name="verify"></a><span data-ttu-id="d56cc-163">Проверка</span><span class="sxs-lookup"><span data-stu-id="d56cc-163">Verify</span></span>

<span data-ttu-id="d56cc-164">После встраив HMA, следующий вход клиента будет использовать новый поток auth.</span><span class="sxs-lookup"><span data-stu-id="d56cc-164">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="d56cc-165">Обратите внимание, что включение HMA не вызовет повторной оценки для любого клиента.</span><span class="sxs-lookup"><span data-stu-id="d56cc-165">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="d56cc-166">Клиенты повторно обнародуются в зависимости от срока службы маркеров auth и/или сертификатов, которые у них есть.</span><span class="sxs-lookup"><span data-stu-id="d56cc-166">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="d56cc-167">Кроме того, необходимо придержать клавишу CTRL, щелкнув правой кнопкой мыши значок для клиента Outlook (также в подносе Уведомлений Windows) и нажмите кнопку "Состояние подключения".</span><span class="sxs-lookup"><span data-stu-id="d56cc-167">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="d56cc-168">Иском адрес SMTP клиента в отношении типа 'Authn' 'Bearer', который представляет маркер носители, используемый \* в OAuth.</span><span class="sxs-lookup"><span data-stu-id="d56cc-168">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

> [!NOTE]
> <span data-ttu-id="d56cc-169">Необходимо настроить Skype для бизнеса с помощью HMA?</span><span class="sxs-lookup"><span data-stu-id="d56cc-169">Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="d56cc-170">Вам потребуется две статьи: одна из них, которая перечисляет поддерживаемые [топологии,](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)и одна, которая показывает, как [сделать конфигурацию.](configure-skype-for-business-for-hybrid-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="d56cc-170">You'll need two articles: One that lists [supported topologies](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>


## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="d56cc-171">Гибридная современная проверка подлинности в случае Outlook для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="d56cc-171">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="d56cc-172">Если вы — локальное клиент, использующее сервер Exchange на TCP 443, обходить обработку трафика для следующих диапазонов IP-адресов:</span><span class="sxs-lookup"><span data-stu-id="d56cc-172">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP address ranges:</span></span>

```
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a><span data-ttu-id="d56cc-173">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d56cc-173">Related topics</span></span>

[<span data-ttu-id="d56cc-174">Современные требования к конфигурации проверки подлинности для перехода с Office 365 dedicated/ITAR на vNext</span><span class="sxs-lookup"><span data-stu-id="d56cc-174">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
