---
title: Служба обработчика данных для уведомлений в Windows Enterprise согласно GDPR
description: Сведения о том, как служба обработчика данных для Windows Enterprise обеспечивает защиту от нарушений безопасности персональных данных и как корпорация Майкрософт реагирует на такие нарушения и оповещает вас о них.
keywords: Служба обработчика данных для Windows Enterprise, Microsoft 365, документация Microsoft 365, GDPR
localization_priority: Priority
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: siosulli
author: DaniHalfin
manager: dansimp
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: 5d0a5563de2443e5af0f3b7efda0947d4f669cee
ms.sourcegitcommit: e03bc2945e63f7f2638257e530056ae9283b45d9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "49070903"
---
# <a name="data-processor-service-for-windows-enterprise-breach-notification-under-the-gdpr"></a>Служба обработчика данных для уведомлений о нарушениях в Windows Enterprise согласно GDPR

>[!NOTE]
>This topic is intended for participants in the data processor service for Windows Enterprise preview program and requires acceptance of specific terms of use. To learn more about the program and agree to the terms of use, see [https://aka.ms/WindowsEnterprisePublicPreview](https://aka.ms/WindowsEnterprisePublicPreview).

Microsoft data processor service for Windows Enterprise takes its obligations under the General Data Protection Regulation (GDPR) seriously. Microsoft data processor service for Windows Enterprise takes extensive security measures to protect against data breaches. These include dedicated threat management teams that proactively anticipate, prevent, and mitigate malicious access.  Internal security measures such as port scanning, perimeter vulnerability scanning, and intrusion detection detect and prevent malicious access, as well as automated security processes, comprehensive information security and privacy policies, and security and privacy training for all personnel. 

Security is built into the Microsoft data processor service for Windows Enterprise from the ground up, starting with the [Security Development Lifecycle](https://www.microsoft.com/sdl/), a mandatory development process that incorporates privacy-by-design and privacy-by-default methodologies. The guiding principle of Microsoft's security strategy is to 'assume breach', which is an extension of the defense-in-depth strategy. By constantly challenging the security capabilities of the data processor service for Windows Enterprise, Microsoft can stay ahead of emerging threats. For more information on the data processor service for Windows Enterprise security, please review these [resources](https://www.microsoft.com/TrustCenter/Security/windows10-security) the data processor service for Windows Enterprise responds to a potential data breach according to the security incident response process. The data processor service for Windows Enterprise security incident response is implemented using a five-stage process: Detect, Assess, Diagnose, Stabilize, and Close. The Security Incident Response Team may alternate between the diagnose and stabilize stages as the investigation progresses. An overview of the security incident response process is below: 

|**Этап**|**Описание**|
| ------- | ------------- |
| **_1 — Обнаружение_* _ | Первый признак потенциального инцидента. |
| _*_2 — Оценка_*_ | Участник группы реагирования на инциденты оценивает уровень серьезности события и его последствия. Оценка, основанная на полученных сведениях, может привести к дальнейшему обращению к группе по безопасности. |
| _*_3 — Диагностика_*_ | Security response experts conduct the technical or forensic investigation, identify containment, mitigation, and workaround strategies. If the security team believes that customer data may have become exposed to an unlawful or unauthorized individual, execution of the Customer Incident Notification process begins in parallel. |
| _*_4 — Стабилизация и восстановление_*_ | Чтобы устранить проблему, группа реагирования на инциденты создает план восстановления. Меры по сдерживанию кризиса, такие как помещение систем в карантин, могут предприниматься немедленно, параллельно с диагностикой. После устранения непосредственных угроз потребуется больше времени на их полное устранение. |
| _*_5 — Закрытие и анализ_*_ | По завершении группа реагирования на инциденты анализирует работу и создает отчет, в котором кратко излагаются сведения об инциденте, чтобы пересмотреть политики, процедуры и процессы и предотвратить повторение события. |

The detection processes used by Microsoft data processor service for Windows Enterprise are designed to discover events that risk the confidentiality, integrity, and availability of the data processor service for Windows Enterprise. Several events can trigger an investigation: 

 - Automated system alerts via internal monitoring and alerting frameworks. These alerts could come in the way of signature-based alarms such as anti-malware, intrusion detection or via algorithms designed to profile expected activity and alert upon anomalies.
 - Отчеты из служб Microsoft, запущенных в Microsoft Azure и Azure для государственных организаций.
 - Security vulnerabilities are reported to the [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) via [secure@microsoft.com] (mailto:secure@microsoft.com). MSRC works with partners and security researchers around the world to help prevent security incidents and to advance Microsoft product security.
 - Отчеты клиентов с портала поддержки клиентов или портала управления Microsoft Azure и Microsoft Azure для государственных организаций, в которых говорится о подозрительной активности в инфраструктуре Azure (в отличие от активности в сфере ответственности клиента).
 - Security [Red Team and Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) activity. This strategy uses a highly skilled Red Team of offensive Microsoft security experts to uncover and attack potential weaknesses in Azure. The security response Blue Team must detect and defend against the Red Team’s activity. Both Red and Blue Team actions are used to verify that Azure security response efforts are effectively managing security incidents. Security Red Team and Blue Team activities are operated under rules of engagement to help ensure the protection of customer data.
 - Эскалации, выполняемые операторами служб Azure. Сотрудники Майкрософт обучены определять потенциальные проблемы безопасности и передавать их на рассмотрение.

 ## <a name="data-processor-service-for-windows-enterprise-data-breach-response"></a>Реагирование на нарушения безопасности данных в службе обработчика данных для Windows Enterprise 

 Microsoft assigns the investigation appropriate priority and severity levels by determining the functional impact, recoverability, and information impact of the incident. Both the priority and severity may change over the course of the investigation, based on new findings and conclusions. Security events involving imminent or confirmed risk to customer data are treated as high severity and worked around the clock to resolution. Microsoft data processor service for Windows Enterprise categorizes the information impact of the incident into the following breach categories: 

| _ *Категория**             | **Определение**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| **_Нет_* _               | Информация не была удалена, изменена или скомпрометирована иным способом. |
| _*_Нарушение конфиденциальности_*_     | Был получен доступ к конфиденциальным персональным данным налогоплательщиков, сотрудников, бенефициаров и т. д., или они были удалены. |
| _*_Нарушение безопасности защищаемой информации_*_ | Был получен доступ к защищаемой информации, а именно защищаемой критической информации инфраструктуры (PCII), или она была удалена. |
| _*_Потеря целостности данных_*_     | Конфиденциальная или защищаемая информация была изменена или удалена. |

The Security Response Team works with Microsoft data processor service for Windows Enterprise Security Engineers and SMEs to classify the event based on factual data from the evidence. A security event may be classified as: 

 - _*False Positive**: An event that meets detection criteria but is found to be part of a normal business practice and may need to be filtered. The service team will identify the root cause for false positives and will address them in a systematic way leveraging detection sources and fine-tuning them as needed. 
 - **Инцидент безопасности.** Инцидент, в котором незаконный доступ к данным клиента или службы поддержки, хранящимся на оборудовании либо объектах Майкрософт, а также несанкционированный доступ к оборудованию либо объектам, приводит к потере, раскрытию или изменению данных клиента или данных службы поддержки. 
 - **Инцидент безопасности, сообщаемый клиентом (CRSI).** Незаконный или несанкционированный доступ к системам Майкрософт, оборудованию или объектам, что приводит к раскрытию, изменению или потере данных клиента. 
 - **Privacy Breach** : A subtype of Security Incident involving personal data. Handling procedures are no different than a security incident. 

 Чтобы объявить CRSI, Майкрософт должна определить, что произошел или с большой долей вероятности произошел несанкционированный доступ к данным клиента и/или по закону либо договору клиент должен получить уведомление. Желательно, но не обязательно, знать степень воздействия на клиента, доступ к ресурсам и действия по исправлению. Инцидент обычно объявляют CRSI после заключения на этапе диагностики инцидента. Тем не менее, при наличии всей необходимой информации его можно объявить в любой момент. Для начала процедуры уведомления клиентов об инциденте менеджер должен установить факт того, что событие произошло. 

В ходе исследования группа реагирования на нарушения безопасности тесно сотрудничает и консультируется с юристами со всего мира, чтобы убедиться, что исследование выполняется в соответствии с правовыми обязательствами и обязательствами перед клиентами. Кроме того, существуют значительные ограничения на просмотр системы и данных клиента, обработки в различных операционных системах. Конфиденциальные данные, а также данные клиента, не переносятся из рабочей среды без письменного разрешения менеджера по инцидентам, записанного в соответствующем билете об инциденте. 

Майкрософт проверяет, успешно ли ограничен риск для бизнеса и клиентов и реализованы ли исправительные меры. При необходимости предпринимаются шаги по устранению непосредственных угроз безопасности, связанных с событием. 

Microsoft also completes an internal post-mortem for data breaches. As a part of this exercise, sufficiency of response and operating procedures are evaluated, and any updates that may be necessary to the Security Incident Response SOP or related processes are identified and implemented. Internal postmortems for data breaches are highly confidential records not available to customers. Postmortems may, however, be summarized and included in other customer event notifications. These reports are provided to external auditors for review as part of the data processor service for Windows Enterprise routine audit cycle. 

## <a name="customer-notice"></a>Уведомление клиента

Microsoft data processor service for Windows Enterprise notifies customers and regulatory authorities of data breaches as required. Microsoft relies on heavy internal compartmentalization in the operation of the data processor service for Windows Enterprise. Data flow logs are also robust. As a benefit of this design, most incidents can be scoped to specific customers. The goal is to provide impacted customers with an accurate, actionable, and timely notice when their data has been breached. 

After the declaration of a CRSI, the notification process takes place as expeditiously as possible while still considering the security risks of moving quickly. Generally, the process of drafting notifications occurs as the incident investigation is ongoing. Customer notices are delivered in no more than 72 hours from the time we declared a breach except for the following circumstances: 

 - Майкрософт считает, что отправка уведомления увеличивает риск для других клиентов. Например, отправка уведомления может предупредить злоумышленника, что приведет к невозможности исправления. 
 - Другие необычные или экстремальные обстоятельства, проверенные юридическим отделом корпорации Майкрософт CELA и исполнительным менеджером по вопросам инцидентов. 

 Служба обработчика данных (Майкрософт) для Windows Enterprise предоставляет клиентам детальную информацию, что позволяет проводить внутренние расследования, а также помогает выполнять обязательства перед пользователями, не задерживая при этом отправку уведомлений. 

Уведомление о нарушении безопасности персональных данных будет доставлено клиенту любым способом, который выберет Майкрософт, включая электронную почту. Уведомление о нарушении безопасности данных будет доставлено контактным лицам по вопросам безопасности из списка, предоставляемого Azure Defender, который можно настроить, следуя [рекомендациям по реализации](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details). Если контактная информация не приведена в Azure Defender, уведомление отправляется одному или нескольким администраторам в подписке на Azure. Чтобы уведомление было успешно доставлено, клиент должен проверить контактную информацию администраторов на всех порталах подписок и веб-служб.

Команда службы обработчика данных для Windows Enterprise также может уведомить дополнительный персонал Майкрософт, например службу поддержки пользователей и менеджеров по работе с клиентами или менеджеров по технической поддержке. Эти люди взаимодействуют с клиентом и ускоряют процесс исправления. 

Дополнительные информацию о том, как Майкрософт обнаруживает нарушения безопасности персональных данных и реагирует на них, см. в статье [Уведомление о нарушениях безопасности данных согласно требованиям GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRBreach) на портале Service Trust Portal.
