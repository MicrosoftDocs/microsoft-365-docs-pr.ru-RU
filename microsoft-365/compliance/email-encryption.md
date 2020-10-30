---
title: Шифрование писем в Microsoft 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: Сведения о различиях вариантов шифрования Microsoft 365, в том числе шифрования сообщений Office (OME), S/MIME, службы управления правами на доступ к данным (IRM), а также о протоколе TLS.
ms.openlocfilehash: 81ce8ca567c2b696060a1dd41b9af06bfc7b94a7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769057"
---
# <a name="email-encryption"></a>Шифрование электронной почты

В этой статье сравниваются возможности шифрования в Microsoft 365, в том числе шифрование сообщений Office (OME), S/MIME и службы управления правами на доступ к данным (IRM), а также объясняется протокол TLS.
  
Microsoft 365 delivers multiple encryption options to help you meet your business needs for email security. This article presents three ways to encrypt email in Office 365. If you want to learn more about all security features in Office 365, visit the [Office 365 Trust Center](https://go.microsoft.com/fwlink/p/?LinkID=282470). This article introduces the three types of encryption available for Microsoft 365 administrators to help secure email in Office 365:
  
- шифрование сообщений Microsoft (OME);

- Secure/Multipurpose Internet Mail Extensions (S/MIME);

- управления правами на доступ к данным (IRM).

## <a name="email-encryption-and-how-microsoft-365-uses-it"></a>Шифрование писем и способ его использования в Microsoft 365

Encryption is the process by which information is encoded so that only an authorized recipient can decode and consume the information. Microsoft 365 uses encryption in two ways: in the service, and as a customer control. In the service, encryption is used in Microsoft 365 by default; you don't have to configure anything. For example, Microsoft 365 uses Transport Layer Security (TLS) to encrypt the connection, or session, between two servers. 
  
Вот как обычно работает шифрование электронной почты:
  
- Сообщение шифруется или преобразуется из обычного текста в нечитаемый зашифрованный текст на компьютере отправителя или на центральном сервере во время пересылки сообщения.

- Сообщение сохраняется в зашифрованном виде во время передачи, чтобы защитить его от чтения при возможном перехвате.

- После получения сообщения получателем оно преобразуется в читаемый обычный текст одним из двух способов:

  - компьютер получателя использует ключ для расшифровки сообщения;

  - центральный сервер расшифровывает сообщение от имени получателя после проверки удостоверения получателя.

Дополнительные сведения о том, как Microsoft 365 защищает соединение между серверами, например между серверами нескольких организаций с Microsoft 365 или между серверами организаций с Microsoft 365 и серверами доверенного партнера, не использующего Microsoft 365, см. в статье [Использование протокола TLS службой Exchange Online для защиты электронной почты в Office 365](exchange-online-uses-tls-to-secure-email-connections.md).
  
Просмотрите видеоролик о [шифровании в Office 365](https://www.youtube.com/watch?v=KmfxCd5ublI).
  
## <a name="comparing-email-encryption-options-available-in-office-365"></a>Сравнение вариантов шифрования электронной почты, доступных в Office 365

||![Концептуальная иллюстрация, описывающая OME](../media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)|![Концептуальная иллюстрация, описывающая IRM](../media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)|![Концептуальная иллюстрация, описывающая SMIME](../media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)|
|:-----|:-----|:-----|:-----|
|Что это такое?|Шифрование сообщений Office 365 (OME) — это служба, основанная на службе Azure RMS, которая позволяет отправлять шифрованные письма пользователям внутри или за пределами организации независимо от того конечного электронного адреса (Gmail, Yahoo! Mail, Outlook.com и т. д.). <br/> Как администратор вы можете настроить правила транспорта, которые определяют условия шифрования. Когда пользователь отправляет сообщение, соответствующее правилу, шифрование применяется автоматически. <br/> To view encrypted messages, recipients can either get a one-time passcode, sign in with a Microsoft account, or sign in with a work or school account associated with Office 365. Recipients can also send encrypted replies. They don't need a Microsoft 365 subscription to view encrypted messages or send encrypted replies.|IRM — это решение шифрования, которое также применяет ограничения к письмам. Это позволяет предотвратить печать, пересылку или копирование конфиденциальных сведений несанкционированными людьми. <br/> Для реализации возможностей IRM в Microsoft 365 используется служба управления правами Azure (Azure RMS).|S/MIME is a certificate-based encryption solution that allows you to both encrypt and digitally sign a message. The message encryption helps ensure that only the intended recipient can open and read the message. A digital signature helps the recipient validate the identity of the sender. <br/> Цифровые подписи и шифрование сообщений реализуются с помощью уникальных цифровых сертификатов, которые содержат ключи для проверки цифровых подписей и шифрования или расшифровки сообщений. <br/> To use S/MIME, you must have public keys on file for each recipient. Recipients have to maintain their own private keys, which must remain secure. If a recipient's private keys are compromised, the recipient needs to get a new private key and redistribute public keys to all potential senders.|
|Для чего оно используется?|OME: <br/> шифрует сообщения, отправляемые внутренним или внешним получателям. <br/>  Позволяет пользователям отправлять зашифрованные сообщения на любой электронный адрес, включая Outlook.com, Yahoo! Mail и Gmail. <br/>  Позволяет администратору настроить портал для просмотра электронной почты в соответствии с фирменным стилем организации. <br/> Корпорация Майкрософт управляет ключами и хранит их, поэтому вам не нужно об этом беспокоиться. <br/> Специальное клиентское программное обеспечение не требуется, так как зашифрованное сообщение (оно отправляется как HTML-вложение) можно открыть в браузере.|IRM: <br/> Использует шифрование и ограничения для защиты писем и вложений в сетевом и автономном режиме. <br/> Предоставляет вам как администратору возможность настроить правила транспорта или правила защиты Outlook, которые автоматически применяют IRM к определенным сообщениям. <br/> Позволяет пользователям вручную применять шаблоны в Outlook или Outlook в Интернете (прежнее название — Outlook Web App).|Протокол S/MIME используется для проверки подлинности адресов отправителей с помощью цифровых подписей и шифрования сообщений.|
|Для чего оно не используется?|OME doesn't let you apply usage restrictions to messages. For example, you can't use it to stop a recipient from forwarding or printing an encrypted message.|Some applications may not support IRM emails on all devices. For more information about these and other products that support IRM email, see [Client device capabilities](https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities).|Протокол S/MIME не допускает проверку зашифрованных сообщений на наличие вредоносных программ, нежелательной почты или на соответствие политикам.|
|Рекомендации и примеры сценариев|We recommend using OME when you want to send sensitive business information to people outside your organization, whether they're consumers or other businesses. For example:  <br/>  Сотрудник банка отправляет клиентам выписки по кредитным картам.  <br/>  Сотрудник больницы отправляет медицинские записи пациенту.  <br/>  Адвокат передает конфиденциальные юридические сведения другому адвокату.|Мы рекомендуем использовать IRM, чтобы применять ограничения использования, а также шифрование. Например:  <br/>  Руководитель отправляет своей рабочей группе конфиденциальные сведения о новом продукте с параметром "Не пересылать".  <br/>  Руководителю требуется отправить предложение другой компании, которое содержит вложение от партнера, использующего Office 365, с защитой письма и вложения.|Мы рекомендуем использовать S/MIME, если вашей организации или организации получателя требуется одноранговое шифрование.  <br/>  S/MIME чаще всего используется в следующих случаях:  <br/>  Государственные учреждения взаимодействуют с другими государственными учреждениями.  <br/>  Компания взаимодействует с государственным учреждением.|
||

Если вы используете как [Azure Information Protection](https://docs.microsoft.com/microsoft-365/compliance/protect-information), так и шифрование писем для защиты данных, рассмотрите следующие возможности:
- Вы можете использовать метки конфиденциальности с шифрованием OME и IRM. Дополнительные сведения см. в статье [Ограничение доступа к содержимому при использовании меток конфиденциальности для шифрования](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels?view=o365-worldwide#what-happens-to-existing-encryption-when-a-labels-applied).
- Вы можете применять метки конфиденциальности к сообщениям с цифровой подписью S/MIME.
- Вы не можете применять метки конфиденциальности к сообщениям, зашифрованным с помощью S/MIME, так как сообщения, защищенные с помощью комплексного шифрования, не обрабатываются политиками.

## <a name="encryption-options-available-for-my-microsoft-365-subscription"></a>Доступные варианты шифрования для подписки на Microsoft 365

Сведения о вариантах шифрования электронной почты для подписки на Microsoft 365 см. в статье [Описание службы Exchange Online](https://technet.microsoft.com/library/exchange-online-service-description.aspx). Здесь вы найдете сведения о следующих функциях шифрования:

- Azure RMS, включая возможности IRM и новые возможности OME

- S/MIME

- TLS;

- шифрование неактивных данных (BitLocker).

С Microsoft 365 можно также использовать сторонние средства шифрования, например PGP (Pretty Good Privacy). Microsoft 365 не поддерживает стандарт PGP/MIME, и для отправки и получения сообщений, зашифрованных с помощью PGP, вы можете использовать только PGP/Inline.

## <a name="what-about-encryption-for-data-at-rest"></a>Как насчет шифрования неактивных данных?

"Неактивные данные" — это данные, которые не передаются в текущий момент. В Microsoft 365 данные электронной почты при хранении шифруются с помощью шифрования диска BitLocker. Для обеспечения улучшенной защиты от несанкционированного доступа жесткие диски в центрах обработки данных корпорации Майкрософт шифруются с использованием BitLocker. Дополнительные сведения см. в [обзоре компонента BitLocker](https://go.microsoft.com/fwlink/p/?LinkId=394737).
  
## <a name="more-information-about-email-encryption-options"></a>Дополнительные сведения о вариантах шифрования электронной почты

Дополнительные сведения о вариантах шифрования электронной почты, описанных в этой статье, а также о протоколе TLS см. в следующих статьях:
  
**OME**
  
[Шифрование сообщений Office 365 (OME)](ome.md)
  
**IRM**
  
[Управление правами на доступ к данным в Exchange Online](https://technet.microsoft.com/library/jj983436%28v=exchg.150%29.aspx)
  
[Управление правами Azure](https://technet.microsoft.com/library/jj585026)
  
**S/MIME**
  
[S/MIME для подписи и шифрования сообщений](https://technet.microsoft.com/library/dn626158)
  
[Общие сведения о S/MIME](https://technet.microsoft.com/library/aa995740%28v=exchg.65%29.aspx)
  
[Общие сведения о шифровании с открытым ключом](https://technet.microsoft.com/library/aa998077%28v=exchg.65%29.aspx)
  
**TLS**
  
[Настройка пользовательского потока обработки почты с помощью соединителей](https://technet.microsoft.com/library/jj723138%28v=exchg.150%29.aspx)
