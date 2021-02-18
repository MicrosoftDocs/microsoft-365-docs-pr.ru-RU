---
title: Вопросы и ответы о защите от спуфинга
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Администраторы могут просматривать часто задающие вопросы и ответы о защите от спуфинга в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d2d307d201af8ad09a4faf7a865a29da8942bdf8
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288913"
---
# <a name="anti-spoofing-protection-faq"></a>Вопросы и ответы о защите от спуфинга

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

В этой статье данная статья содержит вопросы и ответы о защите от спуфинга для организаций Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организаций Exchange Online Protection (EOP) без почтовых ящиков Exchange Online.

Вопросы и ответы о защите от нежелательной почты см. в вопросах о защите от нежелательной [почты.](anti-spam-protection-faq.md)

Вопросы и ответы о защите от вредоносных программ см. в вопросы и ответы по защите от [вредоносных программ](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Почему корпорация Майкрософт выбрала нежелаическую почту, не проавентированную по электронной почте?

Корпорация Майкрософт считает, что риск того, что неавтоматированная входящие сообщения будет продолжена, выше, чем риск потери допустимой входящие сообщения электронной почты.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>Означает ли нежелачная почта, не проавентированная по электронной почте, помечаемая как нежелачная?

Когда корпорация Майкрософт включила эту функцию в 2018 г., произошли некоторые ложные срабатываия (хорошие сообщения были помечены как плохое). Однако со временем отправителю необходимо подстраиться под требования. Количество сообщений, которые были неправильно заданы как поддельные, стало незначительным для большинства путей электронной почты.

Корпорация Майкрософт сначала приняла новые требования к проверке подлинности электронной почты за несколько недель до ее развертывания для клиентов. Хотя сначала наступали проблемы, их количество постепенно снижалось.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a>Доступна ли аналитика спуфинга пользователям Microsoft 365 без Защитника для Office 365?

Да. С октября 2018 г. аналитика спуфинга доступна всем организациям с почтовыми ящиками в Exchange Online и автономным организациям EOP без почтовых ящиков Exchange Online.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Как сообщить спама или фишинговых сообщений назад в корпорацию Майкрософт?

См. [Передача информации о сообщениях и файлах в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Я администратор и не знаю все источники сообщений в моем домене электронной почты!

См. ["Вы не знаете все источники для своей электронной почты".](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>Что произойдет, если отключить защиту от спуфинга в моей организации?

Не рекомендуется отключать защиту от спуфинга. Отключение защиты позволит доставить больше фишинговых и нежелательных сообщений в вашей организации. Не все фишинговые сообщения являются спуфингом, и не все поддельные сообщения будут пропущены. Однако риск будет выше.

Теперь, [когда доступна](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) расширенная фильтрация для соединителю, мы больше не рекомендуем отключать защиту от спуфинга, когда ваша электронная почта маршрутит через другую службу перед EOP.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>Означает ли защита от спуфинга защиту от всех фишинговых сообщений?

К сожалению, нет. Злоумышленники адаптируются к использованию других методов (например, компрометации учетных записей или учетных записей в бесплатных службах электронной почты). Однако защита от фишинга намного лучше работает для обнаружения других типов фишинговых методов. Уровни защиты в EOP разработаны совместно и работают друг над другом.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>Блокируют ли другие крупные службы электронной почты входящие сообщения, не непросвещенные?

Почти во всех крупных службах электронной почты реализованы традиционные проверки SPF, DKIM и DMARC. Некоторые службы имеют другие, более строгие проверки, но лишь некоторые из них не дойдут до EOP, чтобы заблокировать неавтерицированную электронную почту и рассматривать их как поддельные сообщения. Однако в отрасли все больше известно о проблемах с электронной почтой, неавтериированной, особенно из-за фишинга.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>Нужно ли по-прежнему включить параметр Advanced Spam Filter "Запись SPF: жесткий сбой" (_MarkAsSpamSpfRecordHardFail),_ если я влюлю анти спуфинг?

Нет. Этот параметр ASF больше не требуется. Защита от спуфинга рассматривает как жесткие сбой sPF, так и гораздо более широкий набор критериев. Если у вас активированы защита от спуфинга и **Запись инфраструктуры политики отправителей: серьезный сбой** (_MarkAsSpamSpfRecordHardFail_), вы, скорее всего, будете получать больше ложных срабатываний.

Мы рекомендуем отключить эту функцию, так как она практически не предоставляет дополнительных преимуществ для обнаружения спама или фишинговых сообщений, а вместо этого будет генерировать в основном ложные срабатывания. Дополнительные сведения см. в параметрах [advanced Spam Filter (ASF) в EOP.](advanced-spam-filtering-asf-options.md)

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>Помогает ли схема переописи отправитель исправить перенаправляемую электронную почту?

SRS только частично устраняет проблемы с пересланным письмом. Переописав SMTP **MAIL FROM,** SRS гарантирует, что пересылаемая почта пройдет SPF в следующем месте назначения. Тем не менее, так как в  основе антишуфинга лежит адрес "От" в сочетании с доменом **MAIL FROM** или DKIM-подписью (или другими сигналами), недостаточно предотвратить пометку электронной почты, пересылаемой SRS, как подмену.
