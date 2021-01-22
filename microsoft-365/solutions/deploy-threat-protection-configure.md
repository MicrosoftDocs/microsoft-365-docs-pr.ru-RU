---
title: Действия по настройке возможностей защиты от угроз в Microsoft 365
description: Узнайте, как развернуть службы и возможности защиты от угроз в Microsoft 365 E5.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 492db78c9aea881ae05dbc66f5e84ad98629b923
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931990"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>Настройка возможностей защиты от угроз в Microsoft 365

Выполните следующие действия, чтобы настроить защиту от угроз в Microsoft 365.


## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>Шаг 1. Настройка многофакторной проверки подлинности и политик условного доступа

[Многофакторная проверка](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) подлинности (MFA) требует, чтобы пользователи проверяли свои удостоверения с помощью телефонного вызова или приложения для проверки подлинности. [Политики условного доступа определяют](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) определенные требования, которые должны быть выполнены для доступа пользователей к приложениям и данным в Microsoft 365. Политики MFA и условного доступа совместно защищают вашу организацию. Например, если кто-то пытается войти с мобильного устройства с использованием учетной записи, которая не включена для MFA, а политика условного доступа требует, чтобы MFA вступила в силу, этому пользователю будет отключен вход.  

Корпорация Майкрософт проверила и рекомендует определенный набор условного доступа и связанные политики для защиты доступа ко всем приложениям SaaS, особенно Microsoft 365. Политики рекомендуются для базовой, конфиденциальной и строго регулируемой защиты. Начните с реализации политик для базовой защиты. 


[ ![ Общие политики для настройки удостоверений и](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)доступа к устройствам 
 [См. более крупную версию этого изображения](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>Реализация базовой защиты для Microsoft 365

![Процесс развертывания базовой защиты](../media/solutions-architecture-center/deploy-threat-protection-identity-access-steps.png) 

1. [Настройте необходимые условия, в том числе Azure Identity Protection.](../security/office-365-security/identity-access-prerequisites.md)
2. [Настройте общие политики доступа к удостоверениям](../security/office-365-security/identity-access-policies.md) и устройствам для базовой защиты.
3. Настройте политики для гостевых [пользователей,](../security/office-365-security/identity-access-policies-guest-access.md) [Microsoft Teams,](../security/office-365-security/teams-access-policies.md) [Exchange Online,](../security/office-365-security/secure-email-recommended-policies.md) [SharePoint Online и OneDrive.](../security/office-365-security/sharepoint-file-access-policies.md)

### <a name="more-information-about-protecting-identities"></a>Дополнительные сведения о защите удостоверений

- [Конфигурации доступа для удостоверений и устройств](../security/office-365-security/microsoft-365-policies-configurations.md)
- [Руководство по безопасности для Azure MFA](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-microsoft-defender-for-identity"></a>Шаг 2. Настройка Microsoft Defender для удостоверений

[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) — это облачное решение для обеспечения безопасности, которое работает с сигналами локальной службы [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) для выявления, обнаружения и изучения расширенных угроз, скомпрометных удостоверений и вредоносных действий внутри организации, направленных на вашу организацию.

Microsoft Defender for Identity позволяет аналитикам операций безопасности (SecOps) и специалистам по безопасности обнаруживать сложные атаки в гибридных средах для:
- Отслеживайте пользователей, поведение су организаций и действия с помощью аналитики на основе обучения.
- Защищать удостоверения и учетные данные пользователей, хранящиеся в Active Directory.
- Выявление и расследование подозрительных действий пользователей и продвинутых атак по всей цепочке уничтожений.
- Предоставьте четкую информацию об инциденте на простой временной шкале для быстрой сортировки.

### <a name="to-set-up-microsoft-defender-for-identity"></a>Настройка Microsoft Defender для удостоверений

![Процесс развертывания Microsoft Defender для удостоверений](../media/solutions-architecture-center/deploy-azure-atp-steps.png) 

1. [Настройка Microsoft Defender для удостоверений](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) для защиты основных сред.
2. Защитите [все контроллеры домена](https://docs.microsoft.com/azure-advanced-threat-protection/atp-sensor-monitoring) и [леса.](https://docs.microsoft.com/azure-advanced-threat-protection/atp-multi-forest)
3. Интеграция [оповещений Microsoft Defender для](https://docs.microsoft.com/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) удостоверений в рабочий процесс операций безопасности (SecOps).

### <a name="more-information-about-microsoft-defender-for-identity"></a>Дополнительные сведения о Microsoft Defender для удостоверений

- [Что такое Microsoft Defender для удостоверений?](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Видео: введение в Microsoft Defender для удостоверений](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Развертывание Microsoft Defender для удостоверений](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-365-defender"></a>Шаг 3. Включив Защитник Microsoft 365

[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) объединяет сигналы и оркестрирует возможности в одном решении. Благодаря интегрированному решению Microsoft 365 Defender специалисты по безопасности могут совмесить сигналы угроз, получаемые каждым из этих продуктов, и определить полный уровень и влияние угрозы; как он вошел в среду, на что она влияет и как она в настоящее время влияет на организацию. Защитник Microsoft 365 автоматически предотвращает или останавливает атаки, а также самостоятельно исцеляет затронутые почтовые ящики, конечные точки и удостоверения пользователей.

Microsoft 365 Defender объединяет оповещения, инциденты, автоматизированное исследование и реагирование, а также расширенный поиск по рабочим нагрузкам (Microsoft Defender для удостоверений, Microsoft Defender для Office 365, Microsoft Defender для конечной точки и Microsoft Cloud App Security) в единой области. После настройки одной или более служб Защитника Office 365 включите Microsoft 365. Новые возможности постоянно добавляются в Microsoft 365 Defender; рассмотрите возможность получения предварительных функций.

### <a name="to-set-up-microsoft-365-defender"></a>Настройка Защитника Microsoft 365

![Процесс развертывания Защитника Microsoft 365](../media/solutions-architecture-center/deploy-mtp-steps.png) 

1. [Просмотрите необходимые условия.](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)
2. [Включив Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)
3. [Отказаться от предварительного просмотра функций.](https://docs.microsoft.com/microsoft-365/security/mtp/preview)

### <a name="more-information-about-microsoft-365-defender"></a>Дополнительные сведения о Защитнике Microsoft 365

- [Что такое Microsoft 365 Defender?](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [Новые возможности Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)

## <a name="step-4-configure-microsoft-defender-for-office-365"></a>Шаг 4. Настройка Microsoft Defender для Office 365

[Microsoft Defender для Office 365 защищает](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) организацию от вредоносных угроз в сообщениях электронной почты (вложениях и URL-адресах), документах Office и средствах совместной работы. В следующей таблице перечислены функции и возможности Microsoft Defender для Office 365, включенные в Microsoft 365 E5:

|Возможности настройки, защиты и обнаружения|Возможности автоматизации, исследования, исправлений и образования|
|---|---|
|[Безопасные вложения](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br/>[Безопасные ссылки](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)<br/>[Безопасные документы](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)<br/>[ATP для SharePoint, OneDrive и Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)<br/>[Защита от фишинга в Defender для Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#exclusive-settings-in-atp-anti-phishing-policies)|[Трекеры угроз](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-trackers)<br/>[Обозреватель угроз](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)<br/>[Автоматизированный анализ угроз и реагирование на них](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>[Эмулятор атак](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)|
|

С помощью Microsoft Defender для Office 365 сотрудники организации могут общаться и совместно работать более безопасно, с помощью защиты от угроз для содержимого электронной почты и документов Office.

### <a name="to-set-up-microsoft-defender-for-office-365"></a>Настройка Microsoft Defender для Office 365

![Процесс развертывания Microsoft Defender для Office 365](../media/solutions-architecture-center/deploy-office365-atp-steps.png) 

1. [Настройте и настройте политики Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)в Microsoft Defender.
2. [Просмотр и использование отчетов Microsoft Defender для Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)
3. [Использование возможностей исследования угроз и реагирования на них.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)

### <a name="more-information-about-microsoft-defender-for-office-365"></a>Дополнительные сведения о Microsoft Defender для Office 365

- [Обзор Microsoft Defender для Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [Новые возможности Microsoft Defender для Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

## <a name="step-5-configure-microsoft-defender-for-endpoint"></a>Шаг 5. Настройка Microsoft Defender для конечной точки

[Microsoft Defender для конечной точки](https://docs.microsoft.com/windows/security/threat-protection) защищает устройства вашей организации (также называются конечными точками) от киберугроз, расширенных атак и нарушений безопасности данных. Группы безопасности могут более эффективно управлять безопасностью конечных точек. Надежные инструменты помогают организациям следить за невыгруженными системами, используя обнаружение уязвимостей с помощью [управления угрозами и уязвимостами.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Автоматизированное обнаружение и устранение таких возможностей, как уменьшение поверхности [атаки,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)защита нового [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) [поколения,](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)обнаружение конечных точек и реагирование, [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)а также автоматизированное исследование и исправление помогают защитить устройства от вредоносных программ. Помимо этих возможностей, клиенты могут получать упреждающие уведомления и по запросу обращаться к экспертам по угрозам Майкрософт в рамках службы управляемого вынаружия. 


### <a name="set-up-microsoft-defender-for-endpoint"></a>Настройка Microsoft Defender для конечной точки

![Процесс развертывания Microsoft Defender для конечной точки](../media/solutions-architecture-center/deploy-mdatp-steps.png) 

1. [Подготовьте Microsoft Defender к развертыванию конечной точки.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases)
2. [Настройка Microsoft Defender для развертывания конечных точек](https://docs.microsoft.com/windows/security/threat-protection/micros.oft-defender-atp/production-deployment)
3. [Onboard to the Microsoft Defender for Endpoint service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboarding).
4. [Выполните свои главные задачи администрирования безопасности.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)

### <a name="more-information-about-microsoft-defender-for-endpoint"></a>Дополнительные сведения о Microsoft Defender для конечной точки

- [Узнайте больше о Microsoft Defender для конечной точки.](https://docs.microsoft.com/windows/security/threat-protection)
- [Попробуйте лабораторию оценки в Microsoft Defender для конечной точки.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluation-lab)

## <a name="step-6-configure-microsoft-cloud-app-security"></a>Шаг 6. Настройка Microsoft Cloud App Security

[Microsoft Cloud App Security —](https://docs.microsoft.com/cloud-app-security) это брокер безопасности облачного доступа, который поддерживает сбор журналов, соединители API и обратный прокси-сервер. Microsoft Cloud App Security обеспечивает богатый обзор, контроль над перемещениями данных и сложную аналитику для идентификации и борьбы с киберугрозами во всех облачных службах. С помощью Microsoft Cloud App Security ваши операции по обеспечению безопасности могут защищать конфиденциальную информацию вашей организации, защищать от киберугроз и аномалий, обнаруживая и отслеживая приложения, которые имеют доступ к данным вашей организации, и помогая убедиться, что облачные приложения вашей организации соответствуют требованиям соответствия требованиям.

### <a name="set-up-microsoft-cloud-app-security"></a>Настройка Microsoft Cloud App Security

![Процесс развертывания Microsoft Cloud App Security](../media/solutions-architecture-center/deploy-mcas-steps.png) 

1. [Настройка портала и других основных требований.](https://docs.microsoft.com/cloud-app-security/general-setup)
2. [Настройка облачного обнаружения и](https://docs.microsoft.com/cloud-app-security/set-up-cloud-discovery) [подключение приложений.](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)
3. [Развертывание управления приложениями условного доступа для рекомендуемых приложений.](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad)
4. [Используйте средства исследования и панели мониторинга.](https://docs.microsoft.com/cloud-app-security/investigate)

### <a name="more-information-about-microsoft-cloud-app-security"></a>Дополнительные сведения о Microsoft Cloud App Security

- [Просмотрите новые функции и возможности.](https://docs.microsoft.com/cloud-app-security/release-notes)
- [Узнайте больше о Microsoft Cloud App Security.](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)

## <a name="step-7-monitor-status-and-take-actions"></a>Шаг 7. Отслеживание состояния и действия

После того как вы настроите и развернете службы и возможности защиты от угроз, следующим шагом будет отслеживание обнаружения угроз и соответствующие действия. Лучше всего начать с Центра безопасности Microsoft 365 ( ), где можно отслеживать и управлять безопасностью в удостоверениях, данных, устройствах, приложениях и инфраструктуре [https://security.microsoft.com](https://security.microsoft.com) Майкрософт. 

![Центр безопасности Microsoft 365](../media/solutions-architecture-center/m365-security-center.png)

Центр безопасности Microsoft 365 предназначен специально для администраторов безопасности и групп управления безопасностью. В Центре безопасности Microsoft 365 вы можете:
- Просмотр общей системы безопасности организации с помощью [оценки безопасности.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)
- [Мониторинг и просмотр отчетов](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting) о состоянии удостоверений, данных, устройств, приложений и инфраструктуры.
- Подключите точки в оповещениях через [инциденты.](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- Используйте [автоматизированное исследование и исправление](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir) для устранения угроз.
- [Упреждающий поиск угроз,](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview)таких как попытки вторжений или нарушения безопасности электронной почты, данных, устройств и удостоверений.
- [Обзор последних кампаний и](https://docs.microsoft.com/microsoft-365/security/mtp/latest-attack-campaigns) методов атак с помощью аналитики угроз.
- ... и не только!

### <a name="more-information-about-the-microsoft-365-security-center"></a>Дополнительные сведения о Центре безопасности Microsoft 365

- [Начало работы с Центром безопасности Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)
- [Мониторинг и просмотр отчетов.](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting)
- [См. порталы безопасности в Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/mtp/portals)

## <a name="step-8-train-users"></a>Шаг 8. Обучение пользователей

Обучение пользователей может сэкономить много времени и раздражение ваших пользователей и операций безопасности. Опытные пользователи реже открывают вложения или щелкают ссылки в сомнительных сообщениях электронной почты и с большей вероятностью избегают подозрительных веб-сайтов. 

Руководство по [](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) кампании по кибербезопасности в учебном заведении предоставляет отличное руководство по созданию сильной культуры осведомленности о безопасности в организации, включая обучение пользователей выявлению фишинговых атак. 

Microsoft 365 предоставляет следующие ресурсы для информирования пользователей в организации:

|Концепция  |Ресурсы  |
|---------|---------|
|Microsoft 365     |[Настраиваемые пути обучения](https://docs.microsoft.com/office365/customlearning/) <p>Эти ресурсы помогут вам собрать учебные курсы для конечных пользователей в организации        |
|Безопасность Microsoft 365 |[Модуль обучения: защита организации с помощью встроенной интеллектуальной системы безопасности из Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>Этот модуль позволяет описать, как функции безопасности Microsoft 365 работают вместе, и рассказать о преимуществах этих функций безопасности. |
|Многофакторная проверка подлинности     | [Двухшаговая проверка: что такое дополнительная страница проверки?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Эта статья помогает конечным пользователям понять, что такое многофакторная проверка подлинности и почему она используется в вашей организации.    |

В дополнение к этому руководству Корпорация Майкрософт рекомендует вашим пользователям принять меры, описанные в этой статье: защита учетной записи и устройств от злоумышленников и вредоносных [программ.](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx) К этим действиям относятся:
- Использование надежных паролей
- Защита устройств 
- Включение функций безопасности на ПК с Windows 10 и Mac (для неугодных устройств)
    
Корпорация Майкрософт также рекомендует пользователям защищать свои личные учетные записи электронной почты, выбирая действия, рекомендуемые в следующих статьях:
- [Защита учетной записи Outlook.com электронной почты](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [Защита учетной записи Gmail с помощью двухшаговой проверки](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
