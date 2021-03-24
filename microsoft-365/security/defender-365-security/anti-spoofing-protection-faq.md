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
description: Администраторы могут просматривать часто задамые вопросы и ответы о защите от спуфинга в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a5843ee7f791fbc2c37914194b153fdd05866d0a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073574"
---
# <a name="anti-spoofing-protection-faq"></a>Вопросы и ответы о защите от спуфинга

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

В этой статье часто задаются вопросы и ответы о защите от спуфинга для организаций Microsoft 365 с почтовыми ящиками в Exchange Online или автономных организаций Exchange Online Protection (EOP) без почтовых ящиков Exchange Online.

Вопросы и ответы о защите от нежелательной почты см. в [faq anti-spam protection.](anti-spam-protection-faq.md)

Вопросы и ответы о защите от вредоносных программ см. в faq [anti-malware protection](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Почему Корпорация Майкрософт выбрала нежелательной неавентированной входящие сообщения электронной почты?

Корпорация Майкрософт считает, что риск продолжения допуска недостоверной входящий электронной почты выше, чем риск потери законной входящие сообщения электронной почты.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>Вызывает ли нежелательное почта неавентированное входящие сообщения нежелательной почты как нежелательной почты?

Когда Microsoft включила эту функцию в 2018 г., произошли некоторые ложные срабатыва(хорошие сообщения были отмечены как плохие). Однако со временем отправители адаптировались к требованиям. Количество сообщений, ошибочно заверенных в качестве поддельных, стало незначительным для большинства путей электронной почты.

Корпорация Майкрософт впервые приняла новые требования к проверке подлинности электронной почты за несколько недель до ее развертывания для клиентов. Хотя сначала наступали проблемы, их количество постепенно снижалось.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a>Доступна ли подмена сведений клиентам Microsoft 365 без Defender для Office 365?

Да. С октября 2018 г. сведения о подмене доступны всем организациям с почтовыми ящиками в Exchange Online и автономными организациями EOP без почтовых ящиков Exchange Online.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Как сообщить спама или фишинговых сообщений назад в корпорацию Майкрософт?

См. [Передача информации о сообщениях и файлах в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Я администратор и не знаю всех источников сообщений в моем домене электронной почты!

См. [не все источники электронной почты.](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>Что произойдет, если я отключу защиту от подмены для организации?

Мы не рекомендуем отключить защиту от спуфинга. Отключение защиты позволит доставить больше фишинговых и спам-сообщений в организации. Не все фишинговые сообщения являются подменой, и не все поддельные сообщения будут пропущены. Однако риск будет выше.

Теперь, [когда](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) расширенная фильтрация для соединители доступна, мы больше не рекомендуем отключать защиту от подмены, когда ваша электронная почта передается через другую службу перед EOP.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>Означает ли защита от подмены, что я буду защищен от всех фишинговых атак?

К сожалению, нет. Злоумышленники будут адаптироваться к использованию других методов (например, скомпрометированная учетная запись или учетные записи в бесплатных службах электронной почты). Однако защита от фишинга гораздо лучше работает для обнаружения этих других типов методов фишинга. Уровни защиты в EOP разработаны совместно и строятся друг на друге.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>Блокируют ли другие крупные службы электронной почты недоверимую входящие сообщения?

Почти все крупные службы электронной почты реализуют традиционные проверки SPF, DKIM и DMARC. Некоторые службы имеют другие, более строгие проверки, но лишь немногие идут до EOP, чтобы заблокировать неавентированную электронную почту и относиться к ним как к поддельным сообщениям. Однако отрасль становится все более осведомленной о проблемах с недостоверной электронной почтой, особенно из-за проблемы фишинга.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>Необходимо ли включить параметр Advanced Spam Filter "SPF record: hard fail"_(MarkAsSpamSpfRecordHardFail),_ если я встану для борьбы с подменой?

Нет. Этот параметр ASF больше не требуется. Защита от спуфинга рассматривает как жесткий SPF- сбой, так и гораздо более широкий набор критериев. Если у вас активированы защита от спуфинга и **Запись инфраструктуры политики отправителей: серьезный сбой** (_MarkAsSpamSpfRecordHardFail_), вы, скорее всего, будете получать больше ложных срабатываний.

Мы рекомендуем отключить эту функцию, так как она практически не предоставляет дополнительных преимуществ для обнаружения нежелательной почты или фишинга, а вместо этого создает в основном ложные срабатывания. Дополнительные сведения см. в дополнительных настройках фильтра нежелательной почты [(ASF) в EOP.](advanced-spam-filtering-asf-options.md)

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>Помогает ли схема переописывающего отправщика исправить отправленную электронную почту?

SRS только частично устраняет проблемы с пересланным письмом. Переписав SMTP **MAIL FROM,** SRS может убедиться, что отправленное сообщение передает SPF в следующем пункте назначения. Однако, так как анти-спуфинг основан на адресе **From** в сочетании с доменом **MAIL FROM** или DKIM-подписанием (или другими сигналами), этого недостаточно, чтобы не допустить, чтобы отправленная SRS электронная почта была помечена как поддельный.