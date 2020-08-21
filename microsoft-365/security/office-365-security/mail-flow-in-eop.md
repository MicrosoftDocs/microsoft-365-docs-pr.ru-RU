---
title: Поток обработки почты в службе EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: Администратор изучите параметры настройки потока обработки почты и маршрутизации в Exchange Online Protection (EOP).
ms.openlocfilehash: c58981afaadf2c4083b6a6db99c74cf9544715c3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827729"
---
# <a name="mail-flow-in-eop"></a>Поток обработки почты в службе EOP

В организациях Microsoft 365 с почтовыми ящиками Exchange Online или в организациях с автономной службой Exchange Online Protection (EOP) все сообщения, отправляемые в организацию, проходят через EOP до того, как ваши звонят ваши клиенты. Перенаправлять сообщения, которые проходят через EOP, можно перед их маршрутизацией в папки "Входящие" ваших рабочих процессов.

## <a name="working-with-messages-and-message-access-options"></a>Возможности для работы с сообщениями и доступа к ним

Служба EOP обеспечивает гибкость в маршрутизации сообщений. В указанных ниже разделах описаны шаги процесса потока обработки почты.

[Использование пограничной блокировки на основе каталогов для отклонения сообщений, отправленных недопустимым получателям](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Описание функции пограничной блокировки на основе каталогов, которая позволяет отклонять сообщения для недопустимых получателей в периметре сервисной сети.

В разделе [View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) описано, как управлять доменами, сопоставленными со службой EOP.

Если вы добавляете поддомены в организацию, служба EOP поможет вам управлять и ими. Дополнительные сведения о поддоменах см. в [разделе "Включение потока обработки почты для поддоменов в Exchange Online".](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)

[Настройка потока обработки почты с помощью](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) соединителей ознакомления и их использование при настройке маршрутизации почты. Среди сценариев обеспечение безопасной связи с партнерской организацией и настройка промежуточного узла.

[Улучшенная фильтрация для соединителей](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) описывает, как настроить соединители, если почта направляется в службу или на устройство перед EOP.

Чтобы нежелательная почта правильно маршрутизировалась в папки нежелательной почты каждого пользователя, необходимо выполнить несколько действий по настройке. Они подробно рассмотрены [в разделе "Настройка автономной службы EOP для доставки спама в папку нежелательной почты в гибридных средах".](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) Если вы не хотите перемещать сообщения в папку "Нежелательная почта" каждого пользователя, можно выбрать другое действие с помощью политик защиты от нежелательной почты (также называемых политиками фильтрации содержимого). Дополнительные сведения см. в статье [Настройка политик защиты от нежелательной почты](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Проверка потока почты

Чтобы убедиться в правильности настройки EOP, включая конфигурацию соединителей, см. раздел "Проверка выполнения" в [Настройка службы EOP](set-up-your-eop-service.md).

[Протестируйте поток обработки почты, проверив соединители Microsoft 365,](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) следуя инструкциям по проверке правильности настройки потока обработки почты.
