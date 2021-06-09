---
title: Установка Microsoft Project или microsoft Visio на компьютеры, управляемые Майкрософт устройствах
description: Сведения об установке Microsoft Project или microsoft Visio на компьютеры, управляемые Майкрософт устройствах
keywords: компьютеры, управляемые Майкрософт, Microsoft 365, Microsoft Project, Microsoft Visio
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
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Установка Microsoft Project или microsoft Visio на компьютеры, управляемые Майкрософт устройствах

Microsoft Project и microsoft Visio требуются определенные действия, которые необходимо установить на компьютеры, управляемые Майкрософт устройствах. В этом разделе документироваться необходимые условия и процесс установки для этих приложений.

## <a name="prerequisites"></a>Предварительные условия

Администраторы должны убедиться, что они соответствуют этим требованиям:
- **Количество лицензий** — необходимое количество Microsoft Project лицензий и Visio microsoft должны быть доступны для пользователей. компьютеры, управляемые Майкрософт в настоящее время поддерживает только 64-битные версии этих приложений. 
- **Имена лицензий** . Соответствующие имена лицензий для этих приложений:
    - **Microsoft Project** - Project Online профессиональный или Project Online расширенный
    - **Microsoft Visio** - Visio Online Plan 2
- **Корпоративный портал** . Корпоративный портал клиент должен быть доступен пользователям для установки этих приложений. Если Корпоративный портал не развернут в клиенте, см. Корпоративный портал [.](company-portal.md)

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Развертывание Project и Visio для компьютеры, управляемые Майкрософт устройств
компьютеры, управляемые Майкрософт добавит Microsoft Project Microsoft Visio в качестве двух приложений Win32 в Microsoft Intune. Мы также создадим две группы в Azure Active Directory, которые будут назначены соответствующему приложению с намерением "Доступно". 

**Развертывание Project и Visio** Добавьте пользователя в соответствующую группу, и приложение станет доступным в Корпоративный портал. Синхронизация может занять несколько минут, но затем пользователи могут установить приложения из Корпоративный портал. 

Имя группы Azure AD | Какие пользователи назначать?   
 --- | ---
Современные рабочие Office-Project_Install | Пользователям, Project
Современные рабочие Office-Visio_Install | Пользователи, нуждающиеся в Visio

## <a name="communicate-changes"></a>Связывать изменения
ИТ-администраторы должны знать, как установить Project и Visio. К ним относятся: 
- Уведомление пользователей о том, когда эти приложения доступны для них. 
- Инструкции по установке этих приложений из Корпоративный портал.
