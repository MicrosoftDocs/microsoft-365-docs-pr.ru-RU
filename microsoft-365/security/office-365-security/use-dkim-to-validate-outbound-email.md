---
title: Использование DKIM для работы с электронной почтой в личном домене
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
audience: ITPro
ms.topic: article
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как использовать технологию DomainKeys Identified Mail (DKIM) для Microsoft 365, чтобы обеспечить доверие конечных почтовых систем к сообщениям, отправленным из вашего личного домена.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9aa67d7875bb7f81c6569b56704d221b57378962
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108503"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a><span data-ttu-id="7b89e-103">Используйте DKIM для проверки исходящей электронной почты, отправленной с вашего пользовательского домена</span><span class="sxs-lookup"><span data-stu-id="7b89e-103">Use DKIM to validate outbound email sent from your custom domain</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7b89e-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="7b89e-104">**Applies to**</span></span>
- [<span data-ttu-id="7b89e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7b89e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7b89e-106">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="7b89e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7b89e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b89e-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

 <span data-ttu-id="7b89e-108">В этой статье описаны шаги использования DomainKeys Identified Mail (DKIM) с Microsoft 365, гарантирующие, что системы электронной почты назначения доверяют сообщениям, отправленным вовне с вашего пользовательского домена.</span><span class="sxs-lookup"><span data-stu-id="7b89e-108">This article lists the steps to use DomainKeys Identified Mail (DKIM) with Microsoft 365 to ensure that destination email systems trust messages sent outbound from your custom domain.</span></span>

<span data-ttu-id="7b89e-109">В этой статье</span><span class="sxs-lookup"><span data-stu-id="7b89e-109">In this article:</span></span>

- [<span data-ttu-id="7b89e-110">Как DKIM работает лучше, чем один SPF, для предотвращения злонамеренного подмены</span><span class="sxs-lookup"><span data-stu-id="7b89e-110">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>](#how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing)
- [<span data-ttu-id="7b89e-111">Шаги по обновлению 1024-разрядных ключей до 2048-разрядных ключей шифрования DKIM вручную</span><span class="sxs-lookup"><span data-stu-id="7b89e-111">Steps to manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>](#steps-to-manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys)
- [<span data-ttu-id="7b89e-112">Шаги для настройки DKIM вручную</span><span class="sxs-lookup"><span data-stu-id="7b89e-112">Steps to manually set up DKIM</span></span>](#steps-to-manually-set-up-dkim)
- [<span data-ttu-id="7b89e-113">Шаги для настройки DKIM для нескольких личных доменов</span><span class="sxs-lookup"><span data-stu-id="7b89e-113">Steps to configure DKIM for more than one custom domain</span></span>](#to-configure-dkim-for-more-than-one-custom-domain)
- [<span data-ttu-id="7b89e-114">Отключение политики подписи DKIM для пользовательского домена</span><span class="sxs-lookup"><span data-stu-id="7b89e-114">Disabling the DKIM signing policy for a custom domain</span></span>](#disabling-the-dkim-signing-policy-for-a-custom-domain)
- [<span data-ttu-id="7b89e-115">Поведение по умолчанию для DKIM и Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b89e-115">Default behavior for DKIM and Microsoft 365</span></span>](#default-behavior-for-dkim-and-microsoft-365)
- [<span data-ttu-id="7b89e-116">Как настроить DKIM так, чтобы сторонняя служба могла отправлять сообщения электронной почты от имени вашего личного домена</span><span class="sxs-lookup"><span data-stu-id="7b89e-116">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>](#set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain)
- [<span data-ttu-id="7b89e-117">Следующие шаги: после настройки DKIM для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b89e-117">Next steps: After you set up DKIM for Microsoft 365</span></span>](#next-steps-after-you-set-up-dkim-for-microsoft-365)

> [!NOTE]
> <span data-ttu-id="7b89e-118">Microsoft 365 автоматически настраивает DKIM для своих первоначальных доменов «onmicrosoft.com».</span><span class="sxs-lookup"><span data-stu-id="7b89e-118">Microsoft 365 automatically sets up DKIM for its initial 'onmicrosoft.com' domains.</span></span> <span data-ttu-id="7b89e-119">Это означает, что вам не нужно ничего делать, чтобы настроить DKIM для любого исходного имени домена (например, litware.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="7b89e-119">That means you don't need to do anything to set up DKIM for any initial domain names (for example, litware.onmicrosoft.com).</span></span> <span data-ttu-id="7b89e-120">Дополнительные сведения о доменах см. в статье [Вопросы и ответы о доменах](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span><span class="sxs-lookup"><span data-stu-id="7b89e-120">For more information about domains, see [Domains FAQ](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span></span>

<span data-ttu-id="7b89e-121">DKIM — один из трех методов проверки подлинности (SPF, DKIM и DMARC), помогающих запретить злоумышленникам отправлять сообщения, которые выглядят так, как будто они приходят из вашего домена.</span><span class="sxs-lookup"><span data-stu-id="7b89e-121">DKIM is one of the trio of Authentication methods (SPF, DKIM and DMARC) that help prevent attackers from sending messages that look like they come from your domain.</span></span>

<span data-ttu-id="7b89e-p102">DKIM позволяет добавлять цифровую подпись в заголовки отправляемых вовне сообщений электронной почты. При настройке DKIM вы авторизуете домен, чтобы связать его имя с сообщением электронной почты, или подписать сообщение этим именем, с помощью криптографической проверки подлинности. С помощью этой цифровой подписи системы электронной почты могут определить, действительно ли входящее сообщение отправлено из вашего домена.</span><span class="sxs-lookup"><span data-stu-id="7b89e-p102">DKIM lets you add a digital signature to outbound email messages in the message header. When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message using cryptographic authentication. Email systems that get email from your domain can use this digital signature to help verify whether incoming email is legitimate.</span></span>

<span data-ttu-id="7b89e-125">В двух словах, закрытый ключ используется для шифрования заголовка в направленном вовне сообщении электронной почты домена.</span><span class="sxs-lookup"><span data-stu-id="7b89e-125">In basic, a private key encrypts the header in a domain's outgoing email.</span></span> <span data-ttu-id="7b89e-126">В записях DNS домена вы публикуете открытый ключ, с помощью которого принимающие серверы расшифровывают подпись.</span><span class="sxs-lookup"><span data-stu-id="7b89e-126">The public key is published in the domain's DNS records, and receiving servers can use that key to decode the signature.</span></span> <span data-ttu-id="7b89e-127">Проверка DKIM помогает принимающим серверам подтвердить, что почта действительно отправлена из вашего домена и это не *спуфинг*.</span><span class="sxs-lookup"><span data-stu-id="7b89e-127">DKIM verification helps the receiving servers confirm the mail is really coming from your domain and not someone *spoofing* your domain.</span></span>

> [!TIP]
><span data-ttu-id="7b89e-p104">Вы также можете не настраивать DKIM для личного домена. В этом случае Office 365 создаст пару ключей — закрытый и открытый, — включит подпись с помощью DKIM и настроит политику по умолчанию для личного домена Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7b89e-p104">You can choose to do nothing about DKIM for your custom domain too. If you don't set up DKIM for your custom domain, Microsoft 365 creates a private and public key pair, enables DKIM signing, and then configures the Microsoft 365 default policy for your custom domain.</span></span>

 <span data-ttu-id="7b89e-p105">Хотя встроенной в Microsoft 365 конфигурации достаточно для большинства клиентов, вы должны вручную настроить DKIM своего пользовательского домена в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="7b89e-p105">Microsoft-365's built-in DKIM configuration is sufficient coverage for most customers. However, you should manually configure DKIM for your custom domain in the following circumstances:</span></span>

- <span data-ttu-id="7b89e-132">у вас есть несколько пользовательских доменов в Microsoft 365;</span><span class="sxs-lookup"><span data-stu-id="7b89e-132">You have more than one custom domain in Microsoft 365</span></span>
- <span data-ttu-id="7b89e-133">вы также собираетесь настроить DMARC (**рекомендуется**);</span><span class="sxs-lookup"><span data-stu-id="7b89e-133">You're going to set up DMARC too (**recommended**)</span></span>
- <span data-ttu-id="7b89e-134">вам необходим контроль над закрытым ключом;</span><span class="sxs-lookup"><span data-stu-id="7b89e-134">You want control over your private key</span></span>
- <span data-ttu-id="7b89e-135">вам необходимо настроить записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="7b89e-135">You want to customize your CNAME records</span></span>
- <span data-ttu-id="7b89e-136">вам нужно настроить ключи DKIM для сообщений электронной почты со стороннего домена, например при использовании стороннего средства для массовых рассылок.</span><span class="sxs-lookup"><span data-stu-id="7b89e-136">You want to set up DKIM keys for email originating out of a third-party domain, for example, if you use a third-party bulk mailer.</span></span>

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a><span data-ttu-id="7b89e-137">Как DKIM работает лучше, чем один SPF, для предотвращения злонамеренного подмены</span><span class="sxs-lookup"><span data-stu-id="7b89e-137">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>
<span data-ttu-id="7b89e-138"><a name="HowDKIMWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="7b89e-138"><a name="HowDKIMWorks"> </a></span></span>

<span data-ttu-id="7b89e-139">SPF добавляет данные в конверт сообщения, а технология DKIM *шифрует* подпись в заголовке сообщения.</span><span class="sxs-lookup"><span data-stu-id="7b89e-139">SPF adds information to a message envelope but DKIM *encrypts* a signature within the message header.</span></span> <span data-ttu-id="7b89e-140">При пересылке фрагменты конверта этого сообщения могут быть удалены сервером пересылки.</span><span class="sxs-lookup"><span data-stu-id="7b89e-140">When you forward a message, portions of that message's envelope can be stripped away by the forwarding server.</span></span> <span data-ttu-id="7b89e-141">Поскольку цифровая подпись остается в заголовке сообщения, технология DKIM работает даже при пересылке, как показано в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="7b89e-141">Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span></span>

![Схема, на которой показана проверка подлинности DKIM: пересланное сообщение не прошло проверку инфраструктурой политики отправителей](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

<span data-ttu-id="7b89e-p107">В этом примере, если бы вы опубликовали только запись типа TXT инфраструктуры политики отправителей для домена, почтовый сервер получателя мог бы пометить ваше сообщение как спам, что привело бы к ложному срабатыванию. \*\*Добавление DKIM в этом сценарии позволяет снизить количество \*ложных срабатываний\*\*\*. Поскольку в технологии DKIM для проверки подлинности используются не только IP-адреса, но и шифрование с помощью открытого ключа, она считается более надежным способом проверки подлинности, чем SPF. Рекомендуем использовать в вашей инфраструктуре одновременно SPF и DKIM, а также DMARC.</span><span class="sxs-lookup"><span data-stu-id="7b89e-p107">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result. **The addition of DKIM in this scenario reduces *false positive* spam reporting.** Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF. We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span></span>

> [!TIP]
> <span data-ttu-id="7b89e-147">DKIM использует закрытый ключ для вставки зашифрованной подписи в заголовки сообщений.</span><span class="sxs-lookup"><span data-stu-id="7b89e-147">DKIM uses a private key to insert an encrypted signature into the message headers.</span></span> <span data-ttu-id="7b89e-148">Имя подписывающего домена (или домена исходящей почты) вставляется в заголовок в качестве значения поля **d=**.</span><span class="sxs-lookup"><span data-stu-id="7b89e-148">The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header.</span></span> <span data-ttu-id="7b89e-149">Проверяющий домен (или домен получателя) затем использует поле **d=** для поиска открытого ключа в DNS и проверки подлинности сообщения.</span><span class="sxs-lookup"><span data-stu-id="7b89e-149">The verifying domain, or recipient's domain, then uses the **d=** field to look up the public key from DNS, and authenticate the message.</span></span> <span data-ttu-id="7b89e-150">Так сообщение проходит проверку DKIM.</span><span class="sxs-lookup"><span data-stu-id="7b89e-150">If the message is verified, the DKIM check passes.</span></span>


## <a name="steps-to-manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a><span data-ttu-id="7b89e-151">Шаги по обновлению 1024-разрядных ключей до 2048-разрядных ключей шифрования DKIM вручную</span><span class="sxs-lookup"><span data-stu-id="7b89e-151">Steps to manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>
<span data-ttu-id="7b89e-152"><a name="1024to2048DKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="7b89e-152"><a name="1024to2048DKIM"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="7b89e-153">Microsoft 365 автоматически настраивает DKIM для своих доменов *onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="7b89e-153">Microsoft 365 automatically sets up DKIM for *onmicrosoft.com* domains.</span></span> <span data-ttu-id="7b89e-154">Чтобы начать использование DKIM для начальных доменных имен (например, *litware.onmicrosoft.com*), не требуется никаких действий.</span><span class="sxs-lookup"><span data-stu-id="7b89e-154">No steps are needed to use DKIM for any initial domain names (like litware.*onmicrosoft.com*).</span></span> <span data-ttu-id="7b89e-155">Дополнительные сведения о доменах см. в статье [Вопросы и ответы о доменах](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span><span class="sxs-lookup"><span data-stu-id="7b89e-155">For more information about domains, see [Domains FAQ](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span></span>

<span data-ttu-id="7b89e-156">Так как ключи DKIM могут быть 1024- и 2048-разрядными, эти инструкции предназначены для обновления 1024-разрядных ключей до 2048-разрядных в [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="7b89e-156">Since both 1024 and 2048 bitness are supported for DKIM keys, these directions will tell you how to upgrade your 1024-bit key to 2048 in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="7b89e-157">Описанные ниже действия относятся к двум вариантам использования. Выберите вариант, подходящий для вашей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7b89e-157">The steps below are for two use-cases, please choose the one that best fits your configuration.</span></span>

- <span data-ttu-id="7b89e-158">Если вы **уже настроили DKIM**, измените разрядность, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7b89e-158">When you **already have DKIM configured**, you rotate bitness by running the following command:</span></span>

  ```powershell
  Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
  ```

  <span data-ttu-id="7b89e-159">**или**</span><span class="sxs-lookup"><span data-stu-id="7b89e-159">**or**</span></span>

- <span data-ttu-id="7b89e-160">В случае **новой реализации DKIM** выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7b89e-160">For a **new implementation of DKIM**, run the following command:</span></span>

  ```powershell
  New-DkimSigningConfig -DomainName <Domain for which config is to be created> -KeySize 2048 -Enabled $true
  ```

<span data-ttu-id="7b89e-161">Сохраняйте подключение к Exchange Online PowerShell, чтобы *проверить* конфигурацию, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7b89e-161">Stay connected to Exchange Online PowerShell to *verify* the configuration by running the following command:</span></span>

```powershell
Get-DkimSigningConfig -Identity <Domain for which the configuration was set> | Format-List
```

> [!TIP]
> <span data-ttu-id="7b89e-162">Этот новый 2048-разрядный ключ вступает в силу с даты, указанной в параметре RotateOnDate. Пока же сообщения электронной почты будут отправляться с использованием 1024-разрядного ключа.</span><span class="sxs-lookup"><span data-stu-id="7b89e-162">This new 2048-bit key takes effect on the RotateOnDate, and will send emails with the 1024-bit key in the interim.</span></span> <span data-ttu-id="7b89e-163">Через четыре дня вы снова можете выполнить проверку с использованием 2048-разрядного ключа (то есть после применения изменения ко второму селектору).</span><span class="sxs-lookup"><span data-stu-id="7b89e-163">After four days, you can test again with the 2048-bit key (that is, once the rotation takes effect to the second selector).</span></span>

<span data-ttu-id="7b89e-164">Если вы хотите перейти ко второму селектору, вы можете: а) позволить службе Microsoft 365 повернуть селектор и обновить ее до 2048-разрядности в течение следующих 6 месяцев, или б) через 4 дня и подтвердить, что 2048-разрядности используется вручную поверните вторую клавишу выбора с помощью соответствующего командлета, указанного выше.</span><span class="sxs-lookup"><span data-stu-id="7b89e-164">If you want to rotate to the second selector, your options are a) let the Microsoft 365 service rotate the selector and upgrade to 2048-bitness within the next 6 months, or b) after 4 days and confirming that 2048-bitness is in use, manually rotate the second selector key by using the appropriate cmdlet listed above.</span></span>

<span data-ttu-id="7b89e-165">Дополнительные сведения о синтаксисе и параметрах см. в следующих статьях: [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig), [New-DkimSigningConfig](/powershell/module/exchange/new-dkimsigningconfig) и [Get-DkimSigningConfig](/powershell/module/exchange/get-dkimsigningconfig).</span><span class="sxs-lookup"><span data-stu-id="7b89e-165">For detailed syntax and parameter information, see the following articles: [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig), [New-DkimSigningConfig](/powershell/module/exchange/new-dkimsigningconfig), and [Get-DkimSigningConfig](/powershell/module/exchange/get-dkimsigningconfig).</span></span>

## <a name="steps-to-manually-set-up-dkim"></a><span data-ttu-id="7b89e-166">Необходимые шаги для настройки DKIM вручную</span><span class="sxs-lookup"><span data-stu-id="7b89e-166">Steps to manually set up DKIM</span></span>
<span data-ttu-id="7b89e-167"><a name="SetUpDKIMO365"> </a></span><span class="sxs-lookup"><span data-stu-id="7b89e-167"><a name="SetUpDKIMO365"> </a></span></span>

<span data-ttu-id="7b89e-168">Настройка DKIM состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="7b89e-168">To configure DKIM, you will complete these steps:</span></span>

- [<span data-ttu-id="7b89e-169">Публикация двух записей CNAME для личного домена в DNS</span><span class="sxs-lookup"><span data-stu-id="7b89e-169">Publish two CNAME records for your custom domain in DNS</span></span>](use-dkim-to-validate-outbound-email.md#Publish2CNAME)
- [<span data-ttu-id="7b89e-170">Включите подпись DKIM для вашего пользовательского домена</span><span class="sxs-lookup"><span data-stu-id="7b89e-170">Enable DKIM signing for your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a><span data-ttu-id="7b89e-171">Публикация двух записей CNAME для личного домена в DNS</span><span class="sxs-lookup"><span data-stu-id="7b89e-171">Publish two CNAME records for your custom domain in DNS</span></span>
<span data-ttu-id="7b89e-172"><a name="Publish2CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="7b89e-172"><a name="Publish2CNAME"> </a></span></span>

<span data-ttu-id="7b89e-173">Для каждого домена, для которого требуется добавить подпись DKIM в DNS, необходимо опубликовать две записи CNAME.</span><span class="sxs-lookup"><span data-stu-id="7b89e-173">For each domain for which you want to add a DKIM signature in DNS, you need to publish two CNAME records.</span></span>

> [!NOTE]
> <span data-ttu-id="7b89e-174">Если вы не ознакомились с полной статьей, вы могли пропустить эти сведения о подключении PowerShell, экономящие время: [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="7b89e-174">If you haven't read the full article, you may have missed this time-saving PowerShell connection information: [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="7b89e-175">Чтобы создать записи селектора, выполните следующие команды в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7b89e-175">Run the following commands in Exchange Online PowerShell to create the selector records:</span></span>

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

<span data-ttu-id="7b89e-p112">Для каждого домена, создаваемого в Microsoft 365 в дополнение к начальному домену, следует опубликовать две записи CNAME. Таким образом, если у вас два домена, необходимо опубликовать две дополнительные записи CNAME и так далее.</span><span class="sxs-lookup"><span data-stu-id="7b89e-p112">If you have provisioned custom domains in addition to the initial domain in Microsoft 365, you must publish two CNAME records for each additional domain. So, if you have two domains, you must publish two additional CNAME records, and so on.</span></span>

<span data-ttu-id="7b89e-178">Для записей CNAME используйте указанный ниже формат.</span><span class="sxs-lookup"><span data-stu-id="7b89e-178">Use the following format for the CNAME records.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b89e-179">Если вы один из наших клиентов GCC High, мы вычисляем _domainGuid_ другим способом.</span><span class="sxs-lookup"><span data-stu-id="7b89e-179">If you are one of our GCC High customers, we calculate _domainGuid_ differently!</span></span> <span data-ttu-id="7b89e-180">Вместо поиска записи MX для вашего _initialDomain_ с целью вычисления _domainGuid_ мы вычисляем его непосредственно на основании личного домена.</span><span class="sxs-lookup"><span data-stu-id="7b89e-180">Instead of looking up the MX record for your _initialDomain_ to calculate _domainGuid_, instead we calculate it directly from the customized domain.</span></span> <span data-ttu-id="7b89e-181">Например, если ваш личный домен — contoso.com, ваш domainGuid будет иметь вид contoso-com, то есть все точки будут заменены дефисами.</span><span class="sxs-lookup"><span data-stu-id="7b89e-181">For example, if your customized domain is "contoso.com" your domainGuid becomes "contoso-com", any periods are replaced with a dash.</span></span> <span data-ttu-id="7b89e-182">Таким образом, независимо от записи MX, на которую указывает ваш initialDomain, вы всегда можете использовать описанный выше метод для вычисления domainGuid, чтобы использовать его в записях CNAME.</span><span class="sxs-lookup"><span data-stu-id="7b89e-182">So, regardless of what MX record your initialDomain points to, you'll always use the above method to calculate the domainGuid to use in your CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

<span data-ttu-id="7b89e-183">Где:</span><span class="sxs-lookup"><span data-stu-id="7b89e-183">Where:</span></span>

- <span data-ttu-id="7b89e-184">В Microsoft 365 селекторами всегда будут «селектор1» или «селектор2».</span><span class="sxs-lookup"><span data-stu-id="7b89e-184">For Microsoft 365, the selectors will always be "selector1" or "selector2".</span></span>
- <span data-ttu-id="7b89e-p114">Значение _domainGUID_ совпадает со значением _domainGUID_, указанным в настроенной записи MX для личного домена. Например, в следующей записи MX для домена contoso.com _domainGUID_ — это contoso-com:</span><span class="sxs-lookup"><span data-stu-id="7b89e-p114">_domainGUID_ is the same as the _domainGUID_ in the customized MX record for your custom domain that appears before mail.protection.outlook.com. For example, in the following MX record for the domain contoso.com, the _domainGUID_ is contoso-com:</span></span>

  > <span data-ttu-id="7b89e-p115">contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7b89e-p115">contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span></span>

- <span data-ttu-id="7b89e-189">_initialDomain_ - это домен, который вы использовали при регистрации в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7b89e-189">_initialDomain_ is the domain that you used when you signed up for Microsoft 365.</span></span> <span data-ttu-id="7b89e-190">Исходные домены всегда заканчиваются на onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="7b89e-190">Initial domains always end in onmicrosoft.com.</span></span> <span data-ttu-id="7b89e-191">О том, как узнать свой исходный домен, читайте в разделе [часто задаваемых вопросов](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span><span class="sxs-lookup"><span data-stu-id="7b89e-191">For information about determining your initial domain, see [Domains FAQ](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span></span>

<span data-ttu-id="7b89e-192">Например, если у вас есть исходный домен cohovineyardandwinery.onmicrosoft.com и два личных домена cohovineyard.com и cohowinery.com, вам необходимо настроить две записи CNAME для каждого дополнительного домена (всего четыре записи CNAME).</span><span class="sxs-lookup"><span data-stu-id="7b89e-192">For example, if you have an initial domain of cohovineyardandwinery.onmicrosoft.com, and two custom domains cohovineyard.com and cohowinery.com, you would need to set up two CNAME records for each additional domain, for a total of four CNAME records.</span></span>

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
> <span data-ttu-id="7b89e-193">Важно создать вторую запись, но только один из селекторов может быть доступен во время создания.</span><span class="sxs-lookup"><span data-stu-id="7b89e-193">It's important to create the second record, but only one of the selectors may be available at the time of creation.</span></span> <span data-ttu-id="7b89e-194">По сути, второй селектор может указывать на адрес, который еще не создан.</span><span class="sxs-lookup"><span data-stu-id="7b89e-194">In essence, the second selector might point to an address that hasn't been created yet.</span></span> <span data-ttu-id="7b89e-195">Мы все же рекомендуем создать вторую запись CNAME, так как ротация ключей будет беспроблемной.</span><span class="sxs-lookup"><span data-stu-id="7b89e-195">We still recommended that you create the second CNAME record, because your key rotation will be seamless.</span></span>

### <a name="steps-to-enable-dkim-signing-for-your-custom-domain"></a><span data-ttu-id="7b89e-196">Шаги по включению подписи DKIM для личного домена</span><span class="sxs-lookup"><span data-stu-id="7b89e-196">Steps to enable DKIM signing for your custom domain</span></span>
<span data-ttu-id="7b89e-197"><a name="EnableDKIMinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="7b89e-197"><a name="EnableDKIMinO365"> </a></span></span>

<span data-ttu-id="7b89e-p118">После публикации записей CNAME в DNS включите подпись с помощью DKIM в Microsoft 365. Это можно сделать в Центре администрирования Microsoft 365 или с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b89e-p118">Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Microsoft 365. You can do this either through the Microsoft 365 admin center or by using PowerShell.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="7b89e-200">Чтобы включить подпись DKIM для вашего личного домена на портале Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b89e-200">To enable DKIM signing for your custom domain in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="7b89e-201">Откройте портал Microsoft 365 Defender [с помощью своей рабочей или учебной учетной записи](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="7b89e-201">Open the Microsoft 365 Defender portal [using your work or school account](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="7b89e-202">Выберите **Сообщения электронной почты и совместная работа** \> **Политики и правила** \> страница **Политики в отношении угроз** \> раздел **Правила** \> **DKIM**.</span><span class="sxs-lookup"><span data-stu-id="7b89e-202">Go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **DKIM**.</span></span> <span data-ttu-id="7b89e-203">Или перейдите непосредственно на страницу DKIM по ссылке <https://security.microsoft.com/dkimv2>.</span><span class="sxs-lookup"><span data-stu-id="7b89e-203">Or, to go directly to the DKIM page, use <https://security.microsoft.com/dkimv2>.</span></span>

3. <span data-ttu-id="7b89e-204">На странице **DKIM** выберите домен, щелкнув имя.</span><span class="sxs-lookup"><span data-stu-id="7b89e-204">On the **DKIM** page, select the domain by clicking on the name.</span></span>

4. <span data-ttu-id="7b89e-205">В открывшемся окне сведений присвойте параметру **Добавлять подписи DKIM в сообщения для этого домена** значение **Включено** (![Переключатель в состоянии "Вкл"](../../media/scc-toggle-on.png))</span><span class="sxs-lookup"><span data-stu-id="7b89e-205">In the details flyout that appears, chang the **Sign messages for this domain with DKIM signatures** setting to **Enabled** (![Toggle on](../../media/scc-toggle-on.png))</span></span>

   <span data-ttu-id="7b89e-206">После завершения нажмите **Смена ключей DKIM**.</span><span class="sxs-lookup"><span data-stu-id="7b89e-206">When you're finished, click **Rotate DKIM keys**.</span></span>

5. <span data-ttu-id="7b89e-207">Повторите этот шаг для каждого личного домена.</span><span class="sxs-lookup"><span data-stu-id="7b89e-207">Repeat these step for each custom domain.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a><span data-ttu-id="7b89e-208">Как включить подпись с помощью DKIM для личного домена, используя PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b89e-208">To enable DKIM signing for your custom domain by using PowerShell</span></span>

> [!IMPORTANT]
> :::image type="content" source="../../media/dkim.png" alt-text="Ошибка &quot;Для этого домена нет сохраненных ключей DKIM&quot;.":::
> <span data-ttu-id="7b89e-210">Если вы настраиваете DKIM в первый раз и столкнулись с ошибкой "Для этого домена нет сохраненных ключей DKIM", выполните команду из шага 2 ниже (например, `Set-DkimSigningConfig -Identity contoso.com -Enabled $true`), чтобы увидеть ключ.</span><span class="sxs-lookup"><span data-stu-id="7b89e-210">If you are configuring DKIM for the first time and see the error 'No DKIM keys saved for this domain' complete the command in step 2 below (for example, `Set-DkimSigningConfig -Identity contoso.com -Enabled $true`) to see the key.</span></span>

1. <span data-ttu-id="7b89e-211">[Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="7b89e-211">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="7b89e-212">Используйте следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="7b89e-212">Use the following syntax:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity <Domain> -Enabled $true
   ```

   <span data-ttu-id="7b89e-213">\<Domain\> — это имя личного домена, для которого требуется включить функцию подписывания с помощью DKIM.</span><span class="sxs-lookup"><span data-stu-id="7b89e-213">\<Domain\> is the name of the custom domain that you want to enable DKIM signing for.</span></span>

   <span data-ttu-id="7b89e-214">В этом примере показано включение подписи DKIM для домена contoso.com:</span><span class="sxs-lookup"><span data-stu-id="7b89e-214">This example enables DKIM signing for the domain contoso.com:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a><span data-ttu-id="7b89e-215">Подтвердить, что подпись DKIM правильно настроена для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b89e-215">To Confirm DKIM signing is configured properly for Microsoft 365</span></span>

<span data-ttu-id="7b89e-p120">Прежде чем выполнять указанные ниже действия для проверки настройки DKIM, подождите несколько минут. Для распространения информации DKIM о домене по сети требуется время.</span><span class="sxs-lookup"><span data-stu-id="7b89e-p120">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM. This allows time for the DKIM information about the domain to be spread throughout the network.</span></span>

- <span data-ttu-id="7b89e-218">Отправьте сообщение из учетной записи в домене Microsoft 365 с поддержкой DKIM на другую учетную запись электронной почты, например outlook.com или Hotmail.com.</span><span class="sxs-lookup"><span data-stu-id="7b89e-218">Send a message from an account within your Microsoft 365 DKIM-enabled domain to another email account such as outlook.com or Hotmail.com.</span></span>
- <span data-ttu-id="7b89e-p121">Не используйте для проверки учетную запись aol.com. AOL может пропустить проверку DKIM в случае успешной проверки SPF. Такая проверка будет недействительной.</span><span class="sxs-lookup"><span data-stu-id="7b89e-p121">Do not use an aol.com account for testing purposes. AOL may skip the DKIM check if the SPF check passes. This will nullify your test.</span></span>
- <span data-ttu-id="7b89e-p122">Откройте сообщение и посмотрите на заголовок. Инструкции для просмотра заголовка сообщения могут быть разными, в зависимости от клиента вашей электронной связи. Дополнительные сведения о том, как просматривать заголовки сообщений в Outlook, см. в разделе [Просмотр заголовков сообщений из Интернета в Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span><span class="sxs-lookup"><span data-stu-id="7b89e-p122">Open the message and look at the header. Instructions for viewing the header for the message will vary depending on your messaging client. For instructions on viewing message headers in Outlook, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

  <span data-ttu-id="7b89e-p123">Сообщение, подписанное с помощью DKIM, будет содержать имя узла и доменное имя, указанные вами при публикации записей CNAME. Сообщение будет выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="7b89e-p123">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries. The message will look something like this example:</span></span>

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- <span data-ttu-id="7b89e-p124">Найдите заголовок Authentication-Results. Принимающие службы помечают входящую почту по-разному, но результат должен содержать элемент, подобный **DKIM=pass** или **DKIM=OK**.</span><span class="sxs-lookup"><span data-stu-id="7b89e-p124">Look for the Authentication-Results header. While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span></span>

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a><span data-ttu-id="7b89e-229">Чтобы настроить DKIM для нескольких пользовательских доменов</span><span class="sxs-lookup"><span data-stu-id="7b89e-229">To configure DKIM for more than one custom domain</span></span>
<span data-ttu-id="7b89e-230"><a name="DKIMMultiDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="7b89e-230"><a name="DKIMMultiDomain"> </a></span></span>

<span data-ttu-id="7b89e-231">Действия, описанные в этой статье, необходимо выполнить для каждого дополнительного личного домена, для которого требуется включить DKIM.</span><span class="sxs-lookup"><span data-stu-id="7b89e-231">If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain.</span></span> <span data-ttu-id="7b89e-232">В частности, выполните все шаги в разделе [Что нужно сделать, чтобы вручную настроить DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span><span class="sxs-lookup"><span data-stu-id="7b89e-232">Specifically, complete all steps in [What you need to do to manually set up DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span></span>

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a><span data-ttu-id="7b89e-233">Отключение политики подписи DKIM для пользовательского домена</span><span class="sxs-lookup"><span data-stu-id="7b89e-233">Disabling the DKIM signing policy for a custom domain</span></span>
<span data-ttu-id="7b89e-234"><a name="DisableDKIMSigningPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="7b89e-234"><a name="DisableDKIMSigningPolicy"> </a></span></span>

<span data-ttu-id="7b89e-235">Отключение политики подписывания полностью не отключает DKIM.</span><span class="sxs-lookup"><span data-stu-id="7b89e-235">Disabling the signing policy does not completely disable DKIM.</span></span> <span data-ttu-id="7b89e-236">Через некоторое время Microsoft 365 автоматически применит политику по умолчанию для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="7b89e-236">After a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span> <span data-ttu-id="7b89e-237">Для получения дополнительной информации см. [Поведение по умолчанию для DKIM и Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span><span class="sxs-lookup"><span data-stu-id="7b89e-237">For more information, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a><span data-ttu-id="7b89e-238">Отключение политики подписывания DKIM с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b89e-238">To disable the DKIM signing policy by using Windows PowerShell</span></span>

1. <span data-ttu-id="7b89e-239">[Подключение к PowerShell для Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="7b89e-239">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="7b89e-240">Выполните одну из указанных ниже команд для каждого домена, для которого требуется отключить подпись с помощью DKIM.</span><span class="sxs-lookup"><span data-stu-id="7b89e-240">Run one of the following commands for each domain for which you want to disable DKIM signing.</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity <Domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="7b89e-241">Пример:</span><span class="sxs-lookup"><span data-stu-id="7b89e-241">For example:</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="7b89e-242">или</span><span class="sxs-lookup"><span data-stu-id="7b89e-242">Or</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   <span data-ttu-id="7b89e-p127">Где _number_ — это индекс политики. Например:</span><span class="sxs-lookup"><span data-stu-id="7b89e-p127">Where _number_ is the index of the policy. For example:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a><span data-ttu-id="7b89e-245">Поведение по умолчанию для DKIM и Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b89e-245">Default behavior for DKIM and Microsoft 365</span></span>
<span data-ttu-id="7b89e-246"><a name="DefaultDKIMbehavior"> </a></span><span class="sxs-lookup"><span data-stu-id="7b89e-246"><a name="DefaultDKIMbehavior"> </a></span></span>

<span data-ttu-id="7b89e-p128">Если вы не включите DKIM, Microsoft 365 автоматически создаст 1024-разрядный открытый ключ DKIM для вашего домена по умолчанию и соответствующий закрытый ключ. Мы будем хранить эти ключи в нашем центре обработки данных. Для доменов без действующей политики Microsoft 365 использует конфигурацию подписывания по умолчанию. Это означает, что если вы не настроите DKIM самостоятельно, Microsoft 365 включит DKIM для вашего домена, используя политику по умолчанию и автоматически созданные ключи.</span><span class="sxs-lookup"><span data-stu-id="7b89e-p128">If you do not enable DKIM, Microsoft 365 automatically creates a 1024-bit DKIM public key for your default domain and the associated private key which we store internally in our datacenter. By default, Microsoft 365 uses a default signing configuration for domains that do not have a policy in place. This means that if you do not set up DKIM yourself, Microsoft 365 will use its default policy and keys it creates to enable DKIM for your domain.</span></span>

<span data-ttu-id="7b89e-250">Кроме того, если вы отключите подпись DKIM после включения, через некоторое время Microsoft 365 автоматически применит политику по умолчанию для вашего домена.</span><span class="sxs-lookup"><span data-stu-id="7b89e-250">Also, if you disable DKIM signing after enabling it, after a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span>

<span data-ttu-id="7b89e-p129">Предположим, что в примере ниже подпись DKIM для домена fabrikam.com включена автоматически Microsoft 365, а не администратором домена. Это означает, что в DNS нет нужных записей CNAME. Подписи DKIM для электронной почты из этого домена будут выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="7b89e-p129">In the following example, suppose that DKIM for fabrikam.com was enabled by Microsoft 365, not by the administrator of the domain. This means that the required CNAMEs do not exist in DNS. DKIM signatures for email from this domain will look something like this:</span></span>

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

<span data-ttu-id="7b89e-254">В этом примере имя узла и доменное имя содержат значения, на которые указывала бы запись CNAME, если бы администратор домена настроил подпись DKIM для домена fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="7b89e-254">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator.</span></span> <span data-ttu-id="7b89e-255">В конце концов, каждое сообщение, отправленное из Microsoft 365, будет подписано DKIM.</span><span class="sxs-lookup"><span data-stu-id="7b89e-255">Eventually, every single message sent from Microsoft 365 will be DKIM-signed.</span></span> <span data-ttu-id="7b89e-256">Если вы включили DKIM самостоятельно, то домен будет совпадать с доменом, указанным в адресе From: (в этом случае fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="7b89e-256">If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com.</span></span> <span data-ttu-id="7b89e-257">В противном случае будет использоваться исходный домен организации.</span><span class="sxs-lookup"><span data-stu-id="7b89e-257">If you don't, it will not align and instead will use your organization's initial domain.</span></span> <span data-ttu-id="7b89e-258">О том, как узнать свой исходный домен, читайте в разделе [часто задаваемых вопросов](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span><span class="sxs-lookup"><span data-stu-id="7b89e-258">For information about determining your initial domain, see [Domains FAQ](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span></span>

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a><span data-ttu-id="7b89e-259">Настройте DKIM таким образом, чтобы сторонняя служба могла отправлять электронные письма от имени вашего личного домена</span><span class="sxs-lookup"><span data-stu-id="7b89e-259">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>
<span data-ttu-id="7b89e-260"><a name="SetUp3rdPartyspoof"> </a></span><span class="sxs-lookup"><span data-stu-id="7b89e-260"><a name="SetUp3rdPartyspoof"> </a></span></span>

<span data-ttu-id="7b89e-p131">Некоторые поставщики услуг массовой рассылки электронной почты или поставщики программного обеспечения как услуги позволяют настраивать ключи DKIM для сообщений электронной почты, отправляемых из их службы. Для этого требуется обеспечить согласованность между вами и сторонним поставщиком, чтобы настроить необходимые записи DNS. Некоторые сторонние серверы могут иметь собственные записи CNAME с различными селекторами. В каждой организации это делают по-своему. Процесс полностью зависит от конкретного предприятия.</span><span class="sxs-lookup"><span data-stu-id="7b89e-p131">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service. This requires coordination between yourself and the third-party in order to set up the necessary DNS records. Some third-party servers can have their own CNAME records with different selectors. No two organizations do it exactly the same way. Instead, the process depends entirely on the organization.</span></span>

<span data-ttu-id="7b89e-266">Пример сообщения с правильно настроенными ключами DKIM для доменов contoso.com и bulkemailprovider.com:</span><span class="sxs-lookup"><span data-stu-id="7b89e-266">An example message showing a properly configured DKIM for contoso.com and bulkemailprovider.com might look like this:</span></span>

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

<span data-ttu-id="7b89e-267">В этом примере для достижения представленного результата:</span><span class="sxs-lookup"><span data-stu-id="7b89e-267">In this example, in order to achieve this result:</span></span>

1. <span data-ttu-id="7b89e-268">Поставщик услуг массовой рассылки предоставил компании Contoso открытый ключ DKIM.</span><span class="sxs-lookup"><span data-stu-id="7b89e-268">Bulk Email Provider gave Contoso a public DKIM key.</span></span>

2. <span data-ttu-id="7b89e-269">Компания Contoso опубликовала ключ DKIM в своей записи DNS.</span><span class="sxs-lookup"><span data-stu-id="7b89e-269">Contoso published the DKIM key to its DNS record.</span></span>

3. <span data-ttu-id="7b89e-p132">При отправке сообщения поставщик услуг массовой рассылки подписывает ключ соответствующим закрытым ключом. Таким образом он добавляет подпись DKIM в заголовок сообщения.</span><span class="sxs-lookup"><span data-stu-id="7b89e-p132">When sending email, Bulk Email Provider signs the key with the corresponding private key. By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span></span>

4. <span data-ttu-id="7b89e-272">Получающие почтовые системы выполняют проверку DKIM путем сравнения значения подписи DKIM-Signature d=\<domain\>с доменом в поле адреса "От" (5322.From) сообщения.</span><span class="sxs-lookup"><span data-stu-id="7b89e-272">Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message.</span></span> <span data-ttu-id="7b89e-273">В этом примере значения совпадают:</span><span class="sxs-lookup"><span data-stu-id="7b89e-273">In this example, the values match:</span></span>

   > <span data-ttu-id="7b89e-274">sender@**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="7b89e-274">sender@**contoso.com**</span></span>

   > <span data-ttu-id="7b89e-275">d=**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="7b89e-275">d=**contoso.com**</span></span>

## <a name="identify-domains-that-do-not-send-email"></a><span data-ttu-id="7b89e-276">Идентификация доменов, с которых не отправляется почта</span><span class="sxs-lookup"><span data-stu-id="7b89e-276">Identify domains that do not send email</span></span>

<span data-ttu-id="7b89e-277">Организациям следует явно указать, отправляется ли почта с домена, с помощью `v=DKIM1; p=` в записи DKIM для этих доменов.</span><span class="sxs-lookup"><span data-stu-id="7b89e-277">Organizations should explicitly state if a domain does not send email by specifying `v=DKIM1; p=` in the DKIM record for those domains.</span></span> <span data-ttu-id="7b89e-278">При этом почтовым серверам получателя сообщается об отсутствии допустимых открытых ключей для этого домена и необходимости отклонить любое сообщение из него.</span><span class="sxs-lookup"><span data-stu-id="7b89e-278">This advises receiving email servers that there are no valid public keys for the domain, and any email claiming to be from that domain should be rejected.</span></span> <span data-ttu-id="7b89e-279">Это нужно сделать для каждого домена и поддомена, использующего DKIM.</span><span class="sxs-lookup"><span data-stu-id="7b89e-279">You should do this for each domain and subdomain using a wildcard DKIM.</span></span>

<span data-ttu-id="7b89e-280">Например, запись DKIM может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7b89e-280">For example, the DKIM record would look like this:</span></span>

```console
*._domainkey.SubDomainThatShouldntSendMail.contoso.com. TXT "v=DKIM1; p="
```

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a><span data-ttu-id="7b89e-281">Следующие шаги: после настройки DKIM для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b89e-281">Next steps: After you set up DKIM for Microsoft 365</span></span>
<span data-ttu-id="7b89e-282"><a name="DKIMNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="7b89e-282"><a name="DKIMNextSteps"> </a></span></span>

<span data-ttu-id="7b89e-283">Несмотря на то, что технология DKIM предназначена для предотвращения спуфинга, она работает эффективнее вместе с инфраструктурой политики отправителей и DMARC.</span><span class="sxs-lookup"><span data-stu-id="7b89e-283">Although DKIM is designed to help prevent spoofing, DKIM works better with SPF and DMARC.</span></span> <span data-ttu-id="7b89e-284">После настройки DKIM настройте инфраструктуру политики отправителей.</span><span class="sxs-lookup"><span data-stu-id="7b89e-284">Once you have set up DKIM, if you have not already set up SPF you should do so.</span></span> <span data-ttu-id="7b89e-285">Для быстрого ознакомления с SPF и его быстрой настройки см. раздел [Настройка SPF в Microsoft 365, чтобы предотвратить подделку](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="7b89e-285">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="7b89e-286">Для более глубокого понимания того, как Microsoft 365 использует SPF, или для устранения неполадок или нестандартных развертываний, таких как гибридные развертывания, начните с того, [как Microsoft 365 использует Sender Policy Framework (SPF) для предотвращения спуфинга](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="7b89e-286">For a more in-depth understanding of how Microsoft 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="7b89e-287">Далее см. [Использование DMARC для проверки электронной почты](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="7b89e-287">Next, see [Use DMARC to validate email](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="7b89e-288">[Заголовки сообщений защиты от спама](anti-spam-message-headers.md) включают поля синтаксиса и заголовка, используемые Microsoft 365 для проверок DKIM.</span><span class="sxs-lookup"><span data-stu-id="7b89e-288">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for DKIM checks.</span></span>

## <a name="more-information"></a><span data-ttu-id="7b89e-289">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="7b89e-289">More information</span></span>

<span data-ttu-id="7b89e-290">Ротация ключей с помощью командлета [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig) в PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b89e-290">Key rotation via PowerShell [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig)</span></span>
