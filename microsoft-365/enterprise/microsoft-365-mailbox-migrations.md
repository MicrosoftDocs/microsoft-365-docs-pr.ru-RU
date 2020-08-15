---
title: Миграция почтовых ящиков Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 1a31eda9c33aa12e4f7c1fe3da4580eba9e1698a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693284"
---
# <a name="microsoft-365-mailbox-migrations"></a>Миграция почтовых ящиков Microsoft 365

С помощью гибридного развертывания на основе Exchange клиенты могут выбрать, как переместить локальные почтовые ящики Exchange в организацию [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) или переместить почтовые ящики Exchange Online в [локальную организацию Exchange](https://docs.microsoft.com/Exchange/exchange-server) . Пакеты миграции используются при перемещении почтовых ящиков между локальной организацией и организацией Exchange Online.

Пользователи могут просматривать статистику и другие сведения о миграции почтовых ящиков с помощью следующих командлетов:

- [Get – MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps): предоставляет статистику по умолчанию для почтового ящика пользователя, включающую состояние, размер почтового ящика, размер архивного почтового ящика и процент выполнения.
- [Get/Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
): содержит сводный список объектов и атрибутов почтовых ящиков в Организации.
- [Get – Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps): предоставляет список существующих объектов с включенной поддержкой почты, таких как почтовые ящики, почтовые пользователи, контакты и группы рассылки.
- [Get – MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps): предоставляет подробные сведения о состоянии текущей миграции почтовых ящиков.
- [Get – MigrationUser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps): сведения о перемещении и миграции почтовых ящиков пользователей.
- [Get – MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps): содержит сведения о состоянии текущего пакета миграции.
- [Get – мигратионусерстатистикс](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps): предоставляет подробные сведения о состоянии миграции для определенного пользователя.
- [Get – MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps): предоставляет сведения о почтовых ящиках, например размер, количество сообщений и время последнего обращения.

Дополнительные сведения о командлетах приведены [в статье Move and Migration командлеты в Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).
