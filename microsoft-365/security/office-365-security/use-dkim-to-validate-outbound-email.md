---
title: Использование DKIM для работы с электронной почтой в личном домене в Office 365 (длина ключа 1024 или 2048 бит, пошаговые инструкции, принципы работы, инфраструктура политики отправителей, DMARC)
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/8/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
description: Сводка. В этой статье описано, как обеспечить доверие целевых почтовых систем к сообщениям, отправляемым из личного домена, с помощью технологии DKIM (DomainKeys Identified Mail) в Office 365.
ms.openlocfilehash: d76c31c6a3f0ce1550f0259ee40996189b60cb79
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42084397"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain-in-office-365"></a><span data-ttu-id="025ef-103">Проверка исходящей электронной почты, отправляемой с личного домена в Office 365, с помощью DKIM</span><span class="sxs-lookup"><span data-stu-id="025ef-103">Use DKIM to validate outbound email sent from your custom domain in Office 365</span></span>

 <span data-ttu-id="025ef-104">**Сводка.** В этой статье рассказывается, как обеспечить доверие целевых почтовых систем к сообщениям, отправляемым из личного домена, с помощью технологии DKIM (DomainKeys Identified Mail) в Office 365.</span><span class="sxs-lookup"><span data-stu-id="025ef-104">**Summary:** This article describes how you use DomainKeys Identified Mail (DKIM) with Office 365 to ensure that destination email systems trust messages sent outbound from your custom domain.</span></span>

<span data-ttu-id="025ef-105">Используйте DKIM вместе с инфраструктурой политики отправителей и DMARC, чтобы злоумышленники не могли отправлять сообщения якобы из вашего домена.</span><span class="sxs-lookup"><span data-stu-id="025ef-105">You should use DKIM in addition to SPF and DMARC to help prevent spoofers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="025ef-106">DKIM позволяет добавлять цифровую подпись в заголовки исходящих сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="025ef-106">DKIM lets you add a digital signature to outbound email messages in the message header.</span></span> <span data-ttu-id="025ef-107">Это может показаться сложным, но на самом деле все просто.</span><span class="sxs-lookup"><span data-stu-id="025ef-107">It may sound complicated, but it's really not.</span></span> <span data-ttu-id="025ef-108">При настройке DKIM вы авторизуете домен, чтобы сопоставить его имя с сообщением электронной почты с помощью криптографической проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="025ef-108">When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message by using cryptographic authentication.</span></span> <span data-ttu-id="025ef-109">С помощью этой цифровой подписи системы электронной почты могут определить, действительно ли входящее сообщение отправлено из вашего домена.</span><span class="sxs-lookup"><span data-stu-id="025ef-109">Email systems that receive email from your domain can use this digital signature to help determine if incoming email that they receive is legitimate.</span></span>

<span data-ttu-id="025ef-110">По сути, вы используете закрытый ключ для шифрования заголовков сообщений, отправляемых из домена.</span><span class="sxs-lookup"><span data-stu-id="025ef-110">Basically, you use a private key to encrypt the header in your domain's outgoing email.</span></span> <span data-ttu-id="025ef-111">В записях DNS домена вы публикуете открытый ключ, с помощью которого принимающие серверы расшифровывают подпись.</span><span class="sxs-lookup"><span data-stu-id="025ef-111">You publish a public key to your domain's DNS records that receiving servers can then use to decode the signature.</span></span> <span data-ttu-id="025ef-112">С помощью открытого ключа они проверяют, действительно ли сообщения отправлены вами, а не злоумышленниками, *подделавшими* ваш домен.</span><span class="sxs-lookup"><span data-stu-id="025ef-112">They use the public key to verify that the messages are really coming from you and not coming from someone *spoofing* your domain.</span></span>

<span data-ttu-id="025ef-113">Office 365 автоматически настраивает DKIM для своих исходных доменов onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="025ef-113">Office 365 automatically sets up DKIM for its initial 'onmicrosoft.com' domains.</span></span> <span data-ttu-id="025ef-114">Это означает, что вам не нужно ничего делать, чтобы настроить DKIM для любого исходного имени домена (например, litware.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="025ef-114">That means you don't need to do anything to set up DKIM for any initial domain names (for example, litware.onmicrosoft.com).</span></span> <span data-ttu-id="025ef-115">Дополнительные сведения о доменах см. в статье [Вопросы и ответы о доменах](https://docs.microsoft.com/office365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span><span class="sxs-lookup"><span data-stu-id="025ef-115">For more information about domains, see [Domains FAQ](https://docs.microsoft.com/office365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

<span data-ttu-id="025ef-116">Вы также можете не настраивать DKIM для личного домена.</span><span class="sxs-lookup"><span data-stu-id="025ef-116">You can choose to do nothing about DKIM for your custom domain too.</span></span> <span data-ttu-id="025ef-117">В этом случае Office 365 создаст пару ключей — закрытый и открытый, включит подпись с помощью DKIM и настроит политику по умолчанию для личного домена.</span><span class="sxs-lookup"><span data-stu-id="025ef-117">If you don't set up DKIM for your custom domain, Office 365 creates a private and public key pair, enables DKIM signing, and then configures the Office 365 default policy for your custom domain.</span></span> <span data-ttu-id="025ef-118">Этого вполне достаточно для защиты большинства пользователей Office 365. Настраивать DKIM для личного домена вручную следует в таких случаях:</span><span class="sxs-lookup"><span data-stu-id="025ef-118">While this is sufficient coverage for most Office 365 customers, you should manually configure DKIM for your custom domain in the following circumstances:</span></span>

- <span data-ttu-id="025ef-119">у вас есть несколько личных доменов в Office 365;</span><span class="sxs-lookup"><span data-stu-id="025ef-119">You have more than one custom domain in Office 365</span></span>

- <span data-ttu-id="025ef-120">вы также собираетесь настроить DMARC (рекомендуется);</span><span class="sxs-lookup"><span data-stu-id="025ef-120">You're going to set up DMARC too (recommended)</span></span>

- <span data-ttu-id="025ef-121">вам необходим контроль над закрытым ключом;</span><span class="sxs-lookup"><span data-stu-id="025ef-121">You want control over your private key</span></span>

- <span data-ttu-id="025ef-122">вам необходимо настроить записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="025ef-122">You want to customize your CNAME records</span></span>

- <span data-ttu-id="025ef-123">вам нужно настроить ключи DKIM для сообщений электронной почты со стороннего домена, например при использовании стороннего средства для массовых рассылок.</span><span class="sxs-lookup"><span data-stu-id="025ef-123">You want to set up DKIM keys for email originating out of a third-party domain, for example, if you use a third-party bulk mailer.</span></span>

<span data-ttu-id="025ef-124">В этой статье</span><span class="sxs-lookup"><span data-stu-id="025ef-124">In this article:</span></span>

- [<span data-ttu-id="025ef-125">Преимущества технологии DKIM над инфраструктурой политики отправителей для предотвращения спуфинга в Office 365</span><span class="sxs-lookup"><span data-stu-id="025ef-125">How DKIM works better than SPF alone to prevent malicious spoofing in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [<span data-ttu-id="025ef-126">Обновление 1024-разрядных ключей до 2048-разрядных ключей шифрования DKIM вручную</span><span class="sxs-lookup"><span data-stu-id="025ef-126">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [<span data-ttu-id="025ef-127">Действия для настройки DKIM в Office 365 вручную</span><span class="sxs-lookup"><span data-stu-id="025ef-127">Steps you need to do to manually set up DKIM in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [<span data-ttu-id="025ef-128">Настройка DKIM для нескольких личных доменов в Office 365</span><span class="sxs-lookup"><span data-stu-id="025ef-128">To configure DKIM for more than one custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [<span data-ttu-id="025ef-129">Как отключить политику подписывания DKIM для личного домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="025ef-129">Disabling the DKIM signing policy for a custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [<span data-ttu-id="025ef-130">Настройка по умолчанию для DKIM и Office 365</span><span class="sxs-lookup"><span data-stu-id="025ef-130">Default behavior for DKIM and Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [<span data-ttu-id="025ef-131">Как настроить DKIM так, чтобы сторонняя служба могла отправлять сообщения электронной почты от имени вашего личного домена</span><span class="sxs-lookup"><span data-stu-id="025ef-131">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [<span data-ttu-id="025ef-132">Дальнейшие действия: после настройки DKIM для Office 365</span><span class="sxs-lookup"><span data-stu-id="025ef-132">Next steps: After you set up DKIM for Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing-in-office-365"></a><span data-ttu-id="025ef-133">Преимущества технологии DKIM над инфраструктурой политики отправителей для предотвращения спуфинга в Office 365</span><span class="sxs-lookup"><span data-stu-id="025ef-133">How DKIM works better than SPF alone to prevent malicious spoofing in Office 365</span></span>
<span data-ttu-id="025ef-134"><a name="HowDKIMWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="025ef-134"><a name="HowDKIMWorks"> </a></span></span>

<span data-ttu-id="025ef-p105">Инфраструктура политики отправителей добавляет сведения в конверт сообщения, а технология DKIM шифрует подпись в заголовке сообщения. При пересылке фрагменты конверта этого сообщения могут быть удалены сервером пересылки. Поскольку цифровая подпись остается в заголовке сообщения, технология DKIM работает даже при пересылке, как показано в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="025ef-p105">SPF adds information to a message envelope but DKIM actually encrypts a signature within the message header. When you forward a message, portions of that message's envelope can be stripped away by the forwarding server. Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span></span>

![Схема, на которой показана проверка подлинности DKIM: пересланное сообщение не прошло проверку инфраструктурой политики отправителей](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

<span data-ttu-id="025ef-p106">Если бы в этом примере вы опубликовали только запись типа TXT инфраструктуры политики отправителей для домена, почтовый сервер получателя мог бы пометить ваше сообщение как спам, что привело бы к ложному срабатыванию. Добавление DKIM в этом сценарии позволяет снизить количество ложных срабатываний. Так как в технологии DKIM для проверки подлинности используется шифрование с помощью открытого ключа, а не только IP-адресов, она считается более надежным способом проверки подлинности, чем инфраструктура политики отправителей. Рекомендуем использовать обе эти технологии, а также DMARC в вашем развертывании.</span><span class="sxs-lookup"><span data-stu-id="025ef-p106">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result. The addition of DKIM in this scenario reduces false positive spam reporting. Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF. We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span></span>

<span data-ttu-id="025ef-p107">Подробности: DKIM использует закрытый ключ для вставки зашифрованной подписи в заголовки сообщений. Имя подписывающего домена (или домена исходящей почты) вставляется в заголовок в качестве значения поля **d=**. Проверяющий домен (или домен получателя) затем использует поле **d=** для поиска открытого ключа в DNS и проверки подлинности сообщения. Так сообщение проходит проверку DKIM.</span><span class="sxs-lookup"><span data-stu-id="025ef-p107">The nitty gritty: DKIM uses a private key to insert an encrypted signature into the message headers. The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header. The verifying domain, or recipient's domain, then use the **d=** field to look up the public key from DNS and authenticate the message. If the message is verified, the DKIM check passes.</span></span>

## <a name="manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a><span data-ttu-id="025ef-147">Обновление 1024-разрядных ключей до 2048-разрядных ключей шифрования DKIM вручную</span><span class="sxs-lookup"><span data-stu-id="025ef-147">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>
<span data-ttu-id="025ef-148"><a name="1024to2048DKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="025ef-148"><a name="1024to2048DKIM"> </a></span></span>

<span data-ttu-id="025ef-149">Так как ключи DKIM могут быть 1024- и 2048-разрядными, эти инструкции предназначены для перехода с 1024- на 2048-разрядные ключи.</span><span class="sxs-lookup"><span data-stu-id="025ef-149">Since both 1024 and 2048 bitness are supported for DKIM keys, these directions will tell you how to upgrade your 1024-bit key to 2048.</span></span> <span data-ttu-id="025ef-150">Описанные ниже действия относятся к двум вариантам использования. Выберите вариант, подходящий для вашей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="025ef-150">The steps below are for two use-cases, please choose the one that best fits your configuration.</span></span>

1. <span data-ttu-id="025ef-151">Если вы **уже настроили DKIM**, измените разрядность следующим образом:</span><span class="sxs-lookup"><span data-stu-id="025ef-151">When you **already have DKIM configured**, you rotate bitness as follows:</span></span>
    1. <span data-ttu-id="025ef-152">[Подключитесь к рабочим нагрузкам Office 365 с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="025ef-152">[Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="025ef-153">(Командлет из Exchange Online.)</span><span class="sxs-lookup"><span data-stu-id="025ef-153">(The cmdlet comes from Exchange Online.)</span></span>
    1. <span data-ttu-id="025ef-154">Затем выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="025ef-154">And then execute the following cmdlet:</span></span>

<span data-ttu-id="025ef-155">&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}`</span><span class="sxs-lookup"><span data-stu-id="025ef-155">&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}`</span></span>

1. <span data-ttu-id="025ef-156">В случае **новой реализации DKIM**:</span><span class="sxs-lookup"><span data-stu-id="025ef-156">Or for a **new implementation of DKIM**:</span></span>
    1. <span data-ttu-id="025ef-157">[Подключитесь к рабочим нагрузкам Office 365 с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="025ef-157">[Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="025ef-158">(Это командлет Exchange Online.)</span><span class="sxs-lookup"><span data-stu-id="025ef-158">(This is an Exchange Online cmdlet.)</span></span>
    1. <span data-ttu-id="025ef-159">Выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="025ef-159">Execute the following cmdlet:</span></span>

<span data-ttu-id="025ef-160">&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True`</span><span class="sxs-lookup"><span data-stu-id="025ef-160">&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True`</span></span>

<span data-ttu-id="025ef-161">Сохраняйте подключение к Office 365, чтобы *проверить* настройку.</span><span class="sxs-lookup"><span data-stu-id="025ef-161">Stay connected to Office 365 to *verify* the configuration.</span></span>

2. <span data-ttu-id="025ef-162">Выполните командлет:</span><span class="sxs-lookup"><span data-stu-id="025ef-162">Execute the cmdlet:</span></span>

<span data-ttu-id="025ef-163">&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `Get-DkimSigningConfig | fl`</span><span class="sxs-lookup"><span data-stu-id="025ef-163">&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `Get-DkimSigningConfig | fl`</span></span>

> [!TIP]
><span data-ttu-id="025ef-164">Этот новый 2048-разрядный ключ вступает в силу с даты, указанной в параметре RotateOnDate. Пока же сообщения электронной почты будут отправляться с использованием 1024-разрядного ключа.</span><span class="sxs-lookup"><span data-stu-id="025ef-164">This new 2048-bit key takes effect on the RotateOnDate, and will send emails with the 1024-bit key in the interim.</span></span> <span data-ttu-id="025ef-165">Через четыре дня вы снова можете выполнить проверку с использованием 2048-разрядного ключа (то есть после применения изменения ко второму селектору).</span><span class="sxs-lookup"><span data-stu-id="025ef-165">After four days, you can test again with the 2048-bit key (that is, once the rotation takes effect to the second selector).</span></span>

<span data-ttu-id="025ef-166">Если нужно выполнить изменение для второго селектора, доступны следующие варианты: а) позвольте службе Office 365 изменить селектор и выполнить обновление до 2048-разрядных ключей в течение следующих 6 месяцев или б) после 4 дней и подтверждения применения 2048-разрядных ключей вручную измените ключ второго селектора с помощью соответствующего командлета, указанного выше.</span><span class="sxs-lookup"><span data-stu-id="025ef-166">If you want to rotate to the second selector, your options are a) let the Office 365 service rotate the selector and upgrade to 2048-bitness within the next 6 months, or b) after 4 days and confirming that 2048-bitness is in use, manually rotate the second selector key by using the appropriate cmdlet listed above.</span></span>

## <a name="steps-you-need-to-do-to-manually-set-up-dkim-in-office-365"></a><span data-ttu-id="025ef-167">Действия для настройки DKIM в Office 365 вручную</span><span class="sxs-lookup"><span data-stu-id="025ef-167">Steps you need to do to manually set up DKIM in Office 365</span></span>
<span data-ttu-id="025ef-168"><a name="SetUpDKIMO365"> </a></span><span class="sxs-lookup"><span data-stu-id="025ef-168"><a name="SetUpDKIMO365"> </a></span></span>

<span data-ttu-id="025ef-169">Настройка DKIM состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="025ef-169">To configure DKIM, you will complete these steps:</span></span>

- [<span data-ttu-id="025ef-170">Публикация двух записей CNAME для личного домена в DNS</span><span class="sxs-lookup"><span data-stu-id="025ef-170">Publish two CNAME records for your custom domain in DNS</span></span>](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [<span data-ttu-id="025ef-171">Включение подписи с помощью DKIM для личного домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="025ef-171">Enable DKIM signing for your custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a><span data-ttu-id="025ef-172">Публикация двух записей CNAME для личного домена в DNS</span><span class="sxs-lookup"><span data-stu-id="025ef-172">Publish two CNAME records for your custom domain in DNS</span></span>
<span data-ttu-id="025ef-173"><a name="Publish2CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="025ef-173"><a name="Publish2CNAME"> </a></span></span>

<span data-ttu-id="025ef-174">Для каждого домена, для которого требуется добавить подпись DKIM в DNS, необходимо опубликовать две записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="025ef-174">For each domain for which you want to add a DKIM signature in DNS, you need to publish two CNAME records.</span></span>

<span data-ttu-id="025ef-175">Чтобы создать записи селектора, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="025ef-175">Run the following commands to create the selector records:</span></span>

```powershell
    New-DkimSigningConfig -DomainName <domain> -Enabled $false
    Get-DkimSigningConfig -Identity <domain> | fl Selector1CNAME, Selector2CNAME
```

<span data-ttu-id="025ef-176">Создание записей CNAME, на которые имеется ссылка в выходных данных команды Get-DkimSigningConfig</span><span class="sxs-lookup"><span data-stu-id="025ef-176">Create CNAMEs referenced in Get-DkimSigningConfig output</span></span>

```powershell
    Set-DkimSigningConfig -Identity <domain> -Enabled $true
```

<span data-ttu-id="025ef-p112">Office 365 выполняет автоматическую ротацию ключей, используя две заданные записи. Для каждого дополнительного домена в Office 365 необходимо опубликовать две записи CNAME. Таким образом, если у вас есть два домена, необходимо опубликовать две дополнительные записи CNAME и так далее.</span><span class="sxs-lookup"><span data-stu-id="025ef-p112">Office 365 performs automatic key rotation using the two records that you establish. If you have provisioned custom domains in addition to the initial domain in Office 365, you must publish two CNAME records for each additional domain. So, if you have two domains, you must publish two additional CNAME records, and so on.</span></span>

<span data-ttu-id="025ef-180">Для записей CNAME используйте указанный ниже формат.</span><span class="sxs-lookup"><span data-stu-id="025ef-180">Use the following format for the CNAME records.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="025ef-181">Если вы один из наших клиентов GCC High, мы вычисляем _domainGuid_ другим способом.</span><span class="sxs-lookup"><span data-stu-id="025ef-181">If you are one of our GCC High customers, we calculate _domainGuid_ differently!</span></span> <span data-ttu-id="025ef-182">Вместо поиска записи MX для вашего _initialDomain_ с целью вычисления _domainGuid_ мы вычисляем его непосредственно на основании личного домена.</span><span class="sxs-lookup"><span data-stu-id="025ef-182">Instead of looking up the MX record for your _initialDomain_ to calculate _domainGuid_, instead we calculate it directly from the customized domain.</span></span> <span data-ttu-id="025ef-183">Например, если ваш личный домен — contoso.com, ваш domainGuid будет иметь вид contoso-com, то есть все точки будут заменены дефисами.</span><span class="sxs-lookup"><span data-stu-id="025ef-183">For example, if your customized domain is "contoso.com" your domainGuid becomes "contoso-com", any periods are replaced with a dash.</span></span> <span data-ttu-id="025ef-184">Таким образом, независимо от записи MX, на которую указывает ваш initialDomain, вы всегда можете использовать описанный выше метод для вычисления domainGuid, чтобы использовать его в записях CNAME.</span><span class="sxs-lookup"><span data-stu-id="025ef-184">So, regardless of what MX record your initialDomain points to, you'll always use the above method to calculate the domainGuid to use in your CNAME records.</span></span>

```text
Host name:          selector1._domainkey
Points to address or value: selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

<span data-ttu-id="025ef-185">Где:</span><span class="sxs-lookup"><span data-stu-id="025ef-185">Where:</span></span>

- <span data-ttu-id="025ef-186">selector1 и selector2 — это селекторы для Office 365.</span><span class="sxs-lookup"><span data-stu-id="025ef-186">For Office 365, the selectors will always be "selector1" or "selector2".</span></span>

- <span data-ttu-id="025ef-187">Значение _domainGUID_ — такое же, как и значение _domainGUID_ в пользовательской записи MX для вашего личного домена, которое указывается перед адресом mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="025ef-187">_domainGUID_ is the same as the _domainGUID_ in the customized MX record for your custom domain that appears before mail.protection.outlook.com.</span></span> <span data-ttu-id="025ef-188">Например, в следующей записи MX для домена contoso.com значение _domainGUID_ равно contoso-com:</span><span class="sxs-lookup"><span data-stu-id="025ef-188">For example, in the following MX record for the domain contoso.com, the _domainGUID_ is contoso-com:</span></span>

    ```text
    contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com
    ```

- <span data-ttu-id="025ef-189">_initialDomain_ — это домен, который вы использовали при регистрации в Office 365.</span><span class="sxs-lookup"><span data-stu-id="025ef-189">_initialDomain_ is the domain that you used when you signed up for Office 365.</span></span> <span data-ttu-id="025ef-190">Исходные домены всегда заканчиваются на onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="025ef-190">Initial domains always end in onmicrosoft.com.</span></span> <span data-ttu-id="025ef-191">О том, как узнать свой исходный домен, читайте в разделе [часто задаваемых вопросов](https://docs.microsoft.com/office365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span><span class="sxs-lookup"><span data-stu-id="025ef-191">For information about determining your initial domain, see [Domains FAQ](https://docs.microsoft.com/office365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

<span data-ttu-id="025ef-192">Например, если у вас есть исходный домен cohovineyardandwinery.onmicrosoft.com и два личных домена cohovineyard.com и cohowinery.com, вам необходимо настроить две записи CNAME для каждого дополнительного домена (всего четыре записи CNAME).</span><span class="sxs-lookup"><span data-stu-id="025ef-192">For example, if you have an initial domain of cohovineyardandwinery.onmicrosoft.com, and two custom domains cohovineyard.com and cohowinery.com, you would need to set up two CNAME records for each additional domain, for a total of four CNAME records.</span></span>

```text
Host name:          selector1._domainkey
Points to address or value: selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector1._domainkey
Points to address or value: selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600
```

> [!NOTE]
> <span data-ttu-id="025ef-193">Важно создать вторую запись, но только один из селекторов может быть доступен во время создания.</span><span class="sxs-lookup"><span data-stu-id="025ef-193">It's important to create the second record, but only one of the selectors may be available at the time of creation.</span></span> <span data-ttu-id="025ef-194">По сути, второй селектор может указывать на адрес, который еще не создан.</span><span class="sxs-lookup"><span data-stu-id="025ef-194">In essence, the second selector might point to an address that hasn't been created yet.</span></span> <span data-ttu-id="025ef-195">Мы все же рекомендуем создать вторую запись CNAME, так как ротация ключей будет беспроблемной и вам не потребуется выполнять какие-либо действия вручную.</span><span class="sxs-lookup"><span data-stu-id="025ef-195">We still recommended that you create the second CNAME record, because your key rotation will be seamless and you won't need to do any manual steps yourself.</span></span>

### <a name="enable-dkim-signing-for-your-custom-domain-in-office-365"></a><span data-ttu-id="025ef-196">Включение подписи с помощью DKIM для личного домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="025ef-196">Enable DKIM signing for your custom domain in Office 365</span></span>
<span data-ttu-id="025ef-197"><a name="EnableDKIMinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="025ef-197"><a name="EnableDKIMinO365"> </a></span></span>

<span data-ttu-id="025ef-198">После публикации записей CNAME в DNS включите подпись с помощью DKIM в Office 365.</span><span class="sxs-lookup"><span data-stu-id="025ef-198">Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Office 365.</span></span> <span data-ttu-id="025ef-199">Это можно сделать в Центре администрирования Microsoft 365 или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="025ef-199">You can do this either through the Microsoft 365 admin center or by using PowerShell.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a><span data-ttu-id="025ef-200">Включение функции подписывания с помощью DKIM для личного домена в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="025ef-200">To enable DKIM signing for your custom domain through the admin center</span></span>

1. <span data-ttu-id="025ef-201">[Войдите в Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) с помощью своей учебной или рабочей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="025ef-201">[Sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="025ef-202">В левом верхнем углу щелкните значок средства запуска приложений и выберите **Администратор**.</span><span class="sxs-lookup"><span data-stu-id="025ef-202">Select the app launcher icon in the upper-left and choose **Admin**.</span></span>

3. <span data-ttu-id="025ef-203">В области навигации слева внизу разверните узел **Администратор** и выберите элемент **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="025ef-203">In the lower-left navigation, expand **Admin** and choose **Exchange**.</span></span>

4. <span data-ttu-id="025ef-204">Перейдите в раздел **Защита** \> **dkim**.</span><span class="sxs-lookup"><span data-stu-id="025ef-204">Go to **Protection** \> **dkim**.</span></span>

5. <span data-ttu-id="025ef-p118">Выберите домен, для которого требуется включить DKIM, а затем в разделе **Добавлять подписи DKIM в сообщения для этого домена** нажмите **Включить**. Повторите этот шаг для каждого личного домена.</span><span class="sxs-lookup"><span data-stu-id="025ef-p118">Select the domain for which you want to enable DKIM and then, for **Sign messages for this domain with DKIM signatures**, choose **Enable**. Repeat this step for each custom domain.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a><span data-ttu-id="025ef-207">Как включить подпись с помощью DKIM для личного домена, используя PowerShell</span><span class="sxs-lookup"><span data-stu-id="025ef-207">To enable DKIM signing for your custom domain by using PowerShell</span></span>

1. <span data-ttu-id="025ef-208">[Подключение к PowerShell для Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="025ef-208">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="025ef-209">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="025ef-209">Run the following command:</span></span>

    ```powershell
    Set-DkimSigningConfig -Identity <domain> -Enabled $true
    ```

   <span data-ttu-id="025ef-210">Где _domain_ — имя личного домена, для которого требуется включить функцию подписывания с помощью DKIM.</span><span class="sxs-lookup"><span data-stu-id="025ef-210">Where _domain_ is the name of the custom domain that you want to enable DKIM signing for.</span></span>

   <span data-ttu-id="025ef-211">Например, для домена contoso.com:</span><span class="sxs-lookup"><span data-stu-id="025ef-211">For example, for the domain contoso.com:</span></span>

    ```powershell
    Set-DkimSigningConfig -Identity contoso.com -Enabled $true
    ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-office-365"></a><span data-ttu-id="025ef-212">Как проверить настройку подписи с помощью DKIM для Office 365</span><span class="sxs-lookup"><span data-stu-id="025ef-212">To Confirm DKIM signing is configured properly for Office 365</span></span>

<span data-ttu-id="025ef-p119">Прежде чем выполнять указанные ниже действия для проверки настройки DKIM, подождите несколько минут. Для распространения информации DKIM о домене по сети требуется время.</span><span class="sxs-lookup"><span data-stu-id="025ef-p119">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM. This allows time for the DKIM information about the domain to be spread throughout the network.</span></span>

- <span data-ttu-id="025ef-215">Отправьте сообщение из учетной записи в вашем домене Office 365 с включенной проверкой DKIM в другую учетную запись электронной почты, например outlook.com или Hotmail.com.</span><span class="sxs-lookup"><span data-stu-id="025ef-215">Send a message from an account within your Office 365 DKIM-enabled domain to another email account such as outlook.com or Hotmail.com.</span></span>

- <span data-ttu-id="025ef-p120">Не используйте для проверки учетную запись aol.com. AOL может пропустить проверку DKIM в случае успешной проверки SPF. Такая проверка будет недействительной.</span><span class="sxs-lookup"><span data-stu-id="025ef-p120">Do not use an aol.com account for testing purposes. AOL may skip the DKIM check if the SPF check passes. This will nullify your test.</span></span>

- <span data-ttu-id="025ef-p121">Откройте сообщение и посмотрите на заголовок. Инструкции по просмотру заголовка сообщения зависят от вашего почтового клиента. Инструкции по просмотру заголовков сообщений в Outlook см. в статье [Просмотр заголовков сообщений электронной почты](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C).</span><span class="sxs-lookup"><span data-stu-id="025ef-p121">Open the message and look at the header. Instructions for viewing the header for the message will vary depending on your messaging client. For instructions on viewing message headers in Outlook, see [View e-mail message headers](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C).</span></span>

  <span data-ttu-id="025ef-p122">Сообщение, подписанное с помощью DKIM, будет содержать имя узла и доменное имя, указанные вами при публикации записей CNAME. Сообщение будет выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="025ef-p122">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries. The message will look something like this example:</span></span>

  ```text
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- <span data-ttu-id="025ef-p123">Найдите заголовок Authentication-Results. Принимающие службы помечают входящую почту по-разному, но результат должен содержать элемент, подобный **DKIM=pass** или **DKIM=OK**.</span><span class="sxs-lookup"><span data-stu-id="025ef-p123">Look for the Authentication-Results header. While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span></span>

## <a name="to-configure-dkim-for-more-than-one-custom-domain-in-office-365"></a><span data-ttu-id="025ef-226">Настройка DKIM для нескольких личных доменов в Office 365</span><span class="sxs-lookup"><span data-stu-id="025ef-226">To configure DKIM for more than one custom domain in Office 365</span></span>
<span data-ttu-id="025ef-227"><a name="DKIMMultiDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="025ef-227"><a name="DKIMMultiDomain"> </a></span></span>

<span data-ttu-id="025ef-p124">Действия, описанные в этой статье, необходимо выполнить для каждого дополнительного личного домена, для которого требуется включить DKIM. В частности, выполните все действия, описанные в разделе [Как настроить DKIM в Office 365 вручную](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span><span class="sxs-lookup"><span data-stu-id="025ef-p124">If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain. Specifically, complete all steps in [What you need to do to manually set up DKIM in Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span></span>

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain-in-office-365"></a><span data-ttu-id="025ef-230">Как отключить политику подписывания DKIM для личного домена в Office 365</span><span class="sxs-lookup"><span data-stu-id="025ef-230">Disabling the DKIM signing policy for a custom domain in Office 365</span></span>
<span data-ttu-id="025ef-231"><a name="DisableDKIMSigningPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="025ef-231"><a name="DisableDKIMSigningPolicy"> </a></span></span>

<span data-ttu-id="025ef-p125">Отключение политики подписывания полностью не отключает DKIM. Через некоторое время служба Office 365 автоматически применит политику Office 365 по умолчанию для вашего домена. Дополнительные сведения см. в разделе [Настройка по умолчанию для DKIM и Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span><span class="sxs-lookup"><span data-stu-id="025ef-p125">Disabling the signing policy does not completely disable DKIM. After a period of time, Office 365 will automatically apply the default Office 365 policy for your domain. For more information, see [Default behavior for DKIM and Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a><span data-ttu-id="025ef-235">Отключение политики подписывания DKIM с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="025ef-235">To disable the DKIM signing policy by using Windows PowerShell</span></span>

1. <span data-ttu-id="025ef-236">[Подключение к PowerShell для Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="025ef-236">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="025ef-237">Выполните одну из указанных ниже команд для каждого домена, для которого требуется отключить подпись с помощью DKIM.</span><span class="sxs-lookup"><span data-stu-id="025ef-237">Run one of the following commands for each domain for which you want to disable DKIM signing.</span></span>

    ```powershell
    $p = Get-DkimSigningConfig -Identity <domain>
    $p[0] | Set-DkimSigningConfig -Enabled $false
    ```

   <span data-ttu-id="025ef-238">Пример:</span><span class="sxs-lookup"><span data-stu-id="025ef-238">For example:</span></span>

    ```powershell
    $p = Get-DkimSigningConfig -Identity contoso.com
    $p[0] | Set-DkimSigningConfig -Enabled $false
    ```

   <span data-ttu-id="025ef-239">или</span><span class="sxs-lookup"><span data-stu-id="025ef-239">Or</span></span>

    ```powershell
    Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
    ```

    <span data-ttu-id="025ef-240">Где _number_ — индекс политики.</span><span class="sxs-lookup"><span data-stu-id="025ef-240">Where _number_ is the index of the policy.</span></span> <span data-ttu-id="025ef-241">Пример:</span><span class="sxs-lookup"><span data-stu-id="025ef-241">For example:</span></span>

    ```powershell
    Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
    ```

## <a name="default-behavior-for-dkim-and-office-365"></a><span data-ttu-id="025ef-242">Настройка по умолчанию для DKIM и Office 365</span><span class="sxs-lookup"><span data-stu-id="025ef-242">Default behavior for DKIM and Office 365</span></span>
<span data-ttu-id="025ef-243"><a name="DefaultDKIMbehavior"> </a></span><span class="sxs-lookup"><span data-stu-id="025ef-243"><a name="DefaultDKIMbehavior"> </a></span></span>

<span data-ttu-id="025ef-244">Если вы не включите DKIM, Office 365 автоматически создаст 1024-разрядный открытый ключ DKIM для вашего домена, используемого по умолчанию, и соответствующий закрытый ключ, который будет храниться в нашем центре обработки данных.</span><span class="sxs-lookup"><span data-stu-id="025ef-244">If you do not enable DKIM, Office 365 automatically creates a 1024-bit DKIM public key for your default domain and the associated private key which we store internally in our datacenter.</span></span> <span data-ttu-id="025ef-245">Для доменов без действующей политики Office 365 использует конфигурацию подписывания по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="025ef-245">By default, Office 365 uses a default signing configuration for domains that do not have a policy in place.</span></span> <span data-ttu-id="025ef-246">Это означает, что если вы не настроите DKIM самостоятельно, Office 365 включит DKIM для вашего домена, используя политику по умолчанию и созданные ключи.</span><span class="sxs-lookup"><span data-stu-id="025ef-246">This means that if you do not set up DKIM yourself, Office 365 will use its default policy and keys it creates in order to enable DKIM for your domain.</span></span>

<span data-ttu-id="025ef-247">Кроме того, если вы отключите подпись с помощью DKIM, то через некоторое время Office 365 автоматически включит для вашего домена политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="025ef-247">Also, if you disable DKIM signing after enabling it, after a period of time, Office 365 will automatically apply the Office 365 default policy for your domain.</span></span>

<span data-ttu-id="025ef-p128">Предположим, что в примере ниже подпись DKIM для домена fabrikam.com включил Office 365, а не администратор домена. Это означает, что в службе DNS нет требуемых записей CNAME. Подписи DKIM для электронной почты из этого домена будут выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="025ef-p128">In the following example, suppose that DKIM for fabrikam.com was enabled by Office 365, not by the administrator of the domain. This means that the required CNAMEs do not exist in DNS. DKIM signatures for email from this domain will look something like this:</span></span>

```text
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

<span data-ttu-id="025ef-p129">В этом примере имя узла и доменное имя содержат значения, на которые указывала бы запись CNAME, если бы администратор домена настроил подпись DKIM для домена fabrikam.com. Каждое сообщение, отправленное из Office 365, будет подписано с помощью DKIM. Если вы включили DKIM самостоятельно, то домен будет совпадать с доменом, указанным в адресе отправителя (в этом случае  fabrikam.com). В противном случае будет использоваться исходный домен организации. О том, как узнать свой исходный домен, читайте в разделе [часто задаваемых вопросов](https://docs.microsoft.com/office365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span><span class="sxs-lookup"><span data-stu-id="025ef-p129">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator. Eventually, every single message sent from Office 365 will be DKIM-signed. If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com. If you don't, it will not align and instead will use your organization's initial domain. For information about determining your initial domain, see [Domains FAQ](https://docs.microsoft.com/office365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a><span data-ttu-id="025ef-256">Настройте DKIM таким образом, чтобы сторонняя служба могла отправлять электронные письма от имени вашего личного домена</span><span class="sxs-lookup"><span data-stu-id="025ef-256">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>
<span data-ttu-id="025ef-257"><a name="SetUp3rdPartyspoof"> </a></span><span class="sxs-lookup"><span data-stu-id="025ef-257"><a name="SetUp3rdPartyspoof"> </a></span></span>

<span data-ttu-id="025ef-p130">Некоторые поставщика услуг электронной почты, или поставщики программного обеспечения как службы, позволяют настраивать ключи DKIM для сообщений электронной почты, отправляемых из их службы. Для этого вам необходимо координировать свои действия с третьей стороной, чтобы настроить необходимые записи DNS. В каждой организации это делают по-своему. Процесс полностью зависит от конкретного предприятия.</span><span class="sxs-lookup"><span data-stu-id="025ef-p130">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service. This requires coordination between yourself and the third-party in order to set up the necessary DNS records. No two organizations do it exactly the same way. Instead, the process depends entirely on the organization.</span></span>

<span data-ttu-id="025ef-262">Пример сообщения с правильно настроенными ключами DKIM для доменов contoso.com и bulkemailprovider.com:</span><span class="sxs-lookup"><span data-stu-id="025ef-262">An example message showing a properly configured DKIM for contoso.com and bulkemailprovider.com might look like this:</span></span>

```text
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

<span data-ttu-id="025ef-263">В этом примере для достижения представленного результата:</span><span class="sxs-lookup"><span data-stu-id="025ef-263">In this example, in order to achieve this result:</span></span>

1. <span data-ttu-id="025ef-264">Поставщик услуг массовой рассылки предоставил компании Contoso открытый ключ DKIM.</span><span class="sxs-lookup"><span data-stu-id="025ef-264">Bulk Email Provider gave Contoso a public DKIM key.</span></span>

2. <span data-ttu-id="025ef-265">Компания Contoso опубликовала ключ DKIM в своей записи DNS.</span><span class="sxs-lookup"><span data-stu-id="025ef-265">Contoso published the DKIM key to its DNS record.</span></span>

3. <span data-ttu-id="025ef-p131">При отправке сообщения поставщик услуг массовой рассылки подписывает ключ соответствующим закрытым ключом. Таким образом он добавляет подпись DKIM в заголовок сообщения.</span><span class="sxs-lookup"><span data-stu-id="025ef-p131">When sending email, Bulk Email Provider signs the key with the corresponding private key. By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span></span>

4. <span data-ttu-id="025ef-p132">Почтовые системы получателей выполняют проверку DKIM путем сравнения значения DKIM-Signature d=\<domain\> с доменом в поле "От" (5322.From) сообщения. В этом примере значения совпадают:</span><span class="sxs-lookup"><span data-stu-id="025ef-p132">Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message. In this example, the values match:</span></span>

    <span data-ttu-id="025ef-270">отправитель@**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="025ef-270">sender@**contoso.com**</span></span>

    <span data-ttu-id="025ef-271">d=**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="025ef-271">d=**contoso.com**</span></span>

## <a name="next-steps-after-you-set-up-dkim-for-office-365"></a><span data-ttu-id="025ef-272">Дальнейшие действия: после настройки инфраструктуры политики отправителей для Office 365</span><span class="sxs-lookup"><span data-stu-id="025ef-272">Next steps: After you set up DKIM for Office 365</span></span>
<span data-ttu-id="025ef-273"><a name="DKIMNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="025ef-273"><a name="DKIMNextSteps"> </a></span></span>

<span data-ttu-id="025ef-274">Несмотря на то, что технология DKIM предназначена для предотвращения спуфинга, она работает эффективнее вместе с инфраструктурой политики отправителей и DMARC.</span><span class="sxs-lookup"><span data-stu-id="025ef-274">Although DKIM is designed to help prevent spoofing, DKIM works better with SPF and DMARC.</span></span> <span data-ttu-id="025ef-275">После настройки DKIM настройте инфраструктуру политики отправителей.</span><span class="sxs-lookup"><span data-stu-id="025ef-275">Once you have set up DKIM, if you have not already set up SPF you should do so.</span></span> <span data-ttu-id="025ef-276">Краткий обзор инфраструктуры политики отправителей и инструкции по ее быстрой настройке см. в статье [Настройка инфраструктуры политики отправителей в Office 365 для предотвращения спуфинга](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="025ef-276">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="025ef-277">Дополнительные сведения об использовании инфраструктуры политики отправителей в Office 365, рекомендации по устранению неполадок и инструкции для нестандартных, в том числе гибридных, развертываний см. в статье [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="025ef-277">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="025ef-278">Затем см. статью [Использование протокола DMARC для проверки электронной почты в Office 365](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="025ef-278">Next, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="025ef-279">[Anti-Spam Message Headers](anti-spam-message-headers.md) включает синтаксис и поля заголовков, которые Office 365 использует для проверок с помощью DKIM.</span><span class="sxs-lookup"><span data-stu-id="025ef-279">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Office 365 for DKIM checks.</span></span>
