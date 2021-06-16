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
ms.openlocfilehash: 12c7609635d9140f2e8efda3f6f1397619ce4790
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929909"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a>Используйте DKIM для проверки исходящей электронной почты, отправленной с вашего пользовательского домена

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

 В этой статье описаны шаги использования DomainKeys Identified Mail (DKIM) с Microsoft 365, гарантирующие, что системы электронной почты назначения доверяют сообщениям, отправленным вовне с вашего пользовательского домена.

В этой статье

- [Как DKIM работает лучше, чем один SPF, для предотвращения злонамеренного подмены](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [Шаги по обновлению 1024-разрядных ключей до 2048-разрядных ключей шифрования DKIM вручную](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [Шаги для настройки DKIM вручную](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [Шаги для настройки DKIM для нескольких личных доменов](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [Отключение политики подписи DKIM для пользовательского домена](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [Поведение по умолчанию для DKIM и Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [Как настроить DKIM так, чтобы сторонняя служба могла отправлять сообщения электронной почты от имени вашего личного домена](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [Следующие шаги: после настройки DKIM для Microsoft 365](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

> [!NOTE]
> Microsoft 365 автоматически настраивает DKIM для своих первоначальных доменов «onmicrosoft.com». Это означает, что вам не нужно ничего делать, чтобы настроить DKIM для любого исходного имени домена (например, litware.onmicrosoft.com). Дополнительные сведения о доменах см. в статье [Вопросы и ответы о доменах](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

DKIM — один из трех методов проверки подлинности (SPF, DKIM и DMARC), помогающих запретить злоумышленникам отправлять сообщения, которые выглядят так, как будто они приходят из вашего домена.

DKIM позволяет добавлять цифровую подпись в заголовки отправляемых вовне сообщений электронной почты. При настройке DKIM вы авторизуете домен, чтобы связать его имя с сообщением электронной почты, или подписать сообщение этим именем, с помощью криптографической проверки подлинности. С помощью этой цифровой подписи системы электронной почты могут определить, действительно ли входящее сообщение отправлено из вашего домена.

В двух словах, закрытый ключ используется для шифрования заголовка в направленном вовне сообщении электронной почты домена. В записях DNS домена вы публикуете открытый ключ, с помощью которого принимающие серверы расшифровывают подпись. Проверка DKIM помогает принимающим серверам подтвердить, что почта действительно отправлена из вашего домена и это не *спуфинг*.

> [!TIP]
>Вы также можете не настраивать DKIM для личного домена. В этом случае Office 365 создаст пару ключей — закрытый и открытый, — включит подпись с помощью DKIM и настроит политику по умолчанию для личного домена Microsoft 365.

 Хотя встроенной в Microsoft 365 конфигурации достаточно для большинства клиентов, вы должны вручную настроить DKIM своего пользовательского домена в следующих случаях:

- у вас есть несколько пользовательских доменов в Microsoft 365;

- вы также собираетесь настроить DMARC (**рекомендуется**);

- вам необходим контроль над закрытым ключом;

- вам необходимо настроить записи CNAME.

- вам нужно настроить ключи DKIM для сообщений электронной почты со стороннего домена, например при использовании стороннего средства для массовых рассылок.


## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a>Как DKIM работает лучше, чем один SPF, для предотвращения злонамеренного подмены
<a name="HowDKIMWorks"> </a>

SPF добавляет данные в конверт сообщения, а технология DKIM *шифрует* подпись в заголовке сообщения. При пересылке фрагменты конверта этого сообщения могут быть удалены сервером пересылки. Поскольку цифровая подпись остается в заголовке сообщения, технология DKIM работает даже при пересылке, как показано в примере ниже.

![Схема, на которой показана проверка подлинности DKIM: пересланное сообщение не прошло проверку инфраструктурой политики отправителей](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

В этом примере, если бы вы опубликовали только запись типа TXT инфраструктуры политики отправителей для домена, почтовый сервер получателя мог бы пометить ваше сообщение как спам, что привело бы к ложному срабатыванию. **Добавление DKIM в этом сценарии позволяет снизить количество *ложных срабатываний***. Поскольку в технологии DKIM для проверки подлинности используются не только IP-адреса, но и шифрование с помощью открытого ключа, она считается более надежным способом проверки подлинности, чем SPF. Рекомендуем использовать в вашей инфраструктуре одновременно SPF и DKIM, а также DMARC.

> [!TIP]
> DKIM использует закрытый ключ для вставки зашифрованной подписи в заголовки сообщений. Имя подписывающего домена (или домена исходящей почты) вставляется в заголовок в качестве значения поля **d=**. Проверяющий домен (или домен получателя) затем использует поле **d=** для поиска открытого ключа в DNS и проверки подлинности сообщения. Так сообщение проходит проверку DKIM.


## <a name="steps-to-manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a>Шаги по обновлению 1024-разрядных ключей до 2048-разрядных ключей шифрования DKIM вручную
<a name="1024to2048DKIM"> </a>

> [!NOTE]
> Microsoft 365 автоматически настраивает DKIM для своих доменов *onmicrosoft.com*. Чтобы начать использование DKIM для начальных доменных имен (например, *litware.onmicrosoft.com*), не требуется никаких действий. Дополнительные сведения о доменах см. в статье [Вопросы и ответы о доменах](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

Так как ключи DKIM могут быть 1024- и 2048-разрядными, эти инструкции предназначены для обновления 1024-разрядных ключей до 2048-разрядных в [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Описанные ниже действия относятся к двум вариантам использования. Выберите вариант, подходящий для вашей конфигурации.

- Если вы **уже настроили DKIM**, измените разрядность, выполнив следующую команду:

  ```powershell
  Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
  ```

  **или**

- В случае **новой реализации DKIM** выполните следующую команду:

  ```powershell
  New-DkimSigningConfig -DomainName <Domain for which config is to be created> -KeySize 2048 -Enabled $true
  ```

Сохраняйте подключение к Exchange Online PowerShell, чтобы *проверить* конфигурацию, выполнив следующую команду:

```powershell
Get-DkimSigningConfig -Identity <Domain for which the configuration was set> | Format-List
```

> [!TIP]
> Этот новый 2048-разрядный ключ вступает в силу с даты, указанной в параметре RotateOnDate. Пока же сообщения электронной почты будут отправляться с использованием 1024-разрядного ключа. Через четыре дня вы снова можете выполнить проверку с использованием 2048-разрядного ключа (то есть после применения изменения ко второму селектору).

Если вы хотите перейти ко второму селектору, вы можете: а) позволить службе Microsoft 365 повернуть селектор и обновить ее до 2048-разрядности в течение следующих 6 месяцев, или б) через 4 дня и подтвердить, что 2048-разрядности используется вручную поверните вторую клавишу выбора с помощью соответствующего командлета, указанного выше.

Дополнительные сведения о синтаксисе и параметрах см. в следующих статьях: [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig), [New-DkimSigningConfig](/powershell/module/exchange/new-dkimsigningconfig) и [Get-DkimSigningConfig](/powershell/module/exchange/get-dkimsigningconfig).

## <a name="steps-to-manually-set-up-dkim"></a>Необходимые шаги для настройки DKIM вручную
<a name="SetUpDKIMO365"> </a>

Настройка DKIM состоит из двух этапов:

- [Публикация двух записей CNAME для личного домена в DNS](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [Включите подпись DKIM для вашего пользовательского домена](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a>Публикация двух записей CNAME для личного домена в DNS
<a name="Publish2CNAME"> </a>

Для каждого домена, для которого требуется добавить подпись DKIM в DNS, необходимо опубликовать две записи CNAME.

> [!NOTE]
> Если вы не ознакомились с полной статьей, вы могли пропустить эти сведения о подключении PowerShell, экономящие время: [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

Чтобы создать записи селектора, выполните следующие команды в Exchange Online PowerShell:

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

Для каждого домена, создаваемого в Microsoft 365 в дополнение к начальному домену, следует опубликовать две записи CNAME. Таким образом, если у вас два домена, необходимо опубликовать две дополнительные записи CNAME и так далее.

Для записей CNAME используйте указанный ниже формат.

> [!IMPORTANT]
> Если вы один из наших клиентов GCC High, мы вычисляем _domainGuid_ другим способом. Вместо поиска записи MX для вашего _initialDomain_ с целью вычисления _domainGuid_ мы вычисляем его непосредственно на основании личного домена. Например, если ваш личный домен — contoso.com, ваш domainGuid будет иметь вид contoso-com, то есть все точки будут заменены дефисами. Таким образом, независимо от записи MX, на которую указывает ваш initialDomain, вы всегда можете использовать описанный выше метод для вычисления domainGuid, чтобы использовать его в записях CNAME.

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

Где:

- В Microsoft 365 селекторами всегда будут «селектор1» или «селектор2».

- Значение _domainGUID_ совпадает со значением _domainGUID_, указанным в настроенной записи MX для личного домена. Например, в следующей записи MX для домена contoso.com _domainGUID_ — это contoso-com:

  > contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com

- _initialDomain_ - это домен, который вы использовали при регистрации в Microsoft 365. Исходные домены всегда заканчиваются на onmicrosoft.com. О том, как узнать свой исходный домен, читайте в разделе [часто задаваемых вопросов](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

Например, если у вас есть исходный домен cohovineyardandwinery.onmicrosoft.com и два личных домена cohovineyard.com и cohowinery.com, вам необходимо настроить две записи CNAME для каждого дополнительного домена (всего четыре записи CNAME).

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
> Важно создать вторую запись, но только один из селекторов может быть доступен во время создания. По сути, второй селектор может указывать на адрес, который еще не создан. Мы все же рекомендуем создать вторую запись CNAME, так как ротация ключей будет беспроблемной.


### <a name="steps-to-enable-dkim-signing-for-your-custom-domain"></a>Шаги по включению подписи DKIM для личного домена
<a name="EnableDKIMinO365"> </a>

После публикации записей CNAME в DNS включите подпись с помощью DKIM в Microsoft 365. Это можно сделать в Центре администрирования Microsoft 365 или с помощью PowerShell.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a>Включение функции подписывания с помощью DKIM для личного домена в Центре администрирования

1. [Войдите в Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4), используя свою рабочую или учебную учетную запись.

2. Перейдите на сайт [security.microsoft.com](https://security.microsoft.com) и следуйте пути, указанному ниже.

3. Выберите **Сообщение электронной почты и совместная работа > Политики и правила > Политики в отношении угроз > DKIM**.

4. Выберите домен, для которого требуется включить DKIM, а затем в разделе **Добавлять подписи DKIM в сообщения для этого домена** нажмите **Включить**. Повторите этот шаг для каждого личного домена.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a>Как включить подпись с помощью DKIM для личного домена, используя PowerShell

> [!IMPORTANT]
>:::image type="content" source="../../media/dkim.png" alt-text="Ошибка &quot;Для этого домена нет сохраненных ключей DKIM&quot;.":::
> Если вы настраиваете DKIM в первый раз и столкнулись с ошибкой "Для этого домена нет сохраненных ключей DKIM", выполните команду из шага 2 ниже (например, *Set-DkimSigningConfig -Identity contoso.com -Enabled $true*), чтобы увидеть ключ.

1. [Подключение к PowerShell для Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Выполните следующую команду:

   ```powershell
   Set-DkimSigningConfig -Identity <domain> -Enabled $true
   ```

   Где _domain_ — имя личного домена, для которого требуется включить функцию подписывания с помощью DKIM.

   Например, для домена contoso.com:

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a>Подтвердить, что подпись DKIM правильно настроена для Microsoft 365

Прежде чем выполнять указанные ниже действия для проверки настройки DKIM, подождите несколько минут. Для распространения информации DKIM о домене по сети требуется время.

- Отправьте сообщение из учетной записи в домене Microsoft 365 с поддержкой DKIM на другую учетную запись электронной почты, например outlook.com или Hotmail.com.

- Не используйте для проверки учетную запись aol.com. AOL может пропустить проверку DKIM в случае успешной проверки SPF. Такая проверка будет недействительной.

- Откройте сообщение и посмотрите на заголовок. Инструкции для просмотра заголовка сообщения могут быть разными, в зависимости от клиента вашей электронной связи. Дополнительные сведения о том, как просматривать заголовки сообщений в Outlook, см. в разделе [Просмотр заголовков сообщений из Интернета в Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).

  Сообщение, подписанное с помощью DKIM, будет содержать имя узла и доменное имя, указанные вами при публикации записей CNAME. Сообщение будет выглядеть примерно так:

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- Найдите заголовок Authentication-Results. Принимающие службы помечают входящую почту по-разному, но результат должен содержать элемент, подобный **DKIM=pass** или **DKIM=OK**.

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a>Чтобы настроить DKIM для нескольких пользовательских доменов
<a name="DKIMMultiDomain"> </a>

Действия, описанные в этой статье, необходимо выполнить для каждого дополнительного личного домена, для которого требуется включить DKIM. В частности, выполните все шаги в разделе [Что нужно сделать, чтобы вручную настроить DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a>Отключение политики подписи DKIM для пользовательского домена
<a name="DisableDKIMSigningPolicy"> </a>

Отключение политики подписывания полностью не отключает DKIM. Через некоторое время Microsoft 365 автоматически применит политику по умолчанию для вашего домена. Для получения дополнительной информации см. [Поведение по умолчанию для DKIM и Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a>Отключение политики подписывания DKIM с помощью Windows PowerShell

1. [Подключение к PowerShell для Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Выполните одну из указанных ниже команд для каждого домена, для которого требуется отключить подпись с помощью DKIM.

   ```powershell
   $p = Get-DkimSigningConfig -Identity <domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   Пример:

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   или

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   Где _number_ — это индекс политики. Например:

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a>Поведение по умолчанию для DKIM и Microsoft 365
<a name="DefaultDKIMbehavior"> </a>

Если вы не включите DKIM, Microsoft 365 автоматически создаст 1024-разрядный открытый ключ DKIM для вашего домена по умолчанию и соответствующий закрытый ключ. Мы будем хранить эти ключи в нашем центре обработки данных. Для доменов без действующей политики Microsoft 365 использует конфигурацию подписывания по умолчанию. Это означает, что если вы не настроите DKIM самостоятельно, Microsoft 365 включит DKIM для вашего домена, используя политику по умолчанию и автоматически созданные ключи.

Кроме того, если вы отключите подпись DKIM после включения, через некоторое время Microsoft 365 автоматически применит политику по умолчанию для вашего домена.

Предположим, что в примере ниже подпись DKIM для домена fabrikam.com включена автоматически Microsoft 365, а не администратором домена. Это означает, что в DNS нет нужных записей CNAME. Подписи DKIM для электронной почты из этого домена будут выглядеть примерно так:

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

В этом примере имя узла и доменное имя содержат значения, на которые указывала бы запись CNAME, если бы администратор домена настроил подпись DKIM для домена fabrikam.com. В конце концов, каждое сообщение, отправленное из Microsoft 365, будет подписано DKIM. Если вы включили DKIM самостоятельно, то домен будет совпадать с доменом, указанным в адресе From: (в этом случае fabrikam.com). В противном случае будет использоваться исходный домен организации. О том, как узнать свой исходный домен, читайте в разделе [часто задаваемых вопросов](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a>Настройте DKIM таким образом, чтобы сторонняя служба могла отправлять электронные письма от имени вашего личного домена
<a name="SetUp3rdPartyspoof"> </a>

Некоторые поставщики услуг массовой рассылки электронной почты или поставщики программного обеспечения как услуги позволяют настраивать ключи DKIM для сообщений электронной почты, отправляемых из их службы. Для этого требуется обеспечить согласованность между вами и сторонним поставщиком, чтобы настроить необходимые записи DNS. Некоторые сторонние серверы могут иметь собственные записи CNAME с различными селекторами. В каждой организации это делают по-своему. Процесс полностью зависит от конкретного предприятия.

Пример сообщения с правильно настроенными ключами DKIM для доменов contoso.com и bulkemailprovider.com:

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

В этом примере для достижения представленного результата:

1. Поставщик услуг массовой рассылки предоставил компании Contoso открытый ключ DKIM.

2. Компания Contoso опубликовала ключ DKIM в своей записи DNS.

3. При отправке сообщения поставщик услуг массовой рассылки подписывает ключ соответствующим закрытым ключом. Таким образом он добавляет подпись DKIM в заголовок сообщения.

4. Получающие почтовые системы выполняют проверку DKIM путем сравнения значения подписи DKIM-Signature d=\<domain\>с доменом в поле адреса "От" (5322.From) сообщения. В этом примере значения совпадают:

   > sender@**contoso.com**

   > d=**contoso.com**

## <a name="identify-domains-that-do-not-send-email"></a>Идентификация доменов, с которых не отправляется почта

Организациям следует явно указать, отправляется ли почта с домена, с помощью `v=DKIM1; p=` в записи DKIM для этих доменов. При этом почтовым серверам получателя сообщается об отсутствии допустимых открытых ключей для этого домена и необходимости отклонить любое сообщение из него. Это нужно сделать для каждого домена и поддомена, использующего DKIM.

Например, запись DKIM может выглядеть следующим образом:

```console
*._domainkey.SubDomainThatShouldntSendMail.contoso.com. TXT "v=DKIM1; p="
```

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a>Следующие шаги: после настройки DKIM для Microsoft 365
<a name="DKIMNextSteps"> </a>

Несмотря на то, что технология DKIM предназначена для предотвращения спуфинга, она работает эффективнее вместе с инфраструктурой политики отправителей и DMARC. После настройки DKIM настройте инфраструктуру политики отправителей. Для быстрого ознакомления с SPF и его быстрой настройки см. раздел [Настройка SPF в Microsoft 365, чтобы предотвратить подделку](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Для более глубокого понимания того, как Microsoft 365 использует SPF, или для устранения неполадок или нестандартных развертываний, таких как гибридные развертывания, начните с того, [как Microsoft 365 использует Sender Policy Framework (SPF) для предотвращения спуфинга](how-office-365-uses-spf-to-prevent-spoofing.md). Далее см. [Использование DMARC для проверки электронной почты](use-dmarc-to-validate-email.md). [Заголовки сообщений защиты от спама](anti-spam-message-headers.md) включают поля синтаксиса и заголовка, используемые Microsoft 365 для проверок DKIM.

## <a name="more-information"></a>Дополнительные сведения

Ротация ключей с помощью командлета [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig) в PowerShell
