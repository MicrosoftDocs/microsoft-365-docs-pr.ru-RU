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
description: Узнайте, как настроить Skype для бизнеса для использования гибридной современной проверки подлинности (HMA), предлагая более безопасную проверку подлинности и авторизацию пользователей.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9695815d0a085931b10f7f64b9fca2e997af9077
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286061"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="1fdbf-103">Как настроить локальное развертывание Skype для бизнеса для использования гибридной современной проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="1fdbf-103">How to configure Skype for Business on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="1fdbf-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="1fdbf-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1fdbf-105">Современная проверка подлинности — это метод управления удостоверениями, который обеспечивает более безопасную проверку подлинности и авторизацию пользователей, доступен для локального сервера Skype для бизнеса и Exchange сервера, а также гибридов с раздельным доменом Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-105">Modern Authentication, is a method of identity management that offers more secure user authentication and authorization, is available for Skype for Business server on-premises and Exchange server on-premises, and split-domain Skype for Business hybrids.</span></span>

 <span data-ttu-id="1fdbf-106">**Важно** Хотите узнать больше о современной проверке подлинности и о том, почему вы можете использовать ее в своей компании или организации?</span><span class="sxs-lookup"><span data-stu-id="1fdbf-106">**Important** Would you like to know more about Modern Authentication (MA) and why you might prefer to use it in your company or organization?</span></span> <span data-ttu-id="1fdbf-107">Ознакомьтесь [с этим документом.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1fdbf-107">Check [this document](hybrid-modern-auth-overview.md) for an overview.</span></span> <span data-ttu-id="1fdbf-108">Если вам нужно знать, Skype для бизнеса топологии поддерживаются с помощью ma, это описано здесь!</span><span class="sxs-lookup"><span data-stu-id="1fdbf-108">If you need to know what Skype for Business topologies are supported with MA, that's documented here!</span></span>

 <span data-ttu-id="1fdbf-109">**Перед началом** работы я использую эти термины:</span><span class="sxs-lookup"><span data-stu-id="1fdbf-109">**Before we begin**, I use these terms:</span></span>

- <span data-ttu-id="1fdbf-110">Современная проверка подлинности (MA)</span><span class="sxs-lookup"><span data-stu-id="1fdbf-110">Modern Authentication (MA)</span></span>

- <span data-ttu-id="1fdbf-111">Гибридная современная проверка подлинности (HMA)</span><span class="sxs-lookup"><span data-stu-id="1fdbf-111">Hybrid Modern Authentication (HMA)</span></span>

- <span data-ttu-id="1fdbf-112">Exchange (EXCH)</span><span class="sxs-lookup"><span data-stu-id="1fdbf-112">Exchange on-premises (EXCH)</span></span>

- <span data-ttu-id="1fdbf-113">Exchange Online (EXO)</span><span class="sxs-lookup"><span data-stu-id="1fdbf-113">Exchange Online (EXO)</span></span>

- <span data-ttu-id="1fdbf-114">Skype для бизнеса локальной (SFB)</span><span class="sxs-lookup"><span data-stu-id="1fdbf-114">Skype for Business on-premises (SFB)</span></span>

- <span data-ttu-id="1fdbf-115">Skype для бизнеса Online (SFBO)</span><span class="sxs-lookup"><span data-stu-id="1fdbf-115">Skype for Business Online (SFBO)</span></span>

<span data-ttu-id="1fdbf-116">Кроме того, если на рисунке в этой статье имеется объект с серым  цветом или затемнеет, это означает, что элемент, показанный в сером цвете, не входит в конфигурацию, определенную ma.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-116">Also, if a graphic in this article has an object that's grayed-out or dimmed that means the element shown in gray **isn't** included in MA-specific configuration.</span></span>

## <a name="read-the-summary"></a><span data-ttu-id="1fdbf-117">Чтение сводки</span><span class="sxs-lookup"><span data-stu-id="1fdbf-117">Read the summary</span></span>

<span data-ttu-id="1fdbf-118">Это сводка разбивает процесс на действия, которые в противном случае могут потеряться во время выполнения, и хорошо для общего контрольного списка, чтобы отслеживать, где вы находитесь в процессе.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-118">This summary breaks down the process into steps that might otherwise get lost during the execution, and is good for an overall checklist to keep track of where you are in the process.</span></span>

1. <span data-ttu-id="1fdbf-119">Во-первых, убедитесь, что вы соответствуете всем необходимым требованиям.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-119">First, make sure you meet all the prerequisites.</span></span>

1. <span data-ttu-id="1fdbf-120">Поскольку **многие обязательные** условия являются общими как для Skype для бизнеса, так и для Exchange, см. статью обзор для списка [предварительного переопреставки](hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1fdbf-120">Since many **prerequisites** are common for both Skype for Business and Exchange, [see the overview article for your pre-req checklist](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="1fdbf-121">Сделайте  *это,*  прежде чем приступить к любым шагам в этой статье.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-121">Do this  *before*  you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="1fdbf-122">Сбор информации, определенной для HMA, в файле или OneNote.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-122">Collect the HMA-specific info you'll need in a file, or OneNote.</span></span>

1. <span data-ttu-id="1fdbf-123">Включи современную проверку подлинности для EXO (если она еще не включена).</span><span class="sxs-lookup"><span data-stu-id="1fdbf-123">Turn ON Modern Authentication for EXO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="1fdbf-124">Включи современную проверку подлинности для SFBO (если она еще не включена).</span><span class="sxs-lookup"><span data-stu-id="1fdbf-124">Turn ON Modern Authentication for SFBO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="1fdbf-125">Включи гибридную современную проверку подлинности Exchange локально.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-125">Turn ON Hybrid Modern Authentication for Exchange on-premises.</span></span>

1. <span data-ttu-id="1fdbf-126">Включи гибридную современную проверку подлинности Skype для бизнеса локально.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-126">Turn ON Hybrid Modern Authentication for Skype for Business on-premises.</span></span>

<span data-ttu-id="1fdbf-127">Эти действия включаем ma для SFB, SFBO, EXCH и EXO , то есть все продукты, которые могут участвовать в конфигурации HMA SFB и SFBO (включая зависимости от EXCH/EXO).</span><span class="sxs-lookup"><span data-stu-id="1fdbf-127">These steps turn on MA for SFB, SFBO, EXCH, and EXO - that is, all the products that can participate in an HMA configuration of SFB and SFBO (including dependencies on EXCH/EXO).</span></span> <span data-ttu-id="1fdbf-128">Другими словами, если ваши пользователи находятся в почтовых ящиках, созданных в любой части гибрида (EXO + SFBO, EXO + SFB, EXCH + SFBO или EXCH + SFB), готовый продукт будет выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="1fdbf-128">In other words, if your users are homed in/have mailboxes created in any part of the Hybrid (EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB), your finished product will look like this:</span></span>

![Топология смешанных 6 Skype для бизнеса HMA имеет ma во всех четырех возможных расположениях.](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)

<span data-ttu-id="1fdbf-130">Как видите, есть четыре разных места для включаемой магистрали!</span><span class="sxs-lookup"><span data-stu-id="1fdbf-130">As you can see there are four different places to turn on MA!</span></span> <span data-ttu-id="1fdbf-131">Для наилучшего пользовательского интерфейса рекомендуется включить ma во всех четырех этих расположениях.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-131">For the best user experience, we recommend you turn on MA in all four of these locations.</span></span> <span data-ttu-id="1fdbf-132">Если вы не можете включить ma во всех этих расположениях, отрегулировать действия так, чтобы включить MA только в местах, необходимых для вашей среды.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-132">If you can't turn MA on in all these locations, adjust the steps so that you turn on MA only in the locations that are necessary for your environment.</span></span>

<span data-ttu-id="1fdbf-133">См. [раздел Поддержка для Skype для бизнеса с ma](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported) для поддерживаемых топологий.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-133">See the [Supportability topic for Skype for Business with MA](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported) for supported topologies.</span></span>

 <span data-ttu-id="1fdbf-134">**Важно** Дважды убедитесь, что перед началом работы вы выполнили все необходимые условия.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-134">**Important** Double-check that you've met all the prerequisites before you begin.</span></span> <span data-ttu-id="1fdbf-135">Вы найдете эту информацию в [обзоре современной гибридной проверки подлинности и необходимых данных.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1fdbf-135">You'll find that information in [Hybrid modern authentication overview and prerequisites](hybrid-modern-auth-overview.md).</span></span>

## <a name="collect-all-hma-specific-info-youll-need"></a><span data-ttu-id="1fdbf-136">Сбор всех необходимых для HMA данных</span><span class="sxs-lookup"><span data-stu-id="1fdbf-136">Collect all HMA-specific info you'll need</span></span>

<span data-ttu-id="1fdbf-137">После того как вы дважды [](hybrid-modern-auth-overview.md) проверили, соответствуют ли вам необходимые условия для использования современной проверки подлинности (см. примечание выше), необходимо создать файл для удержания информации, необходимой для настройки HMA на шагах вперед.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-137">After you've double-checked that you meet the [prerequisites](hybrid-modern-auth-overview.md) to use Modern Authentication (see the note above), you should create a file to hold the info you'll need for configuring HMA in the steps ahead.</span></span> <span data-ttu-id="1fdbf-138">Примеры, используемые в этой статье:</span><span class="sxs-lookup"><span data-stu-id="1fdbf-138">Examples used in this article:</span></span>

- <span data-ttu-id="1fdbf-139">**Домен SIP/SMTP**</span><span class="sxs-lookup"><span data-stu-id="1fdbf-139">**SIP/SMTP domain**</span></span>

  - <span data-ttu-id="1fdbf-140">Ex.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-140">Ex.</span></span> <span data-ttu-id="1fdbf-141">contoso.com (федерален с Office 365)</span><span class="sxs-lookup"><span data-stu-id="1fdbf-141">contoso.com (is federated with Office 365)</span></span>

- <span data-ttu-id="1fdbf-142">**Идентификатор клиента**</span><span class="sxs-lookup"><span data-stu-id="1fdbf-142">**Tenant ID**</span></span>

  - <span data-ttu-id="1fdbf-143">GUID, который представляет Office 365 клиента (на входе contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="1fdbf-143">The GUID that represents your Office 365 tenant (at the login of contoso.onmicrosoft.com).</span></span>

- <span data-ttu-id="1fdbf-144">**URL-адреса веб-службы CU5 2015**</span><span class="sxs-lookup"><span data-stu-id="1fdbf-144">**SFB 2015 CU5 Web Service URLs**</span></span>

<span data-ttu-id="1fdbf-145">Для всех развернутых пулов SfB 2015 вам потребуется URL-адреса внутренних и внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-145">you'll need internal and external web service URLs for all SfB 2015 pools deployed.</span></span> <span data-ttu-id="1fdbf-146">Чтобы получить эти данные, запустите следующее из Skype для бизнеса Management Shell:</span><span class="sxs-lookup"><span data-stu-id="1fdbf-146">To obtain these, run the following from Skype for Business Management Shell:</span></span>

```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- <span data-ttu-id="1fdbf-147">Ex.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-147">Ex.</span></span> <span data-ttu-id="1fdbf-148">Внутренние: https://lyncwebint01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fdbf-148">Internal: https://lyncwebint01.contoso.com</span></span>

- <span data-ttu-id="1fdbf-149">Ex.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-149">Ex.</span></span> <span data-ttu-id="1fdbf-150">Внешний: https://lyncwebext01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1fdbf-150">External: https://lyncwebext01.contoso.com</span></span>

<span data-ttu-id="1fdbf-151">Если вы используете сервер выпуск Standard, внутренний URL-адрес будет пустым.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-151">If you're using a Standard Edition server, the internal URL will be blank.</span></span> <span data-ttu-id="1fdbf-152">В этом случае используйте fqdn пула для внутреннего URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-152">In this case, use the pool fqdn for the internal URL.</span></span>

## <a name="turn-on-modern-authentication-for-exo"></a><span data-ttu-id="1fdbf-153">Включить современную проверку подлинности для EXO</span><span class="sxs-lookup"><span data-stu-id="1fdbf-153">Turn on Modern Authentication for EXO</span></span>

<span data-ttu-id="1fdbf-154">Следуйте инструкциям здесь: Exchange Online: как включить клиента [для современной проверки подлинности.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span><span class="sxs-lookup"><span data-stu-id="1fdbf-154">Follow the instructions here: [Exchange Online: How to enable your tenant for modern authentication.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span></span>

## <a name="turn-on-modern-authentication-for-sfbo"></a><span data-ttu-id="1fdbf-155">Включить современную проверку подлинности для SFBO</span><span class="sxs-lookup"><span data-stu-id="1fdbf-155">Turn on Modern Authentication for SFBO</span></span>

<span data-ttu-id="1fdbf-156">Следуйте инструкциям здесь: [Skype для бизнеса Online: Включить клиента для современной проверки подлинности.](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</span><span class="sxs-lookup"><span data-stu-id="1fdbf-156">Follow the instructions here: [Skype for Business Online: Enable your tenant for modern authentication](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span>

## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a><span data-ttu-id="1fdbf-157">Включи гибридную современную проверку подлинности для Exchange локальной</span><span class="sxs-lookup"><span data-stu-id="1fdbf-157">Turn on Hybrid Modern Authentication for Exchange on-premises</span></span>

<span data-ttu-id="1fdbf-158">Следуйте инструкциям здесь. Как настроить Exchange Server [локальное использование гибридной современной проверки подлинности.](configure-exchange-server-for-hybrid-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="1fdbf-158">Follow the instructions here: [How to configure Exchange Server on-premises to use Hybrid Modern Authentication](configure-exchange-server-for-hybrid-modern-authentication.md).</span></span>

## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a><span data-ttu-id="1fdbf-159">Включи гибридную современную проверку подлинности для Skype для бизнеса локальной</span><span class="sxs-lookup"><span data-stu-id="1fdbf-159">Turn on Hybrid Modern Authentication for Skype for Business on-premises</span></span>

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a><span data-ttu-id="1fdbf-160">Добавление URL-адресов веб-службы на локальной основе в качестве СНО в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1fdbf-160">Add on-premises web service URLs as SPNs in Azure Active Directory</span></span>

<span data-ttu-id="1fdbf-161">Теперь вам потребуется выполнить команды, чтобы добавить URL-адреса (собранные ранее) в качестве главных служб в SFBO.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-161">Now you'll need to run commands to add the URLs (collected earlier) as Service Principals in SFBO.</span></span>

 <span data-ttu-id="1fdbf-162">**Примечание** Имена основных служб (SPNs) определяют веб-службы и связывают их с главными службами безопасности (например, именем учетной записи или группой), чтобы служба действовала от имени уполномоченного пользователя.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-162">**Note** Service principal names (SPNs) identify web services and associate them with a security principal (such as an account name or group) so that the service can act on the behalf of an authorized user.</span></span> <span data-ttu-id="1fdbf-163">Клиенты, проверка подлинности на сервере, используют сведения, содержащиеся в spNs.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-163">Clients authenticating to a server make use of information that's contained in SPNs.</span></span>

1. <span data-ttu-id="1fdbf-164">Во-первых, подключите Azure Active Directory (Azure AD) с [этими инструкциями.](/powershell/azure/active-directory/overview)</span><span class="sxs-lookup"><span data-stu-id="1fdbf-164">First, connect to Azure Active Directory (Azure AD) with [these instructions](/powershell/azure/active-directory/overview).</span></span>

2. <span data-ttu-id="1fdbf-165">Запустите эту команду локально, чтобы получить список URL-адресов веб-службы SFB.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-165">Run this command, on-premises, to get a list of SFB web service URLs.</span></span>

   <span data-ttu-id="1fdbf-166">Обратите внимание, что AppPrincipalId начинается с `00000004` .</span><span class="sxs-lookup"><span data-stu-id="1fdbf-166">Note that the AppPrincipalId begins with `00000004`.</span></span> <span data-ttu-id="1fdbf-167">Это соответствует Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-167">This corresponds to Skype for Business Online.</span></span>

   <span data-ttu-id="1fdbf-168">Обратите внимание (и снимок экрана для более позднего сравнения) вывода этой команды, которая будет включать URL-адрес SE и WS, но в основном состоят из spNs, которые начинаются с `00000004-0000-0ff1-ce00-000000000000/` .</span><span class="sxs-lookup"><span data-stu-id="1fdbf-168">Take note of (and screenshot for later comparison) the output of this command, which will include an SE and WS URL, but mostly consist of SPNs that begin with `00000004-0000-0ff1-ce00-000000000000/`.</span></span>

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. <span data-ttu-id="1fdbf-169">Если **внутренние** или внешние URL-адреса SFB из локального помещения отсутствуют (например, нам потребуется добавить эти конкретные записи в этот https://lyncwebint01.contoso.com https://lyncwebext01.contoso.com) список.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-169">If the internal **or** external SFB URLs from on-premises are missing (for example, https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com) we will need to add those specific records to this list.</span></span>

    <span data-ttu-id="1fdbf-170">Не забудьте заменить  *ниже пример URL-адресов* фактическими URL-адресами в командах Добавить!</span><span class="sxs-lookup"><span data-stu-id="1fdbf-170">Be sure to replace  *the example URLs* below with your actual URLs in the Add commands!</span></span>

```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```

4. <span data-ttu-id="1fdbf-171">Убедитесь, что новые записи были добавлены путем запуска команды **Get-MsolServicePrincipal** со 2-го шага и проверки вывода.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-171">Verify your new records were added by running the **Get-MsolServicePrincipal** command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="1fdbf-172">Сравните список или снимок экрана до нового списка spNs.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-172">Compare the list or screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="1fdbf-173">Вы также можете сделать снимок экрана нового списка для записей.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-173">You might also screenshot the new list for your records.</span></span> <span data-ttu-id="1fdbf-174">Если вы успешно, вы увидите два новых URL-адреса в списке.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-174">If you were successful, you'll see the two new URLs in the list.</span></span> <span data-ttu-id="1fdbf-175">В нашем примере список СНО теперь будет включать конкретные https://lyncwebint01.contoso.com URL-адреса и https://lyncwebext01.contoso.com/ .</span><span class="sxs-lookup"><span data-stu-id="1fdbf-175">Going by our example, the list of SPNs will now include the specific URLs https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com/.</span></span>

### <a name="create-the-evosts-auth-server-object"></a><span data-ttu-id="1fdbf-176">Создание объекта Auth Server EvoSTS</span><span class="sxs-lookup"><span data-stu-id="1fdbf-176">Create the EvoSTS Auth Server Object</span></span>

<span data-ttu-id="1fdbf-177">Запустите следующую команду в командной Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-177">Run the following command in the Skype for Business Management Shell.</span></span>

```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a><span data-ttu-id="1fdbf-178">Включить гибридную современную проверку подлинности</span><span class="sxs-lookup"><span data-stu-id="1fdbf-178">Enable Hybrid Modern Authentication</span></span>

<span data-ttu-id="1fdbf-179">Это шаг, который фактически включает ma.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-179">This is the step that actually turns on MA.</span></span> <span data-ttu-id="1fdbf-180">Все предыдущие действия можно выполнить заранее, не изменяя поток проверки подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-180">All the previous steps can be run ahead of time without changing the client authentication flow.</span></span> <span data-ttu-id="1fdbf-181">Когда вы будете готовы изменить поток проверки подлинности, запустите эту команду в командной Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-181">When you're ready to change the authentication flow, run this command in the Skype for Business Management Shell.</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a><span data-ttu-id="1fdbf-182">Проверка</span><span class="sxs-lookup"><span data-stu-id="1fdbf-182">Verify</span></span>

<span data-ttu-id="1fdbf-183">После встраив HMA, следующий вход клиента будет использовать новый поток auth.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-183">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="1fdbf-184">Обратите внимание, что включение HMA не вызовет повторной оценки для любого клиента.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-184">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="1fdbf-185">Клиенты повторно обнародуются в зависимости от срока службы маркеров auth и/или сертификатов, которые у них есть.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-185">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="1fdbf-186">Чтобы проверить, работает ли HMA после включения, выйдите из тестового клиента SFB Windows и нажмите кнопку "Удалить учетные данные".</span><span class="sxs-lookup"><span data-stu-id="1fdbf-186">To test that HMA is working after you've enabled it, sign out of a test SFB Windows client and be sure to click 'delete my credentials'.</span></span> <span data-ttu-id="1fdbf-187">Войми снова.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-187">Sign in again.</span></span> <span data-ttu-id="1fdbf-188">Теперь клиент должен использовать поток modern **Auth,** и теперь в вашем входе будет Office 365 для учетной записи "Работа или школа", которая будет видна перед тем, как клиент свянется с сервером и войдите в него.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-188">The client should now use the Modern Auth flow and your login will now include an **Office 365** prompt for a 'Work or school' account, seen right before the client contacts the server and logs you in.</span></span>

<span data-ttu-id="1fdbf-189">Также необходимо проверить "Сведения о конфигурации" для Skype для бизнеса клиентов для "OAuth Authority".</span><span class="sxs-lookup"><span data-stu-id="1fdbf-189">You should also check the 'Configuration Information' for Skype for Business Clients for an 'OAuth Authority'.</span></span> <span data-ttu-id="1fdbf-190">Чтобы сделать это на клиентской компьютере, удерживайте клавишу CTRL, щелкнув правой кнопкой мыши значок Skype для бизнеса в подносе Windows уведомления.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-190">To do this on your client computer, hold down the CTRL key at the same time you right-click the Skype for Business Icon in the Windows Notification tray.</span></span> <span data-ttu-id="1fdbf-191">Щелкните **Сведения о конфигурации** в меню, которое отображается.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-191">Click **Configuration Information** in the menu that appears.</span></span> <span data-ttu-id="1fdbf-192">В окне "Skype для бизнеса конфигурации", которое появится на рабочем столе, посмотрите на следующее:</span><span class="sxs-lookup"><span data-stu-id="1fdbf-192">In the 'Skype for Business Configuration Information' window that will appear on the desktop, look for the following:</span></span>

![Сведения о конфигурации клиента Skype для бизнеса с помощью современной проверки подлинности показывают URL-адрес Lync и EWS OAUTH Authority https://login.windows.net/common/oauth2/authorize .](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)

<span data-ttu-id="1fdbf-194">Кроме того, необходимо удерживать клавишу CTRL одновременно с правой кнопкой мыши значок для клиента Outlook (также в подносе Windows уведомлений) и нажмите кнопку "Состояние подключения".</span><span class="sxs-lookup"><span data-stu-id="1fdbf-194">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="1fdbf-195">Иском адрес SMTP клиента в отношении типа AuthN 'Bearer', который представляет маркер носители, используемый \* в OAuth.</span><span class="sxs-lookup"><span data-stu-id="1fdbf-195">Look for the client's SMTP address against an AuthN type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

## <a name="related-articles"></a><span data-ttu-id="1fdbf-196">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="1fdbf-196">Related articles</span></span>

<span data-ttu-id="1fdbf-197">[Ссылка на обзор современной проверки подлинности.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1fdbf-197">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md).</span></span>

<span data-ttu-id="1fdbf-198">Нужно ли знать, как использовать современную проверку подлинности (ADAL) для Skype для бизнеса клиентов?</span><span class="sxs-lookup"><span data-stu-id="1fdbf-198">Do you need to know how to use Modern Authentication (ADAL) for your Skype for Business clients?</span></span> <span data-ttu-id="1fdbf-199">У нас есть шаги [здесь](./hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1fdbf-199">We've got steps [here](./hybrid-modern-auth-overview.md).</span></span>