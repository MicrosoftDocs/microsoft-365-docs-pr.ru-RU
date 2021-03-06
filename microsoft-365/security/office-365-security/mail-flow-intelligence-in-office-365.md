---
title: Аналитика потока почты
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Администраторы могут узнать о кодах ошибок, связанных с доставкой сообщений с помощью соединители (также известный как разведданные потока почты).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 44f2272c98f0c011c05cbe728e720f4d3180c09d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844674"
---
# <a name="mail-flow-intelligence-in-eop"></a>Аналитика потока обработки почты в EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

В Microsoft 365 организациях с почтовыми ящиками в Exchange Online или автономных организациях Exchange Online Protection (EOP) без Exchange Online почтовых ящиков обычно используется соединитель для маршрутов сообщений электронной почты из EOP в локальной среде электронной почты. Можно также использовать соединители для маршрутизации сообщений из Microsoft 365 в организацию-партнер. Когда Microsoft 365 не могут доставить эти сообщения через соединители, они в очереди в Microsoft 365. Microsoft 365 будет продолжать повторное вручную доставку для каждого сообщения в течение 24 часов. По истечении 24 часов срок ожидания сообщения истекает, и сообщение будет возвращено исходному отправителю в отчете о невывозе (также известном как сообщение NDR или отказов).

Microsoft 365 создает ошибку, когда сообщение не может быть доставлено с помощью соединитетеля. Наиболее распространенные ошибки и их решения описаны в этой статье. В совокупности ошибки в очередях и уведомлениях для неразличимых сообщений, отправленных через соединители, называются _разведданными потока почты._

## <a name="error-code-450-44312-dns-query-failed"></a>Код ошибки: 450 4.4.312 Сбой запроса DNS

Как правило, эта ошибка Microsoft 365, чтобы подключиться к смарт-хосту, указанному в соединителе, но запрос DNS для поиска IP-адресов смарт-хоста не удалось. Возможные причины этой ошибки:

- Проблема со службой размещения DNS домена (компанией, которая обслуживает полномочные серверы доменных имен для вашего домена).

- Срок действия домена недавно истек, поэтому запись MX невозможно восстановить.

- Запись MX вашего домена недавно изменилась, и DNS-серверы до сих пор кэшировали данные DNS для вашего домена.

### <a name="how-do-i-fix-error-code-450-44312"></a>Как исправить код ошибки 450 4.4.312?

- Работайте со службой размещения DNS для выявления и устранения проблемы с доменом.

- Если ошибка произошла из организации-партнера (например, поставщика облачных служб третьей стороны), обратитесь к партнеру, чтобы устранить проблему.

## <a name="error-code-450-44315-connection-timed-out"></a>Код ошибки: 450 4.4.315 Время ожидания подключения истекло

Обычно это означает, Microsoft 365 не может подключиться к серверу электронной почты назначения. Описание проблемы см. в сведениях об ошибке. Например:

- На локальном сервере электронной почты не будет.

- В настройках смарт-хостов соединительная система имеет ошибку, поэтому Microsoft 365 пытается подключиться к неправильному IP-адресу.

### <a name="how-do-i-fix-error-code-450-44315"></a>Как исправить код ошибки 450 4.4.315?

- Выясните, какой из этих пунктов относится к вам, и внесите необходимые изменения. Например, если поток почты работает правильно и параметры соединителю не изменены, необходимо проверить локальное окружение электронной почты, чтобы узнать, не работает ли сервер или произошли ли какие-либо изменения в сетевой инфраструктуре (например, вы изменили поставщиков услуг Интернета, поэтому теперь у вас есть разные IP-адреса).

- Если ошибка произошла из организации-партнера (например, поставщика облачных служб третьей стороны), обратитесь к партнеру, чтобы устранить проблему.

## <a name="error-code-450-44316-connection-refused"></a>Код ошибки: 450 4.4.316 В подключении отказано

Как правило, эта ошибка означает, Microsoft 365 при подключении к почтовому серверу назначения столкнулись с ошибкой подключения. Вероятной причиной этой ошибки является блокировка подключения брандмауэра с Microsoft 365 IP-адресов. Или эта ошибка может быть по ошибке, если вы полностью перенаселили локальной системы электронной почты в Microsoft 365 и закрыть локальной среде электронной почты.

### <a name="how-do-i-fix-error-code-450-44316"></a>Как исправить код ошибки 450 4.4.316?

- Если в локальной среде есть почтовые ящики, необходимо изменить параметры брандмауэра, чтобы разрешить подключение с Microsoft 365 IP-адресов в порту TCP 25 на локальном сервере электронной почты. Список ip-адресов Microsoft 365 см. в Microsoft 365 [URL-адресов и диапазонов IP-адресов.](../../enterprise/urls-and-ip-address-ranges.md)

- Если больше не следует отправлять сообщения в локальной  среде, щелкните Исправление в оповещении, чтобы Microsoft 365 немедленно отклонить сообщения с недействительными получателями. Это снизит риск превышения квоты организации для недействительных получателей, что может повлиять на нормальную доставку сообщений. Чтобы вручную устранить проблему, можно использовать следующие инструкции.

  - В центре [Exchange администратора (EAC)](/Exchange/exchange-admin-center)отключите или удалите соединители, доставляя электронную почту из Microsoft 365 в локальной среде электронной почты:

    1. В EAC перейдите к **соединитетелям потока** \> **почты.**

    2. Выберите соединитектор  с Office 365 значением и  сервером электронной почты Вашей организации и сделайте один из следующих действий:  
       - Удаление соединитетеля, щелкнув **значок Delete** ![ Remove Remove](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)
       - Отключайте соединители, щелкнув значок **Edit** ![ Edit и ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) включив его. 

  - Измените принятый домен в Microsoft 365, связанный с локальной средой электронной почты, с внутреннего **ретрансляции** на **авторитетный.** Инструкции см. в [инструкции Управление принятыми доменами в Exchange Online.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)

  **Примечание.** Как правило, эти изменения вступает в силу от 30 минут до одного часа. Через час убедитесь, что ошибка больше не будет допущена.

- Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных служб), свяжитесь с ней, чтобы решить проблему.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Код ошибки: 450 4.4.317 Не удается подключиться к удаленному серверу

Как правило, эта ошибка Microsoft 365 подключена к почтовому серверу назначения, но сервер ответил немедленной ошибкой или не отвечает требованиям к подключению. Описание проблемы см. в сведениях об ошибке. Например:

- Сервер электронной почты назначения ответил ошибкой "Служба недоступна", что указывает на то, что сервер не может поддерживать связь с Microsoft 365.
- Соединитель настроен для TLS, но сервер электронной почты назначения не поддерживает TLS.

### <a name="how-do-i-fix-error-code-450-44317"></a>Как исправить код ошибки 450 4.4.317?

- Проверьте параметры TLS и сертификаты на локальном сервере электронной почты и параметры TLS на соединителенном.
- Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных услуг), свяжитесь с ней, чтобы решить проблему.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Код ошибки: 450 4.4.318 Соединение было внезапно прервано

Как правило, эта ошибка Microsoft 365 с трудностями в общении с локальной средой электронной почты, поэтому подключение было отброшено. Возможные причины этой ошибки:

- Брандмауэр использует правила проверки пакетов SMTP, и эти правила работают неправильно.
- Локальное сервер электронной почты работает неправильно (например, служба зависает, сбои или низкий уровень системных ресурсов), что приводит к тому, что сервер будет отсутвлять время и закрывать подключение к Microsoft 365.
- Существуют сетевые проблемы между локальной средой и Microsoft 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>Как исправить код ошибки 450 4.4.318?

- Выясните, какой из этих пунктов относится к вам, и внесите необходимые изменения.
- Если проблема вызвана сетевыми неполадками между локальной средой и Microsoft 365, свяжитесь с сетевой командой, чтобы устранить проблему.
- Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных услуг), свяжитесь с ней, чтобы решить проблему.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Код ошибки: 450 4.7.320 Не удалось проверить сертификат

Как правило, эта ошибка Microsoft 365 при попытке проверить сертификат почтового сервера назначения. Описание см. в сведениях об ошибке. Например:

- Срок действия сертификата истек
- Субъект сертификата не совпадает с именем узла
- Сертификат больше не действителен

### <a name="how-do-i-fix-error-code-450-47320"></a>Как исправить код ошибки 450 4.7.320?

- Исправьте сертификат или параметры соединитетеля, чтобы можно было доставить Microsoft 365 в очереди.
- Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных служб), свяжитесь с ней, чтобы решить проблему.

## <a name="other-error-codes"></a>Коды других ошибок

Microsoft 365 затруднена доставка сообщений на локальном сервере или сервере электронной почты партнера. Используйте информацию **Конечный сервер** в сообщении об ошибке, чтобы устранить проблему в своей среде, или измените соединитель, если ошибка связана с конфигурацией.

Если ошибка связана с партнерской организацией (например, сторонним поставщиком облачных услуг), свяжитесь с ней, чтобы решить проблему.
