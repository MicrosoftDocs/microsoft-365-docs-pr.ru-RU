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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: Ответы на наиболее распространенные общие вопросы об облачной службе фильтрации электронной почты Exchange Online Protection (EOP).
ms.openlocfilehash: aa0b881250466c71cb05123216fcf9eccc64018d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202919"
---
# <a name="eop-general-faq"></a>Общие вопросы и ответы по EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Здесь мы будем отвечать на наиболее распространенные общие вопросы о облачной службе фильтрации электронной почты Exchange Online Protection (EOP). Другие разделы, посвященные вопросам и ответам, можно найти по следующим ссылкам:

- [Поставленные в очередь, отложенные и возвращенные сообщения EOP: вопросы и ответы](eop-queued-deferred-and-bounced-messages-faq.md)

- [Вопросы и ответы по делегированному администрированию](delegated-administration-faq.md)

- [Вопросы и ответы по защите от нежелательной почты](anti-spam-protection-faq.md)

- [Вопросы и ответы, посвященные карантину](quarantine-faq.md)

- [Вопросы и ответы по защите от вредоносных программ](anti-malware-protection-faq-eop.md)

- [Вопросы и ответы по трассировке сообщений](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>Что такое EOP?

EOP  это облачная служба фильтрации электронной почты, предназначенная для защиты клиентов от нежелательной почты и вредоносных программ, а также для внедрения настраиваемых правил политики. EOP включен в любую подписку на Microsoft 365, содержащую почтовые ящики Exchange Online. EOP также можно использовать в качестве автономного предложения для защиты локальных почтовых сред.

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>Как подписаться на пробную версию EOP или купить EOP?

Получите пробную версию EOP или купите EOP на [домашней странице Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection). Обратите внимание на то, что функциональность пробной версии подписки аналогична платной, но также содержит дополнительные возможности, предоставляемые [Exchange Enterprise CAL со службами](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview).

## <a name="how-is-eop-priced"></a>Каковы расценки на EOP?

EOP лицензируется по количеству пользователей. Последние сведения о ценах можно найти на [домашней странице Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection).

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>Сколько времени требуется на ввод EOP в рабочий режим?

Если поток вашей почты проходит через EOP, фильтрация начинается сразу после изменения записи MX (инструкции по изменению приводятся в разделе [Настройка службы EOP](set-up-your-eop-service.md)). На распространение записи MX через DNS может потребоваться от 24 до 48 часов. Вы можете настроить параметры защиты в любое время в ходе этого процесса.

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>Нужно ли использовать все функции Microsoft 365 для использования EOP? Что делать, если я только хочу EOP защиту и все?

Вы можете использовать EOP для защиты локальных почтовых ящиков, не используя никакие другие функции Microsoft 365. Это называется "автономной подпиской". Список функций EOP можно найти в статье [Описание службы Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>Зачем нужен клиент Microsoft 365 при регистрации для фильтрации электронной почты с помощью EOP?

Microsoft 365 — это имя, присваиваемое семейству продуктов и служб, доступ к которым можно получить с помощью клиента Microsoft 365. Подумаем о клиенте Microsoft 365 в качестве отправной точки, к которой вы можете добавить лицензии для фильтрации электронной почты.

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>Содержит ли служба EOP такой коммуникационный портал, где можно узнать об известных проблемах и предполагаемых решениях? Какие новые функции этой службы?

В центре администрирования Microsoft 365 будет указана часть этих сведений. Если вы оказываете влияние на событие уровня обслуживания, то после входа в центр администрирования Microsoft 365 вы увидите оповещение о связи (обычно сопровождается значком колокольчика). Рекомендуем прочитать его и выполнить необходимые действия.

О новых возможностях EOP [корпорация майкрософт 365 для бизнеса](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) — это хороший ресурс для получения сведений о новых возможностях. Кроме того, мы будем отправлять статьи блогов о новых возможностях на веб-сайт [блогов Microsoft 365](https://www.microsoft.com/microsoft-365/blog/) .

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>Работает ли служба с прежними версиями Exchange (например, с Exchange Server 2010) и средами, не основанными на Exchange?

Да, служба не зависит от сервера и может использоваться с любым агентом передачи почты SMTP.

## <a name="what-size-organization-can-use-the-service"></a>Организации какого размера могут использовать службу?

Любого. Сеть EOP обладает достаточной пропускной способностью, чтобы учесть рост вашей организации, независимо от темпов роста.

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>Какие разрешения нужны для настройки EOP?

Для настройки EOP необходимо быть глобальным администратором или администратором компании Exchange (группа ролей управления организацией).

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>Как я могу убедиться в безопасности моих данных и конфиденциальных сведений?

Дополнительные сведения о мерах, которые мы предпринимаем для обеспечения безопасности ваших данных и конфиденциальных сведений, в том числе сведений о соглашениях об уровне обслуживания, можно найти на веб-сайте [Центр управления безопасностью Office 365](https://www.microsoft.com/trust-center).

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>Существуют ли ограничения, о которых мне следует знать, например ограничения размера сообщения?

Да. Более подробную информацию об ограничении в EOP можно узнать в статье [Exchange Online Protection Limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

## <a name="does-eop-support-powershell"></a>Поддерживает ли EOP PowerShell?

Да, полнофункциональные функции EOP доступны через PowerShell: Exchange Online PowerShell для организаций с почтовыми ящиками Exchange Online; Изолированная EOP PowerShell для автономных организаций EOP. Дополнительные сведения см. в статье [Exchange Online PowerShell PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) и [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell).
