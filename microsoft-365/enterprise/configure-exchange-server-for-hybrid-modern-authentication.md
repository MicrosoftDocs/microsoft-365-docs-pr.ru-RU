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
ms.openlocfilehash: 46646f35d3b41821424269f66721fbf829d339f7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928206"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="4d20a-103">Как настроить локальное развертывание Exchange Server для использования гибридной современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="4d20a-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="4d20a-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="4d20a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4d20a-105">Гибридная современная проверка подлинности (HMA) — это метод управления удостоверениями, который обеспечивает более безопасную проверку подлинности и авторизацию пользователей и доступен для локального гибридного развертывания сервера Exchange.</span><span class="sxs-lookup"><span data-stu-id="4d20a-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="4d20a-106">FYI</span><span class="sxs-lookup"><span data-stu-id="4d20a-106">FYI</span></span>

<span data-ttu-id="4d20a-107">Перед началом работы я вызываю:</span><span class="sxs-lookup"><span data-stu-id="4d20a-107">Before we begin, I call:</span></span>

- <span data-ttu-id="4d20a-108">Гибридная современная \> проверка подлинности HMA</span><span class="sxs-lookup"><span data-stu-id="4d20a-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="4d20a-109">Exchange на локальной \> основе EXCH</span><span class="sxs-lookup"><span data-stu-id="4d20a-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="4d20a-110">Exchange Online \> EXO</span><span class="sxs-lookup"><span data-stu-id="4d20a-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="4d20a-111">Кроме того, если на рисунке в этой статье имеется объект с "серым" или "замутненым", это означает, что элемент, показанный в сером цвете, не входит в конфигурацию, определенную *HMA.*</span><span class="sxs-lookup"><span data-stu-id="4d20a-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="4d20a-112">Включение гибридной современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="4d20a-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="4d20a-113">Включение HMA означает:</span><span class="sxs-lookup"><span data-stu-id="4d20a-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="4d20a-114">Убедитесь, что перед началом работы вы встретите предварительные окрики.</span><span class="sxs-lookup"><span data-stu-id="4d20a-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="4d20a-115">Так **как** для Skype для бизнеса и Exchange используется множество необходимых условий, обзор гибридной современной проверки подлинности и необходимые условия для его использования на локальном сервере Skype для бизнеса и [Exchange.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4d20a-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="4d20a-116">Сделайте это, прежде чем приступить к любым шагам в этой статье.</span><span class="sxs-lookup"><span data-stu-id="4d20a-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="4d20a-117">Добавление URL-адресов веб-служб локальной службы в качестве имен основных служб **(SPNs)** в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4d20a-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span>

1. <span data-ttu-id="4d20a-118">Обеспечение включения всех виртуальных каталогов для HMA</span><span class="sxs-lookup"><span data-stu-id="4d20a-118">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="4d20a-119">Проверка объекта Auth Server EvoSTS</span><span class="sxs-lookup"><span data-stu-id="4d20a-119">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="4d20a-120">Включение HMA в EXCH.</span><span class="sxs-lookup"><span data-stu-id="4d20a-120">Enabling HMA in EXCH.</span></span>

 <span data-ttu-id="4d20a-121">**Примечание** Поддерживает ли ваша версия Ma Office?</span><span class="sxs-lookup"><span data-stu-id="4d20a-121">**Note** Does your version of Office support MA?</span></span> <span data-ttu-id="4d20a-122">Узнайте, как работает современная проверка подлинности для клиентских приложений [Office 2013 и Office 2016.](modern-auth-for-office-2013-and-2016.md)</span><span class="sxs-lookup"><span data-stu-id="4d20a-122">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>

## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="4d20a-123">Убедитесь, что вы соответствуете всем необходимым требованиям</span><span class="sxs-lookup"><span data-stu-id="4d20a-123">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="4d20a-124">Так как для Skype для бизнеса и Exchange используется множество необходимых условий, просмотрите обзор гибридной современной проверки подлинности и необходимые условия для его использования на локальном сервере Skype для бизнеса и [Exchange.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4d20a-124">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="4d20a-125">Сделайте  *это,*  прежде чем приступить к любым шагам в этой статье.</span><span class="sxs-lookup"><span data-stu-id="4d20a-125">Do this  *before*  you begin any of the steps in this article.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="4d20a-126">Добавление URL-адресов веб-службы на локальной основе в качестве SPNs в Azure AD</span><span class="sxs-lookup"><span data-stu-id="4d20a-126">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="4d20a-127">Запустите команды, которые назначают URL-адреса локальной веб-службы в качестве SPNs Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4d20a-127">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="4d20a-128">SpNs используются клиентские машины и устройства во время проверки подлинности и авторизации.</span><span class="sxs-lookup"><span data-stu-id="4d20a-128">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="4d20a-129">Все URL-адреса, которые можно использовать для подключения из локального в Azure Active Directory (Azure AD), должны быть зарегистрированы в Azure AD (это включает внутренние и внешние пространства имен).</span><span class="sxs-lookup"><span data-stu-id="4d20a-129">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="4d20a-130">Сначала соберйте все URL-адреса, которые необходимо добавить в AAD.</span><span class="sxs-lookup"><span data-stu-id="4d20a-130">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="4d20a-131">Запустите эти команды на месте:</span><span class="sxs-lookup"><span data-stu-id="4d20a-131">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

<span data-ttu-id="4d20a-132">Убедитесь, что клиенты URL-адресов могут подключаться к числу основных имен служб HTTPS в AAD.</span><span class="sxs-lookup"><span data-stu-id="4d20a-132">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span>

1. <span data-ttu-id="4d20a-133">Во-первых, подключите К AAD с [этими инструкциями.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="4d20a-133">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

   <span data-ttu-id="4d20a-134">**Примечание** Чтобы использовать приведенную ниже команду, необходимо использовать параметр _Connect-MsolService_ на этой странице.</span><span class="sxs-lookup"><span data-stu-id="4d20a-134">**Note** You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="4d20a-135">Для URL-адресов, связанных с Exchange, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4d20a-135">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="4d20a-136">Обратите внимание (и снимок экрана для более позднего сравнения) вывода этой команды, которая должна включать URL-адрес https://  *autodiscover.yourdomain.com*  и https://  *mail.yourdomain.com,* но в основном состоит из SPNs, которые начинаются с 0000002-0000-0ff1-ce00-0000000000000/.</span><span class="sxs-lookup"><span data-stu-id="4d20a-136">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="4d20a-137">Если из локального https:// отсутствуют URL-адреса, нам потребуется добавить эти конкретные записи в этот список.</span><span class="sxs-lookup"><span data-stu-id="4d20a-137">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="4d20a-138">Если вы не видите в этом списке внутренние и внешние записи MAPI/HTTP, EWS, ActiveSync, OAB и Autodiscover, необходимо добавить их с помощью команд ниже (например URL-адреса в примере ' и ', но вы замените URL-адреса примера `mail.corp.contoso.com` `owa.contoso.com` собственными): </span><span class="sxs-lookup"><span data-stu-id="4d20a-138">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="4d20a-139">Убедитесь, что новые записи были добавлены, Get-MsolServicePrincipal команду из шага 2 и проверив выход.</span><span class="sxs-lookup"><span data-stu-id="4d20a-139">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="4d20a-140">Сравните список и снимок экрана до нового списка spNs.</span><span class="sxs-lookup"><span data-stu-id="4d20a-140">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="4d20a-141">Вы также можете сделать снимок экрана нового списка для записей.</span><span class="sxs-lookup"><span data-stu-id="4d20a-141">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="4d20a-142">Если вы были успешными, вы увидите два новых URL-адреса в списке.</span><span class="sxs-lookup"><span data-stu-id="4d20a-142">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="4d20a-143">В нашем примере список СНО теперь будет включать конкретные  `https://mail.corp.contoso.com`  URL-адреса и  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="4d20a-143">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="4d20a-144">Проверка правильной настройки виртуальных каталогов</span><span class="sxs-lookup"><span data-stu-id="4d20a-144">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="4d20a-145">Теперь убедитесь, что OAuth включен должным образом в Exchange во всех виртуальных каталогах Outlook, которые можно использовать при запуске следующих команд:</span><span class="sxs-lookup"><span data-stu-id="4d20a-145">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="4d20a-146">Проверьте вывод, чтобы убедиться, что **OAuth** включен в каждом из этих VDirs, он будет выглядеть так (и главное, что нужно посмотреть, это OAuth):</span><span class="sxs-lookup"><span data-stu-id="4d20a-146">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="4d20a-147">Если OAuth отсутствует на любом сервере и любом из четырех виртуальных каталогов, его необходимо добавить с помощью соответствующих команд перед началом работы[(Set-MapiVirtualDirectory,](/powershell/module/exchange/set-mapivirtualdirectory) [Set-WebServicesVirtualDirectory,](/powershell/module/exchange/set-webservicesvirtualdirectory) [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)и [Set-AutodiscoverVirtualDirectory).](/powershell/module/exchange/set-autodiscovervirtualdirectory)</span><span class="sxs-lookup"><span data-stu-id="4d20a-147">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="4d20a-148">Подтверждение на наличие объекта Auth Server EvoSTS</span><span class="sxs-lookup"><span data-stu-id="4d20a-148">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="4d20a-149">Возвращайся к локальной командной оболочке Exchange для последней команды.</span><span class="sxs-lookup"><span data-stu-id="4d20a-149">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="4d20a-150">Теперь вы можете проверить, есть ли у локального поставщика проверки подлинности evoSTS запись:</span><span class="sxs-lookup"><span data-stu-id="4d20a-150">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="4d20a-151">На выходе должен быть показываться AuthServer имени EvoSts, а состояние "Включено" должно быть True.</span><span class="sxs-lookup"><span data-stu-id="4d20a-151">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="4d20a-152">Если этого не видно, следует скачать и запустить новейшую версию мастера гибридной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4d20a-152">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

 <span data-ttu-id="4d20a-153">**Важно** Если вы работаете в среде Exchange 2010, поставщик проверки подлинности EvoSTS не будет создан.</span><span class="sxs-lookup"><span data-stu-id="4d20a-153">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="4d20a-154">Включить HMA</span><span class="sxs-lookup"><span data-stu-id="4d20a-154">Enable HMA</span></span>

<span data-ttu-id="4d20a-155">Запустите следующую команду в локальной командной оболочке Exchange:</span><span class="sxs-lookup"><span data-stu-id="4d20a-155">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a><span data-ttu-id="4d20a-156">Проверка</span><span class="sxs-lookup"><span data-stu-id="4d20a-156">Verify</span></span>

<span data-ttu-id="4d20a-157">После встраив HMA, следующий вход клиента будет использовать новый поток auth.</span><span class="sxs-lookup"><span data-stu-id="4d20a-157">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="4d20a-158">Обратите внимание, что включение HMA не вызовет повторной оценки для любого клиента.</span><span class="sxs-lookup"><span data-stu-id="4d20a-158">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="4d20a-159">Клиенты повторно обнародуются в зависимости от срока службы маркеров auth и/или сертификатов, которые у них есть.</span><span class="sxs-lookup"><span data-stu-id="4d20a-159">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="4d20a-160">Кроме того, необходимо придержать клавишу CTRL, щелкнув правой кнопкой мыши значок для клиента Outlook (также в подносе Уведомлений Windows) и нажмите кнопку "Состояние подключения".</span><span class="sxs-lookup"><span data-stu-id="4d20a-160">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="4d20a-161">Иском адрес SMTP клиента в отношении типа 'Authn' 'Bearer', который представляет маркер носители, используемый \* в OAuth.</span><span class="sxs-lookup"><span data-stu-id="4d20a-161">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

 <span data-ttu-id="4d20a-162">**Примечание** Необходимо настроить Skype для бизнеса с помощью HMA?</span><span class="sxs-lookup"><span data-stu-id="4d20a-162">**Note** Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="4d20a-163">Вам потребуется две статьи: одна из них, которая перечисляет поддерживаемые [топологии,](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)и одна, которая показывает, как [сделать конфигурацию.](configure-skype-for-business-for-hybrid-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="4d20a-163">You'll need two articles: One that lists [supported topologies](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="4d20a-164">Гибридная современная проверка подлинности в случае Outlook для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="4d20a-164">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="4d20a-165">Если вы локальное клиент, использующее сервер Exchange на TCP 443, обходить обработку трафика для следующих диапазонов IP:</span><span class="sxs-lookup"><span data-stu-id="4d20a-165">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP ranges:</span></span>

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a><span data-ttu-id="4d20a-166">Родственные темы</span><span class="sxs-lookup"><span data-stu-id="4d20a-166">Related topics</span></span>

[<span data-ttu-id="4d20a-167">Современные требования к конфигурации проверки подлинности для перехода с Office 365 dedicated/ITAR на vNext</span><span class="sxs-lookup"><span data-stu-id="4d20a-167">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)