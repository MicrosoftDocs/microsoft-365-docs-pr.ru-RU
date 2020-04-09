---
title: Шифрование служб Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 4/8/2020
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Сводка. сведения о шифровании данных на уровне службы в Microsoft Office 365.
ms.openlocfilehash: a8faded033ade013924eeeab269aa213840430b4
ms.sourcegitcommit: 13f28aa762e467bab8ab1e95e1917b3ac28931da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2020
ms.locfileid: "43193465"
---
# <a name="office-365-service-encryption"></a>Шифрование служб Office 365

В дополнение к использованию BitLocker для шифрования на уровне тома, Exchange Online, Skype для бизнеса, SharePoint Online, OneDrive для бизнеса и Teams также используют шифрование служб для шифрования данных клиентов. Шифрование службы позволяет использовать два параметра управления ключами:

- Корпорация Майкрософт управляет всеми ключами шифрования. В настоящее время этот параметр доступен в SharePoint Online, OneDrive для бизнеса, Skype для бизнеса и командах чата. По умолчанию данные шифруются с помощью управляемых ключей Майкрософт.

- Ваша организация предоставляет корневые ключи. Управление этими ключами осуществляется с помощью Azure Key Vault. Этот параметр называется ключом клиента. В настоящее время ключ клиента доступен для файлов Exchange Online, SharePoint Online, OneDrive для бизнеса, Skype для бизнеса и Teams. Если вы используете ключ клиента, эти ключи заменяют управляемые ключи Майкрософт для шифрования данных.

Независимо от выбранного варианта шифрование службы предоставляет несколько преимуществ:

- Обеспечивает проверку подлинности пользователей для получения и расшифровки данных, запрашиваемых авторизованным пользователем.

- Обеспечивает разделение администраторов операционной системы Windows от доступа к данным клиентов, хранящимся или обрабатываемым операционной системой.

- Расширяет возможности Office 365 для удовлетворения требований клиентов, имеющих требования по обеспечению соответствия требованиям для шифрования.

Сведения о том, как настроить ключ клиента для Office 365 для Exchange Online, Skype для бизнеса, SharePoint Online, OneDrive для бизнеса и файлов Teams, можно найти в следующих статьях:

- [Шифрование службы с помощью ключа клиента в Office 365](customer-key-overview.md)

- [Настройка ключа клиента для Office 365](customer-key-set-up.md)

- [Управление ключом клиента для Office 365](customer-key-manage.md)

- [Вращение или поворот ключа клиента или ключа доступности](customer-key-availability-key-roll.md)

- [Общие сведения о ключе доступности](customer-key-availability-key-understand.md)
