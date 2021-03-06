---
title: Настройка возможностей автоматического расследования и ответа в Microsoft 365 Defender
description: Настройка автоматического исследования и ответа с помощью самовосстановления в Microsoft 365 Defender
search.appverid: MET150
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 4275339e048a4197590c91c5904733ce99b22f9f
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083444"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Настройка возможностей автоматического расследования и ответа в Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 365 Defender включает в себя мощные [возможности](m365d-autoir.md) автоматического расследования и реагирования, которые могут сэкономить много времени и усилий вашей группы операций безопасности. С [помощью самовосстановления](m365d-autoir.md#how-automated-investigation-and-self-healing-works)эти возможности имитируют действия аналитика безопасности для расследования и реагирования на угрозы, только быстрее и с большей возможностью масштабирования.

В этой статье описывается настройка автоматического расследования и ответа в Microsoft 365 Defender с помощью этих действий:

1. [Просмотрите необходимые условия.](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
2. [Просмотрите или измените уровень автоматизации для групп устройств.](#review-or-change-the-automation-level-for-device-groups)
3. [Просмотрите политики безопасности и оповещения](#review-your-security-and-alert-policies-in-office-365)в Office 365.
4. [Убедитесь, Microsoft 365 Defender включен.](#make-sure-microsoft-365-defender-is-turned-on)

Затем после всех действий можно просматривать и управлять действиями по исправлению в [центре действий.](m365d-autoir-actions.md)

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Необходимые условия для автоматического расследования и ответа в Microsoft 365 Defender

<br>

****

|Требование|Сведения|
|---|---|
|Требования к подписке:|Одна из этих подписок: <ul><li>Microsoft 365 E5</li><li>Microsoft 365 A5</li><li>Microsoft 365 E3 с Безопасность Microsoft 365 E5 надстройки</li><li>Microsoft 365 A3 надстройка Microsoft 365 A5 безопасности</li><li>Office 365 E5 плюс Enterprise Mobility + Security E5 плюс Windows E5</li></ul> <p> См. [Microsoft 365 Defender требования к лицензированию.](./prerequisites.md#licensing-requirements)|
|Требования к сети|<ul><li>[Microsoft Defender for Identity включен](/azure-advanced-threat-protection/what-is-atp)</li><li>[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security) настроены</li><li>[Microsoft Defender для интеграции удостоверений](/cloud-app-security/mdi-integration)</li></ul>|
|Требования к компьютеру Windows:|<ul><li>Windows 10 версии 1709 или более поздней версии (см. Windows 10 [сведения о выпуске)](/windows/release-information/)</li><li>Настроены следующие службы защиты от угроз:<ul><li>[Microsoft Defender для конечной точки](../defender-endpoint/configure-endpoints.md)</li><li>[Антивирусная программа в Microsoft Defender](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</li></ul></li></ul>|
|Защита контента электронной почты и Office файлов|[Microsoft Defender для Office 365](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) настроен|
|Разрешения|Чтобы настроить возможности автоматического расследования и ответа, необходимо, чтобы роль глобального администратора или администратора безопасности была назначена в Azure Active Directory () или <https://portal.azure.com> в Центр администрирования Microsoft 365 ( <https://admin.microsoft.com> ). <p> Чтобы получить разрешения, необходимые для работы с автоматизированными возможностями расследования и реагирования, такими как проверка, одобрение или отклонение ожидающих действий, см. в документе [Required permissions for Action Center tasks.](m365d-action-center.md#required-permissions-for-action-center-tasks)|
|

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Обзор или изменение уровня автоматизации для групп устройств

Независимо от того, запускаются ли автоматические расследования и принимаются ли действия по исправлению автоматически или только после утверждения для устройств, зависят от определенных параметров, например политик группы устройств организации. Просмотрите настроенный уровень автоматизации для политик групп устройств.

1. Перейдите в Центр безопасности в Microsoft Defender [https://securitycenter.windows.com](https://securitycenter.windows.com) () и войдите.

2. Перейдите **Параметры**  >  **группы устройств**  >  **разрешений.**

3. Просмотрите политики группы устройств. В частности, посмотрите на **столбец уровня исправлений.** Рекомендуется автоматически **использовать угрозы полного устранения.**  Возможно, потребуется создать или изменить группы устройств, чтобы получить необходимый уровень автоматизации. Чтобы получить помощь в этой задаче, см. в следующих статьях:
   - [Устранение угроз](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [Создание групп устройств и управление ими](/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Просмотрите политики безопасности и оповещения в Office 365

Корпорация Майкрософт предоставляет встроенные [политики оповещения,](../../compliance/alert-policies.md) которые помогают выявлять определенные риски. К этим рискам относятся Exchange разрешений администратора, активность вредоносных программ, потенциальные внешние и внутренние угрозы, а также риски управления информацией. Некоторые оповещения могут вызвать [автоматическое расследование](../office-365-security/office-365-air.md)и ответ в Office 365 . Убедитесь, что [функции Defender для Office 365](../office-365-security/defender-for-office-365.md) настроены правильно.

Хотя определенные оповещения и политики безопасности могут вызывать автоматические расследования, для электронной почты и контента не принимаются автоматические действия по *исправлению.* Вместо этого все действия по исправлению содержимого электронной почты и электронной почты ожидают утверждения вашей командой операций безопасности в [Центре действий.](m365d-action-center.md)

Параметры безопасности в Office 365 помогают защитить электронную почту и содержимое. Чтобы просмотреть или изменить эти параметры, следуйте указаниям в ["Защита от угроз".](../office-365-security/protect-against-threats.md)

1. На портале Microsoft 365 Defender <https://security.microsoft.com> () перейдите к **политикам & политики** \> **угрозы** правил .

2. Убедитесь, что все следующие политики настроены. Чтобы получить помощь и рекомендации, см. в [справке "Защита от угроз".](/microsoft-365/security/office-365-security/protect-against-threats)
   - [Anti-malware](../office-365-security/protect-against-threats.md#part-1---anti-malware-protection-in-eop)
   - [Anti-phishing](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)
   - [Безопасные вложения](../office-365-security/protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)
   - [Безопасные ссылки](../office-365-security/protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)
   - [Противодействие нежелательной почте](../office-365-security/protect-against-threats.md#part-3---anti-spam-protection-in-eop)

3. Убедитесь, Сейф вложения [для SharePoint, OneDrive и](../office-365-security/mdo-for-spo-odb-and-teams.md) Microsoft Teams включен.

4. Убедитесь, что автоматическая очистка нулевого часа [(ZAP)](../office-365-security/zero-hour-auto-purge.md) в Exchange Online действует.

5. (Этот шаг необязателен.) Просмотрите [Office 365 политики](../../compliance/alert-policies.md) оповещения в Центр соответствия требованиям Microsoft 365 ( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). Несколько политик оповещений по умолчанию находятся в категории управление угрозами. Некоторые из этих оповещений могут вызвать автоматическое расследование и ответ. Дополнительные дополнительные новости см. в [дополнительных правилах оповещения по умолчанию.](../../compliance/alert-policies.md#default-alert-policies)

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Убедитесь, Microsoft 365 Defender включен

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP на":::

1. Вход на портал Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ).

2. В области навигации посмотрите на & оповещений,  центра охоты и действий, как показано на предыдущем изображении. 
   - Если вы **видите, & оповещения,** **охота** и центр действий, Microsoft 365 Defender включена. См. [раздел Обзор или изменение уровня автоматизации для групп](#review-or-change-the-automation-level-for-device-groups) устройств в этой статье.
   - Если вы не *видите* **инциденты,** центр действий или **охоту,** Microsoft 365 Defender не может быть включена. В этом случае посетите [центр действий).](m365d-action-center.md)

3. В области навигации **выберите** Параметры  >  **Microsoft 365 Defender**. Подтверди, Microsoft 365 Defender включена.

> [!TIP]
> Нужна помощь? См. [в Microsoft 365 Defender.](m365d-enable.md)

## <a name="next-steps"></a>Дальнейшие действия

- [Действия по исправлению Microsoft 365 Defender](m365d-remediation-actions.md)
- [Посещение Центра уведомлений](m365d-action-center.md)
