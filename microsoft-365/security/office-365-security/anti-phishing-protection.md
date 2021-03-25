---
title: Защита от фишинга
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Администраторы могут узнать о средствах защиты от фишинга в Exchange Online Protection (EOP) и Microsoft Defender для Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b0ca7a83e8e8d66bd58fddfc46f53df32f4f623c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206898"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Защита от фишинга в Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Фишинг —* это атака электронной почты, которая пытается украсть конфиденциальные сведения в сообщениях, которые, как представляется, являются законными или доверенными отправителями. Существуют определенные категории фишинга. Пример.

- **При фишинге** копья используется специализированный настраиваемый контент, специально настроенный для целевых получателей (как правило, после разведки получателей злоумышленником).

- **Китобойный промывка** ориентирован на руководителей или другие целевые объекты с высоким значением в организации для максимального эффекта.

- Бизнес-компромисс электронной почты **(BEC)** использует поддельные доверенные отправители (финансовые сотрудники, клиенты, доверенные партнеры и т.д.) для обмана получателей в согласовании платежей, передаче средств или раскрытии данных клиентов.

-  Программы-вымогательы, шифрующие данные и требующие оплаты, чтобы расшифровать их, почти всегда начинаются с фишинговых сообщений. Защита от фишинга не поможет расшифровать зашифрованные файлы, но поможет обнаружить начальные фишинговые сообщения, связанные с кампанией вымогателей. Дополнительные сведения о восстановлении после атаки вымогателей см. в сайте [Recover from a ransomware attack in Microsoft 365.](recover-from-ransomware.md)

В связи с растущей сложностью атак даже трудно обучить пользователей распознать сложные фишинговые сообщения. К счастью, могут помочь Exchange Online Protection (EOP) и дополнительные функции в Microsoft Defender для Office 365.

## <a name="anti-phishing-protection-in-eop"></a>Защита от фишинга в EOP

EOP (то есть организации Microsoft 365 без Microsoft Defender для Office 365) содержит функции, которые могут защитить организацию от фишинговых угроз:

- **Аналитика подделки**: Просмотрите поддельные сообщения от отправителей во внутренних и внешних доменах и разрешите или заблокируйте этих отправителей. Дополнительные сведения см. в [перенастройке сведений о подмене в EOP.](learn-about-spoof-intelligence.md)

- Политики защиты от фишинга в **EOP:** включите или отключите спуф-аналитику, включите неавентированную идентификацию отправителей в Outlook или выключение и укажите действие для заблокированных подмененных отправителей (переходить в папку нежелательной почты или карантин). Дополнительные сведения см. в [сообщении Configure anti-phishing policies in EOP.](configure-anti-phishing-policies-eop.md)

- Неявная проверка подлинности **электронной** почты: EOP повышает стандартную проверку подлинности электронной почты для входящие сообщения [(SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)и [DMARC)](use-dmarc-to-validate-email.md)с репутацией отправителей, историей отправителей, историей получателей, поведенческим анализом и другими передовыми методами, которые помогут определить поддельных отправителей. Дополнительные сведения см. в статье [Поверка подлинности электронной почты в Microsoft 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Дополнительная защита от фишинга в Microsoft Defender для Office 365

Microsoft Defender для Office 365 содержит дополнительные и более продвинутые функции защиты от фишинга:

- Политики защиты от фишинга в **Microsoft Defender для Office 365:** создание новых настраиваемых политик, настройка параметров защиты от обезличения (защита пользователей и доменов от обезличения), параметры разведданных почтовых ящиков и регулируемые пороги расширенных фишинговых атак. Дополнительные сведения см. в [сообщении Configure anti-phishing policies in Microsoft Defender for Office 365.](configure-atp-anti-phishing-policies.md) Дополнительные сведения о различиях между политиками защиты от фишинга в EOP и антифишинговыми политиками в Defender for Office 365 см. в сообщении о политике защиты от фишинга в [Microsoft 365.](set-up-anti-phishing-policies.md)

- **Просмотры** кампании. Машинное обучение и другие юристики определяют и анализируют сообщения, участвующие в скоординированных фишинговых атаках на всю службу и организацию. Дополнительные сведения см. в [веб-сайте Представления кампании в Microsoft Defender для Office 365.](campaigns.md)

- **Симулятор атак.** Администраторы могут создавать поддельные фишинговые сообщения и отправлять их внутренним пользователям в качестве средства обучения. Дополнительные сведения см. в [сайте Attack Simulator в Microsoft Defender для Office 365.](attack-simulator.md)

## <a name="other-anti-phishing-resources"></a>Другие ресурсы по борьбе с фишингом

- Для конечных пользователей: [защитите себя от фишинговых схем](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)и других форм мошенничества в Интернете.

- [Как Microsoft 365 проверяет адрес From для предотвращения фишинга.](how-office-365-validates-the-from-address.md)
