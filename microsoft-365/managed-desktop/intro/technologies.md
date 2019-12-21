---
title: Управляемые технологии для настольных ПК Майкрософт
description: В этом разделе перечислены технологии и приложения, используемые в Microsoft Managed Desktop.
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: beab5df5b978cc3e2fd6dd345609a22209501298
ms.sourcegitcommit: 237589a0c8a24510e5c8f3b8b4747d944ad0afbf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "37113722"
---
# <a name="microsoft-managed-desktop-technologies"></a>Управляемые технологии для настольных ПК Майкрософт

В этом разделе перечислены технологии и приложения, используемые в Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Для всех пользователей настольных компьютеров Майкрософт необходимо лицензирование Microsoft 365 Enterprise. Дополнительные сведения о требованиях к лицензированию для службы приведены в разделе [Предварительные условия для управляемого рабочего стола Майкрософт](../get-ready/prerequisites.md).

В этом разделе представлен обзор компонентов, включенных в необходимые корпоративные лицензии, а также описание того, как служба использует каждый компонент с настольными устройствами, управляемыми корпорацией Майкрософт. Конкретные роли и обязанности для каждой области подробно описаны в документации на настольном компьютере, управляемой корпорацией Майкрософт. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 или в ~
 |
 --- | ---
Office 365 профессиональный плюс (64-бит) | Эти приложения Office будут поставляться вместе с устройством: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype для бизнеса, OneNote.<br><br>64 — полные версии Microsoft Project и Microsoft Visio не включены. Тем не менее, поскольку установка этих приложений зависит от установки Office 365 профессиональный плюс, на компьютере, управляемом Майкрософт, были созданы развертывания Microsoft Intune по умолчанию и группы безопасности, которые можно использовать для развертывания этих приложений в соответствии с лицензией конечные пользователи. Дополнительные сведения: [Install Microsoft Project или Microsoft Visio на настольных устройствах, управляемых Майкрософт](../get-started/project-visio.md).
OneDrive для бизнеса |Служба единого входа Azure Active Directory включена для конечных пользователей при первом входе в OneDrive для бизнеса.<br><br>Включается перенаправление папок "Рабочий стол", "документ" и "изображения". включается и настраивается на настольном компьютере, управляемом Майкрософт. 
Приложения Магазина |    Microsoft Sway и Power BI не поставляются вместе с устройством. Эти приложения доступны для скачивания из Microsoft Store.
Приложения Win32 |    Teams не поставляется с устройством, но упаковывается и предоставляется корпорацией Майкрософт для настольных устройств, управляемых Майкрософт. Клиент Azure Information Protection не поставляется с устройством, но его можно подготовить к развертыванию. 
Веб-приложения |  Yammer, Office в браузере, delve, Flow, StaffHub, PowerApps и планировщике не входят в комплект поставки устройства. Пользователи могут получать доступ к веб-версиям этих приложений с помощью браузера.


## <a name="windows-10-enterprise-e3-or-e5"></a>Windows 10 Корпоративная, E3 или 10

 |
 --- | ---
Виртуализация приложений (App-V) |    Клиенты могут развертывать пакеты App # V с помощью клиента управления приложениями Intune Win32.
Advanced Threat Protection в Microsoft Defender |  На рабочем столе Майкрософт это используется для мониторинга безопасности устройств. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security/Security

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Для управления устройствами MDM можно использовать все функции Enterprise Mobility + Security E3 и Azure Active Directory Premium P2.
Microsoft Cloud App Security |  Вы можете использовать эту необязательную функцию с настольным компьютером, управляемым Майкрософт.
Azure Information Protection P2  | Вы можете использовать эту необязательную функцию с настольным компьютером, управляемым Майкрософт.
