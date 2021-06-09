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
description: Администратор может узнать о параметрах настройки потока почты и маршрутинга в Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9636025796aee1ba2027edff38a16f131974134f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842498"
---
# <a name="mail-flow-in-eop"></a>Поток обработки почты в EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

В Microsoft 365 организациях с Exchange Online почтовыми ящиками или автономными организациями Exchange Online Protection (EOP) без Exchange Online почтовых ящиков все сообщения, отправленные в организацию, передаются через EOP перед их просмотром сотрудниками. У вас есть варианты маршрутивка сообщений, которые передаются через EOP для обработки, прежде чем они будут переданы в почтовые ящики рабочих.

## <a name="working-with-messages-and-message-access-options"></a>Возможности для работы с сообщениями и доступа к ним

EOP обеспечивает гибкость в маршрутных маршрутах сообщений. В указанных ниже разделах описаны шаги процесса потока обработки почты.

[Использование блокировки края на основе каталога для отклонить сообщения, отправленные недействительным получателям](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Описывает функцию блокировки на основе каталогов, которая позволяет отклонить сообщения для недействительных получателей в периметре сети службы.

[Просмотр или изменение принятых доменов](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) в EOP описывает управление доменами, связанными с вашей службой EOP.

Если вы добавляете поддомены в организацию, служба EOP поможет вам управлять и ими. Дополнительные новости о поддоменах в списке Включить поток почты для [поддоменов](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)в Exchange Online .

[Настройка потока почты с помощью соединители](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) вводит соединители и показывает, как их можно использовать для настройки маршрутизации почты. Среди сценариев обеспечение безопасной связи с партнерской организацией и настройка промежуточного узла.

[Расширенная фильтрация соединители описывает](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) настройку соединители, если ваша почта передается в службу или устройство перед EOP.

В гибридных средах, в которых EOP защищает локальные почтовые ящики Exchange, требуется настроить правила потока обработки почты (также называемые правилами транспорта) в локальной среде Exchange для преобразования решения фильтра нежелательной почты EOP, чтобы правило нежелательной почты могло перемещать сообщение в папку "Нежелательная почта". Дополнительные сведения см. в статье [Настройка EOP для доставки спама в папку нежелательной почты в гибридных средах](/exchange/standalone-eop/configure-eop-spam-protection-hybrid). Если вы не хотите перемещать сообщения в папку нежелательной почты каждого пользователя, вы можете выбрать другое действие, редактировать политики по борьбе со спамом (также известные как политики фильтра контента). Дополнительные сведения см. в статье [Настройка политик защиты от нежелательной почты](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Проверка потока почты

Чтобы убедиться в правильности настройки EOP, включая конфигурацию соединителей, см. раздел "Проверка выполнения" в [Настройка службы EOP](/exchange/standalone-eop/set-up-your-eop-service).

[Проверка потока почты](/exchange/mail-flow-best-practices/test-mail-flow) путем проверки Microsoft 365 соединителю предоставляет инструкции по проверке правильной настройка потока почты.
