---
title: Установка Microsoft Project или Microsoft Visio на управляемых Майкрософт настольных устройствах
description: Сведения об установке Microsoft Project или Microsoft Visio на устройствах, управляемых Майкрософт
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c04bcdf846bafaa7838ef5932c8de595f5035992
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950536"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Установка Microsoft Project или Microsoft Visio на управляемых Майкрософт настольных устройствах

Microsoft Project и Microsoft Visio требуют установки определенных действий на настольных устройствах, управляемых Майкрософт. В этом разделе документироваться необходимые условия и процесс установки для этих приложений.

## <a name="prerequisites"></a>Предварительные условия

Администраторы должны убедиться, что они соответствуют указанным условиям.
- **Количество лицензий** — для пользователей должно быть доступно правильное количество лицензий Microsoft Project и Microsoft Visio. В настоящее время на компьютере, управляемом Майкрософт, поддерживаются только 64-битные версии этих приложений. 
- **Имена лицензий—** соответствующие имена лицензий для этих приложений:
    - **Microsoft Project** — Project Online профессиональный или Project Online премиум
    - **Microsoft Visio** — Visio Online (план 2)
- **Портал компании** — портал компании должен быть доступен в клиенте, чтобы пользователи установили эти приложения. Если портал компании не развернут в клиенте, см. ["Портал компании".](company-portal.md)

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Развертывание Project и Visio для настольных устройств, управляемых Майкрософт
Microsoft Managed Desktop добавит Microsoft Project и Microsoft Visio в качестве двух приложений Win32 в Microsoft Intune. Мы также создадим две группы в Azure Active Directory, которые будут назначены соответствующему приложению с намерением "Доступно". 

**Развертывание Project и Visio** Добавьте пользователя в соответствующую группу, и приложение станет доступным на портале компании. Синхронизация может занять несколько минут, но пользователи смогут устанавливать приложения с портала компании. 

Имя группы Azure AD | Каких пользователей назначить?   
 --- | ---
Современный workplace-Office-Project_Install | Пользователям нужен Project
Современный workplace-Office-Visio_Install | Пользователям требуется Visio

## <a name="communicate-changes"></a>Сообщить об изменениях
ИТ-администраторам важно дать своим пользователям знать, как установить Project и Visio. К ним относятся: 
- Уведомление пользователей о том, что эти приложения им доступны. 
- Инструкции по установке этих приложений с портала компании.
