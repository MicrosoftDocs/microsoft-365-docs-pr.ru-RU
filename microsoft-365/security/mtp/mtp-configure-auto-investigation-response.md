---
title: Настройка функций автоматического исследования и реагирования в защитнике Microsoft 365
description: Настройка автоматического исследования и реагирования с самостоятельной восстановлением в защитнике Microsoft 365
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
ms.openlocfilehash: 5ba17c414b6f6470d2e9af14d1f484b435cb4f51
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846500"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Настройка функций автоматического исследования и реагирования в защитнике Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Защитник Microsoft 365 включает мощные [функции автоматического исследования и реагирования](mtp-autoir.md) , которые могут значительно сэкономить время и усилия группы управления. С самовосстановлением эти возможности имитируют действия, которые аналитика Безопасности предпримет для исследования и реагирования на угрозы, только быстрее и с большим количеством возможностей масштабирования. В этой статье описывается настройка автоматического исследования и реагирования в защитнике Microsoft 365.

Чтобы настроить функции автоматического исследования и реагирования, выполните следующие действия:

1. [Проверьте предварительные требования](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).
2. [Просмотрите или измените уровень автоматизации для групп устройств](#review-or-change-the-automation-level-for-device-groups).
3. [Ознакомьтесь со своими политиками безопасности и оповещениями в Office 365](#review-your-security-and-alert-policies-in-office-365).
4. [Убедитесь, что включен Защитник Microsoft 365](#make-sure-microsoft-365-defender-is-turned-on).

После завершения настройки [Просмотрите ожидающие и завершенные действия в центре уведомлений](#review-pending-and-completed-actions-in-the-action-center). 


## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Необходимые условия для автоматического исследования и ответа в защитнике Microsoft 365

|Требования |Сведения |
|--|--|
|Требования к подписке: |Одна из подписок: <br/>— Microsoft 365 <br/>— Microsoft 365 A5 <br/>— Microsoft 365, безопасность<br/>— Безопасность Microsoft 365 A5<br/>— Office 365 в ~ и Enterprise Mobility + Security/безопасность а, Windows ~<br/><br/>Ознакомьтесь с [требованиями к лицензированию защитника Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements).|
|Требования к сети: |- [Защитник Майкрософт для удостоверения](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) включен<br/>- Настроенная [система безопасности облачного приложения Майкрософт](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)<br/>- [Microsoft Cloud App Security, интегрированное с защитником Майкрософт для удостоверения](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Требования к компьютеру Windows: |-Windows 10 версии 1709 или более поздней (ознакомьтесь со [сведениями о выпуске Windows 10](https://docs.microsoft.com/windows/release-information/)) со следующими настройками служб защиты от угроз:<br/>- [Защитник Майкрософт для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Антивирусная программа "защитник Майкрософт"](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Защита содержимого электронной почты и файлов Office |Настроенный [защитник Майкрософт для Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
|Разрешения |-Для настройки функций автоматического исследования и реагирования необходимо, чтобы роль глобального администратора или администратора безопасности была назначена в Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) или в центре администрирования Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ).<br/><br/>— Чтобы получить разрешения, необходимые для работы с автоматизированными функциями расследования и ответа, такими как просмотр, утверждение или отклонение ожидающих действий, ознакомьтесь с [разрешениями, необходимыми для задач центра уведомлений](mtp-action-center.md#required-permissions-for-action-center-tasks). |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Просмотр или изменение уровня автоматизации для групп устройств

Будет ли выполняться автоматическое расследование, а также будут ли действия по исправлению выполняться автоматически или только при утверждении для ваших устройств, зависят от определенных параметров, таких как политики групп устройств Организации. Просмотрите набор уровней автоматизации для групповых политик устройств.

1. Перейдите в центр безопасности защитника (Майкрософт [https://securitycenter.windows.com](https://securitycenter.windows.com) ) и войдите в него.

2. Перейдите в раздел **Параметры**  >  **разрешений** для  >  **групп устройств**. 

3. Проверьте политики групп устройств. В частности, просмотрите столбец **уровень исправления** . Рекомендуется автоматически использовать **полноценные угрозы**.  Для получения необходимого уровня автоматизации может потребоваться создать или изменить группы устройств. Чтобы получить помощь по этой задаче, ознакомьтесь со следующими статьями:

   - [Способы исправления угроз](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   
   - [Создание групп устройств и управление ими](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/machine-groups) 

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Обзор политик безопасности и оповещений в Office 365

Корпорация Майкрософт предоставляет встроенные [политики оповещений](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) , помогающие определить некоторые риски. К таким рискам относятся разрешения администратора Exchange, опасные действия, потенциальные внешние и внутренние угрозы, а также риски управления сведениями. Некоторые оповещения могут инициировать [Автоматическое исследование и отклик в Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air). Убедитесь, что [защитник Майкрософт для компонентов Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) настроен правильно.

Хотя определенные оповещения и политики безопасности могут инициировать автоматическое расследование, никакие действия по исправлению не выполняются автоматически для сообщений электронной почты и контента. Вместо этого все действия по исправлению сообщений электронной почты и сообщений электронной почты ожидают утверждения вашей группой управления операциями в [центре уведомлений](mtp-action-center.md).

Параметры безопасности в Office 365 помогают защитить электронную почту и контент. Чтобы просмотреть или изменить эти параметры, следуйте указаниям в статье [Защита от угроз](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).

1. В центре безопасности Майкрософт 365 ( [https://security.microsoft.com/](https://security.microsoft.com/) ) перейдите к разделу **политики**  >  **защиты от угроз**.

2. Убедитесь, что настроены все указанные ниже политики. Чтобы получить справку и рекомендации, обратитесь к разделу [Защита от угроз](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).

   - [Защита от вредоносных программ (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-1---anti-malware-protection)
   - [Защита от фишинга в защитнике для Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
   - [Безопасные вложения (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-attachments-policies)
   - [Безопасные ссылки (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-links-policies)
   - [Защита от нежелательной почты (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection) 

4. Убедитесь, что [защитник Майкрософт для Office 365 для SharePoint, OneDrive и Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) включен.

5. Убедитесь, что включено [Автоматическое удаление для защиты электронной почты с нулевым временем](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop) . 

8. (Это необязательный параметр.) Ознакомьтесь со своими [политиками оповещений Office 365](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) в центре соответствия требованиям Microsoft 365 ( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). Несколько политик оповещений по умолчанию находятся в категории "Управление угрозами". Некоторые из этих оповещений могут инициировать автоматическое исследование и отклик. Чтобы узнать больше, ознакомьтесь со статьей [Политика оповещений по умолчанию](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?#default-alert-policies).
 
## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Убедитесь, что защитник Microsoft 365 включен

1. Перейдите в центр безопасности Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ) и войдите в систему.

2. В области навигации найдите **инциденты** , **Центр уведомлений** и **Поиск, как** показано на следующем рисунке:

   :::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP в":::

   - Если вы видите **инциденты** , **центр поддержки** и **Поиск, защитник** Microsoft 365 включен. Перейдите к следующей процедуре, [Просмотрите или измените уровень автоматизации для групп устройств](#review-or-change-the-automation-level-for-device-groups).

   - Если вы *не* видите **инциденты** , **Центр уведомлений** **или поиск** , возможно, защитник Microsoft 365 не включен. В этом случае перейдите к следующему шагу.

3. В области навигации выберите **Параметры**  >  **защитник Microsoft 365**. Убедитесь, что защитник Microsoft 365 включен. 

   Нужна помощь? Обратитесь [к разделу Включение защитника Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable).

## <a name="review-pending-and-completed-actions-in-the-action-center"></a>Проверка ожидающих и завершенных действий в центре уведомлений

После настройки автоматического исследования и ответа в защитнике Microsoft 365 необходимо посетить центр уведомлений ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ). Там можно просматривать и утверждать ожидающие действия, а также просматривать действия, которые были сделаны автоматически. 

[Откройте Центр уведомлений](mtp-action-center.md).
