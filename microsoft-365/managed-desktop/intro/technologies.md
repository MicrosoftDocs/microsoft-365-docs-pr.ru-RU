---
title: Технологии компьютеров, управляемых Майкрософт
description: В этом разделе перечислены технологии и приложения, используемые в Microsoft Managed Desktop.
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a6e3e7cc0404a56e4d69da69b95aa95fa6795dd5
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002225"
---
# <a name="microsoft-managed-desktop-technologies"></a>Технологии компьютеров, управляемых Майкрософт

В этом разделе перечислены технологии и приложения, используемые в Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Для всех пользователей настольных компьютеров Майкрософт необходимо лицензирование Microsoft 365 Enterprise. Дополнительные сведения о требованиях к лицензированию для службы приведены в разделе [Предварительные условия для управляемого рабочего стола Майкрософт](../get-ready/prerequisites.md).

В этом разделе представлен обзор компонентов, включенных в необходимые корпоративные лицензии, а также описание того, как служба использует каждый компонент с настольными устройствами, управляемыми корпорацией Майкрософт. Конкретные роли и обязанности для каждой области подробно описаны в документации на настольном компьютере, управляемой корпорацией Майкрософт. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 или в ~
 |
 --- | ---
Приложения Microsoft 365 для предприятий (64-разрядная версия) | Эти приложения Office будут поставляться вместе с устройством: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype для бизнеса, OneNote.<br><br>64 — полные версии Microsoft Project и Microsoft Visio не включены. Тем не менее, так как установка этих приложений зависит от установки приложений Microsoft 365 для предприятия, на компьютере, на котором установлены приложения Microsoft Intune, по умолчанию создаются развертывания Microsoft Intune и группы безопасности, которые можно использовать для развертывания этих приложений на лицензированных пользователей. Дополнительные сведения: [Install Microsoft Project или Microsoft Visio на настольных устройствах, управляемых Майкрософт](../get-started/project-visio.md).
OneDrive |Служба единого входа Azure Active Directory включена для пользователей при первом входе в OneDrive.<br><br>Включается перенаправление папок "Рабочий стол", "документ" и "изображения". включается и настраивается на настольном компьютере, управляемом Майкрософт.
Приложения Магазина |    Microsoft Sway и Power BI не поставляются вместе с устройством. Эти приложения доступны для скачивания из Microsoft Store.
Приложения Win32 |    Teams не поставляется с устройством, но упаковывается и предоставляется корпорацией Майкрософт для настольных устройств, управляемых Майкрософт. Клиент Azure Information Protection не поставляется с устройством, но его можно подготовить к развертыванию.
Веб-приложения |  Yammer, Office в браузере, delve, Flow, StaffHub, PowerApps и планировщике не входят в комплект поставки устройства. Пользователи могут получать доступ к веб-версиям этих приложений с помощью браузера.


## <a name="windows-10-enterprise-e3-or-e5"></a>Windows 10 Корпоративная, E3 или 10

 |
 --- | ---
Виртуализация приложений (App-V) |    Клиенты могут развертывать пакеты App # V с помощью клиента управления приложениями Intune Win32.
Microsoft Defender для конечной точки |    На рабочем столе Майкрософт это используется для мониторинга безопасности устройств. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security/Security

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Для управления устройствами MDM можно использовать все функции Enterprise Mobility + Security E3 и Azure Active Directory Premium P2.
Microsoft Cloud App Security |  Вы можете использовать эту необязательную функцию с настольным компьютером, управляемым Майкрософт.
Azure Information Protection P2  | Вы можете использовать эту необязательную функцию с настольным компьютером, управляемым Майкрософт.
