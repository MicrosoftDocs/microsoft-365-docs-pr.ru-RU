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
description: Следуйте этим рекомендациям для самостоятельной защиты Exchange Online Protection (EOP), чтобы успешно настроиться и избежать распространенных ошибок конфигурации.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c64a9592d93ef046ad1c023a49bf378ccf6cf503
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290837"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>Best practices for configuring standalone EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
-  [Автономный exchange Online Protection](exchange-online-protection-overview.md)

Следуйте этим рекомендациям для самостоятельной защиты Exchange Online Protection (EOP), чтобы успешно настроиться и избежать распространенных ошибок конфигурации. Предполагается, что вы уже завершили установку EOP. В противном случае изучите статью [Настройка службы EOP](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Использование тестового домена

Рекомендуем опробовать функции службы в тестовом домене, поддомене или небольшом домене, прежде чем использовать их в крупных рабочих доменах.

## <a name="synchronize-recipients"></a>Синхронизация получателей

Если в вашей организации есть учетные записи пользователей в локальной среде Active Directory, их можно синхронизировать с Azure Active Directory в облаке. Рекомендуется использовать синхронизацию службы каталогов. Дополнительные информацию о преимуществах синхронизации каталогов и действиях по ее настройке см. в подсети "Управление [почтовыми пользователями в EOP".](manage-mail-users-in-eop.md)

## <a name="recommended-settings"></a>Рекомендуемые параметры

Администраторы безопасности могут настраивать параметры безопасности в целях удовлетворения потребностей организации. Хотя, как правило, в EOP и Microsoft Defender для Office 365 рекомендуется использовать два уровня безопасности: стандартный и строгий. Эти параметры перечислены в рекомендуемых параметрах для EOP и [Microsoft Defender для безопасности Office 365.](recommended-settings-for-eop-and-office365-atp.md)

### <a name="miscellaneousnon-policy-settings"></a>Параметры, не внося в политику

Эти параметры охватывают ряд функций, которые не являются политиками безопасности.

****

|Имя функции безопасности|Стандартный|Строгая|Примечание|
|---|---|---|---|
|[Настройка SPF для предотвращения спуфинга](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Да|Да||
|[Проверка исходящей электронной почты, отправляемой с личного домена в Office 365, с помощью DKIM](use-dkim-to-validate-outbound-email.md)|Да|Да||
|[Использование протокола DMARC для проверки электронной почты в Office 365](use-dmarc-to-validate-email.md)|Да|Да|Используется `action=quarantine` для стандартного и `action=reject` строгого.|
|Развертывание [надстройки Report Message](enable-the-report-message-add-in.md) или надстройки Report [Phishing](enable-the-report-phish-add-in.md) для улучшения отчетов конечных пользователей о подозрительных сообщениях электронной почты|Да|Да||
|Запланировать отчеты о вредоносных программах и спаме|Да|Да||
|Автоматическая переадружение на внешние домены должна быть неоконтролирована или отслеживаться|Да|Да||
|Необходимо включить единый аудит|Да|Да||
|[Подключение IMAP к почтовому ящику](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Отключено|Отключено||
|[Pop connectivity to mailbox](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Отключено|Отключено||
|Отправка SMTP с проверкой подлинности|Отключено|Отключено|Для отправки электронной почты клиентам POP3 и IMAP4 требуется отправка SMTP клиента с проверкой подлинности (также известная как отправка SMTP клиента или ПРОВЕРКА ПОДЛИННОСТИ SMTP).|
|Подключение EWS к почтовому ящику|Отключено|Отключено||
|[Подключение к PowerShell](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)|Отключено|Отключено|Доступно для пользователей почтовых ящиков или почтовых пользователей (объекты пользователей, возвращенные с помощью [cmdlet Get-User).](https://docs.microsoft.com/powershell/module/exchange/get-user)|
|Добавление [отправителей](learn-about-spoof-intelligence.md) в список запрещенных отправителей с помощью аналитики спуфингов|Да|Да||
|[Пограмная блокировка на основе каталогов (DBEB)](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|Включена|Включена|Тип домена = до полномочного|
|[Настройка многофакторной проверки подлинности для всех учетных записей администраторов](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)|Включена|Включена||
|

## <a name="troubleshooting"></a>Устранение неполадок

Устранение общих проблем и тенденций с помощью отчетов в Центре администрирования. Используйте средство трассировки сообщений, чтобы найти конкретные данные о сообщении. Дополнительные данные об отчетах и [трассировка сообщений в Exchange Online Protection.](reporting-and-message-trace-in-exchange-online-protection.md) Узнайте больше о средстве трассировки сообщений в [Центре безопасности & соответствия требованиям.](message-trace-scc.md)

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Сообщение о ложных срабатывах и ложных отрицательных результатах в Корпорацию Майкрософт

Чтобы улучшить фильтрацию нежелательной почты в службе для всех, необходимо сообщить корпорации Майкрософт о ложных срабатываниях (хорошая электронная почта помечена как пустая) и ложных отрицательных результатах (нехвастойкие сообщения) в корпорацию Майкрософт для анализа. Для получения дополнительной информации см. [Отчет о сообщениях и файлах в Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Создание правил транспорта

Создайте правила потока почты (также известные как правила транспорта) или настраиваемые фильтры для удовлетворения бизнес-потребностей.

При развертывании нового правила в рабочей среде сначала выберите один из тестовых режимов. Когда вы будете довольны тем, как правило работает, измените режим правила на **Принудительный**.

При развертывании новых правил рассмотрите возможность добавления действия **Создать отчет об инциденте** для отслеживания используемого правила.

В гибридных средах, в которых организация включает как локальное решение Exchange, так и Exchange Online, учитывайте условия, которые используются в правилах потока почты. Если вы хотите, чтобы правила применялись для всей организации, обязательно используйте условия, доступные как в локальной организации Exchange, так и в Exchange Online. Хотя большинство условий доступны в обеих средах, существует несколько условий, доступных только в одной или других средах. Дополнительные узнать о [правилах потока почты (правилах транспорта) в Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
