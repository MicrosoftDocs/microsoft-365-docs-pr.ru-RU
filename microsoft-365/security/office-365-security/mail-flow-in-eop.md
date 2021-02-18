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
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: Администратор может узнать о параметрах для настройки потока почты и маршрутов в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c988f58a04abf2322e993ae1b75106a338674acb
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289655"
---
# <a name="mail-flow-in-eop"></a>Поток обработки почты в EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

В организациях Microsoft 365 с почтовыми ящиками Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online все сообщения, от отправленные в организацию, проходят через EOP, прежде чем сотрудники увидят их. У вас есть варианты маршрутов сообщений, которые проходят через EOP, для обработки, прежде чем они будут перена переданы в рабочие почтовые ящики.

## <a name="working-with-messages-and-message-access-options"></a>Возможности для работы с сообщениями и доступа к ним

EOP обеспечивает гибкость маршрутов сообщений. В указанных ниже разделах описаны шаги процесса потока обработки почты.

[Использование блокировки на основе каталогов для отклонения сообщений, отправленных недопустимым получателям](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Описывает функцию блокировки на основе каталогов, которая позволяет отклонить сообщения для недопустимых получателей в периметре сети службы.

В разделе [View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) описано, как управлять доменами, сопоставленными со службой EOP.

Если вы добавляете поддомены в организацию, служба EOP поможет вам управлять и ими. Дополнительные узнать о поддоменах можно на [веб-сайте Enable mail flow for subdomains in Exchange Online.](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)

[Настройка потока почты с помощью соединители](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) представляет соединители и показывает, как их можно использовать для настройки маршрутизации почты. Среди сценариев обеспечение безопасной связи с партнерской организацией и настройка промежуточного узла.

[В расширенной фильтрации](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) соединителях описано, как настроить соединители, если почта маршрутизирована в службу или на устройство перед EOP.

В автономных организациях EOP необходимо выполнить несколько действий по настройке, чтобы обеспечить правильную маршрутацию нежелательной почты в папку нежелательной почты каждого пользователя. Они подробно описаны в описании настройки автономных EOP для доставки нежелательной почты в папку нежелательной [почты в гибридных средах.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) Если вы не хотите перемещать сообщения в папку нежелательной почты каждого пользователя, вы можете выбрать другое действие, отредактировать политики нежелательной почты (также известные как политики фильтрации содержимого). Дополнительные сведения см. в статье [Настройка политик защиты от нежелательной почты](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Проверка потока почты

Чтобы убедиться в правильности настройки EOP, включая конфигурацию соединителей, см. раздел "Проверка выполнения" в [Настройка службы EOP](set-up-your-eop-service.md).

[Проверка потока почты путем проверки](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) соединителю Microsoft 365 предоставляет инструкции по проверке правильности настроенного потока почты.
