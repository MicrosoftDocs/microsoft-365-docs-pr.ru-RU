---
title: Технологии компьютеров, управляемых Майкрософт
description: В этой статье перечислены технологии и приложения, используемые на компьютерах, управляемых Майкрософт.
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: cb368939e87ddbbfc8f5386c6fc5d6bff110a7ec
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840905"
---
# <a name="microsoft-managed-desktop-technologies"></a>Технологии компьютеров, управляемых Майкрософт

В этой статье перечислены технологии и приложения, используемые на компьютерах, управляемых Майкрософт.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Для всех пользователей компьютеров, управляемых Майкрософт, требуется лицензирование Microsoft 365 корпоративный. Дополнительные сведения о требованиях к лицензированию для службы см. в предварительных [требованиях для компьютеров,](../get-ready/prerequisites.md)управляемых Майкрософт.

В этой статье кратко описаны компоненты, включенные в необходимые корпоративные лицензии, а также описано, как служба использует каждый компонент на устройствах, управляемых Майкрософт. Конкретные роли и обязанности для каждой области подробно описаны в документации microsoft Managed Desktop. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 или E5
 |
 --- | ---
Приложения Microsoft 365 для предприятий (64-битная) | Эти приложения Office будут поставляться с устройством: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype для бизнеса, OneNote.<br><br>64-битные полные версии Microsoft Project и Microsoft Visio не включены. Однако поскольку установка этих приложений зависит от установки приложений Microsoft 365 для предприятий, на компьютере, управляемом Майкрософт, созданы развертывания Microsoft Intune и группы безопасности по умолчанию, которые затем можно использовать для развертывания этих приложений для лицензированных пользователей. Дополнительные сведения см. в сведениях об [установке Microsoft Project или Microsoft Visio на настольных](../get-started/project-visio.md)устройствах, управляемых Майкрософт.
OneDrive |Единый вход Azure Active Directory включен для пользователей при первом входе в OneDrive.<br><br>Включено перенаправление известных папок для папок "Рабочий стол", "Документ" и "Изображения"; включено и настроено на компьютерах, управляемых Майкрософт.
Приложения Магазина |    Microsoft Sway и Power BI не поставляются вместе с устройством. Эти приложения доступны для скачивания из Microsoft Store.
Приложения Win32 |    Teams не поставляется вместе с устройством, но упаковывается и предоставляется корпорацией Майкрософт для настольных устройств, управляемых Майкрософт. Клиент Azure Information Protection не поставляется вместе с устройством, но его можно упаковить для развертывания.
Веб-приложения |  Yammer, Office в браузере, Delve, Flow, StaffHub, PowerApps и Планировщике не поставляются вместе с устройством. Пользователи могут получить доступ к веб-версии этих приложений с помощью браузера.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Корпоративная E5 или E3 с Microsoft Defender для конечной точки

 |
 --- | ---
Application Virtualization (App-V) |    Клиенты могут развертывать пакеты App-V с помощью клиента управления приложениями Intune Win32.
Microsoft Defender для конечной точки |    На компьютере, управляемом Майкрософт, этот продукт используется для отслеживания безопасности устройств. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Для управления устройствами MDM можно использовать все функции Enterprise Mobility + Security E3 и Azure Active Directory Premium P2.
Microsoft Cloud App Security |  Эту дополнительную функцию можно использовать с компьютером, управляемым Майкрософт.
Azure Information Protection P2  | Эту дополнительную функцию можно использовать с компьютером, управляемым Майкрософт.
