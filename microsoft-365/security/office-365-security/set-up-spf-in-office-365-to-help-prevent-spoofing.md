---
title: Настройка SPF для предотвращения спуфинга
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как обновить запись службы доменных имен (DNS), чтобы использовать инфраструктуру политики отправителей (SPF) с личным доменом в Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 828d76b95a1e3f8d1a1851121d28603a1922f486
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538991"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a><span data-ttu-id="42f5e-103">Настройка SPF для предотвращения спуфинга</span><span class="sxs-lookup"><span data-stu-id="42f5e-103">Set up SPF to help prevent spoofing</span></span>

- [<span data-ttu-id="42f5e-104">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="42f5e-104">Prerequisites</span></span>](#prerequisites)
- [<span data-ttu-id="42f5e-105">Создание или обновление записи SPF TXT</span><span class="sxs-lookup"><span data-stu-id="42f5e-105">Create or update your SPF TXT record</span></span>](#create-or-update-your-spf-txt-record)
- [<span data-ttu-id="42f5e-106">Как работать с поддоменами?</span><span class="sxs-lookup"><span data-stu-id="42f5e-106">How to handle subdomains?</span></span>](#how-to-handle-subdomains)
- [<span data-ttu-id="42f5e-107">Устранение неполадок инфраструктуры политики отправителей</span><span class="sxs-lookup"><span data-stu-id="42f5e-107">Troubleshooting SPF</span></span>](#troubleshooting-spf)

<!--
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Applies to**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 plan 1 and plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)
-->

<span data-ttu-id="42f5e-108">В этой статье описано, как обновить запись DNS, чтобы использовать проверку подлинности электронной почты в инфраструктуре политики отправителей (SPF) с личным доменом в Office 365.</span><span class="sxs-lookup"><span data-stu-id="42f5e-108">This article describes how to update a Domain Name Service (DNS) record so that you can use Sender Policy Framework (SPF)  email authentication with your custom domain in Office 365.</span></span>

<span data-ttu-id="42f5e-109">С помощью инфраструктуры политики отправителей можно *проверять* исходящую почту, отправляемую из личного домена (который указан).</span><span class="sxs-lookup"><span data-stu-id="42f5e-109">SPF helps *validate* outbound email sent from your custom domain (is coming from who it says it is).</span></span> <span data-ttu-id="42f5e-110">Это первый шаг в настройке всех рекомендуемых методов проверки подлинности электронной почты для инфраструктуры политики отправителей, [DKIM](use-dkim-to-validate-outbound-email.md)и [DMARC](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="42f5e-110">It's a first step in setting up the full recommended email authentication methods of SPF, [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md).</span></span>

- [<span data-ttu-id="42f5e-111">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="42f5e-111">Prerequisites</span></span>](#prerequisites)
- [<span data-ttu-id="42f5e-112">Создание или обновление записи SPF TXT</span><span class="sxs-lookup"><span data-stu-id="42f5e-112">Create or update your SPF TXT record</span></span>](#create-or-update-your-spf-txt-record)
  - [<span data-ttu-id="42f5e-113">Как работать с поддоменами?</span><span class="sxs-lookup"><span data-stu-id="42f5e-113">How to handle subdomains?</span></span>](#how-to-handle-subdomains)
- [<span data-ttu-id="42f5e-114">Какие действия выполняет проверка подлинности электронной почты инфраструктуры политики отправителей?</span><span class="sxs-lookup"><span data-stu-id="42f5e-114">What does SPF email authentication actually do?</span></span>](#what-does-spf-email-authentication-actually-do)
  - [<span data-ttu-id="42f5e-115">Устранение неполадок инфраструктуры политики отправителей</span><span class="sxs-lookup"><span data-stu-id="42f5e-115">Troubleshooting SPF</span></span>](#troubleshooting-spf)
- [<span data-ttu-id="42f5e-116">Дополнительные сведения об инфраструктуре политики отправителей</span><span class="sxs-lookup"><span data-stu-id="42f5e-116">More information about SPF</span></span>](#more-information-about-spf)

## <a name="prerequisites"></a><span data-ttu-id="42f5e-117">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="42f5e-117">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42f5e-118">Если вы управляете **малым предприятием** или не знакомы с IP-адресами и настройкой DNS, обратитесь к своему регистратору доменных имен (например,</span><span class="sxs-lookup"><span data-stu-id="42f5e-118">If you are a **small business**, or are unfamiliar with IP addresses or DNS configuration, call your Internet domain registrar (ex.</span></span> <span data-ttu-id="42f5e-119">GoDaddy, Bluehost, web.com) за помощью с настройкой *DNS в SPF* (и любых других методов проверки подлинности электронной почты).</span><span class="sxs-lookup"><span data-stu-id="42f5e-119">GoDaddy, Bluehost, web.com) & ask for help with *DNS configuration of SPF* (and any other email authentication method).</span></span> <p> <span data-ttu-id="42f5e-120">**Если вы не используете настраиваемый URL-адрес** (а URL-адрес, используемый для Office 365 заканчивается на **onmicrosoft.com**), инфраструктура политики отправителей уже настроена для вас в службе Office 365.</span><span class="sxs-lookup"><span data-stu-id="42f5e-120">**If you don't use a custom URL** (and the URL used for Office 365 ends in **onmicrosoft.com**), SPF has already been set up for you in the Office 365 service.</span></span>

<span data-ttu-id="42f5e-121">Итак, приступим!</span><span class="sxs-lookup"><span data-stu-id="42f5e-121">Let's get started.</span></span>

<span data-ttu-id="42f5e-122">Запись SPF TXT для Office 365 будет сделана во внешней службе DNS для любых пользовательских доменов или поддоменов.</span><span class="sxs-lookup"><span data-stu-id="42f5e-122">The SPF TXT record for Office 365 will be made in external DNS for any custom domains or subdomains.</span></span> <span data-ttu-id="42f5e-123">Для записи необходимы некоторые сведения.</span><span class="sxs-lookup"><span data-stu-id="42f5e-123">You need some information to make the record.</span></span> <span data-ttu-id="42f5e-124">Подготовьте указанные ниже данные.</span><span class="sxs-lookup"><span data-stu-id="42f5e-124">Gather this information:</span></span>

- <span data-ttu-id="42f5e-125">Запись SPF TXT для личного домена, если он существует.</span><span class="sxs-lookup"><span data-stu-id="42f5e-125">The SPF TXT record for your custom domain, if one exists.</span></span> <span data-ttu-id="42f5e-126">Инструкции см. в статье [Сбор необходимых сведений для создания DNS-записей Office 365](../../admin/get-help-with-domains/information-for-dns-records.md).</span><span class="sxs-lookup"><span data-stu-id="42f5e-126">For instructions, see [Gather the information you need to create Office 365 DNS records](../../admin/get-help-with-domains/information-for-dns-records.md).</span></span>

- <span data-ttu-id="42f5e-127">Перейдите на свой сервер обмена сообщениями и найдите внешние IP-адреса (требуются со всех локальных серверов обмена сообщениями).</span><span class="sxs-lookup"><span data-stu-id="42f5e-127">Go to your messaging server(s) and find out the External IP addresses (needed from all on-premises messaging servers).</span></span> <span data-ttu-id="42f5e-128">Например, **131.107.2.200**.</span><span class="sxs-lookup"><span data-stu-id="42f5e-128">For example, **131.107.2.200**.</span></span>

- <span data-ttu-id="42f5e-p106">Доменные имена, используемые для всех сторонних доменов, которые требуется включить в запись SPF TXT. Некоторые поставщики массовых рассылок настраивают поддомены для своих клиентов. Например, компания MailChimp создала поддомен **servers.mcsv.net**.</span><span class="sxs-lookup"><span data-stu-id="42f5e-p106">Domain names to use for all third-party domains that you need to include in your SPF TXT record. Some bulk mail providers have set up subdomains to use for their customers. For example, the company MailChimp has set up **servers.mcsv.net**.</span></span>

- <span data-ttu-id="42f5e-132">Определите, какое правило принудительного применения следует использовать для записи SPF TXT.</span><span class="sxs-lookup"><span data-stu-id="42f5e-132">Figure out what enforcement rule you want to use for your SPF TXT record.</span></span> <span data-ttu-id="42f5e-133">Рекомендуется использовать правило **-all**.</span><span class="sxs-lookup"><span data-stu-id="42f5e-133">The **-all** rule is recommended.</span></span> <span data-ttu-id="42f5e-134">Подробные сведения о других вариантах команд см. в разделе [Синтаксис записи SPF TXT для Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).</span><span class="sxs-lookup"><span data-stu-id="42f5e-134">For detailed information about other syntax options, see [SPF TXT record syntax for Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42f5e-135">Чтобы использовать личный домен в Office 365, в запись DNS необходимо добавить запись SPF TXT для предотвращения спуфинга.</span><span class="sxs-lookup"><span data-stu-id="42f5e-135">In order to use a custom domain, Office 365 requires that you add a Sender Policy Framework (SPF) TXT record to your DNS record to help prevent spoofing.</span></span>

## <a name="create-or-update-your-spf-txt-record"></a><span data-ttu-id="42f5e-136">Создание или обновление записи SPF TXT</span><span class="sxs-lookup"><span data-stu-id="42f5e-136">Create or update your SPF TXT record</span></span>

1. <span data-ttu-id="42f5e-137">Убедитесь, что вы знакомы с синтаксисом SPF из следующей таблицы.</span><span class="sxs-lookup"><span data-stu-id="42f5e-137">Ensure that you're familiar with the SPF syntax in the following table.</span></span>

   ****

   |<span data-ttu-id="42f5e-138">Элемент</span><span class="sxs-lookup"><span data-stu-id="42f5e-138">Element</span></span>|<span data-ttu-id="42f5e-139">Используемая система</span><span class="sxs-lookup"><span data-stu-id="42f5e-139">If you're using...</span></span>|<span data-ttu-id="42f5e-140">Распространенная у клиентов?</span><span class="sxs-lookup"><span data-stu-id="42f5e-140">Common for customers?</span></span>|<span data-ttu-id="42f5e-141">Добавляемый параметр</span><span class="sxs-lookup"><span data-stu-id="42f5e-141">Add this...</span></span>|
   |---|---|---|---|
   |<span data-ttu-id="42f5e-142">1</span><span class="sxs-lookup"><span data-stu-id="42f5e-142">1</span></span>|<span data-ttu-id="42f5e-143">Любая почтовая система (обязательно)</span><span class="sxs-lookup"><span data-stu-id="42f5e-143">Any email system (required)</span></span>|<span data-ttu-id="42f5e-p108">Распространенная. Все записи SPF TXT начинаются с этого значения</span><span class="sxs-lookup"><span data-stu-id="42f5e-p108">Common. All SPF TXT records start with this value</span></span>|`v=spf1`|
   |<span data-ttu-id="42f5e-146">2</span><span class="sxs-lookup"><span data-stu-id="42f5e-146">2</span></span>|<span data-ttu-id="42f5e-147">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="42f5e-147">Exchange Online</span></span>|<span data-ttu-id="42f5e-148">Распространенная</span><span class="sxs-lookup"><span data-stu-id="42f5e-148">Common</span></span>|`include:spf.protection.outlook.com`|
   |<span data-ttu-id="42f5e-149">3</span><span class="sxs-lookup"><span data-stu-id="42f5e-149">3</span></span>|<span data-ttu-id="42f5e-150">Только для Exchange Online</span><span class="sxs-lookup"><span data-stu-id="42f5e-150">Exchange Online dedicated only</span></span>|<span data-ttu-id="42f5e-151">Нераспространенная</span><span class="sxs-lookup"><span data-stu-id="42f5e-151">Not common</span></span>|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
   |<span data-ttu-id="42f5e-152">4</span><span class="sxs-lookup"><span data-stu-id="42f5e-152">4</span></span>|<span data-ttu-id="42f5e-153">Office 365 Germany, только Microsoft Cloud Germany</span><span class="sxs-lookup"><span data-stu-id="42f5e-153">Office 365 Germany, Microsoft Cloud Germany only</span></span>|<span data-ttu-id="42f5e-154">Нераспространенная</span><span class="sxs-lookup"><span data-stu-id="42f5e-154">Not common</span></span>|`include:spf.protection.outlook.de`|
   |<span data-ttu-id="42f5e-155">5</span><span class="sxs-lookup"><span data-stu-id="42f5e-155">5</span></span>|<span data-ttu-id="42f5e-156">Сторонняя почтовая система</span><span class="sxs-lookup"><span data-stu-id="42f5e-156">Third-party email system</span></span>|<span data-ttu-id="42f5e-157">Нераспространенная</span><span class="sxs-lookup"><span data-stu-id="42f5e-157">Not common</span></span>|`include:<domain_name>` <p> <span data-ttu-id="42f5e-158">\<domain_name\> — это домен сторонней почтовой системы.</span><span class="sxs-lookup"><span data-stu-id="42f5e-158">\<domain_name\> is the domain of the third-party email system.</span></span>|
   |<span data-ttu-id="42f5e-159">6</span><span class="sxs-lookup"><span data-stu-id="42f5e-159">6</span></span>|<span data-ttu-id="42f5e-p109">Локальная почтовая система, например Exchange Online Protection с другой почтовой системой</span><span class="sxs-lookup"><span data-stu-id="42f5e-p109">On-premises email system. For example, Exchange Online Protection plus another email system</span></span>|<span data-ttu-id="42f5e-162">Нераспространенная</span><span class="sxs-lookup"><span data-stu-id="42f5e-162">Not common</span></span>|<span data-ttu-id="42f5e-163">Используйте один из следующих параметров для каждой дополнительной почтовой системы:</span><span class="sxs-lookup"><span data-stu-id="42f5e-163">Use one of these for each additional mail system:</span></span> <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> <span data-ttu-id="42f5e-164">\<IP_address\> и \<domain_name\> — это IP-адрес и домен другой почтовой системы, отправляющей почту от имени вашего домена.</span><span class="sxs-lookup"><span data-stu-id="42f5e-164">\<IP_address\> and \<domain_name\> are the IP address and domain of the other email system that sends mail on behalf of your domain.</span></span>|
   |<span data-ttu-id="42f5e-165">7</span><span class="sxs-lookup"><span data-stu-id="42f5e-165">7</span></span>|<span data-ttu-id="42f5e-166">Любая почтовая система (обязательно)</span><span class="sxs-lookup"><span data-stu-id="42f5e-166">Any email system (required)</span></span>|<span data-ttu-id="42f5e-p110">Распространенная. Все записи SPF TXT заканчиваются этим значением</span><span class="sxs-lookup"><span data-stu-id="42f5e-p110">Common. All SPF TXT records end with this value</span></span>|`<enforcement rule>` <p> <span data-ttu-id="42f5e-169">Это может быть одно из нескольких значений.</span><span class="sxs-lookup"><span data-stu-id="42f5e-169">This can be one of several values.</span></span> <span data-ttu-id="42f5e-170">Рекомендуется значение `-all`.</span><span class="sxs-lookup"><span data-stu-id="42f5e-170">We recommend the value `-all`.</span></span>|
   |

2. <span data-ttu-id="42f5e-171">Создайте запись SPF TXT (если вы еще не сделали этого), используя синтаксис из таблицы.</span><span class="sxs-lookup"><span data-stu-id="42f5e-171">If you haven't already done so, form your SPF TXT record by using the syntax from the table.</span></span>

   <span data-ttu-id="42f5e-172">Например, если ваша организация целиком размещена в Office 365 (то есть у вас нет локальных почтовых серверов), то в запись SPF TXT будут включены строки 1, 2 и 7, и она будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="42f5e-172">For example, if you are hosted entirely in Office 365, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 2, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   <span data-ttu-id="42f5e-173">**В примере выше используется наиболее распространенная запись SPF TXT**.</span><span class="sxs-lookup"><span data-stu-id="42f5e-173">**The example above is the most common SPF TXT record**.</span></span> <span data-ttu-id="42f5e-174">Эта запись подходит практически для всех, независимо от того, где находится ваш центр обработки данных Майкрософт — в США, Европе (в том числе в Германии) или другом месте.</span><span class="sxs-lookup"><span data-stu-id="42f5e-174">This record works for just about everyone, regardless of whether your Microsoft datacenter is located in the United States, or in Europe (including Germany), or in another location.</span></span>

   <span data-ttu-id="42f5e-p113">Но если вы приобрели Office 365 Germany в составе Microsoft Cloud Germany, следует использовать оператор include из строки 4, а не из строки 2. Например, если ваша организация целиком размещена в Office 365 Germany (то есть у вас нет локальных почтовых серверов), то в запись SPF TXT будут включены строки 1, 4 и 7, и она будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="42f5e-p113">However, if you bought Office 365 Germany, part of Microsoft Cloud Germany, you should use the include statement from line 4 instead of line 2. For example, if you are hosted entirely in Office 365 Germany, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 4, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   <span data-ttu-id="42f5e-177">При переходе с Office 365 на Office 365 Germany необходимо обновить запись SPF TXT для личного домена.</span><span class="sxs-lookup"><span data-stu-id="42f5e-177">If you're already deployed in Office 365 and have set up your SPF TXT records for your custom domain, and you're migrating to Office 365 Germany, you need to update your SPF TXT record.</span></span> <span data-ttu-id="42f5e-178">Чтобы сделать это, измените `include:spf.protection.outlook.com` на `include:spf.protection.outlook.de`.</span><span class="sxs-lookup"><span data-stu-id="42f5e-178">To do this, change `include:spf.protection.outlook.com` to `include:spf.protection.outlook.de`.</span></span>

3. <span data-ttu-id="42f5e-179">Создав запись SPF TXT, вам необходимо будет обновить ее в службе DNS.</span><span class="sxs-lookup"><span data-stu-id="42f5e-179">Once you have formed your SPF TXT record, you need to update the record in DNS.</span></span> <span data-ttu-id="42f5e-180">**Для домена можно создать только одну запись SPF TXT.**</span><span class="sxs-lookup"><span data-stu-id="42f5e-180">**You can only have one SPF TXT record for a domain.**</span></span> <span data-ttu-id="42f5e-181">Поэтому если такая запись существует, то вместо того чтобы добавлять новую запись, следует обновить существующую.</span><span class="sxs-lookup"><span data-stu-id="42f5e-181">If an SPF TXT record exists, instead of adding a new record, you need to update the existing record.</span></span> <span data-ttu-id="42f5e-182">Откройте статью [Создание записей DNS для Office 365 при самостоятельном управлении записями DNS](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md), а затем перейдите по ссылке, соответствующей вашему поставщику DNS.</span><span class="sxs-lookup"><span data-stu-id="42f5e-182">Go to [Create DNS records for Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md), and then select the link for your DNS host.</span></span>

4. <span data-ttu-id="42f5e-183">Проверьте свою запись SPF TXT.</span><span class="sxs-lookup"><span data-stu-id="42f5e-183">Test your SPF TXT record.</span></span>

## <a name="how-to-handle-subdomains"></a><span data-ttu-id="42f5e-184">Как работать с поддоменами?</span><span class="sxs-lookup"><span data-stu-id="42f5e-184">How to handle subdomains?</span></span>

<span data-ttu-id="42f5e-185">Важно отметить, что *вам требуется создать отдельную запись для каждого поддомена, так как поддомены не наследуют запись SPF от своего домена верхнего уровня*.</span><span class="sxs-lookup"><span data-stu-id="42f5e-185">It's important to note that *you need to create a separate record for each subdomain as subdomains don't inherit the SPF record of their top-level domain*.</span></span>

<span data-ttu-id="42f5e-186">Для каждого домена и поддомена требуется запись SPF с подстановочным знаком (`*.`), чтобы помешать злоумышленникам отправлять письма от несуществующих поддоменов.</span><span class="sxs-lookup"><span data-stu-id="42f5e-186">A wildcard SPF record (`*.`) is required for every domain and subdomain to prevent attackers from sending email claiming to be from non-existent subdomains.</span></span> <span data-ttu-id="42f5e-187">Например:</span><span class="sxs-lookup"><span data-stu-id="42f5e-187">For example:</span></span>

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="troubleshooting-spf"></a><span data-ttu-id="42f5e-188">Устранение неполадок инфраструктуры политики отправителей</span><span class="sxs-lookup"><span data-stu-id="42f5e-188">Troubleshooting SPF</span></span>

<span data-ttu-id="42f5e-p117">Возникли проблемы с записью типа TXT инфраструктуры политики отправителей? Прочитайте статью [Устранение неполадок: рекомендации по инфраструктуре политики отправителей в Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span><span class="sxs-lookup"><span data-stu-id="42f5e-p117">Having trouble with your SPF TXT record? Read [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>

## <a name="what-does-spf-email-authentication-actually-do"></a><span data-ttu-id="42f5e-191">Какие действия выполняет проверка подлинности электронной почты инфраструктуры политики отправителей?</span><span class="sxs-lookup"><span data-stu-id="42f5e-191">What does SPF email authentication actually do?</span></span>

<span data-ttu-id="42f5e-p118">Инфраструктура политики отправителей определяет, каким почтовым серверам разрешается отправлять сообщения от вашего имени. Инфраструктура политики отправителей, а также DKIM, DMARC и другие технологии, поддерживаемые Office 365, помогают предотвратить спуфинг и фишинг. Инфраструктура политики отправителей добавляется в виде записи типа TXT, которую служба DNS использует, чтобы определить, какие почтовые серверы могут отправлять сообщения от имени вашего личного домена. Почтовые системы получателей могут просматривать записи типа TXT инфраструктуры политики отправителей, чтобы определить, было ли сообщение из вашего личного домена отправлено с уполномоченного сервера обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="42f5e-p118">SPF identifies which mail servers are allowed to send mail on your behalf. Basically, SPF, along with DKIM, DMARC, and other technologies supported by Office 365, help prevent spoofing and phishing. SPF is added as a TXT record that is used by DNS to identify which mail servers can send mail on behalf of your custom domain. Recipient mail systems refer to the SPF TXT record to determine whether a message from your custom domain comes from an authorized messaging server.</span></span>

<span data-ttu-id="42f5e-p119">Допустим, ваш личный домен contoso.com использует Office 365. Мы добавим запись SPF TXT, в которой перечислены серверы обмена сообщениями Office 365, разрешенные для домена. Когда сервер получателя получает сообщение от joe@contoso.com, сервер находит запись SPF TXT для домена contoso.com и определяет, является ли сообщение допустимым. Если сервер получателя определит, что сообщение отправлено с сервера, не указанного в списке серверов обмена сообщениями Office 365 в записи SPF, то сервер получателя может отклонить сообщение как спам.</span><span class="sxs-lookup"><span data-stu-id="42f5e-p119">For example, let's say that your custom domain contoso.com uses Office 365. You add an SPF TXT record that lists the Office 365 messaging servers as legitimate mail servers for your domain. When the receiving messaging server gets a message from joe@contoso.com, the server looks up the SPF TXT record for contoso.com and finds out whether the message is valid. If the receiving server finds out that the message comes from a server other than the Office 365 messaging servers listed in the SPF record, the receiving mail server can choose to reject the message as spam.</span></span>

<span data-ttu-id="42f5e-p120">Кроме того, если на вашем личном домене отсутствует запись SPF TXT, некоторые серверы получателей могут сразу отклонить сообщение. Это вызвано тем, что сервер получателя не может проверить, отправлено ли сообщение с уполномоченного сервера обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="42f5e-p120">Also, if your custom domain does not have an SPF TXT record, some receiving servers may reject the message outright. This is because the receiving server cannot validate that the message comes from an authorized messaging server.</span></span>

<span data-ttu-id="42f5e-p121">Если для Office 365 уже настроена почта, то серверы обмена сообщениями Майкрософт уже включены в службу DNS в виде записи SPF TXT. Но в некоторых случаях может потребоваться обновить запись SPF TXT в службе DNS. Например:</span><span class="sxs-lookup"><span data-stu-id="42f5e-p121">If you've already set up mail for Office 365, then you have already included Microsoft's messaging servers in DNS as an SPF TXT record. However, there are some cases where you may need to update your SPF TXT record in DNS. For example:</span></span>

- <span data-ttu-id="42f5e-p122">Раньше, если вы использовали SharePoint Online, в личный домен нужно было добавить другую запись SPF TXT. Этого больше не требуется. Это изменение необходимо для того, чтобы уведомления SharePoint Online не попадали в папку нежелательной почты. Обновите запись SPF TXT, если достигнут предел в 10 запросов и возникают ошибки с сообщениями вроде "превышен предел запросов" и "слишком много прыжков".</span><span class="sxs-lookup"><span data-stu-id="42f5e-p122">Previously, you had to add a different SPF TXT record to your custom domain if you were using SharePoint Online. This is no longer required. This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder. Update your SPF TXT record if you are hitting the 10 lookup limit and receiving errors that say things like, "exceeded the lookup limit" and "too many hops".</span></span>

- <span data-ttu-id="42f5e-209">Используется гибридная среда с Office 365 и локальной службой Exchange.</span><span class="sxs-lookup"><span data-stu-id="42f5e-209">If you have a hybrid environment with Office 365 and Exchange on-premises.</span></span>

- <span data-ttu-id="42f5e-210">Вы планируете настроить DKIM и DMARC (рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="42f5e-210">You intend to set up DKIM and DMARC (recommended).</span></span>

## <a name="more-information-about-spf"></a><span data-ttu-id="42f5e-211">Дополнительные сведения об инфраструктуре политики отправителей</span><span class="sxs-lookup"><span data-stu-id="42f5e-211">More information about SPF</span></span>

<span data-ttu-id="42f5e-212">Расширенные примеры, подробное обсуждение поддерживаемого синтаксиса для инфраструктуры политики отправителей и сведения о спуфинге, устранении неполадок и о том, как Office 365 поддерживает инфраструктуру политики отправителей, см. в разделе [Как инфраструктура политики отправителей помогает предотвратить спуфинг и фишинг в Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span><span class="sxs-lookup"><span data-stu-id="42f5e-212">For advanced examples, a more detailed discussion about supported SPF syntax, spoofing, troubleshooting, and how Office 365 supports SPF, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

## <a name="next-steps-dkim-and-dmarc"></a><span data-ttu-id="42f5e-213">Дальнейшие действия: DKIM и DMARC</span><span class="sxs-lookup"><span data-stu-id="42f5e-213">Next Steps: DKIM and DMARC</span></span>

 <span data-ttu-id="42f5e-214">Инфраструктура политики отправителей (SPF) призвана предотвратить спуфинг, но существуют некоторые методики, позволяющие обойти ее.</span><span class="sxs-lookup"><span data-stu-id="42f5e-214">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF can't protect against.</span></span> <span data-ttu-id="42f5e-215">Чтобы защититься от таких атак, по завершении настройки SPF необходимо настроить DKIM и DMARC для Office 365.</span><span class="sxs-lookup"><span data-stu-id="42f5e-215">To defend against these, once you've set up SPF, you should configure DKIM and DMARC for Office 365.</span></span>

<span data-ttu-id="42f5e-216">Цель проверки подлинности электронной почты [DKIM](use-dkim-to-validate-outbound-email.md) — проверить, что содержимое письма не подделано.</span><span class="sxs-lookup"><span data-stu-id="42f5e-216">[DKIM](use-dkim-to-validate-outbound-email.md) email authentication's goal is to prove the contents of the mail haven't been tampered with.</span></span>

<span data-ttu-id="42f5e-217">Цель проверки подлинности электронной почты [DMARC](use-dmarc-to-validate-email.md) — убедиться, что сведения SPF и DKIM соответствуют адресу, указанному в поле "От".</span><span class="sxs-lookup"><span data-stu-id="42f5e-217">[DMARC](use-dmarc-to-validate-email.md) email authentication's goal is to make sure that SPF and DKIM information matches the From address.</span></span>

 <span data-ttu-id="42f5e-218">Расширенные примеры и подробное обсуждение поддерживаемых команд для инфраструктуры политики отправителей см. в разделе [Как инфраструктура политики отправителей помогает предотвратить спуфинг и фишинг в Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span><span class="sxs-lookup"><span data-stu-id="42f5e-218">For advanced examples and a more detailed discussion about supported SPF syntax, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

<span data-ttu-id="42f5e-219">*Выберите "Эта страница" в разделе "Отзывы", если хотите оставить отзыв об этой документации.*</span><span class="sxs-lookup"><span data-stu-id="42f5e-219">*Select 'This page' under 'Feedback' if you have feedback on this documentation.*</span></span>
