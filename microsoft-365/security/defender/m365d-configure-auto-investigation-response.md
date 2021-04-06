---
title: Настройка возможностей автоматического расследования и ответа в Microsoft 365 Defender
description: Настройка автоматического исследования и ответа с помощью самовосстановления в Microsoft 365 Defender
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.technology: m365d
ms.openlocfilehash: 164d4f52f5769d48249c1f4afcdf4be624f6aef7
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592052"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Настройка возможностей автоматического расследования и ответа в Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 365 Defender [](m365d-autoir.md) включает в себя мощные возможности автоматического расследования и реагирования, которые могут сэкономить много времени и усилий вашей группы операций безопасности. С [помощью самовосстановления](m365d-autoir.md#how-automated-investigation-and-self-healing-works)эти возможности имитируют действия аналитика безопасности для расследования и реагирования на угрозы, только быстрее и с большей возможностью масштабирования. В этой статье описывается настройка автоматического расследования и ответа в Microsoft 365 Defender.

Чтобы настроить возможности автоматического расследования и ответа, выполните следующие действия:

1. [Просмотрите необходимые условия.](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
2. [Просмотрите или измените уровень автоматизации для групп устройств.](#review-or-change-the-automation-level-for-device-groups)
3. [Просмотрите политики безопасности и оповещения в Office 365.](#review-your-security-and-alert-policies-in-office-365)
4. [Убедитесь, что microsoft 365 Defender включен.](#make-sure-microsoft-365-defender-is-turned-on)

Затем, после всех действий, просмотр и управление действиями [в центре действий.](m365d-autoir-actions.md)

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Необходимые условия для автоматического расследования и ответа в Microsoft 365 Defender

|Требования |Сведения |
|:----|:----|
|Требования к подписке: |Одна из этих подписок: <br/>- Microsoft 365 E5<br/>- Microsoft 365 A5<br/>- Безопасность Microsoft 365 E5<br/>- Безопасность Microsoft 365 A5<br/>- Office 365 E5 плюс корпоративная мобильность + безопасность E5 плюс Windows E5<p> См. требования к лицензированию [Microsoft 365 Defender.](./prerequisites.md#licensing-requirements)|
|Сетевые требования |- [Microsoft Defender for Identity включен](/azure-advanced-threat-protection/what-is-atp)<br/>- [Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security) configured<br/>- [Microsoft Defender для интеграции удостоверений](/cloud-app-security/mdi-integration) |
|Требования к компьютеру Windows: |-Windows 10 версии 1709 или более поздней (см. статью [Сведения о выпуске Windows 10](/windows/release-information/)) <br/>- Настроены следующие службы защиты от угроз:<br/>- [Microsoft Defender для конечной точки](../defender-endpoint/configure-endpoints.md)<br/>- [Антивирус Microsoft Defender](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Защита контента электронной почты и файлов Office |[Microsoft Defender для Office 365](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) настроен |
|Разрешения | Чтобы настроить возможности автоматического расследования и реагирования, необходимо, чтобы роль глобального администратора или администратора безопасности была назначена в Azure Active Directory () или в центре администрирования [https://portal.azure.com](https://portal.azure.com) Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ).<p>Чтобы получить разрешения, необходимые для работы с автоматизированными возможностями расследования и реагирования, такими как проверка, одобрение или отклонение ожидающих действий, см. в документе [Required permissions for Action Center tasks.](m365d-action-center.md#required-permissions-for-action-center-tasks) |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Обзор или изменение уровня автоматизации для групп устройств

Независимо от того, запускаются ли автоматические расследования и принимаются ли действия по исправлению автоматически или только после утверждения для устройств, зависят от определенных параметров, например политик группы устройств организации. Просмотрите уровень автоматизации, установленный для политик групп устройств.

1. Перейдите в Центр безопасности защитника Майкрософт [https://securitycenter.windows.com](https://securitycenter.windows.com) () и войдите.
2. Перейдите **к группам устройств**  >  **"Параметры**  >  **разрешений".**
3. Просмотрите политики группы устройств. В частности, посмотрите на **столбец уровня исправлений.** Рекомендуется автоматически **использовать угрозы полного устранения.**  Возможно, потребуется создать или изменить группы устройств, чтобы получить необходимый уровень автоматизации. Чтобы получить помощь в этой задаче, см. в следующих статьях:
   - [Устранение угроз](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [Создание групп устройств и управление ими](/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Просмотрите политики безопасности и оповещения в Office 365

Корпорация Майкрософт предоставляет встроенные [политики оповещения,](../../compliance/alert-policies.md) которые помогают выявлять определенные риски. К этим рискам относятся злоупотребление разрешениями администратора Exchange, активность вредоносных программ, потенциальные внешние и внутренние угрозы, а также риски управления информацией. Некоторые оповещения могут вызвать автоматическое расследование и [ответ в Office 365](../office-365-security/office-365-air.md). Убедитесь, [что функции Microsoft Defender для Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) настроены правильно.

Хотя определенные оповещения и политики безопасности могут вызывать автоматические расследования, для электронной почты и контента не принимаются автоматические действия по исправлению. Вместо этого все действия по исправлению содержимого электронной почты и электронной почты ожидают утверждения вашей командой операций безопасности в [Центре действий.](m365d-action-center.md)

Параметры безопасности в Office 365 помогают защитить электронную почту и содержимое. Чтобы просмотреть или изменить эти параметры, следуйте указаниям в ["Защита от угроз".](../office-365-security/protect-against-threats.md)

1. В центре безопасности Microsoft 365 [https://security.microsoft.com](https://security.microsoft.com) (), перейдите к **политике защиты**  >  **от угрозы**.
2. Убедитесь, что все следующие политики настроены. Чтобы получить помощь и рекомендации, см. в [справке "Защита от угроз".](/microsoft-365/security/office-365-security/protect-against-threats)
   - [Anti-malware (Office 365)](../office-365-security/protect-against-threats.md#part-1---anti-malware-protection)
   - [Защита от фишинга в Defender для Office 365)](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection)
   - [Безопасные вложения (Office 365)](../office-365-security/protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)
   - [Безопасные ссылки (Office 365)](../office-365-security/protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)
   - [Противодействие нежелательной почте (Office 365)](../office-365-security/protect-against-threats.md#part-3---anti-spam-protection)
3. [Убедитесь, что Microsoft Defender для Office 365 для SharePoint, OneDrive и Microsoft Teams](../office-365-security/protect-against-threats.md#part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on) включена.
4. [Убедитесь, что автоматическая очистка без](../office-365-security/protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop) часов для защиты электронной почты действует.
5. (Этот шаг необязателен.) Просмотрите [политики оповещений Office 365](../../compliance/alert-policies.md) в центре соответствия требованиям Microsoft 365 [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) (). Несколько политик оповещений по умолчанию находятся в категории управление угрозами. Некоторые из этих оповещений могут вызвать автоматическое расследование и ответ. Дополнительные дополнительные новости см. в [дополнительных правилах оповещения по умолчанию.](../../compliance/alert-policies.md#default-alert-policies)

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Убедитесь, что microsoft 365 Defender включен

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP на":::

1. Перейдите в центр безопасности Microsoft 365 () и [https://security.microsoft.com](https://security.microsoft.com) войдите.
2. В области навигации посмотрите **на** **происшествия,** центр действий и охоту, как показано на предыдущем изображении.
   - Если вы видите **происшествия,** **центр действий** и **охоту,** microsoft 365 Defender включен. См. процедуру, [обзор или изменение уровня автоматизации для групп устройств](#review-or-change-the-automation-level-for-device-groups) (в этой статье).
   - Если вы не *видите* **инциденты,** центр действий или охоту, то Microsoft 365 Defender может не быть включена.  В этом случае переехав [в Центр действий.](m365d-action-center.md)
3. В области навигации выберите **Параметры**  >  **Microsoft 365 Defender**. Подтверди, что microsoft 365 Defender включен. 

> [!TIP]
> Нужна помощь? [Включив Microsoft 365 Defender.](m365d-enable.md)

## <a name="next-steps"></a>Дальнейшие действия

- [Действия по исправлению в Microsoft 365 Defender](m365d-remediation-actions.md)
- [Посещение Центра уведомлений](m365d-action-center.md)
