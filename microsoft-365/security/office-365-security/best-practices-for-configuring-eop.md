---
title: Рекомендации по настройке EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Следуйте этим рекомендациям передовой практики для автономных exchange Online Protection (EOP), чтобы настроить себя на успех и избежать распространенных ошибок конфигурации.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 94586d409d6d8b53ba68c22b6b4f62d2b72266db
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599479"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>Передовая практика настройки автономных EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
-  [Автономный exchange Online Protection](exchange-online-protection-overview.md)

Следуйте этим рекомендациям передовой практики для автономных exchange Online Protection (EOP), чтобы настроить себя на успех и избежать распространенных ошибок конфигурации. Предполагается, что вы уже завершили установку EOP. В противном случае изучите статью [Настройка службы EOP](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Использование тестового домена

Рекомендуем опробовать функции службы в тестовом домене, поддомене или небольшом домене, прежде чем использовать их в крупных рабочих доменах.

## <a name="synchronize-recipients"></a>Синхронизация получателей

Если в организации есть существующие учетные записи пользователей в локальной среде Active Directory, можно синхронизировать эти учетные записи с Azure Active Directory в облаке. Рекомендуется использовать синхронизацию службы каталогов. Дополнительные данные о преимуществах синхронизации каталогов и действиях по ее настройке см. в сообщении [Manage mail users in EOP.](manage-mail-users-in-eop.md)

## <a name="recommended-settings"></a>Рекомендуемые параметры

Мы уполномостили администраторов безопасности настраивать свои параметры безопасности для удовлетворения потребностей своей организации. Хотя, как правило, в EOP и Microsoft Defender для Office 365 есть два уровня безопасности: Стандартный и Строгий. Эти параметры перечислены в рекомендуемых параметрах безопасности EOP и [Microsoft Defender для Office 365.](recommended-settings-for-eop-and-office365.md)

### <a name="miscellaneousnon-policy-settings"></a>Параметры, не вступив в политику,

Эти параметры охватывают ряд функций, не входящего в политику безопасности.

<br>

****

|Имя функции безопасности|Стандартный|Strict|Comment|
|---|---|---|---|
|[Настройка SPF для предотвращения спуфинга](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Да|Да||
|[Проверка исходящей электронной почты, отправляемой с личного домена в Office 365, с помощью DKIM](use-dkim-to-validate-outbound-email.md)|Да|Да||
|[Использование протокола DMARC для проверки электронной почты в Office 365](use-dmarc-to-validate-email.md)|Да|Да|Используйте `action=quarantine` для standard и для `action=reject` Strict.|
|Развертывание [надстройки сообщения отчетов](enable-the-report-message-add-in.md) или надстройки [Report Phishing для](enable-the-report-phish-add-in.md) улучшения отчетности конечных пользователей о подозрительной электронной почте|Да|Да||
|Расписание отчетов о вредоносных программах и спаме|Да|Да||
|Автопроверка во внешние домены должна быть отсеяна или контролироваться|Да|Да||
|Необходимо включить единый аудит|Да|Да||
|[Подключение IMAP к почтовому ящику](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Отключено|Отключено||
|[Подключение POP к почтовому ящику](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Отключено|Отключено||
|Проверка подлинности отправки SMTP|Отключено|Отключено|Проверка подлинности отправки SMTP клиента (также известная как отправка SMTP или SMTP AUTH) требуется для клиентов и приложений и устройств POP3 и IMAP4, которые создают и отправляют электронную почту. <p> Инструкции по глобальному или выборочному отключению SMTP AUTH см. в материале Включить или отключить проверку подлинности отправки SMTP клиента в [Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)|
|Подключение EWS к почтовому ящику|Отключено|Отключено|Outlook использует веб-службы Exchange для бесплатных и загруженных параметров, не в офисе и общего доступа к календарю. Если вы не можете отключить EWS глобально, у вас есть следующие параметры: <ul><li>Используйте [политики проверки подлинности,](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) чтобы предотвратить использование EWS базовой проверки подлинности, если ваши клиенты поддерживают современную проверку подлинности (современный auth).</li><li>Используйте [правила клиентского доступа,](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) чтобы ограничить доступ к EWS определенным пользователям или исходным IP-адресам.</li><li>Управление доступом EWS к определенным приложениям глобально или на каждого пользователя. Инструкции см. в [инструкции Control access to EWS in Exchange.](/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)</li></ul> <p> [Надстройка](enable-the-report-message-add-in.md) сообщения Report и надстройка для фишинга [report](enable-the-report-phish-add-in.md) используют REST по умолчанию в поддерживаемых средах, но отпадет в EWS, если REST не доступен. Поддерживаемые среды, которые используют REST:<ul><li>Exchange Online</li><li>Exchange 2019 или Exchange 2016</li><li>Current Outlook для Windows из подписки Microsoft 365 или одномесячной покупки Outlook 2019.</li><li>Current Outlook для Mac из подписки Microsoft 365 или одномесячной покупки Outlook для Mac 2016 или более поздней.</li><li>Outlook для iOS и Android</li><li>Outlook в Интернете</li></ul>|
|[Подключение PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell)|Отключено|Отключено|Доступно для пользователей почтовых ящиков или пользователей почты (объекты пользователей, возвращаемые комлетом [Get-User).](/powershell/module/exchange/get-user)|
|Используйте [подмену сведений,](learn-about-spoof-intelligence.md) чтобы добавить отправителей в список разрешаний|Да|Да||
|[Блокировка края на основе каталогов (DBEB)](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|Включена|Включена|Тип домена = Авторитетный|
|[Настройка многофакторной проверки подлинности для всех учетных записей администратора](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)|Включена|Включена||
|

## <a name="troubleshooting"></a>Устранение неполадок

Устранение общих проблем и тенденций с помощью отчетов в центре администрирования. Используйте средство трассировки сообщений, чтобы найти конкретные данные о сообщении. Дополнительные данные об отчетах и [трассировка сообщений](reporting-and-message-trace-in-exchange-online-protection.md)в Exchange Online Protection . Узнайте больше о средстве трассировки сообщений в центре отслеживания сообщений [& безопасности.](message-trace-scc.md)

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Сообщение о ложных срабатывавах и ложных отрицательных результатах в Корпорации Майкрософт

Чтобы улучшить фильтрацию нежелательной почты в службе для всех, необходимо сообщить о ложных срабатываниях (хорошая электронная почта, помеченная как плохая) и ложных негативах (разрешена плохая электронная почта) в Корпорацию Майкрософт для анализа. Для получения дополнительной информации см. [Отчет о сообщениях и файлах в Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Создание правил транспорта

Создайте правила потока почты (также известные как правила транспорта) или настраиваемые фильтры для удовлетворения бизнес-потребностей.

При развертывании нового правила в рабочей среде сначала выберите один из тестовых режимов. Когда вы будете довольны тем, как правило работает, измените режим правила на **Принудительный**.

При развертывании новых правил рассмотрите возможность добавления действия **Создать отчет об инциденте** для отслеживания используемого правила.

В гибридных средах, в которых организация включает как локальное Exchange, так и Exchange Online, рассмотрите условия, которые вы используете в правилах потока почты. Если вы хотите, чтобы правила применялись для всей организации, обязательно используйте условия, доступные как в локальной Exchange, так и в Exchange Online. Хотя большинство условий доступны в обеих средах, существует несколько условий, доступных только в одной или другой среде. Дополнительные сообщения см. [в правилах потока почты (правила транспорта) в Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)