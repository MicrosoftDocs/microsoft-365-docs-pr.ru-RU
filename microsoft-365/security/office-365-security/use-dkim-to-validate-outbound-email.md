---
title: Использование DKIM для работы с электронной почтой в личном домене
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
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как использовать технологию DomainKeys Identified Mail (DKIM) для Microsoft 365, чтобы обеспечить доверие конечных почтовых систем к сообщениям, отправленным из вашего личного домена.
ms.openlocfilehash: d2035ed0805215f1bd8e343f9edf1c557035b5c1
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307851"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a><span data-ttu-id="ac4f8-103">Используйте DKIM для проверки исходящей электронной почты, отправленной с вашего пользовательского домена</span><span class="sxs-lookup"><span data-stu-id="ac4f8-103">Use DKIM to validate outbound email sent from your custom domain</span></span>

 <span data-ttu-id="ac4f8-104">**Сводка:** В этой статье описывается, как вы используете DomainKeys Identified Mail (DKIM) с Microsoft 365, чтобы гарантировать, что системы электронной почты назначения доверяют сообщениям, отправленным с вашего пользовательского домена.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-104">**Summary:** This article describes how you use DomainKeys Identified Mail (DKIM) with Microsoft 365 to ensure that destination email systems trust messages sent outbound from your custom domain.</span></span>

<span data-ttu-id="ac4f8-105">Используйте DKIM вместе с инфраструктурой политики отправителей и DMARC, чтобы злоумышленники не могли отправлять сообщения якобы из вашего домена.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-105">You should use DKIM in addition to SPF and DMARC to help prevent spoofers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="ac4f8-106">DKIM позволяет добавлять цифровую подпись в заголовки исходящих сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-106">DKIM lets you add a digital signature to outbound email messages in the message header.</span></span> <span data-ttu-id="ac4f8-107">Это может показаться сложным, но на самом деле все просто.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-107">It may sound complicated, but it's really not.</span></span> <span data-ttu-id="ac4f8-108">При настройке DKIM вы авторизуете домен, чтобы сопоставить его имя с сообщением электронной почты с помощью криптографической проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-108">When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message by using cryptographic authentication.</span></span> <span data-ttu-id="ac4f8-109">С помощью этой цифровой подписи системы электронной почты могут определить, действительно ли входящее сообщение отправлено из вашего домена.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-109">Email systems that receive email from your domain can use this digital signature to help determine if incoming email that they receive is legitimate.</span></span>

<span data-ttu-id="ac4f8-110">По сути, вы используете закрытый ключ для шифрования заголовков сообщений, отправляемых из домена.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-110">Basically, you use a private key to encrypt the header in your domain's outgoing email.</span></span> <span data-ttu-id="ac4f8-111">В записях DNS домена вы публикуете открытый ключ, с помощью которого принимающие серверы расшифровывают подпись.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-111">You publish a public key to your domain's DNS records that receiving servers can then use to decode the signature.</span></span> <span data-ttu-id="ac4f8-112">С помощью открытого ключа они проверяют, действительно ли сообщения отправлены вами, а не злоумышленниками, *подделавшими* ваш домен.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-112">They use the public key to verify that the messages are really coming from you and not coming from someone *spoofing* your domain.</span></span>

<span data-ttu-id="ac4f8-113">Microsoft 365 автоматически настраивает DKIM для своих первоначальных доменов «onmicrosoft.com».</span><span class="sxs-lookup"><span data-stu-id="ac4f8-113">Microsoft 365 automatically sets up DKIM for its initial 'onmicrosoft.com' domains.</span></span> <span data-ttu-id="ac4f8-114">Это означает, что вам не нужно ничего делать, чтобы настроить DKIM для любого исходного имени домена (например, litware.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="ac4f8-114">That means you don't need to do anything to set up DKIM for any initial domain names (for example, litware.onmicrosoft.com).</span></span> <span data-ttu-id="ac4f8-115">Дополнительные сведения о доменах см. в статье [Вопросы и ответы о доменах](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span><span class="sxs-lookup"><span data-stu-id="ac4f8-115">For more information about domains, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

<span data-ttu-id="ac4f8-116">Вы также можете не настраивать DKIM для личного домена.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-116">You can choose to do nothing about DKIM for your custom domain too.</span></span> <span data-ttu-id="ac4f8-117">Если вы не настроили DKIM для своего пользовательского домена, Microsoft 365 создаст пару личного и открытого ключей, разрешит подпись DKIM, а затем настроит политику Microsoft 365 по умолчанию для вашего пользовательского домена.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-117">If you don't set up DKIM for your custom domain, Microsoft 365 creates a private and public key pair, enables DKIM signing, and then configures the Microsoft 365 default policy for your custom domain.</span></span> <span data-ttu-id="ac4f8-118">Хотя это достаточное покрытие для большинства клиентов, вы должны вручную настроить DKIM для своего пользовательского домена в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="ac4f8-118">While this is sufficient coverage for most customers, you should manually configure DKIM for your custom domain in the following circumstances:</span></span>

- <span data-ttu-id="ac4f8-119">У вас есть несколько пользовательских доменов в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac4f8-119">You have more than one custom domain in Microsoft 365</span></span>

- <span data-ttu-id="ac4f8-120">вы также собираетесь настроить DMARC (рекомендуется);</span><span class="sxs-lookup"><span data-stu-id="ac4f8-120">You're going to set up DMARC too (recommended)</span></span>

- <span data-ttu-id="ac4f8-121">вам необходим контроль над закрытым ключом;</span><span class="sxs-lookup"><span data-stu-id="ac4f8-121">You want control over your private key</span></span>

- <span data-ttu-id="ac4f8-122">вам необходимо настроить записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-122">You want to customize your CNAME records</span></span>

- <span data-ttu-id="ac4f8-123">вам нужно настроить ключи DKIM для сообщений электронной почты со стороннего домена, например при использовании стороннего средства для массовых рассылок.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-123">You want to set up DKIM keys for email originating out of a third-party domain, for example, if you use a third-party bulk mailer.</span></span>

<span data-ttu-id="ac4f8-124">В этой статье</span><span class="sxs-lookup"><span data-stu-id="ac4f8-124">In this article:</span></span>

- [<span data-ttu-id="ac4f8-125">Как DKIM работает лучше, чем один SPF, для предотвращения злонамеренного подмены</span><span class="sxs-lookup"><span data-stu-id="ac4f8-125">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [<span data-ttu-id="ac4f8-126">Обновление 1024-разрядных ключей до 2048-разрядных ключей шифрования DKIM вручную</span><span class="sxs-lookup"><span data-stu-id="ac4f8-126">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [<span data-ttu-id="ac4f8-127">Шаги, которые необходимо сделать, чтобы вручную настроить DKIM</span><span class="sxs-lookup"><span data-stu-id="ac4f8-127">Steps you need to do to manually set up DKIM</span></span>](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [<span data-ttu-id="ac4f8-128">Чтобы настроить DKIM для нескольких пользовательских доменов</span><span class="sxs-lookup"><span data-stu-id="ac4f8-128">To configure DKIM for more than one custom domain</span></span>](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [<span data-ttu-id="ac4f8-129">Отключение политики подписи DKIM для пользовательского домена</span><span class="sxs-lookup"><span data-stu-id="ac4f8-129">Disabling the DKIM signing policy for a custom domain</span></span>](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [<span data-ttu-id="ac4f8-130">Поведение по умолчанию для DKIM и Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac4f8-130">Default behavior for DKIM and Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [<span data-ttu-id="ac4f8-131">Как настроить DKIM так, чтобы сторонняя служба могла отправлять сообщения электронной почты от имени вашего личного домена</span><span class="sxs-lookup"><span data-stu-id="ac4f8-131">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [<span data-ttu-id="ac4f8-132">Следующие шаги: после настройки DKIM для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac4f8-132">Next steps: After you set up DKIM for Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a><span data-ttu-id="ac4f8-133">Как DKIM работает лучше, чем один SPF, для предотвращения злонамеренного подмены</span><span class="sxs-lookup"><span data-stu-id="ac4f8-133">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>
<span data-ttu-id="ac4f8-134"><a name="HowDKIMWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="ac4f8-134"><a name="HowDKIMWorks"> </a></span></span>

<span data-ttu-id="ac4f8-p105">Инфраструктура политики отправителей добавляет сведения в конверт сообщения, а технология DKIM шифрует подпись в заголовке сообщения. При пересылке фрагменты конверта этого сообщения могут быть удалены сервером пересылки. Поскольку цифровая подпись остается в заголовке сообщения, технология DKIM работает даже при пересылке, как показано в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-p105">SPF adds information to a message envelope but DKIM actually encrypts a signature within the message header. When you forward a message, portions of that message's envelope can be stripped away by the forwarding server. Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span></span>

![Схема, на которой показана проверка подлинности DKIM: пересланное сообщение не прошло проверку инфраструктурой политики отправителей](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

<span data-ttu-id="ac4f8-p106">Если бы в этом примере вы опубликовали только запись типа TXT инфраструктуры политики отправителей для домена, почтовый сервер получателя мог бы пометить ваше сообщение как спам, что привело бы к ложному срабатыванию. Добавление DKIM в этом сценарии позволяет снизить количество ложных срабатываний. Так как в технологии DKIM для проверки подлинности используется шифрование с помощью открытого ключа, а не только IP-адресов, она считается более надежным способом проверки подлинности, чем инфраструктура политики отправителей. Рекомендуем использовать обе эти технологии, а также DMARC в вашем развертывании.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-p106">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result. The addition of DKIM in this scenario reduces false positive spam reporting. Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF. We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span></span>

<span data-ttu-id="ac4f8-p107">Подробности: DKIM использует закрытый ключ для вставки зашифрованной подписи в заголовки сообщений. Имя подписывающего домена (или домена исходящей почты) вставляется в заголовок в качестве значения поля **d=**. Проверяющий домен (или домен получателя) затем использует поле **d=** для поиска открытого ключа в DNS и проверки подлинности сообщения. Так сообщение проходит проверку DKIM.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-p107">The nitty gritty: DKIM uses a private key to insert an encrypted signature into the message headers. The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header. The verifying domain, or recipient's domain, then use the **d=** field to look up the public key from DNS and authenticate the message. If the message is verified, the DKIM check passes.</span></span>

## <a name="manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a><span data-ttu-id="ac4f8-147">Обновление 1024-разрядных ключей до 2048-разрядных ключей шифрования DKIM вручную</span><span class="sxs-lookup"><span data-stu-id="ac4f8-147">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>
<span data-ttu-id="ac4f8-148"><a name="1024to2048DKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="ac4f8-148"><a name="1024to2048DKIM"> </a></span></span>

<span data-ttu-id="ac4f8-149">Так как ключи DKIM могут быть 1024- и 2048-разрядными, эти инструкции предназначены для перехода с 1024- на 2048-разрядные ключи.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-149">Since both 1024 and 2048 bitness are supported for DKIM keys, these directions will tell you how to upgrade your 1024-bit key to 2048.</span></span> <span data-ttu-id="ac4f8-150">Описанные ниже действия относятся к двум вариантам использования. Выберите вариант, подходящий для вашей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-150">The steps below are for two use-cases, please choose the one that best fits your configuration.</span></span>

1. <span data-ttu-id="ac4f8-151">Если вы **уже настроили DKIM**, измените разрядность следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ac4f8-151">When you **already have DKIM configured**, you rotate bitness as follows:</span></span>

   1. <span data-ttu-id="ac4f8-152">[Подключитесь к рабочим нагрузкам Office 365 с помощью PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="ac4f8-152">[Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="ac4f8-153">(Командлет из Exchange Online.)</span><span class="sxs-lookup"><span data-stu-id="ac4f8-153">(The cmdlet comes from Exchange Online.)</span></span>
   1. <span data-ttu-id="ac4f8-154">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ac4f8-154">Run the following command:</span></span>

      ```powershell 
      Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
      ```

1. <span data-ttu-id="ac4f8-155">В случае **новой реализации DKIM**:</span><span class="sxs-lookup"><span data-stu-id="ac4f8-155">Or for a **new implementation of DKIM**:</span></span>

   1. <span data-ttu-id="ac4f8-156">[Подключитесь к рабочим нагрузкам Office 365 с помощью PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="ac4f8-156">[Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="ac4f8-157">(Это командлет Exchange Online.)</span><span class="sxs-lookup"><span data-stu-id="ac4f8-157">(This is an Exchange Online cmdlet.)</span></span>
   1. <span data-ttu-id="ac4f8-158">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ac4f8-158">Run the following command:</span></span>

      ```powershell
      New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True
      ```

<span data-ttu-id="ac4f8-159">Оставайтесь на связи с Microsoft 365, чтобы *проверить* конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-159">Stay connected to Microsoft 365 to *verify* the configuration.</span></span>

1. <span data-ttu-id="ac4f8-160">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ac4f8-160">Run the following command:</span></span>

   ```powershell
   Get-DkimSigningConfig -Identity {Domain for which the configuration was set} | Format-List
   ```

> [!TIP]
> <span data-ttu-id="ac4f8-161">Этот новый 2048-разрядный ключ вступает в силу с даты, указанной в параметре RotateOnDate. Пока же сообщения электронной почты будут отправляться с использованием 1024-разрядного ключа.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-161">This new 2048-bit key takes effect on the RotateOnDate, and will send emails with the 1024-bit key in the interim.</span></span> <span data-ttu-id="ac4f8-162">Через четыре дня вы снова можете выполнить проверку с использованием 2048-разрядного ключа (то есть после применения изменения ко второму селектору).</span><span class="sxs-lookup"><span data-stu-id="ac4f8-162">After four days, you can test again with the 2048-bit key (that is, once the rotation takes effect to the second selector).</span></span>

<span data-ttu-id="ac4f8-163">Если вы хотите перейти ко второму селектору, вы можете: а) позволить службе Microsoft 365 повернуть селектор и обновить ее до 2048-разрядности в течение следующих 6 месяцев, или б) через 4 дня и подтвердить, что 2048-разрядности используется вручную поверните вторую клавишу выбора с помощью соответствующего командлета, указанного выше.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-163">If you want to rotate to the second selector, your options are a) let the Microsoft 365 service rotate the selector and upgrade to 2048-bitness within the next 6 months, or b) after 4 days and confirming that 2048-bitness is in use, manually rotate the second selector key by using the appropriate cmdlet listed above.</span></span>

## <a name="steps-you-need-to-do-to-manually-set-up-dkim"></a><span data-ttu-id="ac4f8-164">Шаги, которые необходимо сделать, чтобы вручную настроить DKIM</span><span class="sxs-lookup"><span data-stu-id="ac4f8-164">Steps you need to do to manually set up DKIM</span></span>
<span data-ttu-id="ac4f8-165"><a name="SetUpDKIMO365"> </a></span><span class="sxs-lookup"><span data-stu-id="ac4f8-165"><a name="SetUpDKIMO365"> </a></span></span>

<span data-ttu-id="ac4f8-166">Настройка DKIM состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="ac4f8-166">To configure DKIM, you will complete these steps:</span></span>

- [<span data-ttu-id="ac4f8-167">Публикация двух записей CNAME для личного домена в DNS</span><span class="sxs-lookup"><span data-stu-id="ac4f8-167">Publish two CNAME records for your custom domain in DNS</span></span>](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [<span data-ttu-id="ac4f8-168">Включите подпись DKIM для вашего пользовательского домена</span><span class="sxs-lookup"><span data-stu-id="ac4f8-168">Enable DKIM signing for your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a><span data-ttu-id="ac4f8-169">Публикация двух записей CNAME для личного домена в DNS</span><span class="sxs-lookup"><span data-stu-id="ac4f8-169">Publish two CNAME records for your custom domain in DNS</span></span>
<span data-ttu-id="ac4f8-170"><a name="Publish2CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="ac4f8-170"><a name="Publish2CNAME"> </a></span></span>

<span data-ttu-id="ac4f8-171">Для каждого домена, для которого требуется добавить подпись DKIM в DNS, необходимо опубликовать две записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-171">For each domain for which you want to add a DKIM signature in DNS, you need to publish two CNAME records.</span></span>

<span data-ttu-id="ac4f8-172">Чтобы создать записи селектора, выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="ac4f8-172">Run the following commands to create the selector records:</span></span>

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

<span data-ttu-id="ac4f8-173">Если вы подготовили пользовательские домены в дополнение к исходному домену в Microsoft 365, вы должны опубликовать две записи CNAME для каждого дополнительного домена.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-173">If you have provisioned custom domains in addition to the initial domain in Microsoft 365, you must publish two CNAME records for each additional domain.</span></span> <span data-ttu-id="ac4f8-174">Итак, если у вас есть два домена, вы должны опубликовать две дополнительные записи CNAME и так далее.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-174">So, if you have two domains, you must publish two additional CNAME records, and so on.</span></span>

<span data-ttu-id="ac4f8-175">Для записей CNAME используйте указанный ниже формат.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-175">Use the following format for the CNAME records.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac4f8-176">Если вы один из наших клиентов GCC High, мы вычисляем _domainGuid_ другим способом.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-176">If you are one of our GCC High customers, we calculate _domainGuid_ differently!</span></span> <span data-ttu-id="ac4f8-177">Вместо поиска записи MX для вашего _initialDomain_ с целью вычисления _domainGuid_ мы вычисляем его непосредственно на основании личного домена.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-177">Instead of looking up the MX record for your _initialDomain_ to calculate _domainGuid_, instead we calculate it directly from the customized domain.</span></span> <span data-ttu-id="ac4f8-178">Например, если ваш личный домен — contoso.com, ваш domainGuid будет иметь вид contoso-com, то есть все точки будут заменены дефисами.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-178">For example, if your customized domain is "contoso.com" your domainGuid becomes "contoso-com", any periods are replaced with a dash.</span></span> <span data-ttu-id="ac4f8-179">Таким образом, независимо от записи MX, на которую указывает ваш initialDomain, вы всегда можете использовать описанный выше метод для вычисления domainGuid, чтобы использовать его в записях CNAME.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-179">So, regardless of what MX record your initialDomain points to, you'll always use the above method to calculate the domainGuid to use in your CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

<span data-ttu-id="ac4f8-180">Где:</span><span class="sxs-lookup"><span data-stu-id="ac4f8-180">Where:</span></span>

- <span data-ttu-id="ac4f8-181">В Microsoft 365 селекторами всегда будут «селектор1» или «селектор2».</span><span class="sxs-lookup"><span data-stu-id="ac4f8-181">For Microsoft 365, the selectors will always be "selector1" or "selector2".</span></span>

- <span data-ttu-id="ac4f8-182">Значение _domainGUID_ — такое же, как и значение _domainGUID_ в пользовательской записи MX для вашего личного домена, которое указывается перед адресом mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-182">_domainGUID_ is the same as the _domainGUID_ in the customized MX record for your custom domain that appears before mail.protection.outlook.com.</span></span> <span data-ttu-id="ac4f8-183">Например, в следующей записи MX для домена contoso.com значение _domainGUID_ равно contoso-com:</span><span class="sxs-lookup"><span data-stu-id="ac4f8-183">For example, in the following MX record for the domain contoso.com, the _domainGUID_ is contoso-com:</span></span>

  > <span data-ttu-id="ac4f8-184">contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-184">contoso.com.</span></span>  <span data-ttu-id="ac4f8-185">3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ac4f8-185">3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span></span>

- <span data-ttu-id="ac4f8-186">_initialDomain_ - это домен, который вы использовали при регистрации в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-186">_initialDomain_ is the domain that you used when you signed up for Microsoft 365.</span></span> <span data-ttu-id="ac4f8-187">Исходные домены всегда заканчиваются на onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-187">Initial domains always end in onmicrosoft.com.</span></span> <span data-ttu-id="ac4f8-188">О том, как узнать свой исходный домен, читайте в разделе [часто задаваемых вопросов](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span><span class="sxs-lookup"><span data-stu-id="ac4f8-188">For information about determining your initial domain, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

<span data-ttu-id="ac4f8-189">Например, если у вас есть исходный домен cohovineyardandwinery.onmicrosoft.com и два личных домена cohovineyard.com и cohowinery.com, вам необходимо настроить две записи CNAME для каждого дополнительного домена (всего четыре записи CNAME).</span><span class="sxs-lookup"><span data-stu-id="ac4f8-189">For example, if you have an initial domain of cohovineyardandwinery.onmicrosoft.com, and two custom domains cohovineyard.com and cohowinery.com, you would need to set up two CNAME records for each additional domain, for a total of four CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector1._domainkey
Points to address or value:    selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600
```

> [!NOTE]
> <span data-ttu-id="ac4f8-190">Важно создать вторую запись, но только один из селекторов может быть доступен во время создания.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-190">It's important to create the second record, but only one of the selectors may be available at the time of creation.</span></span> <span data-ttu-id="ac4f8-191">По сути, второй селектор может указывать на адрес, который еще не создан.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-191">In essence, the second selector might point to an address that hasn't been created yet.</span></span> <span data-ttu-id="ac4f8-192">Мы все же рекомендуем создать вторую запись CNAME, поскольку ротация ключей будет беспроблемной.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-192">We still recommended that you create the second CNAME record, because your key rotation will be seamless.</span></span>

> [!CAUTION]
> <span data-ttu-id="ac4f8-193">Автоматическая ротация ключей временно отключена, поскольку мы реализуем изменения структуры в процессе создания ключей.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-193">Automatic key rotation has been temporarily disabled as we implement some design changes in how we create keys.</span></span> <span data-ttu-id="ac4f8-194">Рекомендуется использовать несколько ключей для обеспечения их периодической ротации.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-194">It's a good practice to have multiple keys so that you can rotate them periodically.</span></span> <span data-ttu-id="ac4f8-195">Хотя их трудно взломать, однако разумной стратегией снижения рисков считается защита от олицетворения.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-195">Although it's hard to crack, it's still a practical mitigation strategy to protect against things like impersonation.</span></span> <span data-ttu-id="ac4f8-196">Чтобы сделать это в своей организации следуйте положениям документа [Rotate-DkimSigningConfig](https://docs.microsoft.com/powershell/module/exchange/rotate-dkimsigningconfig).</span><span class="sxs-lookup"><span data-stu-id="ac4f8-196">You can follow the [Rotate-DkimSigningConfig](https://docs.microsoft.com/powershell/module/exchange/rotate-dkimsigningconfig) document to help do this for your organization.</span></span> <span data-ttu-id="ac4f8-197">Мы ожидаем повторное включение автоматической ротации до августа 2020 г.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-197">We expect that automatic rotation will be enabled again by August 2020.</span></span>

### <a name="enable-dkim-signing-for-your-custom-domain"></a><span data-ttu-id="ac4f8-198">Включите подпись DKIM для вашего пользовательского домена</span><span class="sxs-lookup"><span data-stu-id="ac4f8-198">Enable DKIM signing for your custom domain</span></span>
<span data-ttu-id="ac4f8-199"><a name="EnableDKIMinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="ac4f8-199"><a name="EnableDKIMinO365"> </a></span></span>

<span data-ttu-id="ac4f8-200">После публикации записей CNAME в DNS вы готовы включить подпись DKIM через Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-200">Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Microsoft 365.</span></span> <span data-ttu-id="ac4f8-201">Это можно сделать в Центре администрирования Microsoft 365 или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-201">You can do this either through the Microsoft 365 admin center or by using PowerShell.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a><span data-ttu-id="ac4f8-202">Включение функции подписывания с помощью DKIM для личного домена в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="ac4f8-202">To enable DKIM signing for your custom domain through the admin center</span></span>

1. <span data-ttu-id="ac4f8-203">[Войдите в Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4), используя свою рабочую или учебную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-203">[Sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="ac4f8-204">В левом верхнем углу щелкните значок средства запуска приложений и выберите **Администратор**.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-204">Select the app launcher icon in the upper-left and choose **Admin**.</span></span>

3. <span data-ttu-id="ac4f8-205">В области навигации слева внизу разверните узел **Администратор** и выберите элемент **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-205">In the lower-left navigation, expand **Admin** and choose **Exchange**.</span></span>

4. <span data-ttu-id="ac4f8-206">Перейдите в раздел **Защита** \> **dkim**.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-206">Go to **Protection** \> **dkim**.</span></span>

5. <span data-ttu-id="ac4f8-p120">Выберите домен, для которого требуется включить DKIM, а затем в разделе **Добавлять подписи DKIM в сообщения для этого домена** нажмите **Включить**. Повторите этот шаг для каждого личного домена.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-p120">Select the domain for which you want to enable DKIM and then, for **Sign messages for this domain with DKIM signatures**, choose **Enable**. Repeat this step for each custom domain.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a><span data-ttu-id="ac4f8-209">Как включить подпись с помощью DKIM для личного домена, используя PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac4f8-209">To enable DKIM signing for your custom domain by using PowerShell</span></span>

1. <span data-ttu-id="ac4f8-210">[Подключение к PowerShell для Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ac4f8-210">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="ac4f8-211">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ac4f8-211">Run the following command:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity <domain> -Enabled $true
   ```

   <span data-ttu-id="ac4f8-212">Где _domain_ — имя личного домена, для которого требуется включить функцию подписывания с помощью DKIM.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-212">Where _domain_ is the name of the custom domain that you want to enable DKIM signing for.</span></span>

   <span data-ttu-id="ac4f8-213">Например, для домена contoso.com:</span><span class="sxs-lookup"><span data-stu-id="ac4f8-213">For example, for the domain contoso.com:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a><span data-ttu-id="ac4f8-214">Подтвердить, что подпись DKIM правильно настроена для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac4f8-214">To Confirm DKIM signing is configured properly for Microsoft 365</span></span>

<span data-ttu-id="ac4f8-p121">Прежде чем выполнять указанные ниже действия для проверки настройки DKIM, подождите несколько минут. Для распространения информации DKIM о домене по сети требуется время.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-p121">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM. This allows time for the DKIM information about the domain to be spread throughout the network.</span></span>

- <span data-ttu-id="ac4f8-217">Отправьте сообщение из учетной записи в домене Microsoft 365 с поддержкой DKIM на другую учетную запись электронной почты, например outlook.com или Hotmail.com.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-217">Send a message from an account within your Microsoft 365 DKIM-enabled domain to another email account such as outlook.com or Hotmail.com.</span></span>

- <span data-ttu-id="ac4f8-p122">Не используйте для проверки учетную запись aol.com. AOL может пропустить проверку DKIM в случае успешной проверки SPF. Такая проверка будет недействительной.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-p122">Do not use an aol.com account for testing purposes. AOL may skip the DKIM check if the SPF check passes. This will nullify your test.</span></span>

- <span data-ttu-id="ac4f8-p123">Откройте сообщение и посмотрите на заголовок. Инструкции для просмотра заголовка сообщения могут быть разными, в зависимости от клиента вашей электронной связи. Дополнительные сведения о том, как просматривать заголовки сообщений в Outlook, см. в разделе [Просмотр заголовков сообщений из Интернета в Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span><span class="sxs-lookup"><span data-stu-id="ac4f8-p123">Open the message and look at the header. Instructions for viewing the header for the message will vary depending on your messaging client. For instructions on viewing message headers in Outlook, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

  <span data-ttu-id="ac4f8-p124">Сообщение, подписанное с помощью DKIM, будет содержать имя узла и доменное имя, указанные вами при публикации записей CNAME. Сообщение будет выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="ac4f8-p124">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries. The message will look something like this example:</span></span>

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- <span data-ttu-id="ac4f8-p125">Найдите заголовок Authentication-Results. Принимающие службы помечают входящую почту по-разному, но результат должен содержать элемент, подобный **DKIM=pass** или **DKIM=OK**.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-p125">Look for the Authentication-Results header. While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span></span>

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a><span data-ttu-id="ac4f8-228">Чтобы настроить DKIM для нескольких пользовательских доменов</span><span class="sxs-lookup"><span data-stu-id="ac4f8-228">To configure DKIM for more than one custom domain</span></span>
<span data-ttu-id="ac4f8-229"><a name="DKIMMultiDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="ac4f8-229"><a name="DKIMMultiDomain"> </a></span></span>

<span data-ttu-id="ac4f8-230">Действия, описанные в этой статье, необходимо выполнить для каждого дополнительного личного домена, для которого требуется включить DKIM.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-230">If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain.</span></span> <span data-ttu-id="ac4f8-231">В частности, выполните все шаги в разделе [Что нужно сделать, чтобы вручную настроить DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span><span class="sxs-lookup"><span data-stu-id="ac4f8-231">Specifically, complete all steps in [What you need to do to manually set up DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span></span>

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a><span data-ttu-id="ac4f8-232">Отключение политики подписи DKIM для пользовательского домена</span><span class="sxs-lookup"><span data-stu-id="ac4f8-232">Disabling the DKIM signing policy for a custom domain</span></span> 
<span data-ttu-id="ac4f8-233"><a name="DisableDKIMSigningPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="ac4f8-233"><a name="DisableDKIMSigningPolicy"> </a></span></span>

<span data-ttu-id="ac4f8-234">Отключение политики подписывания полностью не отключает DKIM.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-234">Disabling the signing policy does not completely disable DKIM.</span></span> <span data-ttu-id="ac4f8-235">Через некоторое время Microsoft 365 автоматически применит политику по умолчанию для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-235">After a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span> <span data-ttu-id="ac4f8-236">Для получения дополнительной информации см. [Поведение по умолчанию для DKIM и Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span><span class="sxs-lookup"><span data-stu-id="ac4f8-236">For more information, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a><span data-ttu-id="ac4f8-237">Отключение политики подписывания DKIM с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac4f8-237">To disable the DKIM signing policy by using Windows PowerShell</span></span>

1. <span data-ttu-id="ac4f8-238">[Подключение к PowerShell для Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ac4f8-238">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="ac4f8-239">Выполните одну из указанных ниже команд для каждого домена, для которого требуется отключить подпись с помощью DKIM.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-239">Run one of the following commands for each domain for which you want to disable DKIM signing.</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity <domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="ac4f8-240">Пример:</span><span class="sxs-lookup"><span data-stu-id="ac4f8-240">For example:</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="ac4f8-241">или</span><span class="sxs-lookup"><span data-stu-id="ac4f8-241">Or</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   <span data-ttu-id="ac4f8-242">Где _number_ — индекс политики.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-242">Where _number_ is the index of the policy.</span></span> <span data-ttu-id="ac4f8-243">Например:</span><span class="sxs-lookup"><span data-stu-id="ac4f8-243">For example:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a><span data-ttu-id="ac4f8-244">Поведение по умолчанию для DKIM и Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac4f8-244">Default behavior for DKIM and Microsoft 365</span></span>
<span data-ttu-id="ac4f8-245"><a name="DefaultDKIMbehavior"> </a></span><span class="sxs-lookup"><span data-stu-id="ac4f8-245"><a name="DefaultDKIMbehavior"> </a></span></span>

<span data-ttu-id="ac4f8-246">Если вы не активируете DKIM, Microsoft 365 автоматически создает 1024-битный открытый ключ DKIM для вашего домена по умолчанию и связанный с ним закрытый ключ, который мы храним внутри нашего центра обработки данных.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-246">If you do not enable DKIM, Microsoft 365 automatically creates a 1024-bit DKIM public key for your default domain and the associated private key which we store internally in our datacenter.</span></span> <span data-ttu-id="ac4f8-247">По умолчанию Microsoft 365 использует конфигурацию подписи по умолчанию для доменов, у которых нет политики.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-247">By default, Microsoft 365 uses a default signing configuration for domains that do not have a policy in place.</span></span> <span data-ttu-id="ac4f8-248">Это означает, что если вы не настроите DKIM самостоятельно, Microsoft 365 будет использовать политику по умолчанию и ключи, которые она создает, чтобы включить DKIM для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-248">This means that if you do not set up DKIM yourself, Microsoft 365 will use its default policy and keys it creates to enable DKIM for your domain.</span></span>

<span data-ttu-id="ac4f8-249">Кроме того, если вы отключите подпись DKIM после включения, через некоторое время Microsoft 365 автоматически применит политику по умолчанию для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-249">Also, if you disable DKIM signing after enabling it, after a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span>

<span data-ttu-id="ac4f8-250">В следующем примере предположим, что DKIM для fabrikam.com был включен Microsoft 365, а не администратором домена.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-250">In the following example, suppose that DKIM for fabrikam.com was enabled by Microsoft 365, not by the administrator of the domain.</span></span> <span data-ttu-id="ac4f8-251">Это означает, что в службе DNS нет требуемых записей CNAME.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-251">This means that the required CNAMEs do not exist in DNS.</span></span> <span data-ttu-id="ac4f8-252">Подписи DKIM для электронной почты из этого домена будут выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ac4f8-252">DKIM signatures for email from this domain will look something like this:</span></span>

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

<span data-ttu-id="ac4f8-253">В этом примере имя узла и доменное имя содержат значения, на которые указывала бы запись CNAME, если бы администратор домена настроил подпись DKIM для домена fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-253">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator.</span></span> <span data-ttu-id="ac4f8-254">В конце концов, каждое сообщение, отправленное из Microsoft 365, будет подписано DKIM.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-254">Eventually, every single message sent from Microsoft 365 will be DKIM-signed.</span></span> <span data-ttu-id="ac4f8-255">Если вы включили DKIM самостоятельно, то домен будет совпадать с доменом, указанным в адресе From: (в этом случае fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="ac4f8-255">If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com.</span></span> <span data-ttu-id="ac4f8-256">В противном случае будет использоваться исходный домен организации.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-256">If you don't, it will not align and instead will use your organization's initial domain.</span></span> <span data-ttu-id="ac4f8-257">О том, как узнать свой исходный домен, читайте в разделе [часто задаваемых вопросов](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span><span class="sxs-lookup"><span data-stu-id="ac4f8-257">For information about determining your initial domain, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a><span data-ttu-id="ac4f8-258">Настройте DKIM таким образом, чтобы сторонняя служба могла отправлять электронные письма от имени вашего личного домена</span><span class="sxs-lookup"><span data-stu-id="ac4f8-258">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>
<span data-ttu-id="ac4f8-259"><a name="SetUp3rdPartyspoof"> </a></span><span class="sxs-lookup"><span data-stu-id="ac4f8-259"><a name="SetUp3rdPartyspoof"> </a></span></span>

<span data-ttu-id="ac4f8-p132">Некоторые поставщика услуг электронной почты, или поставщики программного обеспечения как службы, позволяют настраивать ключи DKIM для сообщений электронной почты, отправляемых из их службы. Для этого вам необходимо координировать свои действия с третьей стороной, чтобы настроить необходимые записи DNS. В каждой организации это делают по-своему. Процесс полностью зависит от конкретного предприятия.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-p132">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service. This requires coordination between yourself and the third-party in order to set up the necessary DNS records. No two organizations do it exactly the same way. Instead, the process depends entirely on the organization.</span></span>

<span data-ttu-id="ac4f8-264">Пример сообщения с правильно настроенными ключами DKIM для доменов contoso.com и bulkemailprovider.com:</span><span class="sxs-lookup"><span data-stu-id="ac4f8-264">An example message showing a properly configured DKIM for contoso.com and bulkemailprovider.com might look like this:</span></span>

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

<span data-ttu-id="ac4f8-265">В этом примере для достижения представленного результата:</span><span class="sxs-lookup"><span data-stu-id="ac4f8-265">In this example, in order to achieve this result:</span></span>

1. <span data-ttu-id="ac4f8-266">Поставщик услуг массовой рассылки предоставил компании Contoso открытый ключ DKIM.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-266">Bulk Email Provider gave Contoso a public DKIM key.</span></span>

2. <span data-ttu-id="ac4f8-267">Компания Contoso опубликовала ключ DKIM в своей записи DNS.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-267">Contoso published the DKIM key to its DNS record.</span></span>

3. <span data-ttu-id="ac4f8-p133">При отправке сообщения поставщик услуг массовой рассылки подписывает ключ соответствующим закрытым ключом. Таким образом он добавляет подпись DKIM в заголовок сообщения.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-p133">When sending email, Bulk Email Provider signs the key with the corresponding private key. By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span></span>

4. <span data-ttu-id="ac4f8-270">Получающие почтовые системы выполняют проверку DKIM путем сравнения значения подписи DKIM-Signature d=\<domain\>с доменом в поле адреса "От" (5322.From) сообщения.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-270">Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message.</span></span> <span data-ttu-id="ac4f8-271">В этом примере значения совпадают:</span><span class="sxs-lookup"><span data-stu-id="ac4f8-271">In this example, the values match:</span></span>

   > <span data-ttu-id="ac4f8-272">sender@**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="ac4f8-272">sender@**contoso.com**</span></span>

   > <span data-ttu-id="ac4f8-273">d=**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="ac4f8-273">d=**contoso.com**</span></span>
   
## <a name="identify-domains-that-do-not-send-email"></a><span data-ttu-id="ac4f8-274">Идентификация доменов, с которых не отправляется почта</span><span class="sxs-lookup"><span data-stu-id="ac4f8-274">Identify domains that do not send email</span></span>

<span data-ttu-id="ac4f8-275">Организациям следует явно указать, отправляется ли почта с домена, с помощью `v=DKIM1; p=` в записи DKIM для этих доменов.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-275">Organizations should explicitly state if a domain does not send email by specifying `v=DKIM1; p=` in the DKIM record for those domains.</span></span> <span data-ttu-id="ac4f8-276">При этом почтовым серверам получателя сообщается об отсутствии допустимых открытых ключей для этого домена и необходимости отклонить любое сообщение из него.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-276">This advises receiving email servers that there are no valid public keys for the domain, and any email claiming to be from that domain should be rejected.</span></span> <span data-ttu-id="ac4f8-277">Это нужно сделать для каждого домена и поддомена, использующего DKIM.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-277">You should do this for each domain and subdomain using a wildcard DKIM.</span></span>

<span data-ttu-id="ac4f8-278">Например, запись DKIM может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ac4f8-278">For example, the DKIM record would look like this:</span></span>

```console
*._domainkey.SubDomainThatShouldntSendMail.contoso.com. TXT "v=DKIM1; p="
```

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a><span data-ttu-id="ac4f8-279">Следующие шаги: после настройки DKIM для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac4f8-279">Next steps: After you set up DKIM for Microsoft 365</span></span>
<span data-ttu-id="ac4f8-280"><a name="DKIMNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="ac4f8-280"><a name="DKIMNextSteps"> </a></span></span>

<span data-ttu-id="ac4f8-281">Несмотря на то, что технология DKIM предназначена для предотвращения спуфинга, она работает эффективнее вместе с инфраструктурой политики отправителей и DMARC.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-281">Although DKIM is designed to help prevent spoofing, DKIM works better with SPF and DMARC.</span></span> <span data-ttu-id="ac4f8-282">После настройки DKIM настройте инфраструктуру политики отправителей.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-282">Once you have set up DKIM, if you have not already set up SPF you should do so.</span></span> <span data-ttu-id="ac4f8-283">Для быстрого ознакомления с SPF и его быстрой настройки см. раздел [Настройка SPF в Microsoft 365, чтобы предотвратить подделку](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="ac4f8-283">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="ac4f8-284">Для более глубокого понимания того, как Microsoft 365 использует SPF, или для устранения неполадок или нестандартных развертываний, таких как гибридные развертывания, начните с того, [как Microsoft 365 использует Sender Policy Framework (SPF) для предотвращения спуфинга](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="ac4f8-284">For a more in-depth understanding of how Microsoft 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="ac4f8-285">Далее см. [Использование DMARC для проверки электронной почты](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="ac4f8-285">Next, see [Use DMARC to validate email](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="ac4f8-286">[Заголовки сообщений защиты от спама](anti-spam-message-headers.md) включают поля синтаксиса и заголовка, используемые Microsoft 365 для проверок DKIM.</span><span class="sxs-lookup"><span data-stu-id="ac4f8-286">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for DKIM checks.</span></span>
