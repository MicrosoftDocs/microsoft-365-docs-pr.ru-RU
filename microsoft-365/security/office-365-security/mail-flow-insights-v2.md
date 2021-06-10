---
title: Сведения о потоке почты в панели мониторинга потока почты
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Администраторы могут ознакомиться с сведениями и отчетами, доступными на панели мониторинга потока почты в Центре & соответствия требованиям.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 39f7b43db62fd19f7500972a3016fdd8dd0875b6
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206288"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>Аналитика потока обработки почты в Центре безопасности и соответствия требованиям

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Администраторы могут использовать панель мониторинга потока почты в Центре & безопасности для обнаружения тенденций, анализов и действий по устранению проблем, связанных с потоком почты в организации.

![Панель мониторинга потока почты в центре & безопасности](../../media/mail-flow-dashboard-v2.png)

Доступные сведения:

- [Анализ автоматически пересылаемых сообщений](mfi-auto-forwarded-messages-report.md)

- [Исправление возможной проницательности цикла почты](mfi-mail-loop-insight.md)<sup>1</sup>

- [Исправление анализа правил медленного потока почты](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>

- [Схема потока обработки почты](mfi-mail-flow-map-report.md)

- [Новые домены, отправленные по электронной почте insight](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [Новые пользователи, переадлив данные электронной почты](mfi-new-users-forwarding-email.md)<sup>2</sup>

- [Отчет о необслуживаемом домене](mfi-non-accepted-domain-report.md)

- [Отчет о недоставке](mfi-non-delivery-report.md)

- [Анализ потока обработки исходящей и входящей почты](mfi-outbound-and-inbound-mail-flow.md)

- [Анализ очередей](mfi-queue-alerts-and-queues.md)

- [Анализ и отчет о клиентах SMTP-AUTH](mfi-smtp-auth-clients-report.md)

- [Анализ состояния для потока обработки почты верхнего домена](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> Это представление отображается в **рекомендуемой** для вас области панели мониторинга потока почты только после обнаружения проблемы. В противном случае вы не увидите его.

<sup>2</sup> Это представление не отображается на панели мониторинга потока почты, но отображается на странице отчета о переадпорте после обнаружения проблемы. [](view-mail-flow-reports.md#forwarding-report) В противном случае вы не увидите его.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>Разрешения, необходимые для просмотра панели мониторинга потока почты

Панель мониторинга потока почты доступна участникам следующих групп ролей:

- **Управление организацией** в Центре & безопасности (глобальные администраторы).

- **[Exchange администратор](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** в Azure Active Directory.

- **Администратор почтового потока** в центре & безопасности. Если учетная запись также не входит в группы ролей Exchange или администратора, рассмотрите следующие проблемы:
  - Пользователь должен войти в Центр & безопасности непосредственно в <https://protection.office.com> .
  - У пользователя будет только разрешение только для чтения на панели мониторинга потока почты.
  - У пользователя не будет доступа к центру администрирования Microsoft 365 администратора.

Дополнительные сведения о разрешениях см. в & Центра & безопасности и предоставить пользователям доступ к Центру & [безопасности.](grant-access-to-the-security-and-compliance-center.md) [](permissions-in-the-security-and-compliance-center.md)

## <a name="where-to-find-the-mail-flow-dashboard"></a>Где найти панель мониторинга потока почты

Откройте центр обеспечения & безопасности в центре, развяви поток почты <https://protection.office.com> и выберите панель **мониторинга.** 

Чтобы перейти непосредственно к панели мониторинга потока почты, откройте <https://protection.office.com/mailflow/dashboard> .