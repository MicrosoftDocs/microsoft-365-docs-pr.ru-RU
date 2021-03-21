---
title: Общие вопросы и ответы по EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: Получите ответы на наиболее распространенные общие вопросы о облачной службе фильтрации электронной почты Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 04246b7c0a241c672328febd1584a56aa11becf2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916962"
---
# <a name="eop-general-faq"></a>Общие вопросы и ответы по EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
-  [Автономный exchange Online Protection](exchange-online-protection-overview.md)

Здесь мы ответим на наиболее распространенные общие вопросы о службе фильтрации электронной почты с облачным хостингом Exchange Online Protection (EOP). Другие разделы, посвященные вопросам и ответам, можно найти по следующим ссылкам:

- [Поставленные в очередь, отложенные и возвращенные сообщения EOP: вопросы и ответы](eop-queued-deferred-and-bounced-messages-faq.md)

- [Вопросы и ответы по делегированному администрированию](delegated-administration-faq.md)

- [Вопросы и ответы по защите от нежелательной почты](anti-spam-protection-faq.md)

- [Вопросы и ответы, посвященные карантину](quarantine-faq.md)

- [Вопросы и ответы по защите от вредоносных программ](anti-malware-protection-faq-eop.md)

- [Вопросы и ответы по трассировке сообщений](/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>Что такое EOP?

EOP  это облачная служба фильтрации электронной почты, предназначенная для защиты клиентов от нежелательной почты и вредоносных программ, а также для внедрения настраиваемых правил политики. EOP включена в любую подписку Microsoft 365, которая содержит почтовые ящики Exchange Online. EOP также доступен в качестве автономных предложений для защиты локальной среды электронной почты.

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>Как подписаться на пробную версию EOP или купить EOP?

Получите пробную версию EOP или купите EOP на [домашней странице Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection). Обратите внимание на то, что функциональность пробной версии подписки аналогична платной, но также содержит дополнительные возможности, предоставляемые [Exchange Enterprise CAL со службами](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview).

## <a name="how-is-eop-priced"></a>Каковы расценки на EOP?

EOP лицензируется по количеству пользователей. Последние сведения о ценах см. на домашней странице [Exchange Online Protection.](https://products.office.com/exchange/exchange-email-security-spam-protection)

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>Сколько времени требуется на ввод EOP в рабочий режим?

Если поток вашей почты проходит через EOP, фильтрация начинается сразу после изменения записи MX (инструкции по изменению приводятся в разделе [Настройка службы EOP](set-up-your-eop-service.md)). На распространение записи MX через DNS может потребоваться от 24 до 48 часов. Вы можете настроить параметры защиты в любое время во время этого процесса.

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>Нужно ли использовать все функции Microsoft 365 для использования EOP? Что делать, если я просто хочу защиту EOP, и это все?

Вы можете использовать EOP для защиты локального почтового ящика без использования других функций Microsoft 365. Это называется "автономной подпиской". Список функций EOP можно найти в статье [Описание службы Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>Зачем нужен клиент Microsoft 365 при регистрации на фильтрацию электронной почты через EOP?

Microsoft 365 — это имя, которое дается коллекции продуктов и служб, к ним можно получить доступ через клиента Microsoft 365. Думайте о клиенте Microsoft 365 в качестве отправной точки, к которой можно добавить лицензии для фильтрации электронной почты.

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>Содержит ли служба EOP такой коммуникационный портал, где можно узнать об известных проблемах и предполагаемых решениях? Какие новые функции этой службы?

Некоторые из этих сведений будут иметься в центре администрирования Microsoft 365. Если на вас влияет событие уровня службы, то после регистрации в центре администрирования Microsoft 365 необходимо увидеть оповещение о связи (обычно сопровождаемом значком колокола). Рекомендуем прочитать его и выполнить необходимые действия.

Что касается новых функций EOP, то [дорожная карта Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) для бизнеса является хорошим ресурсом для получения сведений о предстоящих новых функций. Мы также будем размещать статьи в блоге о новых функций на [веб-сайте Блогов Microsoft 365.](https://www.microsoft.com/microsoft-365/blog/)

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>Работает ли служба с прежними версиями Exchange (например, с Exchange Server 2010) и средами, не основанными на Exchange?

Да, служба является агностиком сервера и может использоваться с любым агентом по передаче почты SMTP.

## <a name="what-size-organization-can-use-the-service"></a>Организации какого размера могут использовать службу?

Любого. Сеть EOP обладает достаточной пропускной способностью, чтобы учесть рост вашей организации, независимо от темпов роста.

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>Какие разрешения нужны для настройки EOP?

Чтобы настроить EOP, необходимо быть глобальным администратором или администратором компании Exchange (группа ролей управления организацией).

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>Как я могу убедиться в безопасности моих данных и конфиденциальных сведений?

Дополнительные сведения о мерах, которые мы предпринимаем для обеспечения безопасности ваших данных и конфиденциальных сведений, в том числе сведений о соглашениях об уровне обслуживания, можно найти на веб-сайте [Центр управления безопасностью Office 365](https://www.microsoft.com/trust-center).

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>Существуют ли ограничения, о которых мне следует знать, например ограничения размера сообщения?

Да. Дополнительные сведения об ограничениях в EOP см. в [рублях Exchange Online Protection Limits.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)

## <a name="does-eop-support-powershell"></a>Поддерживает ли EOP PowerShell?

Да, полный функционал EOP доступен с помощью PowerShell: Exchange Online PowerShell для организаций с почтовыми ящиками Exchange Online; автономный EOP PowerShell для автономных организаций EOP. Дополнительные сведения см. в [exchange Online PowerShell](/powershell/exchange/exchange-online-powershell) и [Exchange Online Protection PowerShell.](/powershell/exchange/exchange-online-protection-powershell)