---
title: Сравнение различных методов защиты данных устройств и приложений
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Выберите один из двух методов MDM и MAM.
ms.openlocfilehash: 6231b7c82f280a60ae9d30bcf27697dc131b2471
ms.sourcegitcommit: 5a355bde865369f64ea1788a378da23c65b1d249
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2020
ms.locfileid: "48930282"
---
# <a name="options-for-protecting-your-devices-and-app-data"></a>Варианты защиты устройств и данных приложений

Существует несколько способов защиты устройств и данных Организации от Microsoft 365 для бизнеса и предприятия. Вы можете использовать следующие автономные планы:

- Intune (часть управления конечными точками Майкрософт)
- Расширенные планы Azure Active Directory.
- Basic Mobility and Security (входит в большинство планов Microsoft 365 для бизнеса и предприятий) или используют подписки, включающие в себя некоторые или все предыдущие автономные планы.

- Подписка на Microsoft 365 Business Premium, которая включает безопасность и защиту от угроз для малого бизнеса в 300 пользователей.
- Microsoft 365 корпоративный план, включающий повышенную безопасность и защиту от угроз.

## <a name="device-management-options"></a>Параметры управления устройствами

![Рисунок, на котором показано, какие подписки должны использовать методы MDM и MAM.](../../m365-mam-mdm.png)

- **Базовая мобильность и безопасность** предлагается для большинства планов Microsoft 365 и является единственным встроенным вариантом, предлагаемым для Microsoft 365 бизнес Standard и Microsoft 365 бизнес базовый. Для получения дополнительных сведений ознакомьтесь с разрешениями [базовых возможностей мобильной работы и безопасности](../basic-mobility-security/choose-between-basic-mobility-and-security-and-intune.md#availability-of-basic-mobility-and-security-and-intune). 

    Если у вас есть Microsoft 365 Business Basic или Microsoft 365 Business Standard, вы также можете приобрести Intune, если у вашей организации есть более сложные требования к безопасности.
 
- **Microsoft Intune** — это автономный план, который также входит в состав некоторых планов Microsoft 365 для бизнеса или предприятий. Если у вас есть Intune как самостоятельная или как часть подписки, она предоставляет возможность точной настройки устройства и управления приложениями. Для получения дополнительных сведений о доступности с помощью Microsoft 365, ознакомьтесь со статьей [доступность Intune](../basic-mobility-security/choose-between-basic-mobility-and-security-and-intune.md#availability-of-basic-mobility-and-security-and-intune).

    Microsoft Intune — это облачная служба, которая специализируется на управлении мобильными устройствами (MDM) и управлении мобильными приложениями (MAM). Вы управляете использованием устройств организации, в том числе мобильных телефонов, планшетов и ноутбуков. Вы также можете настроить конкретные политики для управления приложениями. Для получения дополнительных сведений обратитесь [к документации по Microsoft Intune](https://docs.microsoft.com/mem/intune/).

- Планы по **расширению Azure Active Directory (AD)** — это автономные планы, которые также входят в состав некоторых планов Microsoft 365 для бизнеса и предприятий. Для получения дополнительных сведений обратитесь к разделу [цены Azure AD](https://azure.microsoft.com/pricing/details/active-directory/).

     Azure AD Premium P1 и Azure AD Premium P2 позволяют настраивать функции условного доступа, самостоятельного сброса пароля и т. д. Для получения дополнительных сведений о возможностях планов Premium посетите страницу [ценообразования Azure AD](https://azure.microsoft.com/pricing/details/active-directory/) .
- **Microsoft 365 бизнес премиум** включает Intune и Azure Active Directory Premium P1 и Office 365 Advanced Threat protection. 
 
    Microsoft 365 Business Premium предлагает набор шаблонов политик для защиты устройств и данных приложений. Он обеспечивает хороший уровень безопасности и защиты от угроз для большинства предприятий под 300 пользователей. Дополнительные сведения: [Настройка Microsoft 365 бизнес премиум в мастере установки](../../business/set-up.md), [безопасность компьютеров с Windows 10](../../business/secure-win-10-pcs.md)и [функции безопасности и соответствия требованиям Microsoft 365 Business Premium](../../business/security-features.md).

- **Microsoft 365 для корпоративных** подписок включает Microsoft Intune и, Кроме того, включает планы Azure AD Premium 1 и 2.

    Microsoft 365 в ~ обеспечивает наивысший уровень безопасности и защиты от угроз для всех подписок Microsoft 365. Более подробную информацию можно найти в [статье Microsoft 365 for Enterprise Overview](../../enterprise/microsoft-365-overview.md).
