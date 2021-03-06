---
title: Службы для не клиентов, отправляя почту в Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: Чтобы поддерживать доверие пользователей к использованию электронной почты, Корпорация Майкрософт влала различные политики и технологии для защиты пользователей.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3213cae1b04b3f1a1b861e8f2cfc698576013546
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206517"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a>Службы для не клиентов, отправляя почту в Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Злоупотребление электронной почтой, нежелательной почты и мошеннические сообщения (фишинг) по-прежнему обременяют всю экосистему электронной почты. Чтобы поддерживать доверие пользователей к использованию электронной почты, корпорация Майкрософт использует различные политики и технологии для защиты пользователей. Однако Корпорация Майкрософт понимает, что законное сообщение электронной почты не должно быть негативно затронуто. Поэтому мы создали набор служб, которые помогут отправителям улучшить их возможность доставки электронной почты Microsoft 365 пользователям, активно управляя своей репутацией отправки.

В этом обзоре дается информация о преимуществах, которые мы предоставляем вашей организации, даже если вы не клиент.

## <a name="sender-solutions"></a>Решения отправитель

****

|Служба|Преимущества|
|---|---|
|Это содержимое справки в Интернете|Предоставляет: <ul><li>Отправная точка для любых вопросов, связанных с доставкой сообщений пользователям EOP.</li><li>Включает простое руководство по интернету с нашими политиками и требованиями.</li><li>Обзор фильтров нежелательной почты и технологий проверки подлинности, используемых Корпорацией Майкрософт.</li><ul>|
|[Служба поддержки Майкрософт](#microsoft-support)|Обеспечивает самопомеху и поддержку эскалации для проблем с доставкой.|
|[Портал делиста IP-адресов для защиты от нежелательной почты](#anti-spam-ip-delist-portal)|Средство для отправки запроса на делистинг IP. Перед отправкой этого запроса отправитель несет ответственность за то, чтобы любая дальнейшая почта, исходимая из IP-адреса, не была оскорбительной или вредоносной.|
|[Сообщения о злоупотреблениях и спаме для нежелательной почты, исходя из Exchange Online](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|Сохраняет нежелательной почты и другой нежелательной почты от Exchange Online и захламления в Интернете и вашей почтовой системе.|
|

## <a name="microsoft-support"></a>Служба поддержки Майкрософт

Корпорация Майкрософт предлагает несколько вариантов поддержки для людей, у которых возникли проблемы с отправкой почты Microsoft 365 получателей. Вот несколько рекомендаций.

- Следуйте инструкциям в любом получаемом отчете о невывозе.

- Ознакомьтесь с наиболее распространенными проблемами, с которыми сталкиваются пользователи, не связанные с устранением неполадок при устранении неполадок, отправленных [в Office 365.](troubleshooting-mail-sent-to-office-365.md)

- Используйте портал [Microsoft 365](https://sender.office.com) для отправки запроса на удаление IP-адреса из списка заблокированного отправитель.

- Ознакомьтесь [с форумами сообщества Майкрософт.](https://community.office365.com/f/)

- Свяжитесь с клиентом, с помощью другого метода, и попросите его связаться с службой поддержки Майкрософт и открыть билет на поддержку от вашего имени. В некоторых случаях по юридическим причинам Служба поддержки Майкрософт должна напрямую взаимодействовать с отправительом, которому принадлежит заблокированное IP-пространство. Тем не менее, не-клиенты обычно не могут открыть билеты поддержки.

  Дополнительные сведения о технической поддержке Microsoft для Office 365 см. в [этой записи.](/office365/servicedescriptions/office-365-platform-service-description/support)

## <a name="anti-spam-ip-delist-portal"></a>Портал делиста IP-адресов для защиты от нежелательной почты

Это портал самообслуживаний, который можно использовать для удаления из списка заблокированных Microsoft 365 отправителей. Используйте этот портал, если вы получаете сообщение об ошибке при попытке отправить сообщение электронной почты получателю, адрес электронной почты которого находится в Microsoft 365, и вы не думаете, что вам следует. Дополнительные сведения см. в статье [Удаление себя из списка заблокированных отправителей с помощью портала удаления из списка](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>Сообщения о злоупотреблениях и спаме для нежелательной почты, исходя из Exchange Online

Иногда Microsoft365 используется третьими лицами для отправки нежелательной почты в нарушение условий использования и политики. Если вы получаете нежелательное письмо из Office 365, вы можете сообщить об этих сообщениях в Корпорацию Майкрософт. Инструкции см. в [отчете о сообщениях и файлах в Корпорации Майкрософт.](report-junk-email-messages-to-microsoft.md)