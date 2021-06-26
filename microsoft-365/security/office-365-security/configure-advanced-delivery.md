---
title: Настройка доставки сторонних фишинговых симуляций пользователям и неотображемых сообщений в почтовые ящики SecOps
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Администраторы могут узнать, как использовать передовую политику доставки в Exchange Online Protection (EOP) для идентификации сообщений, которые не должны фильтроваться в определенных поддерживаемых сценариях (сторонние фишинговые симуляции и сообщения, доставленные в почтовые ящики операций безопасности (SecOps).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01d35c1f0c7abc7b6ce34fc9c2ec4d5fd5b228ae
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137743"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>Настройка доставки сторонних фишинговых симуляций пользователям и неотображемых сообщений в почтовые ящики SecOps

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Функция, описанная в этой статье, доступна не всем и подлежит изменениям.

Чтобы обеспечить безопасность организации по [умолчанию,](secure-by-default.md)Exchange Online Protection (EOP) не разрешает безопасные списки или обход фильтрации для сообщений, которые определены как вредоносные программы или высокой достоверности фишинга. Но существуют определенные сценарии, которые требуют доставки неотобраченных сообщений. Например:

- **Сторонние имитации фишинга.** Имитация атак может помочь вам идентифицировать уязвимых пользователей до того, как реальная атака ударит по организации.
- Почтовые ящики операций безопасности **(SecOps)**— выделенные почтовые ящики, используемые группами безопасности для сбора и анализа неотобраченных сообщений (как хороших, так и плохих).

Для _предотвращения_ фильтрации этих сообщений в Microsoft 365  в этих конкретных сценариях используется усовершенствованая политика доставки в Microsoft 365. <sup>\*</sup> Продвинутая политика доставки гарантирует, что сообщения в этих сценариях будут достигать следующих результатов:

- Фильтры в EOP и Microsoft Defender для Office 365 не принимают никаких действий по этим сообщениям.<sup>\*</sup>
- Очистка от нежелательной почты и фишинга с нулевой часовой очисткой [(ZAP)](zero-hour-auto-purge.md) не принимает никаких действий по этим сообщениям.<sup>\*</sup>
- [Для этих сценариев](alerts.md) системные оповещения по умолчанию не запускаются.
- [Air и кластеризация в Defender для Office 365](office-365-air.md) игнорирует эти сообщения.
- В частности, для сторонних имитаций фишинга:
  - [Отправки администратора](admin-submission.md) создают автоматический ответ, который говорит, что сообщение является частью фишинговой кампании моделирования и не представляет реальной угрозы. Оповещения и AIR не будут запускаться.
  - [Сейф ссылки в Defender для Office 365](safe-links.md) не блокируют или не взрывают указанные URL-адреса в этих сообщениях.
  - [Сейф Вложения в Defender для Office 365](safe-attachments.md) не детонировать вложения в этих сообщениях.

<sup>\*</sup> Вы не можете обойти фильтрацию вредоносных программ или ZAP для вредоносных программ.

Сообщения, идентифицированные в продвинутой политике доставки, не являются угрозами безопасности, поэтому сообщения помечены как переопределения системы. Администраторы могут фильтровать и анализировать эти переопределения системы в следующих интерфейсах:

- [Обнаружение обозревателя угроз и обнаружения в режиме реального времени в Defender для Office 365 плана 2](threat-explorer.md)
- Страница [сущности электронной почты в обнаружении обозревателя угроз и обнаружения в режиме реального времени](mdo-email-entity-page.md)
- Отчет [о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report)
- [Расширенный поиск в Microsoft Defender для конечной точки](../defender-endpoint/advanced-hunting-overview.md)
- [Представления кампании](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

- Чтобы открыть портал Microsoft 365 Defender, перейдите на сайт <https://security.microsoft.com>. Чтобы перейти непосредственно на **страницу advanced delivery,** откройте <https://security.microsoft.com/advanceddelivery> .

- Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Прежде чем делать процедуры в этой статье, необходимо получить соответствующие разрешения.
  - Чтобы создать, изменить или удалить настроенные параметры в продвинутой политике доставки,  необходимо быть членом группы ролей администратора безопасности  на портале **Microsoft 365 Defender** и членом группы ролей управления организацией в **Exchange Online**.
  - Для доступа только для чтения к продвинутой политике доставки необходимо быть членом групп ролей **Global Reader** или **Security Reader.**

  Дополнительные сведения см. [в Microsoft 365 Defender](permissions-microsoft-365-security-center.md) и [разрешениях](/exchange/permissions-exo/permissions-exo)в Exchange Online .

  > [!NOTE]
  > Добавление пользователей к соответствующей роли Azure Active Directory дает пользователям необходимые разрешения на  портале Microsoft 365 Defender и разрешения для других функций в Microsoft 365. Дополнительные сведения см. в статье [О ролях администраторов](../../admin/add-users/about-admin-roles.md).

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>Используйте портал Microsoft 365 Defender для настройки почтовых ящиков SecOps в продвинутой политике доставки

1. На портале Microsoft 365 Defender перейдите на страницу Политики **совместной &** электронной почты & Правила правила \>  \>  \>  \> доставки.

2. На странице **Advanced delivery** убедитесь, что выбрана вкладка почтовых ящиков **SecOps,** а затем сделайте один из следующих действий:
   - Нажмите ![ кнопку Изменить ](../../media/m365-cc-sc-edit-icon.png) **значок Изменить**.
   - Если нет настроенных имитаций фишинга, нажмите **кнопку Добавить**.

3. В открываемом флажке Изменить почтовые ящики SecOps введите существующий Exchange Online почтовый ящик, который необходимо назначить почтовым ящиком **SecOps,** предприняв один из следующих действий:
   - Щелкните в поле, дайте список почтовых ящиков разрешить, а затем выберите почтовый ящик.
   - Щелкните в поле начало ввода идентификатора для почтового ящика (имя, имя отображения, псевдоним, адрес электронной почты, имя учетной записи и т.д.) и выберите почтовый ящик (имя отображения) из результатов.

     Повторите этот шаг нужное количество раз. Группы рассылки запрещены.

     Чтобы удалить существующее значение, нажмите "Удалить". ![Значок "Удалить"](../../media/m365-cc-sc-remove-selection-icon.png) рядом со значением.

4. Выполнив необходимые действия, нажмите кнопку **Сохранить**.

Настроенные записи почтовых ящиков SecOps отображаются на вкладке **почтовый ящик SecOps.** Чтобы внести изменения, нажмите ![ кнопку Изменить ](../../media/m365-cc-sc-edit-icon.png) **значок Изменить** на вкладке.

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Используйте портал Microsoft 365 Defender для настройки сторонних фишинговых симуляций в продвинутой политике доставки

1. На портале Microsoft 365 Defender перейдите на страницу Политики **совместной &** электронной почты & Правила правила \>  \>  \>  \> доставки.

2. На странице **Advanced delivery** выберите вкладку **фишинг-моделирования** и сделайте один из следующих действий:
   - Нажмите ![ кнопку Изменить ](../../media/m365-cc-sc-edit-icon.png) **значок Изменить**.
   - Если нет настроенных имитаций фишинга, нажмите **кнопку Добавить**.

3. В **открываемом вылете** редактирования сторонних фишинговых симуляций настройте следующие параметры:

   - **Отправка** домена. Разведите этот параметр и введите по крайней мере один домен электронной почты (например, contoso.com) щелкнув в поле, введите значение, а затем нажмите кнопку Введите или выберите значение, отображаемую ниже окна. Повторите этот шаг нужное количество раз. Можно добавить до 10 записей.
   - **Отправка IP.** Разведите этот параметр и введите хотя бы один допустимый адрес IPv4, щелкнув в поле, введите значение, а затем нажав кнопку Ввод или выбрав значение, отображаемую ниже окна. Повторите этот шаг нужное количество раз. Можно добавить до 10 записей. Допустимые значения:
     - Один IP. Например, 192.168.1.1.
     - Диапазон IP: Например, 192.168.0.1-192.168.0.254.
     - IP CIDR. Например, 192.168.0.1/25.
   - URL-адреса моделирования, позволяющие: расширить этот параметр и дополнительно ввести определенные URL-адреса, которые являются частью вашей кампании фишинг-моделирования, которые не должны быть заблокированы или детонировать, щелкнув в поле, введите значение, а затем нажатие ввода или выбора значения, отображаемого ниже окна. Можно добавить до 10 записей.

   Чтобы удалить существующее значение, нажмите "Удалить". ![Значок "Удалить"](../../media/m365-cc-sc-remove-selection-icon.png) рядом со значением.

4. По завершению сделайте один из следующих действий:
   - **Первый раз:** **Нажмите добавить,** а затем нажмите **кнопку Закрыть**.
   - **Изменение существующего:** **Щелкните Сохранить** и нажмите **кнопку Закрыть**.

Настроенные сторонние записи моделирования фишинга отображаются на вкладке **Имитация** фишинга. Чтобы внести изменения, нажмите ![ кнопку Изменить ](../../media/m365-cc-sc-edit-icon.png) **значок Изменить** на вкладке.

## <a name="additional-scenarios-that-require-filtering-bypass"></a>Дополнительные сценарии, которые требуют обхода фильтрации

В дополнение к двум сценариям, которые может помочь вам усовершенствовать политика доставки, существуют и другие сценарии, которые могут потребовать обхода фильтрации:

- **Сторонние фильтры.** Если запись MX  вашего домена не означает Office 365 (сообщения сначала перенаписыются где-то [еще),](secure-by-default.md) безопасность по умолчанию *недоступна.* Если вы хотите добавить защиту, необходимо включить усиленную фильтрацию для соединители (также известной как *пропустить перечисление).* Дополнительные сведения см. в [ссылке Управление потоком почты с](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)помощью стороннее облачной службы с Exchange Online. Если вы не хотите расширенной фильтрации для соединители, используйте правила потока почты (также известные как правила транспорта), чтобы обойти фильтрацию Microsoft для сообщений, которые уже были оценены сторонним фильтрацией. Дополнительные сведения см. в тексте Правила потока почты для [набора SCL в сообщениях.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)

- **Ложные** срабатываки, которые рассматриваются в настоящее время. Вы [](admin-submission.md) можете временно разрешить некоторым сообщениям, которые по-прежнему анализируются Корпорацией Майкрософт с помощью представлений администратора, сообщать о известных хороших сообщениях, которые неправильно помечены как плохие для Microsoft (ложные срабатываки). Как и во всех переопределениях, мы **_настоятельно рекомендуем,_** чтобы эти надбавки были временными.

## <a name="exchange-online-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a>Exchange Online Процедуры PowerShell для почтовых ящиков SecOps в продвинутой политике доставки

В Exchange Online PowerShell основными элементами почтовых ящиков SecOps в продвинутой политике доставки являются:

- **Политика переопределения SecOps:** управляется с помощью **\* кодлетов -SecOpsOverridePolicy.**
- **Правило переопределения SecOps.** Управляется с помощью **\* кодлетов -SecOpsOverrideRule.**

Это поведение приводит к следующим результатам:

- Сначала создается политика, а затем создается правило, определя которое определяет политику, к которую применяется правило.
- При удалении политики из PowerShell соответствующее правило также удаляется.
- При удалении правила из PowerShell соответствующая политика не удаляется. Соответствующую политику необходимо удалить вручную.

### <a name="use-powershell-to-configure-secops-mailboxes"></a>Использование PowerShell для настройки почтовых ящиков SecOps

Настройка почтового ящика SecOps в продвинутой политике доставки в PowerShell — это двухшаговая процедура:

1. Создание политики переопределения SecOps.
2. Создайте правило переопределения SecOps, которое указывает политику, к которую применяется правило.

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a>Шаг 1. Использование PowerShell для создания политики переопределения SecOps

Чтобы создать политику переопределения SecOps, используйте следующий синтаксис:

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

**Примечание.** Независимо от значения Имя, которое вы указываете, имя политики будет SecOpsOverridePolicy, поэтому вы также можете использовать это значение.

В этом примере создается политика почтовых ящиков SecOps.

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SendTo secops@contoso.com
```

Подробные сведения о синтаксисах и параметрах см. в [обзоре New-SecOpsOverridePolicy.](/powershell/module/exchange/new-secopsoverridepolicy)

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a>Шаг 2. Использование PowerShell для создания правила переопределения SecOps

В этом примере создается правило почтовых ящиков SecOps с указанными настройками.

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

**Примечание.****Независимо от значения Имя, которое вы указываете, имя правила будет SecOpsOverrideRule, где имеется уникальное значение \<GUID\> \<GUID\> GUID (например, 6fed4b63-3563-495d-a481-b24a311f8329).

Подробные сведения о синтаксисах и параметрах см. [в обзоре New-SecOpsOverrideRule.](/powershell/module/exchange/new-secopsoverriderule)

### <a name="use-powershell-to-view-the-secops-override-policy"></a>Использование PowerShell для просмотра политики переопределения SecOps

В этом примере возвращаются подробные сведения о политике почтовых ящиков SecOps.

```powershell
Get-SecOpsOverridePolicy
```

Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-SecOpsOverridePolicy.](/powershell/module/exchange/get-secopsoverridepolicy)

### <a name="use-powershell-to-view-secops-override-rules"></a>Использование PowerShell для просмотра правил переопределения SecOps

В этом примере возвращаются подробные сведения о правилах переопределения SecOps.

```powershell
Get-SecOpsOverrideRule
```

Хотя предыдущая команда должна возвращать только одно правило, все правила, ожидающих удаления, также могут быть включены в результаты.

В этом примере определяются допустимые правила (одно) и все недействительные правила.

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

После определения недействительных правил их можно удалить с помощью **cmdlet Remove-SecOpsOverrideRule,** как описано ниже [в этой статье.](#use-powershell-to-remove-secops-override-rules)

Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-SecOpsOverrideRule.](/powershell/module/exchange/get-secopsoverriderule)

### <a name="use-powershell-to-modify-the-secops-override-policy"></a>Использование PowerShell для изменения политики переопределения SecOps

Чтобы изменить политику переопределения SecOps, используйте следующий синтаксис:

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

В этом примере secops2@contoso.com политики переопределения SecOps.

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

**Примечание.** Если существует связанное, допустимые правила переопределения SecOps, адреса электронной почты в правиле также будут обновлены.

Подробные сведения о синтаксисах и параметрах см. в [обзоре Set-SecOpsOverridePolicy.](/powershell/module/exchange/set-secopsoverridepolicy)

### <a name="use-powershell-to-modify-a-secops-override-rule"></a>Использование PowerShell для изменения правила переопределения SecOps

Кодлет **Set-SecOpsOverrideRule** не изменит адреса электронной почты в правиле переопределения SecOps. Чтобы изменить адреса электронной почты в правиле переопределения SecOps, используйте **cmdlet Set-SecOpsOverridePolicy.**

Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-SecOpsOverrideRule.](/powershell/module/exchange/set-secopsoverriderule)

### <a name="use-powershell-to-remove-the-secops-override-policy"></a>Использование PowerShell для удаления политики переопределения SecOps

В этом примере удаляется политика почтовых ящиков SecOps и соответствующее правило.

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

Подробные сведения о синтаксисе и параметрах см. в этой ссылке [Remove-SecOpsOverridePolicy.](/powershell/module/exchange/remove-secopsoverridepolicy)

### <a name="use-powershell-to-remove-secops-override-rules"></a>Использование PowerShell для удаления правил переопределения SecOps

Чтобы удалить правило переопределения SecOps, используйте следующий синтаксис:

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

В этом примере удаляется указанное правило переопределения SecOps.

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

Подробные сведения о синтаксисах и параметрах см. в этой ссылке [Remove-SecOpsOverrideRule.](/powershell/module/exchange/remove-secopsoverriderule)

## <a name="exchange-online-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Exchange Online Процедуры PowerShell для сторонних имитаций фишинга в продвинутой политике доставки

В Exchange Online PowerShell основными элементами сторонних имитаций фишинга в продвинутой политике доставки являются:

- **Политика** переопределения фишингового моделирования: управляется с помощью **\* кодлетов -PhishSimOverridePolicy.**
- **Правило переопределения фишингового** моделирования: управляется с помощью **\* кодлетов -PhishSimOverrideRule.**

Это поведение приводит к следующим результатам:

- Сначала создается политика, а затем создается правило, определя которое определяет политику, к которую применяется правило.
- Параметры политики и правила изменяются отдельно.
- При удалении политики из PowerShell соответствующее правило также удаляется.
- При удалении правила из PowerShell соответствующая политика не удаляется. Соответствующую политику необходимо удалить вручную.

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a>Использование PowerShell для настройки сторонних фишинговых симуляций

Настройка сторонних имитаций фишинга в продвинутой политике доставки в PowerShell — это двухшаговая процедура:

1. Создайте политику переопределения имитации фишинга.
2. Создайте правило переопределения фишинговых симуляций, которое указывает политику, к которую применяется правило.

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a>Шаг 1. Использование PowerShell для создания политики переопределения фишинговых симуляций

В этом примере создается политика переопределения фишинговых симуляций.

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

**Примечание.** Независимо от значения Имя, которое вы указываете, имя политики будет PhishSimOverridePolicy, поэтому вы также можете использовать это значение.

Подробные сведения о синтаксисах и параметрах см. в [обзоре New-PhishSimOverridePolicy.](/powershell/module/exchange/new-phishsimoverridepolicy)

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a>Шаг 2. Использование PowerShell для создания правила переопределения фишинговых симуляций

Используйте следующий синтаксис.

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs <Domain1>,<Domain2>,...<DomainN> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>
```

Независимо от значения Имя, которое вы указываете, имя правила будет PhishSimOverrideRule, где имеется уникальное значение \<GUID\> \<GUID\> GUID (например, a0eae53e-d755-4a42-9320-b9c6b55c5011).

Допустимая запись IP-адреса — это одно из следующих значений:

- Один IP. Например, 192.168.1.1.
- Диапазон IP: Например, 192.168.0.1-192.168.0.254.
- IP CIDR. Например, 192.168.0.1/25.

В этом примере создается правило переопределения фишинговых симуляций с указанными настройками.

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

Подробные сведения о синтаксисах и параметрах см. в [обзоре New-PhishSimOverrideRule.](/powershell/module/exchange/new-phishsimoverriderule)

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a>Использование PowerShell для просмотра политики переопределения фишинговых симуляций

В этом примере возвращается подробная информация об одной и единственной политике переопределения имитации фишинга.

```powershell
Get-PhishSimOverridePolicy
```

Подробные сведения о синтаксисах и параметрах см. в [обзоре Get-PhishSimOverridePolicy.](/powershell/module/exchange/get-phishsimoverridepolicy)

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a>Использование PowerShell для просмотра правил переопределения имитации фишинга

В этом примере возвращаются подробные сведения о правилах переопределения имитации фишинга.

```powershell
Get-PhishSimOverrideRule
```

Хотя предыдущая команда должна возвращать только одно правило, все правила, ожидающих удаления, также могут быть включены в результаты.

В этом примере определяются допустимые правила (одно) и все недействительные правила.

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

После определения недействительных правил их можно удалить с помощью **cmdlet Remove-PhisSimOverrideRule,** как описано ниже [в этой статье.](#use-powershell-to-remove-phishing-simulation-override-rules)

Подробные сведения о синтаксисах и параметрах см. в [ссылке Get-PhishSimOverrideRule.](/powershell/module/exchange/get-phishsimoverriderule)

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a>Использование PowerShell для изменения политики переопределения фишинговых симуляций

Чтобы изменить политику переопределения имитации фишинга, используйте следующий синтаксис:

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

В этом примере отключает политику переопределения фишинговых симуляций.

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

Подробные сведения о синтаксисах и параметрах см. в [обзоре Set-PhishSimOverridePolicy.](/powershell/module/exchange/set-phishsimoverridepolicy)

### <a name="use-powershell-to-modify-a-phishing-simulation-override-rule"></a>Использование PowerShell для изменения правила переопределения фишинговых симуляций

Чтобы изменить правило переопределения фишинга, используйте следующий синтаксис:

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

В этом примере изменяется указанное правило переопределения имитации фишинга со следующими настройками:

- Добавьте запись домена blueyonderairlines.com.
- Удалите запись IP-адреса 192.168.1.55.

Обратите внимание, что эти изменения не влияют на существующие записи.

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

Подробные сведения о синтаксисах и параметрах см. в [инструкции Set-PhishSimOverrideRule.](/powershell/module/exchange/set-phishsimoverriderule)

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a>Использование PowerShell для удаления политики переопределения фишинговых симуляций

В этом примере удаляется политика переопределения имитации фишинга и соответствующее правило.

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

Подробные сведения о синтаксисах и параметрах см. в [ссылке Remove-PhishSimOverridePolicy.](/powershell/module/exchange/remove-phishsimoverridepolicy)

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a>Использование PowerShell для удаления правил переопределения фишинговых симуляций

Чтобы удалить правило переопределения имитации фишинга, используйте следующий синтаксис:

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

В этом примере удаляется указанное правило переопределения имитации фишинга.

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

Подробные сведения о синтаксисах и параметрах см. в [ссылке Remove-PhishSimOverrideRule.](/powershell/module/exchange/remove-phishsimoverriderule)
