---
title: Поток обработки почты в службе EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: Администратор может узнать о параметрах настройки почтового процесса и маршрутизации в Exchange Online Protection (EOP).
ms.openlocfilehash: cb2ae7370d50fe32802ad5c279cc2170eb35f581
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208334"
---
# <a name="mail-flow-in-eop"></a>Поток обработки почты в службе EOP

В организациях Microsoft 365 с почтовыми ящиками Exchange Online или отдельными организациями Exchange Online Protection (EOP) без почтовых ящиков Exchange Online все сообщения, отправленные в организацию, проходят через EOP, прежде чем сотрудники увидят их. У вас есть параметры маршрутизации сообщений, которые проходят через EOP для обработки, прежде чем они будут направлены в свои ящики рабочих процессов.

## <a name="working-with-messages-and-message-access-options"></a>Возможности для работы с сообщениями и доступа к ним

EOP обеспечивает гибкость при маршрутизации сообщений. В указанных ниже разделах описаны шаги процесса потока обработки почты.

[Использование пограничной блокировки на основе каталогов для отклонения сообщений, отправляемых недопустимым получателям](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Описывает функцию пограничной блокировки на основе каталогов, которая позволяет отклонять сообщения для недопустимых получателей в сети периметра службы.

В разделе [View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) описано, как управлять доменами, сопоставленными со службой EOP.

Если вы добавляете поддомены в организацию, служба EOP поможет вам управлять и ими. Дополнительные сведения о поддоменах [позволяют включить почтовые потоки для поддоменов в Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

[Настройка почтового процесса с помощью соединителей](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) представляет соединители и показывает, как можно использовать их для настройки маршрутизации почты. Среди сценариев обеспечение безопасной связи с партнерской организацией и настройка промежуточного узла.

[Расширенная фильтрация для соединителей](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) описывает, как настроить соединители, если почта перенаправляется в службу или устройство до EOP.

В автономных организациях EOP необходимо выполнить несколько действий по настройке, чтобы убедиться, что нежелательная почта правильно направляется в папку нежелательной почты каждого пользователя. Они подробно описаны в разделе [Настройка автономных EOP для доставки спама в папку нежелательной почты в гибридных средах](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Если вы не хотите перемещать сообщения в папку нежелательной почты каждого пользователя, вы можете выбрать другое действие, отредактировав политики защиты от нежелательной почты (также называемые политиками фильтрации содержимого). Дополнительные сведения см. в статье [Настройка политик защиты от нежелательной почты](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Проверка потока почты

Чтобы убедиться в правильности настройки EOP, включая конфигурацию соединителей, см. раздел "Проверка выполнения" в [Настройка службы EOP](set-up-your-eop-service.md).

[Проверьте процесс обработки почты, проверив соединители Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) . инструкции по проверке правильности настройки почтового процесса.
