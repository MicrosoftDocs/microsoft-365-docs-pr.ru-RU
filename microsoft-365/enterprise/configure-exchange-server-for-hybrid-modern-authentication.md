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
description: Узнайте, как настроить Exchange Server локально для использования гибридной современной проверки подлинности (HMA), что обеспечивает более безопасную проверку подлинности и авторизацию пользователей.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3841f429399500cfc24ebadc89c74d478d2290d9
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780288"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="b47de-103">Как настроить локальное развертывание Exchange Server для использования гибридной современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="b47de-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="b47de-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="b47de-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b47de-105">Гибридная современная проверка подлинности (HMA) — это метод управления удостоверениями, который обеспечивает более безопасную проверку подлинности и авторизацию пользователей и доступен для локального гибридного развертывания сервера Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="b47de-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="b47de-106">FYI</span><span class="sxs-lookup"><span data-stu-id="b47de-106">FYI</span></span>

<span data-ttu-id="b47de-107">Прежде чем начать, я вызываю:</span><span class="sxs-lookup"><span data-stu-id="b47de-107">Before we begin, I call:</span></span>

- <span data-ttu-id="b47de-108">HMA гибридной \> современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="b47de-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="b47de-109">Exchange on-premises \> EXCH</span><span class="sxs-lookup"><span data-stu-id="b47de-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="b47de-110">Exchange Online \> EXO</span><span class="sxs-lookup"><span data-stu-id="b47de-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="b47de-111">Кроме того, если на рисунке в этой статье имеется объект с серым или серым цветом, это означает, что элемент, показанный серым цветом, не включен в конфигурацию, специфическую для *HMA.*</span><span class="sxs-lookup"><span data-stu-id="b47de-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="b47de-112">Включение гибридной современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="b47de-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="b47de-113">Включение HMA означает:</span><span class="sxs-lookup"><span data-stu-id="b47de-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="b47de-114">Перед началом убедитесь, что вы соответствуете предварительным требованиям.</span><span class="sxs-lookup"><span data-stu-id="b47de-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="b47de-115">Так **как** многие предварительные условия являются общими для Skype для бизнеса и Exchange, обзор гибридной современной проверки подлинности и необходимые условия для ее использования с локальной skype для бизнеса и [серверами Exchange.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b47de-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="b47de-116">Сделайте это, прежде чем приступить к любому из действий, которые необходимо предпринять в этой статье.</span><span class="sxs-lookup"><span data-stu-id="b47de-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="b47de-117">Добавление URL-адресов локальной веб-службы в качестве имен основных служб **(SPNs)** в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b47de-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span>

1. <span data-ttu-id="b47de-118">Обеспечение включения HMA для всех виртуальных каталогов</span><span class="sxs-lookup"><span data-stu-id="b47de-118">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="b47de-119">Проверка на предмет объекта Веб-сервер проверки Веб-службы СтиСТА</span><span class="sxs-lookup"><span data-stu-id="b47de-119">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="b47de-120">Включение HMA в EXCH.</span><span class="sxs-lookup"><span data-stu-id="b47de-120">Enabling HMA in EXCH.</span></span>

 <span data-ttu-id="b47de-121">**Примечание** Поддерживает ли ваша версия Office ma?</span><span class="sxs-lookup"><span data-stu-id="b47de-121">**Note** Does your version of Office support MA?</span></span> <span data-ttu-id="b47de-122">Узнайте, как работает современная проверка подлинности для клиентских приложений [Office 2013 и Office 2016.](modern-auth-for-office-2013-and-2016.md)</span><span class="sxs-lookup"><span data-stu-id="b47de-122">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>

## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="b47de-123">Убедитесь, что вы соответствуете всем предварительным требованиям</span><span class="sxs-lookup"><span data-stu-id="b47de-123">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="b47de-124">Так как многие предварительные условия являются общими для Skype для бизнеса и Exchange, просмотрите обзор гибридной современной проверки подлинности и необходимые условия для ее использования с локальной skype для бизнеса и [серверами Exchange.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b47de-124">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="b47de-125">Сделайте  *это,*  прежде чем приступить к любому из действий, которые необходимо предпринять в этой статье.</span><span class="sxs-lookup"><span data-stu-id="b47de-125">Do this  *before*  you begin any of the steps in this article.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="b47de-126">Добавление URL-адресов локальной веб-службы в качестве SPNs в Azure AD</span><span class="sxs-lookup"><span data-stu-id="b47de-126">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="b47de-127">Запустите команды, которые назначают URL-адреса локальной веб-службы в качестве spNs Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b47de-127">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="b47de-128">SpNs используются клиентских компьютеров и устройств во время проверки подлинности и авторизации.</span><span class="sxs-lookup"><span data-stu-id="b47de-128">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="b47de-129">Все URL-адреса, которые могут использоваться для подключения локально к Azure Active Directory (Azure AD), должны быть зарегистрированы в Azure AD (включая внутренние и внешние пространства имен).</span><span class="sxs-lookup"><span data-stu-id="b47de-129">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="b47de-130">Сначала соберем все URL-адреса, которые необходимо добавить в AAD.</span><span class="sxs-lookup"><span data-stu-id="b47de-130">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="b47de-131">Запустите эти команды локально:</span><span class="sxs-lookup"><span data-stu-id="b47de-131">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

<span data-ttu-id="b47de-132">Убедитесь, что клиенты URL-адресов, к которые могут подключаться, указаны в AAD как имена основных служб HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b47de-132">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span>

1. <span data-ttu-id="b47de-133">Во-первых, подключите AAD с [помощью этих инструкций.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="b47de-133">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

   <span data-ttu-id="b47de-134">**Примечание** Чтобы использовать приведенную ниже команду, необходимо использовать параметр _Connect-MsolService_ на этой странице.</span><span class="sxs-lookup"><span data-stu-id="b47de-134">**Note** You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="b47de-135">Для URL-адресов, связанных с Exchange, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b47de-135">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="b47de-136">Обратите внимание (и снимок экрана для более позднего сравнения) результатов этой команды, которые должны включать URL-адрес https://  *autodiscover.yourdomain.com*  и https://  *mail.yourdomain.com,* но в основном состоят из SPNs, которые начинаются с 000000002-0000-0ff1-ce00-000000000000/.</span><span class="sxs-lookup"><span data-stu-id="b47de-136">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="b47de-137">Если отсутствуют https:// url-адреса из локальной данной области, нам потребуется добавить эти записи в этот список.</span><span class="sxs-lookup"><span data-stu-id="b47de-137">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="b47de-138">Если в этом списке нет внутренних и внешних записей MAPI/HTTP, EWS, ActiveSync, OAB и Autodiscover, их необходимо добавить с помощью приведенной ниже команды (например, URL-адреса " и "", но вы замените примеры URL-адресов `mail.corp.contoso.com` `owa.contoso.com` собственными): </span><span class="sxs-lookup"><span data-stu-id="b47de-138">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="b47de-139">Убедитесь, что новые записи были добавлены, вы Get-MsolServicePrincipal команду из шага 2 и проверьте выходные данные.</span><span class="sxs-lookup"><span data-stu-id="b47de-139">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="b47de-140">Сравните список или снимок экрана с новым списком spNs.</span><span class="sxs-lookup"><span data-stu-id="b47de-140">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="b47de-141">Вы также можете сделать снимок экрана с новым списком для ваших записей.</span><span class="sxs-lookup"><span data-stu-id="b47de-141">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="b47de-142">Если вы успешно сравнелись, вы увидите два новых URL-адреса в списке.</span><span class="sxs-lookup"><span data-stu-id="b47de-142">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="b47de-143">В нашем примере список SPNs теперь будет включать определенные URL-адреса  `https://mail.corp.contoso.com`  и  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="b47de-143">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="b47de-144">Проверка правильной настройки виртуальных каталогов</span><span class="sxs-lookup"><span data-stu-id="b47de-144">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="b47de-145">Теперь убедитесь, что OAuth правильно включен в Exchange во всех виртуальных каталогах Outlook, вы можете использовать следующие команды:</span><span class="sxs-lookup"><span data-stu-id="b47de-145">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="b47de-146">Проверьте выходные данные, чтобы убедиться, что **OAuth** включен для каждого из этих VDirs, он будет выглядеть так (и на что нужно посмотреть, так это "OAuth"):</span><span class="sxs-lookup"><span data-stu-id="b47de-146">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="b47de-147">Если OAuth отсутствует на любом сервере и в любом из четырех виртуальных каталогов, необходимо добавить его, используя соответствующие команды, прежде чем перезапись ([Set-MapiVirtualDirectory,](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory) [Set-WebServicesVirtualDirectory,](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory) [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory)и [Set-AutodiscoverVirtualDirectory).](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)</span><span class="sxs-lookup"><span data-stu-id="b47de-147">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="b47de-148">Подтверждение на наличие объекта сервера auth Веб-службы СтиSTS</span><span class="sxs-lookup"><span data-stu-id="b47de-148">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="b47de-149">Вернись к локальной командной оболочке Exchange для этой последней команды.</span><span class="sxs-lookup"><span data-stu-id="b47de-149">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="b47de-150">Теперь вы можете проверить, есть ли в локальной сети запись для поставщика проверки подлинности premisestS:</span><span class="sxs-lookup"><span data-stu-id="b47de-150">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="b47de-151">Выходные данные должны показывать AuthServer для Name Sts, а состояние Enabled должно быть True.</span><span class="sxs-lookup"><span data-stu-id="b47de-151">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="b47de-152">Если вы этого не видите, скачайте и запустите наиболее новую версию мастера гибридной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b47de-152">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

 <span data-ttu-id="b47de-153">**Важно!** Если в вашей среде вы работаете с Exchange 2010, поставщик проверки подлинности ЛожSTS не будет создан.</span><span class="sxs-lookup"><span data-stu-id="b47de-153">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="b47de-154">Включить HMA</span><span class="sxs-lookup"><span data-stu-id="b47de-154">Enable HMA</span></span>

<span data-ttu-id="b47de-155">В локальной командной оболочке Exchange запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b47de-155">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a><span data-ttu-id="b47de-156">Проверка</span><span class="sxs-lookup"><span data-stu-id="b47de-156">Verify</span></span>

<span data-ttu-id="b47de-157">После того как вы в включить HMA, следующий вход клиента будет использовать новый поток авторов.</span><span class="sxs-lookup"><span data-stu-id="b47de-157">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="b47de-158">Обратите внимание, что простое включение HMA не вызовет повторной оценки для любого клиента.</span><span class="sxs-lookup"><span data-stu-id="b47de-158">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="b47de-159">Клиенты повторно проавтоматируют их в зависимости от срока действия маркеров и/или сертификатов, которые у них есть.</span><span class="sxs-lookup"><span data-stu-id="b47de-159">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="b47de-160">Также следует удерживать клавишу CTRL одновременно с щелчком правой кнопкой мыши по значку клиента Outlook (также в области уведомлений Windows) и нажатием кнопки "Состояние подключения".</span><span class="sxs-lookup"><span data-stu-id="b47de-160">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="b47de-161">Наберем SMTP-адрес клиента по типу "Authn" типа "Bearer", который представляет маркер носители, используемый \* в OAuth.</span><span class="sxs-lookup"><span data-stu-id="b47de-161">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

 <span data-ttu-id="b47de-162">**Примечание** Необходимо настроить Skype для бизнеса с HMA?</span><span class="sxs-lookup"><span data-stu-id="b47de-162">**Note** Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="b47de-163">Вам потребуется две статьи: в одной из них перечислены поддерживаемыеpologies, а в одной — показано, как [это сделать.](configure-skype-for-business-for-hybrid-modern-authentication.md) [](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)</span><span class="sxs-lookup"><span data-stu-id="b47de-163">You'll need two articles: One that lists [supported topologies](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="b47de-164">Гибридная современная проверка подлинности в случае Outlook для iOS и Android</span><span class="sxs-lookup"><span data-stu-id="b47de-164">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="b47de-165">Если вы используете локального клиента Exchange Server на TCP 443, обходя обработку трафика для следующих диапазонов IP-адресов:</span><span class="sxs-lookup"><span data-stu-id="b47de-165">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP ranges:</span></span>

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a><span data-ttu-id="b47de-166">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b47de-166">Related topics</span></span>

[<span data-ttu-id="b47de-167">Требования к конфигурации современной проверки подлинности для перехода с office 365 dedicated/ITAR на vNext</span><span class="sxs-lookup"><span data-stu-id="b47de-167">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
