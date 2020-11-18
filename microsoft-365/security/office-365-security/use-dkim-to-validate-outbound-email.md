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
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как использовать технологию DomainKeys Identified Mail (DKIM) для Microsoft 365, чтобы обеспечить доверие конечных почтовых систем к сообщениям, отправленным из вашего личного домена.
ms.openlocfilehash: 7f9e33a6f117f5da592d875e40cefc6a0072fd4a
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126677"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a>Используйте DKIM для проверки исходящей электронной почты, отправленной с вашего пользовательского домена

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 **Сводка:** В этой статье описывается, как вы используете DomainKeys Identified Mail (DKIM) с Microsoft 365, чтобы гарантировать, что системы электронной почты назначения доверяют сообщениям, отправленным с вашего пользовательского домена.

Используйте DKIM вместе с инфраструктурой политики отправителей и DMARC, чтобы злоумышленники не могли отправлять сообщения якобы из вашего домена. DKIM позволяет добавлять цифровую подпись в заголовки исходящих сообщений электронной почты. Это может показаться сложным, но на самом деле все просто. При настройке DKIM вы авторизуете домен, чтобы сопоставить его имя с сообщением электронной почты с помощью криптографической проверки подлинности. С помощью этой цифровой подписи системы электронной почты могут определить, действительно ли входящее сообщение отправлено из вашего домена.

По сути, вы используете закрытый ключ для шифрования заголовков сообщений, отправляемых из домена. В записях DNS домена вы публикуете открытый ключ, с помощью которого принимающие серверы расшифровывают подпись. С помощью открытого ключа они проверяют, действительно ли сообщения отправлены вами, а не злоумышленниками, *подделавшими* ваш домен.

Microsoft 365 автоматически настраивает DKIM для своих первоначальных доменов «onmicrosoft.com». Это означает, что вам не нужно ничего делать, чтобы настроить DKIM для любого исходного имени домена (например, litware.onmicrosoft.com). Дополнительные сведения о доменах см. в статье [Вопросы и ответы о доменах](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).

Вы также можете не настраивать DKIM для личного домена. Если вы не настроили DKIM для своего пользовательского домена, Microsoft 365 создаст пару личного и открытого ключей, разрешит подпись DKIM, а затем настроит политику Microsoft 365 по умолчанию для вашего пользовательского домена. Хотя это достаточное покрытие для большинства клиентов, вы должны вручную настроить DKIM для своего пользовательского домена в следующих случаях:

- У вас есть несколько пользовательских доменов в Microsoft 365

- вы также собираетесь настроить DMARC (рекомендуется);

- вам необходим контроль над закрытым ключом;

- вам необходимо настроить записи CNAME.

- вам нужно настроить ключи DKIM для сообщений электронной почты со стороннего домена, например при использовании стороннего средства для массовых рассылок.

В этой статье

- [Как DKIM работает лучше, чем один SPF, для предотвращения злонамеренного подмены](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [Обновление 1024-разрядных ключей до 2048-разрядных ключей шифрования DKIM вручную](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [Шаги, которые необходимо сделать, чтобы вручную настроить DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [Чтобы настроить DKIM для нескольких пользовательских доменов](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [Отключение политики подписи DKIM для пользовательского домена](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [Поведение по умолчанию для DKIM и Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [Как настроить DKIM так, чтобы сторонняя служба могла отправлять сообщения электронной почты от имени вашего личного домена](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [Следующие шаги: после настройки DKIM для Microsoft 365](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a>Как DKIM работает лучше, чем один SPF, для предотвращения злонамеренного подмены
<a name="HowDKIMWorks"> </a>

Инфраструктура политики отправителей добавляет сведения в конверт сообщения, а технология DKIM шифрует подпись в заголовке сообщения. При пересылке фрагменты конверта этого сообщения могут быть удалены сервером пересылки. Поскольку цифровая подпись остается в заголовке сообщения, технология DKIM работает даже при пересылке, как показано в примере ниже.

![Схема, на которой показана проверка подлинности DKIM: пересланное сообщение не прошло проверку инфраструктурой политики отправителей](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

Если бы в этом примере вы опубликовали только запись типа TXT инфраструктуры политики отправителей для домена, почтовый сервер получателя мог бы пометить ваше сообщение как спам, что привело бы к ложному срабатыванию. Добавление DKIM в этом сценарии позволяет снизить количество ложных срабатываний. Так как в технологии DKIM для проверки подлинности используется шифрование с помощью открытого ключа, а не только IP-адресов, она считается более надежным способом проверки подлинности, чем инфраструктура политики отправителей. Рекомендуем использовать обе эти технологии, а также DMARC в вашем развертывании.

Подробности: DKIM использует закрытый ключ для вставки зашифрованной подписи в заголовки сообщений. Имя подписывающего домена (или домена исходящей почты) вставляется в заголовок в качестве значения поля **d=**. Проверяющий домен (или домен получателя) затем использует поле **d=** для поиска открытого ключа в DNS и проверки подлинности сообщения. Так сообщение проходит проверку DKIM.

## <a name="manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a>Обновление 1024-разрядных ключей до 2048-разрядных ключей шифрования DKIM вручную
<a name="1024to2048DKIM"> </a>

Так как ключи DKIM могут быть 1024- и 2048-разрядными, эти инструкции предназначены для перехода с 1024- на 2048-разрядные ключи. Описанные ниже действия относятся к двум вариантам использования. Выберите вариант, подходящий для вашей конфигурации.

1. Если вы **уже настроили DKIM**, измените разрядность следующим образом:

   1. [Подключитесь к рабочим нагрузкам Office 365 с помощью PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window). (Командлет из Exchange Online.)
   1. Выполните следующую команду:

      ```powershell 
      Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
      ```

1. В случае **новой реализации DKIM**:

   1. [Подключитесь к рабочим нагрузкам Office 365 с помощью PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window). (Это командлет Exchange Online.)
   1. Выполните следующую команду:

      ```powershell
      New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True
      ```

Оставайтесь на связи с Microsoft 365, чтобы *проверить* конфигурацию.

1. Выполните следующую команду:

   ```powershell
   Get-DkimSigningConfig -Identity {Domain for which the configuration was set} | Format-List
   ```

> [!TIP]
> Этот новый 2048-разрядный ключ вступает в силу с даты, указанной в параметре RotateOnDate. Пока же сообщения электронной почты будут отправляться с использованием 1024-разрядного ключа. Через четыре дня вы снова можете выполнить проверку с использованием 2048-разрядного ключа (то есть после применения изменения ко второму селектору).

Если вы хотите перейти ко второму селектору, вы можете: а) позволить службе Microsoft 365 повернуть селектор и обновить ее до 2048-разрядности в течение следующих 6 месяцев, или б) через 4 дня и подтвердить, что 2048-разрядности используется вручную поверните вторую клавишу выбора с помощью соответствующего командлета, указанного выше.

## <a name="steps-you-need-to-do-to-manually-set-up-dkim"></a>Шаги, которые необходимо сделать, чтобы вручную настроить DKIM
<a name="SetUpDKIMO365"> </a>

Настройка DKIM состоит из двух этапов:

- [Публикация двух записей CNAME для личного домена в DNS](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [Включите подпись DKIM для вашего пользовательского домена](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a>Публикация двух записей CNAME для личного домена в DNS
<a name="Publish2CNAME"> </a>

Для каждого домена, для которого требуется добавить подпись DKIM в DNS, необходимо опубликовать две записи CNAME.

Чтобы создать записи селектора, выполните следующие команды:

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

Если вы подготовили пользовательские домены в дополнение к исходному домену в Microsoft 365, вы должны опубликовать две записи CNAME для каждого дополнительного домена. Итак, если у вас есть два домена, вы должны опубликовать две дополнительные записи CNAME и так далее.

Для записей CNAME используйте указанный ниже формат.

> [!IMPORTANT]
> Если вы один из наших клиентов GCC High, мы вычисляем _domainGuid_ другим способом. Вместо поиска записи MX для вашего _initialDomain_ с целью вычисления _domainGuid_ мы вычисляем его непосредственно на основании личного домена. Например, если ваш личный домен — contoso.com, ваш domainGuid будет иметь вид contoso-com, то есть все точки будут заменены дефисами. Таким образом, независимо от записи MX, на которую указывает ваш initialDomain, вы всегда можете использовать описанный выше метод для вычисления domainGuid, чтобы использовать его в записях CNAME.

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

- Значение _domainGUID_ — такое же, как и значение _domainGUID_ в пользовательской записи MX для вашего личного домена, которое указывается перед адресом mail.protection.outlook.com. Например, в следующей записи MX для домена contoso.com значение _domainGUID_ равно contoso-com:

  > contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com

- _initialDomain_ - это домен, который вы использовали при регистрации в Microsoft 365. Исходные домены всегда заканчиваются на onmicrosoft.com. О том, как узнать свой исходный домен, читайте в разделе [часто задаваемых вопросов](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).

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
> Важно создать вторую запись, но только один из селекторов может быть доступен во время создания. По сути, второй селектор может указывать на адрес, который еще не создан. Мы все же рекомендуем создать вторую запись CNAME, поскольку ротация ключей будет беспроблемной.

> [!CAUTION]
> Автоматическая ротация ключей временно отключена, поскольку мы реализуем изменения структуры в процессе создания ключей. Рекомендуется использовать несколько ключей для обеспечения их периодической ротации. Хотя их трудно взломать, однако разумной стратегией снижения рисков считается защита от олицетворения. Чтобы сделать это в своей организации следуйте положениям документа [Rotate-DkimSigningConfig](https://docs.microsoft.com/powershell/module/exchange/rotate-dkimsigningconfig). Мы ожидаем повторное включение автоматической ротации до августа 2020 г.

### <a name="enable-dkim-signing-for-your-custom-domain"></a>Включите подпись DKIM для вашего пользовательского домена
<a name="EnableDKIMinO365"> </a>

После публикации записей CNAME в DNS вы готовы включить подпись DKIM через Microsoft 365. Это можно сделать в Центре администрирования Microsoft 365 или с помощью PowerShell.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a>Включение функции подписывания с помощью DKIM для личного домена в Центре администрирования

1. [Войдите в Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4), используя свою рабочую или учебную учетную запись.

2. В левом верхнем углу щелкните значок средства запуска приложений и выберите **Администратор**.

3. В области навигации слева внизу разверните узел **Администратор** и выберите элемент **Exchange**.

4. Перейдите в раздел **Защита** \> **dkim**.

5. Выберите домен, для которого требуется включить DKIM, а затем в разделе **Добавлять подписи DKIM в сообщения для этого домена** нажмите **Включить**. Повторите этот шаг для каждого личного домена.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a>Как включить подпись с помощью DKIM для личного домена, используя PowerShell

1. [Подключение к PowerShell для Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

2. Выполните следующую команду:

   ```powershell
   Set-DkimSigningConfig -Identity <domain> -Enabled $true
   ```

   Где _domain_ — имя личного домена, для которого требуется включить функцию подписывания с помощью DKIM.

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

1. [Подключение к PowerShell для Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

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

   Где _number_ — индекс политики. Например:

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a>Поведение по умолчанию для DKIM и Microsoft 365
<a name="DefaultDKIMbehavior"> </a>

Если вы не активируете DKIM, Microsoft 365 автоматически создает 1024-битный открытый ключ DKIM для вашего домена по умолчанию и связанный с ним закрытый ключ, который мы храним внутри нашего центра обработки данных. По умолчанию Microsoft 365 использует конфигурацию подписи по умолчанию для доменов, у которых нет политики. Это означает, что если вы не настроите DKIM самостоятельно, Microsoft 365 будет использовать политику по умолчанию и ключи, которые она создает, чтобы включить DKIM для вашего домена.

Кроме того, если вы отключите подпись DKIM после включения, через некоторое время Microsoft 365 автоматически применит политику по умолчанию для вашего домена.

В следующем примере предположим, что DKIM для fabrikam.com был включен Microsoft 365, а не администратором домена. Это означает, что в службе DNS нет требуемых записей CNAME. Подписи DKIM для электронной почты из этого домена будут выглядеть следующим образом:

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

В этом примере имя узла и доменное имя содержат значения, на которые указывала бы запись CNAME, если бы администратор домена настроил подпись DKIM для домена fabrikam.com. В конце концов, каждое сообщение, отправленное из Microsoft 365, будет подписано DKIM. Если вы включили DKIM самостоятельно, то домен будет совпадать с доменом, указанным в адресе From: (в этом случае fabrikam.com). В противном случае будет использоваться исходный домен организации. О том, как узнать свой исходный домен, читайте в разделе [часто задаваемых вопросов](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).

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
