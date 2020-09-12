---
title: Миграция почтовых ящиков Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: В этой статье представлен краткий обзор миграции почтовых ящиков Microsoft 365 и список командлетов, используемых для миграции.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63080643e4994d6b16e77298907725a827997cef
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546802"
---
# <a name="microsoft-365-mailbox-migrations"></a>Миграция почтовых ящиков Microsoft 365

С помощью гибридного развертывания на основе Exchange клиенты могут выбрать, как переместить локальные почтовые ящики Exchange в организацию [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) или переместить почтовые ящики Exchange Online в [локальную организацию Exchange](https://docs.microsoft.com/Exchange/exchange-server) . Пакеты миграции используются при перемещении почтовых ящиков между локальной организацией и организацией Exchange Online.

Пользователи могут просматривать статистику и другие сведения о миграции почтовых ящиков с помощью следующих командлетов:

- [Get – MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/get-moverequeststatistics): предоставляет статистику по умолчанию для почтового ящика пользователя, включающую состояние, размер почтового ящика, размер архивного почтового ящика и процент выполнения.
- [Get/Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox
): содержит сводный список объектов и атрибутов почтовых ящиков в Организации.
- [Get – Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient): предоставляет список существующих объектов с включенной поддержкой почты, таких как почтовые ящики, почтовые пользователи, контакты и группы рассылки.
- [Get – MoveRequest](https://docs.microsoft.com/powershell/module/exchange/get-moverequest): предоставляет подробные сведения о состоянии текущей миграции почтовых ящиков.
- [Get – MigrationUser](https://docs.microsoft.com/powershell/module/exchange/get-migrationuser): сведения о перемещении и миграции почтовых ящиков пользователей.
- [Get – MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/get-migrationbatch): содержит сведения о состоянии текущего пакета миграции.
- [Get – мигратионусерстатистикс](https://docs.microsoft.com/powershell/module/exchange/get-migrationuserstatistics): предоставляет подробные сведения о состоянии миграции для определенного пользователя.
- [Get – MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics): предоставляет сведения о почтовых ящиках, например размер, количество сообщений и время последнего обращения.

Дополнительные сведения о командлетах приведены [в статье Move and Migration командлеты в Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell).
