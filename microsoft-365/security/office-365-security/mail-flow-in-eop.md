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
description: Администратор может узнать о параметрах настройки потока почты и маршрутичности в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 043f093c801725cdf006c7c3afe7672e67d9fcef
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907030"
---
# <a name="mail-flow-in-eop"></a>Поток обработки почты в EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

В организациях Microsoft 365 с почтовыми ящиками Exchange Online или автономных организациях Exchange Online Protection (EOP) без почтовых ящиков Exchange Online все сообщения, отправленные в организацию, передаются через EOP перед их просмотром сотрудниками. У вас есть варианты маршрутивка сообщений, которые передаются через EOP для обработки, прежде чем они будут переданы в почтовые ящики рабочих.

## <a name="working-with-messages-and-message-access-options"></a>Возможности для работы с сообщениями и доступа к ним

EOP обеспечивает гибкость в маршрутных маршрутах сообщений. В указанных ниже разделах описаны шаги процесса потока обработки почты.

[Использование блокировки края на основе каталога для отклонить сообщения, отправленные недействительным получателям](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Описывает функцию блокировки на основе каталогов, которая позволяет отклонить сообщения для недействительных получателей в периметре сети службы.

В разделе [View or Edit Managed Domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) описано, как управлять доменами, сопоставленными со службой EOP.

Если вы добавляете поддомены в организацию, служба EOP поможет вам управлять и ими. Дополнительные новости о поддоменах в списке Включить поток почты для [поддоменов](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)в Exchange Online.

[Настройка потока почты с помощью соединители](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) вводит соединители и показывает, как их можно использовать для настройки маршрутизации почты. Среди сценариев обеспечение безопасной связи с партнерской организацией и настройка промежуточного узла.

[Расширенная фильтрация соединители описывает](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) настройку соединители, если ваша почта передается в службу или устройство перед EOP.

В автономных организациях EOP необходимо выполнить несколько действий по настройке, чтобы убедиться, что нежелательной почты правильно перенаправлять в папку нежелательной почты каждого пользователя. Эти сведения подробно описаны в Настройка автономных EOP для доставки нежелательной почты в папку нежелательной почты [в гибридных средах.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) Если вы не хотите перемещать сообщения в папку нежелательной почты каждого пользователя, вы можете выбрать другое действие, редактировать политики по борьбе со спамом (также известные как политики фильтрации контента). Дополнительные сведения см. в статье [Настройка политик защиты от нежелательной почты](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Проверка потока почты

Чтобы убедиться в правильности настройки EOP, включая конфигурацию соединителей, см. раздел "Проверка выполнения" в [Настройка службы EOP](set-up-your-eop-service.md).

[Проверьте поток почты, проверяя соединители Microsoft 365,](/exchange/mail-flow-best-practices/test-mail-flow) а также инструкции по проверке правильной настройка потока почты.