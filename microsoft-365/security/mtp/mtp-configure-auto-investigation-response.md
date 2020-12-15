---
title: Настройка возможностей автоматического исследования и реагирования в Microsoft 365 Defender
description: Настройка автоматического исследования и реагирования с помощью самостоятельного восстановления в Microsoft 365 Defender
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.openlocfilehash: 12f71011e28d5c8c8287146670282a86a77781ff
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682985"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Настройка возможностей автоматического исследования и реагирования в Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft 365 Defender [](mtp-autoir.md) включает мощные автоматизированные средства исследования и реагирования на них, которые могут сэкономить много времени и усилий для вашей группы по обеспечению безопасности. Благодаря средствам самостоятельного восстановления эти возможности имитируют действия, которые аналитик безопасности должен предпринять для изучения угроз и реагирования на них, только быстрее и с большей возможностью масштабирования. В этой статье описывается настройка автоматического исследования и реагирования в Microsoft 365 Defender.

Чтобы настроить возможности автоматического исследования и реагирования на них, выполните следующие действия.

1. [Просмотрите необходимые условия.](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
2. [Просмотрите или измените уровень автоматизации для групп устройств.](#review-or-change-the-automation-level-for-device-groups)
3. [Просмотрите политики безопасности и оповещений в Office 365.](#review-your-security-and-alert-policies-in-office-365)
4. [Убедитесь, что Защитник Microsoft 365 включен.](#make-sure-microsoft-365-defender-is-turned-on)

Затем после завершения всех действий просмотрите ожидающих и завершенных [действий в центре действий.](#review-pending-and-completed-actions-in-the-action-center) 


## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Необходимые условия для автоматического исследования и реагирования в Microsoft 365 Defender

|Требования |Сведения |
|--|--|
|Требования к подписке: |Одна из подписок: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 A5 <br/>- Безопасность Microsoft 365 E5<br/>- Безопасность Microsoft 365 A5<br/>- Office 365 E5 плюс Enterprise Mobility + Security E5 плюс Windows E5<br/><br/>См. [требования к лицензированию Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements)|
|Требования к сети: |- [Microsoft Defender для удостоверений](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) включен<br/>- [Настройка Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)<br/>- [Microsoft Cloud App Security, интегрированный с Microsoft Defender для удостоверений](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Требования к компьютеру Windows: |- Windows 10 версии 1709 или более поздней (см. сведения о выпуске [Windows 10)](https://docs.microsoft.com/windows/release-information/)со следующими настроенными службами защиты от угроз:<br/>- [Microsoft Defender для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Антивирусная программа "Microsoft Defender"](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Защита содержимого электронной почты и файлов Office |[Настроен Microsoft Defender для Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
|Разрешения |- Чтобы настроить возможности автоматического исследования и реагирования, вам должна быть назначена роль глобального администратора или администратора безопасности в Azure Active Directory ( ) или в Центре администрирования [https://portal.azure.com](https://portal.azure.com) Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ).<br/><br/>- Чтобы получить разрешения, необходимые для работы с автоматизированными возможностями исследования и реагирования, такими как проверка, одобрение или отклонение ожидающих действий, см. необходимые разрешения для задач Центра [действий.](mtp-action-center.md#required-permissions-for-action-center-tasks) |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Просмотр или изменение уровня автоматизации для групп устройств

Запуск автоматических расследований и автоматическое или только после утверждения для устройств зависит от определенных параметров, таких как групповые политики устройств в организации. Просмотрите набор уровней автоматизации для групповых политик устройств.

1. Перейдите в Центр безопасности Microsoft Defender [https://securitycenter.windows.com](https://securitycenter.windows.com) () и войдите.

2. Перейдите **в группы устройств**  >  **"Разрешения**  >  **параметров".** 

3. Просмотрите групповые политики устройств. В частности, посмотрите на **столбец уровня исправлений.** Мы рекомендуем использовать **полное устранение угроз автоматически.**  Вам может потребоваться создать или изменить группы устройств, чтобы получить нужный уровень автоматизации. Чтобы получить помощь по этой задаче, см. следующие статьи:

   - [Как устраняются угрозы](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [Создание групп устройств и управление ими](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/machine-groups) 

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Проверка политик безопасности и оповещений в Office 365

Корпорация Майкрософт предоставляет встроенные политики [оповещений,](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) которые помогают определить определенные риски. К этим рискам относятся злоупотребление разрешениями администратора Exchange, вредоносные программы, потенциальные внешние и внутренние угрозы, а также риски управления информацией. Некоторые оповещения могут инициирует автоматическое исследование и реагирование [в Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) Убедитесь, [что функции Microsoft Defender для Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) настроены правильно.

Несмотря на то что определенные оповещения и политики безопасности могут запускать автоматические расследования, для электронной почты и содержимого не принимаются автоматические действия по исправлению. Вместо этого все действия по исправлению содержимого электронной почты и электронной почты ожидают утверждения вашей командой операций безопасности в [Центре действий.](mtp-action-center.md)

Параметры безопасности в Office 365 помогают защитить электронную почту и содержимое. Чтобы просмотреть или изменить эти параметры, следуйте указаниям в области ["Защита от угроз".](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)

1. В Центре безопасности Microsoft 365 () перейдите в службу [https://security.microsoft.com/](https://security.microsoft.com/) Защиты от угроз   >  **политик.**

2. Убедитесь, что настроены все следующие политики. Чтобы получить помощь и рекомендации, см. ["Защита от угроз".](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)

   - [Антивредоносная программа (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-1---anti-malware-protection)
   - [Защита от фишинга в Защитнике Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
   - [Безопасные вложения (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-attachments-policies)
   - [Безопасные ссылки (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-links-policies)
   - [Anti-spam (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection) 

4. Убедитесь, что Включен Microsoft Defender для [Office 365 для SharePoint, OneDrive](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) и Microsoft Teams.

5. Убедитесь, что действует автоматическая [очистка электронной](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop) почты. 

8. (Необязательный.) Просмотрите политики оповещений [Office 365](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) в Центре соответствия требованиям Microsoft 365 ( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). Несколько политик оповещений по умолчанию находятся в категории управления угрозами. Некоторые из этих оповещений могут инициирует автоматическое исследование и реагирование на них. Дополнительные узнать см. в [политиках оповещений по умолчанию.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?#default-alert-policies)
 
## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Убедитесь, что Защитник Microsoft 365 включен

1. Перейдите в Центр безопасности Microsoft 365 [https://security.microsoft.com](https://security.microsoft.com) () и войдите.

2. В области навигации наймите "Происшествия", "Центр действий" и "Охота", как показано на следующем рисунке: 

   :::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP on":::

   - Если вы видите **"Инциденты",** **"Центр действий"** и **"Охота",** Защитник Microsoft 365 включен. См. процедуру, [обзор или изменение уровня автоматизации для групп устройств](#review-or-change-the-automation-level-for-device-groups) (в этой статье).

   - Если вы не видите *инциденты,* центр действий **или** **охоту,** Возможно, Защитник Microsoft 365 не включен. В этом случае переходите к следующему шагу ( просмотрите ожидающих и завершенных[действий](#review-pending-and-completed-actions-in-the-action-center), в этой статье).

3. В области навигации выберите **"Параметры"**  >  **в Microsoft 365 Defender.** Подтвердим, что Защитник Microsoft 365 включен. 

   Нужна помощь? См. ["Включить Microsoft 365 Defender".](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)

## <a name="review-pending-and-completed-actions-in-the-action-center"></a>Просмотр ожидающих и завершенных действий в центре действий

После настройки автоматического исследования и реагирования в Microsoft 365 Defender необходимо посетить Центр действий ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ). Здесь можно просмотреть и утвердить ожидающих действий и просмотреть действия по исправлению, которые были предприняты автоматически или вручную. 

[Посетите центр действий.](mtp-action-center.md)
