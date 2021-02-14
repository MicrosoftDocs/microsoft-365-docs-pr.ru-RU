---
title: Как настроить локальное развертывание Skype для бизнеса для использования гибридной современной проверки подлинности
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 522d5cec-4e1b-4cc3-937f-293570717bc6
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Learn how to configure Skype for Business on-premises to use Hybrid Modern Authentication (HMA), offering you more secure user authentication and authorization.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74c8e3e0514fbfd8779c2f65e9c541c33b281c59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695026"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="e1d09-103">Как настроить локальное развертывание Skype для бизнеса для использования гибридной современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="e1d09-103">How to configure Skype for Business on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="e1d09-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="e1d09-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e1d09-105">Современная проверка подлинности — это метод управления удостоверениями, который обеспечивает более безопасную проверку подлинности и авторизацию пользователей, доступен для локального сервера Skype для бизнеса и локального сервера Exchange, а также гибридных вариантов Skype для бизнеса с разделенным доменом.</span><span class="sxs-lookup"><span data-stu-id="e1d09-105">Modern Authentication, is a method of identity management that offers more secure user authentication and authorization, is available for Skype for Business server on-premises and Exchange server on-premises, and split-domain Skype for Business hybrids.</span></span>
  
 <span data-ttu-id="e1d09-106">**Важно!** Хотите узнать больше о современной проверке подлинности и о том, почему вы предпочитаете использовать ее в своей компании или организации?</span><span class="sxs-lookup"><span data-stu-id="e1d09-106">**Important** Would you like to know more about Modern Authentication (MA) and why you might prefer to use it in your company or organization?</span></span> <span data-ttu-id="e1d09-107">Ознакомьтесь [с обзором](hybrid-modern-auth-overview.md) этого документа.</span><span class="sxs-lookup"><span data-stu-id="e1d09-107">Check [this document](hybrid-modern-auth-overview.md) for an overview.</span></span> <span data-ttu-id="e1d09-108">Если вам нужно знать, какие topologies Skype для бизнеса поддерживаются с помощью ma, это описано здесь!</span><span class="sxs-lookup"><span data-stu-id="e1d09-108">If you need to know what Skype for Business topologies are supported with MA, that's documented here!</span></span>
  
 <span data-ttu-id="e1d09-109">**Прежде чем начать,** я использую указанные здесь термины.</span><span class="sxs-lookup"><span data-stu-id="e1d09-109">**Before we begin**, I use these terms:</span></span>
  
- <span data-ttu-id="e1d09-110">Современная проверка подлинности (MA)</span><span class="sxs-lookup"><span data-stu-id="e1d09-110">Modern Authentication (MA)</span></span>

- <span data-ttu-id="e1d09-111">Гибридная современная проверка подлинности (HMA)</span><span class="sxs-lookup"><span data-stu-id="e1d09-111">Hybrid Modern Authentication (HMA)</span></span>

- <span data-ttu-id="e1d09-112">Локальное exchange (EXCH)</span><span class="sxs-lookup"><span data-stu-id="e1d09-112">Exchange on-premises (EXCH)</span></span>

- <span data-ttu-id="e1d09-113">Exchange Online (EXO)</span><span class="sxs-lookup"><span data-stu-id="e1d09-113">Exchange Online (EXO)</span></span>

- <span data-ttu-id="e1d09-114">Локальное приложение Skype для бизнеса (SFB)</span><span class="sxs-lookup"><span data-stu-id="e1d09-114">Skype for Business on-premises (SFB)</span></span>

- <span data-ttu-id="e1d09-115">Skype для бизнеса Online (SFBO)</span><span class="sxs-lookup"><span data-stu-id="e1d09-115">Skype for Business Online (SFBO)</span></span>

<span data-ttu-id="e1d09-116">Кроме того, если на рисунке в этой статье имеется объект, серый или  серый, это означает, что элемент, показанный серым цветом, не включен в конфигурацию, специфическую для ma.</span><span class="sxs-lookup"><span data-stu-id="e1d09-116">Also, if a graphic in this article has an object that's grayed-out or dimmed that means the element shown in gray **isn't** included in MA-specific configuration.</span></span>
  
## <a name="read-the-summary"></a><span data-ttu-id="e1d09-117">Чтение сводки</span><span class="sxs-lookup"><span data-stu-id="e1d09-117">Read the summary</span></span>

<span data-ttu-id="e1d09-118">Эта сводка разбивает процесс на шаги, которые в противном случае могут быть потеряны во время выполнения, и хорошо для общего контрольного списка для отслеживания того, где вы находитесь в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="e1d09-118">This summary breaks down the process into steps that might otherwise get lost during the execution, and is good for an overall checklist to keep track of where you are in the process.</span></span>
  
1. <span data-ttu-id="e1d09-119">Во-первых, убедитесь, что вы соответствуете всем предварительным требованиям.</span><span class="sxs-lookup"><span data-stu-id="e1d09-119">First, make sure you meet all the prerequisites.</span></span>

1. <span data-ttu-id="e1d09-120">Так как **многие предварительные** условия являются общими как для Skype для бизнеса, так и для Exchange, см. обзорную статью контрольного списка перед [повторной проверкой.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e1d09-120">Since many **prerequisites** are common for both Skype for Business and Exchange, [see the overview article for your pre-req checklist](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="e1d09-121">Сделайте  *это,*  прежде чем приступить к любому из действий, которые необходимо предпринять в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e1d09-121">Do this  *before*  you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="e1d09-122">Соберет сведения, необходимые для HMA, в файле или OneNote.</span><span class="sxs-lookup"><span data-stu-id="e1d09-122">Collect the HMA-specific info you'll need in a file, or OneNote.</span></span>

1. <span data-ttu-id="e1d09-123">Включит современную проверку подлинности для EXO (если она еще не включена).</span><span class="sxs-lookup"><span data-stu-id="e1d09-123">Turn ON Modern Authentication for EXO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="e1d09-124">Включит современную проверку подлинности для SFBO (если она еще не включена).</span><span class="sxs-lookup"><span data-stu-id="e1d09-124">Turn ON Modern Authentication for SFBO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="e1d09-125">Включит гибридную современную проверку подлинности для локальной системы Exchange.</span><span class="sxs-lookup"><span data-stu-id="e1d09-125">Turn ON Hybrid Modern Authentication for Exchange on-premises.</span></span>

1. <span data-ttu-id="e1d09-126">Turn ON Hybrid Modern Authentication for Skype for Business on-premises.</span><span class="sxs-lookup"><span data-stu-id="e1d09-126">Turn ON Hybrid Modern Authentication for Skype for Business on-premises.</span></span>

<span data-ttu-id="e1d09-127">Эти действия включит ma для SFB, SFBO, EXCH и EXO, то есть все продукты, которые могут участвовать в конфигурации HMA SFB и SFBO (включая зависимости от EXCH/EXO).</span><span class="sxs-lookup"><span data-stu-id="e1d09-127">These steps turn on MA for SFB, SFBO, EXCH, and EXO - that is, all the products that can participate in an HMA configuration of SFB and SFBO (including dependencies on EXCH/EXO).</span></span> <span data-ttu-id="e1d09-128">Другими словами, если ваши пользователи находятся в/имеют почтовые ящики, созданные в любой части гибридной системы (EXO + SFBO, EXO + SFB, EXCH + SFBO или EXCH + SFB), ваш готовый продукт будет выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="e1d09-128">In other words, if your users are homed in/have mailboxes created in any part of the Hybrid (EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB), your finished product will look like this:</span></span>
  
![A Mixed 6 Skype for business HMA topology has MA on in all four possible locations.](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)
  
<span data-ttu-id="e1d09-130">Как вы видите, есть четыре различных места для включаемой ma!</span><span class="sxs-lookup"><span data-stu-id="e1d09-130">As you can see there are four different places to turn on MA!</span></span> <span data-ttu-id="e1d09-131">Для лучшего пользовательского интерфейса мы рекомендуем включить ma во всех четырех этих расположениях.</span><span class="sxs-lookup"><span data-stu-id="e1d09-131">For the best user experience, we recommend you turn on MA in all four of these locations.</span></span> <span data-ttu-id="e1d09-132">Если вы не можете включить ma во всех этих расположениях, настройте действия, чтобы включить ma только в расположениях, необходимых для вашей среды.</span><span class="sxs-lookup"><span data-stu-id="e1d09-132">If you can't turn MA on in all these locations, adjust the steps so that you turn on MA only in the locations that are necessary for your environment.</span></span>
  
<span data-ttu-id="e1d09-133">[Поддерживаемыеpologies см.](https://technet.microsoft.com/library/mt803262.aspx) в разделе "Поддержка Skype для бизнеса с ma".</span><span class="sxs-lookup"><span data-stu-id="e1d09-133">See the [Supportability topic for Skype for Business with MA](https://technet.microsoft.com/library/mt803262.aspx) for supported topologies.</span></span>
  
 <span data-ttu-id="e1d09-134">**Важно!** Перед началом убедитесь, что выполнены все необходимые условия.</span><span class="sxs-lookup"><span data-stu-id="e1d09-134">**Important** Double-check that you've met all the prerequisites before you begin.</span></span> <span data-ttu-id="e1d09-135">Эти сведения можно найти в обзоре современной гибридной проверки подлинности [и предварительных условиях.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e1d09-135">You'll find that information in [Hybrid modern authentication overview and prerequisites](hybrid-modern-auth-overview.md).</span></span>
  
## <a name="collect-all-hma-specific-info-youll-need"></a><span data-ttu-id="e1d09-136">Соберйте все необходимые сведения о HMA</span><span class="sxs-lookup"><span data-stu-id="e1d09-136">Collect all HMA-specific info you'll need</span></span>

<span data-ttu-id="e1d09-137">После двойного проверки того, [](hybrid-modern-auth-overview.md) что вы соответствуете предварительным требованиям для использования современной проверки подлинности (см. примечание выше), необходимо создать файл, в который будут вместить сведения, необходимые для настройки HMA на шагах вперед.</span><span class="sxs-lookup"><span data-stu-id="e1d09-137">After you've double-checked that you meet the [prerequisites](hybrid-modern-auth-overview.md) to use Modern Authentication (see the note above), you should create a file to hold the info you'll need for configuring HMA in the steps ahead.</span></span> <span data-ttu-id="e1d09-138">Примеры, используемые в этой статье:</span><span class="sxs-lookup"><span data-stu-id="e1d09-138">Examples used in this article:</span></span>
  
- <span data-ttu-id="e1d09-139">**Домен SIP/SMTP**</span><span class="sxs-lookup"><span data-stu-id="e1d09-139">**SIP/SMTP domain**</span></span>

  - <span data-ttu-id="e1d09-140">Ex.</span><span class="sxs-lookup"><span data-stu-id="e1d09-140">Ex.</span></span> <span data-ttu-id="e1d09-141">contoso.com (федература с Office 365)</span><span class="sxs-lookup"><span data-stu-id="e1d09-141">contoso.com (is federated with Office 365)</span></span>

- <span data-ttu-id="e1d09-142">**Идентификатор клиента**</span><span class="sxs-lookup"><span data-stu-id="e1d09-142">**Tenant ID**</span></span>

  - <span data-ttu-id="e1d09-143">GUID, который представляет клиент Office 365 (при входе contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="e1d09-143">The GUID that represents your Office 365 tenant (at the login of contoso.onmicrosoft.com).</span></span>

- <span data-ttu-id="e1d09-144">**URL-адреса веб-службы SFB 2015 CU5**</span><span class="sxs-lookup"><span data-stu-id="e1d09-144">**SFB 2015 CU5 Web Service URLs**</span></span>

<span data-ttu-id="e1d09-145">Вам потребуется внутренний и внешний URL-адреса веб-служб для всех развернутых пулов SfB 2015.</span><span class="sxs-lookup"><span data-stu-id="e1d09-145">you'll need internal and external web service URLs for all SfB 2015 pools deployed.</span></span> <span data-ttu-id="e1d09-146">Чтобы получить эти данные, запустите в оболочке управления Skype для бизнеса следующее:</span><span class="sxs-lookup"><span data-stu-id="e1d09-146">To obtain these, run the following from Skype for Business Management Shell:</span></span>
  
```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- <span data-ttu-id="e1d09-147">Ex.</span><span class="sxs-lookup"><span data-stu-id="e1d09-147">Ex.</span></span> <span data-ttu-id="e1d09-148">Внутренний: https://lyncwebint01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e1d09-148">Internal: https://lyncwebint01.contoso.com</span></span>

- <span data-ttu-id="e1d09-149">Ex.</span><span class="sxs-lookup"><span data-stu-id="e1d09-149">Ex.</span></span> <span data-ttu-id="e1d09-150">Внешний: https://lyncwebext01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e1d09-150">External: https://lyncwebext01.contoso.com</span></span>

<span data-ttu-id="e1d09-151">Если вы используете сервер Standard Edition, внутренний URL-адрес будет пустым.</span><span class="sxs-lookup"><span data-stu-id="e1d09-151">If you're using a Standard Edition server, the internal URL will be blank.</span></span> <span data-ttu-id="e1d09-152">В этом случае используйте для внутреннего URL-адреса fqdn пула.</span><span class="sxs-lookup"><span data-stu-id="e1d09-152">In this case, use the pool fqdn for the internal URL.</span></span>
  
## <a name="turn-on-modern-authentication-for-exo"></a><span data-ttu-id="e1d09-153">Включить современную проверку подлинности для EXO</span><span class="sxs-lookup"><span data-stu-id="e1d09-153">Turn on Modern Authentication for EXO</span></span>

<span data-ttu-id="e1d09-154">Следуйте инструкциям в [Exchange Online: как](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx) включить современную проверку подлинности для клиента.</span><span class="sxs-lookup"><span data-stu-id="e1d09-154">Follow the instructions here: [Exchange Online: How to enable your tenant for modern authentication.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span></span>
  
## <a name="turn-on-modern-authentication-for-sfbo"></a><span data-ttu-id="e1d09-155">Включить современную проверку подлинности для SFBO</span><span class="sxs-lookup"><span data-stu-id="e1d09-155">Turn on Modern Authentication for SFBO</span></span>

<span data-ttu-id="e1d09-156">Следуйте инструкциям здесь: [Skype для бизнеса Online: включить современную](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)проверку подлинности для клиента.</span><span class="sxs-lookup"><span data-stu-id="e1d09-156">Follow the instructions here: [Skype for Business Online: Enable your tenant for modern authentication](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span>
  
## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a><span data-ttu-id="e1d09-157">Включить гибридную современную проверку подлинности для локальной системы Exchange</span><span class="sxs-lookup"><span data-stu-id="e1d09-157">Turn on Hybrid Modern Authentication for Exchange on-premises</span></span>

<span data-ttu-id="e1d09-158">Следуйте инструкциям здесь: как Exchange Server локально использовать гибридную современную [проверку подлинности.](configure-exchange-server-for-hybrid-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="e1d09-158">Follow the instructions here: [How to configure Exchange Server on-premises to use Hybrid Modern Authentication](configure-exchange-server-for-hybrid-modern-authentication.md).</span></span>
  
## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a><span data-ttu-id="e1d09-159">Turn on Hybrid Modern Authentication for Skype for Business on-premises</span><span class="sxs-lookup"><span data-stu-id="e1d09-159">Turn on Hybrid Modern Authentication for Skype for Business on-premises</span></span>

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a><span data-ttu-id="e1d09-160">Добавление URL-адресов локальной веб-службы в качестве SPNs в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e1d09-160">Add on-premises web service URLs as SPNs in Azure Active Directory</span></span>

<span data-ttu-id="e1d09-161">Теперь необходимо выполнить команды, чтобы добавить URL-адреса (собранные ранее) в качестве основных служб в SFBO.</span><span class="sxs-lookup"><span data-stu-id="e1d09-161">Now you'll need to run commands to add the URLs (collected earlier) as Service Principals in SFBO.</span></span>
  
 <span data-ttu-id="e1d09-162">**Примечание** Имена основных служб (SPNs) определяют веб-службы и связывают их с основными службами безопасности (например, именем учетной записи или группой), чтобы служба могли действовать от имени авторизованного пользователя.</span><span class="sxs-lookup"><span data-stu-id="e1d09-162">**Note** Service principal names (SPNs) identify web services and associate them with a security principal (such as an account name or group) so that the service can act on the behalf of an authorized user.</span></span> <span data-ttu-id="e1d09-163">Клиенты, которые используют проверку подлинности на сервере, используют сведения, содержащиеся в SPNs.</span><span class="sxs-lookup"><span data-stu-id="e1d09-163">Clients authenticating to a server make use of information that's contained in SPNs.</span></span>
  
1. <span data-ttu-id="e1d09-164">Сначала подключите к Azure Active Directory (Azure AD) с [помощью этих инструкций.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="e1d09-164">First, connect to Azure Active Directory (Azure AD) with [these instructions](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

2. <span data-ttu-id="e1d09-165">Чтобы получить список URL-адресов веб-службы SFB, запустите эту команду локально.</span><span class="sxs-lookup"><span data-stu-id="e1d09-165">Run this command, on-premises, to get a list of SFB web service URLs.</span></span>

   <span data-ttu-id="e1d09-166">Обратите внимание, что AppPrincipalId начинается с `00000004` .</span><span class="sxs-lookup"><span data-stu-id="e1d09-166">Note that the AppPrincipalId begins with `00000004`.</span></span> <span data-ttu-id="e1d09-167">Это соответствует Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e1d09-167">This corresponds to Skype for Business Online.</span></span>

   <span data-ttu-id="e1d09-168">Обратите внимание (и снимок экрана для более позднего сравнения) результатов этой команды, которые будут включать SE и URL-адрес WS, но в основном состоят из SPNs, которые начинаются `00000004-0000-0ff1-ce00-000000000000/` с .</span><span class="sxs-lookup"><span data-stu-id="e1d09-168">Take note of (and screenshot for later comparison) the output of this command, which will include an SE and WS URL, but mostly consist of SPNs that begin with `00000004-0000-0ff1-ce00-000000000000/`.</span></span>

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. <span data-ttu-id="e1d09-169">Если внутренние **или** внешние URL-адреса SFB из локальной системы отсутствуют (например, нам потребуется добавить эти записи в https://lyncwebint01.contoso.com этот https://lyncwebext01.contoso.com) список.</span><span class="sxs-lookup"><span data-stu-id="e1d09-169">If the internal **or** external SFB URLs from on-premises are missing (for example, https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com) we will need to add those specific records to this list.</span></span>

    <span data-ttu-id="e1d09-170">Не забудьте заменить  *url-адреса примера ниже* на фактические URL-адреса в командах "Добавить"!</span><span class="sxs-lookup"><span data-stu-id="e1d09-170">Be sure to replace  *the example URLs* below with your actual URLs in the Add commands!</span></span>
  
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```
  
4. <span data-ttu-id="e1d09-171">Убедитесь, что новые записи были добавлены, снова выпустив команду **Get-MsolServicePrincipal** из шага 2 и проверив выходные данные.</span><span class="sxs-lookup"><span data-stu-id="e1d09-171">Verify your new records were added by running the **Get-MsolServicePrincipal** command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="e1d09-172">Сравните список или снимок экрана с новым списком spNs.</span><span class="sxs-lookup"><span data-stu-id="e1d09-172">Compare the list or screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="e1d09-173">Вы также можете сделать снимок экрана с новым списком для ваших записей.</span><span class="sxs-lookup"><span data-stu-id="e1d09-173">You might also screenshot the new list for your records.</span></span> <span data-ttu-id="e1d09-174">В случае успеха вы увидите два новых URL-адреса в списке.</span><span class="sxs-lookup"><span data-stu-id="e1d09-174">If you were successful, you'll see the two new URLs in the list.</span></span> <span data-ttu-id="e1d09-175">В нашем примере список SPNs теперь будет включать определенные URL-адреса https://lyncwebint01.contoso.com и https://lyncwebext01.contoso.com/ .</span><span class="sxs-lookup"><span data-stu-id="e1d09-175">Going by our example, the list of SPNs will now include the specific URLs https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com/.</span></span>

### <a name="create-the-evosts-auth-server-object"></a><span data-ttu-id="e1d09-176">Создание объекта сервера веб-службы Веб-службы</span><span class="sxs-lookup"><span data-stu-id="e1d09-176">Create the EvoSTS Auth Server Object</span></span>

<span data-ttu-id="e1d09-177">Запустите следующую команду в командной оболочке Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e1d09-177">Run the following command in the Skype for Business Management Shell.</span></span>
  
```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a><span data-ttu-id="e1d09-178">Включить гибридную современную проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="e1d09-178">Enable Hybrid Modern Authentication</span></span>

<span data-ttu-id="e1d09-179">На этом этапе фактически включается ma.</span><span class="sxs-lookup"><span data-stu-id="e1d09-179">This is the step that actually turns on MA.</span></span> <span data-ttu-id="e1d09-180">Все предыдущие шаги можно выполнить заранее, не изменяя поток проверки подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="e1d09-180">All the previous steps can be run ahead of time without changing the client authentication flow.</span></span> <span data-ttu-id="e1d09-181">Когда вы будете готовы изменить поток проверки подлинности, запустите эту команду в командной оболочке Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e1d09-181">When you're ready to change the authentication flow, run this command in the Skype for Business Management Shell.</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a><span data-ttu-id="e1d09-182">Проверка</span><span class="sxs-lookup"><span data-stu-id="e1d09-182">Verify</span></span>

<span data-ttu-id="e1d09-183">После того как вы в включить HMA, следующий вход клиента будет использовать новый поток авторов.</span><span class="sxs-lookup"><span data-stu-id="e1d09-183">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="e1d09-184">Обратите внимание, что простое включение HMA не вызовет повторной оценки для любого клиента.</span><span class="sxs-lookup"><span data-stu-id="e1d09-184">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="e1d09-185">Клиенты повторно проавтоматируют их в зависимости от срока действия маркеров и/или сертификатов, которые у них есть.</span><span class="sxs-lookup"><span data-stu-id="e1d09-185">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>
  
<span data-ttu-id="e1d09-186">Чтобы проверить работу HMA после включения, выйдите из тестового клиента Windows SFB и нажмите кнопку "Удалить мои учетные данные".</span><span class="sxs-lookup"><span data-stu-id="e1d09-186">To test that HMA is working after you've enabled it, sign out of a test SFB Windows client and be sure to click 'delete my credentials'.</span></span> <span data-ttu-id="e1d09-187">Снова во входе.</span><span class="sxs-lookup"><span data-stu-id="e1d09-187">Sign in again.</span></span> <span data-ttu-id="e1d09-188">Теперь клиент должен использовать поток современной проверки право на проверку, и теперь для входа в систему будет включен запрос **Office 365** для учетной записи "Рабочий или учебный", который будет виден прямо перед тем, как клиент свянется с сервером и занося вас в систему.</span><span class="sxs-lookup"><span data-stu-id="e1d09-188">The client should now use the Modern Auth flow and your login will now include an **Office 365** prompt for a 'Work or school' account, seen right before the client contacts the server and logs you in.</span></span>
  
<span data-ttu-id="e1d09-189">Также следует проверить "Сведения о конфигурации" для клиентов Skype для бизнеса на "OAuth Authority".</span><span class="sxs-lookup"><span data-stu-id="e1d09-189">You should also check the 'Configuration Information' for Skype for Business Clients for an 'OAuth Authority'.</span></span> <span data-ttu-id="e1d09-190">Для этого на клиентских компьютерах удерживайте клавишу CTRL, щелкнув правой кнопкой мыши значок Skype для бизнеса в области уведомлений Windows.</span><span class="sxs-lookup"><span data-stu-id="e1d09-190">To do this on your client computer, hold down the CTRL key at the same time you right-click the Skype for Business Icon in the Windows Notification tray.</span></span> <span data-ttu-id="e1d09-191">Щелкните **"Сведения о** конфигурации" в меню.</span><span class="sxs-lookup"><span data-stu-id="e1d09-191">Click **Configuration Information** in the menu that appears.</span></span> <span data-ttu-id="e1d09-192">In the 'Skype for Business Configuration Information' window that will appear on the desktop, look for the following:</span><span class="sxs-lookup"><span data-stu-id="e1d09-192">In the 'Skype for Business Configuration Information' window that will appear on the desktop, look for the following:</span></span>
  
![The Configuration information of a Skype for Business Client using Modern Authentication shows a Lync and EWS OAUTH Authority URL of https://login.windows.net/common/oauth2/authorize .](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)
  
<span data-ttu-id="e1d09-194">Также следует удерживать клавишу CTRL одновременно с щелчком правой кнопкой мыши по значку клиента Outlook (также в области уведомлений Windows) и нажатием кнопки "Состояние подключения".</span><span class="sxs-lookup"><span data-stu-id="e1d09-194">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="e1d09-195">Наберем SMTP-адрес клиента по типу AuthN "Bearer", который представляет маркер носитера, используемый \* в OAuth.</span><span class="sxs-lookup"><span data-stu-id="e1d09-195">Look for the client's SMTP address against an AuthN type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="e1d09-196">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e1d09-196">Related articles</span></span>

<span data-ttu-id="e1d09-197">[Ссылка на обзор современной проверки подлинности.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e1d09-197">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md).</span></span>
  
<span data-ttu-id="e1d09-198">Нужно знать, как использовать современную проверку подлинности (ADAL) для клиентов Skype для бизнеса?</span><span class="sxs-lookup"><span data-stu-id="e1d09-198">Do you need to know how to use Modern Authentication (ADAL) for your Skype for Business clients?</span></span> <span data-ttu-id="e1d09-199">У нас есть по [шагам здесь.](https://technet.microsoft.com/library/mt710548.aspx)</span><span class="sxs-lookup"><span data-stu-id="e1d09-199">We've got steps [here](https://technet.microsoft.com/library/mt710548.aspx).</span></span>
