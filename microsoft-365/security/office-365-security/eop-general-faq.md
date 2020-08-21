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
description: Получите ответы на наиболее распространенные общие вопросы об облачной службе фильтрации электронной почты Exchange Online Protection (EOP).
ms.openlocfilehash: 42162ea841f876fc5e958d67fab61dbe4bffe9de
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827765"
---
# <a name="eop-general-faq"></a>Общие вопросы и ответы по EOP

Ниже приведены ответы на самые распространенные общие вопросы об облачной службе фильтрации электронной почты Exchange Online Protection (EOP). Другие разделы, посвященные вопросам и ответам, можно найти по следующим ссылкам:

- [Поставленные в очередь, отложенные и возвращенные сообщения EOP: вопросы и ответы](eop-queued-deferred-and-bounced-messages-faq.md)

- [Вопросы и ответы по делегированному администрированию](delegated-administration-faq.md)

- [Вопросы и ответы по защите от нежелательной почты](anti-spam-protection-faq.md)

- [Вопросы и ответы, посвященные карантину](quarantine-faq.md)

- [Вопросы и ответы по защите от вредоносных программ](anti-malware-protection-faq-eop.md)

- [Вопросы и ответы по трассировке сообщений](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>Что такое EOP?

EOP  это облачная служба фильтрации электронной почты, предназначенная для защиты клиентов от нежелательной почты и вредоносных программ, а также для внедрения настраиваемых правил политики. EOP включен в любую подписку Microsoft 365, содержащую почтовые ящики Exchange Online. EOP также доступен в качестве автономного предложения для защиты локальных почтовых сред.

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>Как подписаться на пробную версию EOP или купить EOP?

Получите пробную версию EOP или купите EOP на [домашней странице Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection). Обратите внимание на то, что функциональность пробной версии подписки аналогична платной, но также содержит дополнительные возможности, предоставляемые [Exchange Enterprise CAL со службами](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview).

## <a name="how-is-eop-priced"></a>Каковы расценки на EOP?

EOP лицензируется по количеству пользователей. Последние сведения о ценах см. на [домашней странице Exchange Online Protection.](https://products.office.com/exchange/exchange-email-security-spam-protection)

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>Сколько времени требуется на ввод EOP в рабочий режим?

Если поток вашей почты проходит через EOP, фильтрация начинается сразу после изменения записи MX (инструкции по изменению приводятся в разделе [Настройка службы EOP](set-up-your-eop-service.md)). На распространение записи MX через DNS может потребоваться от 24 до 48 часов. Точную настройку параметров защиты можно выполнить в любой момент во время этого процесса.

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>Нужно ли использовать все компоненты Microsoft 365 для использования EOP? Как быть, если я хочу получить только защиту EOP?

Вы можете использовать EOP для защиты локальных почтовых ящиков, не используя другие компоненты Microsoft 365. Это называется "автономной подпиской". Список функций EOP можно найти в статье [Описание службы Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>Зачем нужен клиент Microsoft 365 при подписке на использование фильтров электронной почты через EOP?

Microsoft 365 — это название совокупности продуктов и служб, доступ к которым можно получить с помощью клиента Microsoft 365. Клиент Microsoft 365 служит отправной точкой, к которой можно добавить лицензии на использование фильтров электронной почты.

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>Содержит ли служба EOP такой коммуникационный портал, где можно узнать об известных проблемах и предполагаемых решениях? Какие новые функции этой службы?

Определенные сведения можно ознакомиться в Центре администрирования Microsoft 365. Если произойдет событие уровня обслуживания, то после входа в Центр администрирования Microsoft 365 вы увидите оповещение (обычно помеченное значком коробки). Рекомендуем прочитать его и выполнить необходимые действия.

Новые возможности EOP в [Microsoft 365 для](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) бизнеса — это хороший ресурс, с помощью которых можно ознакомиться с информацией о новых возможностях. Мы также будем публиковать статьи о новых возможностях на [веб-сайте блогов Microsoft 365.](https://www.microsoft.com/microsoft-365/blog/)

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>Работает ли служба с прежними версиями Exchange (например, с Exchange Server 2010) и средами, не основанными на Exchange?

Да, работа службы не является сервером и может использоваться с любым агентом передачи почты SMTP.

## <a name="what-size-organization-can-use-the-service"></a>Организации какого размера могут использовать службу?

Любого. Сеть EOP обладает достаточной пропускной способностью, чтобы учесть рост вашей организации, независимо от темпов роста.

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>Какие разрешения нужны для настройки EOP?

Для настройки EOP вы должны быть глобальным администратором или администратором компании Exchange (группа ролей управления организацией).

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>Как я могу убедиться в безопасности моих данных и конфиденциальных сведений?

Дополнительные сведения о мерах, которые мы предпринимаем для обеспечения безопасности ваших данных и конфиденциальных сведений, в том числе сведений о соглашениях об уровне обслуживания, можно найти на веб-сайте [Центр управления безопасностью Office 365](https://www.microsoft.com/trust-center).

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>Существуют ли ограничения, о которых мне следует знать, например ограничения размера сообщения?

Да. Дополнительные сведения об ограничениях в EOP см. в статье ["Ограничения Exchange Online Protection".](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)

## <a name="does-eop-support-powershell"></a>Поддерживает ли EOP PowerShell?

Да, в PowerShell доступны все функции службы EOP: Exchange Online PowerShell для организаций с почтовыми ящиками Exchange Online; Автономная оболочка EOP PowerShell для отдельных организаций EOP. Дополнительные сведения см. в [статье Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) [и PowerShell в Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell)
