---
title: Критерии выхода инфраструктуры управления мобильными устройствами
description: Microsoft 365 Enterprise включает управление мобильными устройствами с помощью Microsoft Intune. Ознакомьтесь с требованиями и необходимыми условиями, настройте Intune, используя ресурс Azure Active Directory, регистрацию устройств iOS, macOS, Android и Windows, развертывание приложений, создание профиля, использование политики соответствия и включение условного доступа для мобильных устройств Управление устройствами с помощью Microsoft 365 корпоративный.
keywords: Microsoft 365, Microsoft 365 корпоративный, документация по Microsoft 365, управление мобильными устройствами, Intune
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 3e8013426983584783488e6f937f8ba5b02d7a1a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066794"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a>Критерии выхода инфраструктуры управления мобильными устройствами

![Этап 5. Управление мобильными устройствами](../media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

*Это относится к версиям Microsoft 365 корпоративный для E3 и "# $"*

Убедитесь, что ваша конфигурация соответствует следующим требованиям для инфраструктуры управления мобильными устройствами.

- Настроена Intune, в том числе создание пользователей и групп Azure Active Directory (Azure AD) для применения правил вашей организации к устройствам.
- Ваши устройства зарегистрированы в Intune, чтобы они могли получать политики, которые вы создаете.
- На устройства добавляются приложения, чтобы пользователи могли получать доступ к облачным службам Microsoft 365 организации, таким как Exchange Online и SharePoint Online.
- Настройка и применение функций и параметров для устройств выполняется с указанием создаваемых вами групп и пользователей Azure AD. Такая настройка может предусматривать включение антивирусной программы и ограничение работы определенных приложений.
- Политики соответствия требованиям зависят от того, требуется ли брандмауэр или длина пароля на устройстве. Если устройство не соответствует требованиям, условный доступ блокирует доступ к данным вашей организации.

## <a name="results-and-next-steps"></a>Результаты и дальнейшие действия

Ваши устройства зарегистрированы в Intune и настроены с соответствующими политиками.

|||
|:-------|:-----|
|![Этап 6. Защита данных](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| Если вы подписаны на стадии комплексного развертывания Microsoft 365 Enterprise, следующий этап — [Защита информации](infoprotect-infrastructure.md). |
