---
title: Уведомления конечных пользователей о нежелательной почте в Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Администраторы могут узнать о уведомлениях пользователей о нежелательной почте для сообщений в карантине в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bb347f7fd3d3793b563714e8116316b30165ef9a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287549"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Использование уведомлений пользователей о нежелательной почте для освобождения сообщений в карантине и их отчетов

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

В организациях Microsoft 365 с почтовыми ящиками в Exchange Online или в автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online на карантине хранятся потенциально опасные или нежелательные сообщения. Дополнительные сведения см. в сообщении на [карантине в EOP.](quarantine-email-messages.md)

По умолчанию уведомления пользователей о нежелательной почте отключены в политиках борьбы с нежелательной почтой. Когда администратор включает уведомления конечных пользователей о нежелательной [почте,](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)получатели (включая общие почтовые ящики с включенной поддержкой автомагистрали) будут периодически получать уведомления о своих сообщениях, которые были отправлены на карантин как спам, массовая рассылка или (в апреле 2020 г.) фишинг.

Для общих почтовых ящиков уведомления конечных пользователей о нежелательной почте поддерживаются только для пользователей, которым предоставлено разрешение fullAccess для общего почтового ящика. Дополнительные сведения см. в сообщении Об использовании [EAC для изменения делегирования общих почтовых ящиков.](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)

Уведомления пользователей о нежелательной почте не поддерживаются для групп.

> [!NOTE]
> Сообщения, которые были отправлены на карантин как фишинг с высокой достоверности, вредоносные программы или правила потока почты (также известные как правила транспорта), доступны только администраторам. Дополнительные сведения см. в разделе [Управление сообщениями и файлами на карантине в качестве администратора в EOP](manage-quarantined-messages-and-files.md).

Уведомление пользователя о нежелательной почте содержит следующие сведения для каждого сообщения в карантине:

- **Отправитель:** имя отправки и адрес электронной почты сообщения, отправленного в карантин.

- **Тема:** текст строки темы сообщения в карантине.

- **Date**: The date and time (in UTC) that the message was quarantined.

- **Block Sender**: Click this link to add the sender to your Blocked Senders list. Дополнительные сведения см. в сообщении [Block a mail sender.](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)

- **Release**: для нежелательных (не фишинговых) сообщений вы можете освободить это сообщение здесь, не переходить на карантин Центра безопасности & соответствия требованиям.

- **Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages. Дополнительные сведения см. в записи поиска и освобождения сообщений на карантине от пользователя [в EOP.](find-and-release-quarantined-messages-as-a-user.md)

![Пример уведомления пользователя о нежелательной почте](../../media/end-user-spam-notification.png)

> [!NOTE]
> Заблокированный отправитель по-прежнему может отправлять вам почту. Все сообщения от этого отправитель, которые будут отправлены в ваш почтовый ящик, будут немедленно перемещены в папку нежелательной почты. Последующие сообщения от этого отправитель будут перенаправлены в папку нежелательной почты или в карантин пользователя. Если вы хотите удалить эти сообщения при поступлении, а не на карантин, используйте правила потока почты [(также](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) известные как правила транспорта) для удаления сообщений при их поступлении.
