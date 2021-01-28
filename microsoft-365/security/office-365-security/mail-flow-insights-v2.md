---
title: Анализ потока почты на панели мониторинга потока почты
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Администраторы могут ознакомиться с данными и отчетами, доступными на панели мониторинга потока обработки почты в Центре безопасности & соответствия требованиям.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ef9498d19e79cf670fbae52171b78b0c44c45910
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029366"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>Аналитика потока обработки почты в Центре безопасности и соответствия требованиям

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Администраторы могут использовать панель мониторинга потока обработки почты в Центре безопасности & соответствия требованиям для обнаружения тенденций, анализа и действий по устранению проблем, связанных с потоком обработки почты в организации.

![Панель мониторинга потока обработки почты в Центре & соответствия требованиям](../../media/mail-flow-dashboard-v2.png)

Доступные сведения:

- [Анализ автоматически пересылаемых сообщений](mfi-auto-forwarded-messages-report.md)

- [Исправлена возможная информация о почтовом цикле](mfi-mail-loop-insight.md)<sup>1</sup>

- [Исправлена информация о медленных правилах потока почты](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>

- [Схема потока обработки почты](mfi-mail-flow-map-report.md)

- [Новые домены, переададантуемые по электронной почте insight](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [Новые пользователи, переадлицющие данные электронной почты 2](mfi-new-users-forwarding-email.md)<sup></sup>

- [Отчет о необслуживаемом домене](mfi-non-accepted-domain-report.md)

- [Отчет о недоставке](mfi-non-delivery-report.md)

- [Анализ потока обработки исходящей и входящей почты](mfi-outbound-and-inbound-mail-flow.md)

- [Анализ очередей](mfi-queue-alerts-and-queues.md)

- [Анализ и отчет о клиентах SMTP-AUTH](mfi-smtp-auth-clients-report.md)

- [Анализ состояния для потока обработки почты верхнего домена](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> Эта информация отображается в области "Рекомендуемые для **вас"** панели мониторинга потока почты только после обнаружения проблемы. В противном случае вы не увидите его.

<sup>2</sup> Эта информация не отображается на панели мониторинга потока почты, но отображается на странице отчета "Пересылание" после обнаружения проблемы. [](view-mail-flow-reports.md#forwarding-report) В противном случае вы не увидите его.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>Разрешения, необходимые для просмотра панели мониторинга потока почты

Панель мониторинга потока почты доступна участникам следующих групп ролей:

- **Управление организацией** в Центре & соответствия требованиям (глобальные администраторы).

- **[Администратор Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** в Azure Active Directory.

- **Администратор потока обработки почты** в Центре & соответствия требованиям. Если учетная запись также не входит в группы ролей "Управление организацией" или "Администратор Exchange", рассмотрите следующие проблемы:
  - Пользователь должен войти в Центр безопасности & соответствия требованиям непосредственно в <https://protection.office.com> .
  - Пользователь будет иметь разрешение только на чтение панели мониторинга потока почты.
  - У пользователя не будет доступа к Центру администрирования Microsoft 365.

Дополнительные сведения о разрешениях см. в & "Разрешения" и "Предоставить пользователям доступ к Центру безопасности [& соответствия требованиям".](grant-access-to-the-security-and-compliance-center.md) [](permissions-in-the-security-and-compliance-center.md)

## <a name="where-to-find-the-mail-flow-dashboard"></a>Где найти панель мониторинга потока почты

Откройте Центр безопасности & соответствия требованиям на странице , разкрой поток обработки почты <https://protection.office.com> и выберите "Информационная **панель".** 

Чтобы перейти непосредственно на панель мониторинга потока почты, откройте <https://protection.office.com/mailflow/dashboard> .
