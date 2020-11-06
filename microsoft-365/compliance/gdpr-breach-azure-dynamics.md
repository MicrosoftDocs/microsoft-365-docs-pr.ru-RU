---
title: 'Azure и Dynamics 365: уведомление о нарушении безопасности, определенное GDPR'
description: Сведения о том, как Azure и Dynamics 365 обеспечивают защиту от нарушений безопасности персональных данных и как корпорация Майкрософт реагирует на такие нарушения и оповещает вас о них.
keywords: Azure, Microsoft 365, Dynamics 365, документация по Microsoft 365, GDPR
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 0cdd3a2d8e158800cef534a1488df0f25e3d232f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920267"
---
# <a name="azure-and-dynamics-365-breach-notification-under-the-gdpr"></a>Azure и Dynamics 365: уведомление о нарушении безопасности, определенное GDPR

Microsoft Azure серьезно относится к выполнению своих обязательств по Общему регламенту по защите данных (GDPR). Microsoft Azure принимает комплексные меры для защиты от нарушений безопасности данных. К ним относятся: физические и логические средства контроля безопасности, автоматизированные процессы, комплексные политики информационной безопасности и конфиденциальности, обучающие тренинги для сотрудников.

Встроенная с нуля система безопасности Microsoft Azure, начиная с [жизненного цикла разработки защищенных приложений](https://www.microsoft.com/sdl/), является обязательным процессом разработки, который включает: методику проектируемой конфиденциальности и методику конфиденциальности по умолчанию. Основополагающий принцип стратегии безопасности Майкрософт — это "предварительное обнаружение угроз", что является расширением стратегии "глубокая защита". Майкрософт опережает потенциальные угрозы, постоянно улучшая возможности безопасности Azure. Чтобы узнать больше о безопасности Azure, просмотрите эти [ресурсы](https://www.microsoft.com/trustcenter/security/azure-security).

Глобальная служба реагирования на инциденты, связанные с безопасностью, работающая в режиме 24/7, отвечает за устранение последствий атак на Microsoft Azure. Майкрософт прошла различные аудиты безопасности и соответствия требованиям (например, [ISO/IEC 27018](offering-iso-27018.md)). Чтобы предотвратить несанкционированный доступ, мы применяем тщательно разработанные операции и процессы в центрах обработки данных, включая видеомониторинг в режиме 24/7, подготовленных сотрудников службы безопасности, смарт-карты и биометрический контроль.

## <a name="detection-of-potential-breaches"></a>Обнаружение потенциальных нарушений

Due to the nature of modern cloud computing, not all data breaches occurring in a customer cloud environment involve Microsoft Azure services. Microsoft employs a shared responsibility model for Azure services to define security and operational accountabilities. Shared responsibility is important when discussing security of a cloud service, because both the cloud services provider and the customer are accountable for portions of cloud security.

Microsoft does not monitor for or respond to security incidents within the customer's realm of responsibility. A customer-only security compromise would not be processed as an Azure security incident and would require the customer tenant to manage the response effort. Customer incident response may involve collaboration with Microsoft Azure [customer support](https://azure.microsoft.com/support/options/), given appropriate service contracts. Microsoft Azure также предлагает различные службы (например, [Azure Defender](https://azure.microsoft.com/services/security-center/)), которые клиенты могут использовать для разработки мер реагирования на инциденты безопасности и управления такими мерами.

Azure реагирует на потенциальное нарушение безопасности данных согласно процедуре, которая входит в план управления инцидентами Microsoft Azure. Реагирование на связанный с безопасностью инцидент в Azure включает пять этапов: обнаружение, оценка, диагностика, стабилизация и закрытие. Группа реагирования на инциденты, связанные с безопасностью, может чередовать этапы диагностики и стабилизации. Обзор процесса реагирования на инцидент, связанный с безопасностью, см. ниже:

|**Этап**|**Описание**|
| ------- | ------------- |
| **_1 — Обнаружение_* _ | Первый признак потенциального инцидента. |
| _*_2 — Оценка_*_ | Участник группы реагирования на инциденты оценивает уровень серьезности события и его последствия. Оценка, основанная на полученных сведениях, может привести к дальнейшему обращению к группе по безопасности. |
| _*_3 — Диагностика_*_ | Security response experts conduct the technical or forensic investigation, identify containment, mitigation, and workaround strategies. If the security team believes that customer data may have become exposed to an unlawful or unauthorized individual, execution of the Customer Incident Notification process begins in parallel. |
| _*_4 — Стабилизация и восстановление_*_ | Чтобы устранить проблему, группа реагирования на инциденты создает план восстановления. Меры по сдерживанию кризиса, такие как помещение систем в карантин, могут предприниматься немедленно, параллельно с диагностикой. После устранения непосредственных угроз потребуется больше времени на их полное устранение. |
| _*_5 — Закрытие и анализ_*_ | По завершении группа реагирования на инциденты анализирует работу и создает отчет, в котором кратко излагаются сведения об инциденте, чтобы пересмотреть политики, процедуры и процессы и предотвратить повторение события. |

В [этом техническом документе ](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678) описывается, как Майкрософт анализирует, управляет и реагирует на инциденты, связанные с безопасностью, в Azure.

Процессы, которые использует Microsoft Azure, разработаны для обнаружения событий, ставящих под угрозу конфиденциальность, целостность и доступность служб Azure. Несколько событий могут инициировать исследование:

- Automated system alerts via internal monitoring and alerting frameworks. These alerts could come in the way of signature-based alarms such as anti-malware, intrusion detection or via algorithms designed to profile expected activity and alert upon anomalies.
- Отчеты из служб Microsoft, запущенных в Microsoft Azure и Azure для государственных организаций.
- Security vulnerabilities are reported to the [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) via [secure@microsoft.com](mailto:secure@microsoft.com). MSRC works with partners and security researchers around the world to help prevent security incidents and to advance Microsoft product security.
- Отчеты клиентов с [портала поддержки клиентов](https://www.windowsazure.com/support/contact/) или портала управления Microsoft Azure и Microsoft Azure для государственных организаций, в которых говорится о подозрительной активности в инфраструктуре Azure (в отличие от активности в сфере ответственности клиента).
- Security [Red Team and Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) activity. This strategy uses a highly skilled Red Team of offensive Microsoft security experts to uncover and attack potential weaknesses in Azure. The security response Blue Team must detect and defend against the Red Team's activity. Both Red and Blue Team actions are used to verify that Azure security response efforts are effectively managing security incidents. Security Red Team and Blue Team activities are operated under rules of engagement to help ensure the protection of customer data.
- Эскалации, выполняемые операторами служб Azure. Сотрудники Майкрософт обучены определять потенциальные проблемы безопасности и передавать их на рассмотрение.

## <a name="azures-data-breach-response"></a>Реагирование на нарушения безопасности данных в Azure

Microsoft assigns the investigation appropriate priority and severity levels by determining the functional impact, recoverability, and information impact of the incident. Both the priority and severity may change over the course of the investigation, based on new findings and conclusions. Security events involving imminent or confirmed risk to customer data are treated as high severity and worked around the clock to resolution. 

Microsoft Azure классифицирует информационное воздействие инцидента в соответствии со следующими категориями нарушения безопасности данных.

| _ *Категория**             | **Определение**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| **_Нет_* _               | Информация не была перехвачена, изменена, удалена или скомпрометирована иным способом.                                                      |
| _*_Нарушение конфиденциальности_*_     | Был получен доступ к конфиденциальным персональным данным налогоплательщиков, сотрудников, бенефициаров и т. д., или произошла их утечка.                                |
| _*_Нарушение безопасности защищаемой информации_*_ | Был получен доступ к защищаемой информации, а именно защищаемой критической информации инфраструктуры (PCII), или произошла ее утечка. |
| _*_Потеря целостности данных_*_     | Конфиденциальная или защищаемая информация была изменена или удалена.                                                                     |

Группа реагирования на инциденты, связанные с безопасностью, работает с инженерами и экспертами по безопасности Microsoft Azure, чтобы классифицировать события на основе собранных данных. Событие безопасности можно классифицировать как:

- _*False Positive**: An event that meets detection criteria but is found to be part of a normal business practice and may need to be filtered. The service team identifies the root cause for false positives and will address them in a systematic way using detection sources and fine-tuning them as needed.
- **Инцидент безопасности.** Инцидент, в котором незаконный доступ к данным клиента или службы поддержки, хранящимся на оборудовании либо объектах Майкрософт, а также несанкционированный доступ к оборудованию либо объектам, приводит к потере, раскрытию или изменению данных клиента или данных службы поддержки.
- **Инцидент нарушения конфиденциальности или безопасности, сообщаемый клиентом (CRSPI).** Незаконный или несанкционированный доступ к системам, оборудованию или объектам Майкрософт либо их использование, результатом которого является раскрытие, изменение или потеря данных клиента.
- **Privacy Breach** : A subtype of Security Incident involving personal data. Handling procedures are no different than a security incident.

For a CRSPI to be declared, Microsoft must determine that unauthorized access to customer data has or has likely occurred and/or that there is a legal or contractual commitment that notification must occur. It is desired, but not required, that specific customer impact, resource access, and repair steps be known. An incident is generally declared a CRSPI after the conclusion of the Diagnose stage of a security incident. However, the declaration may happen at any point that all pertinent information is available. The security incident manager must establish evidence beyond reasonable doubt that a reportable event has occurred to begin execution of the Customer Incident Notification Process.

В ходе исследования группа реагирования на нарушения безопасности тесно сотрудничает и консультируется с юристами со всего мира, чтобы убедиться, что исследование выполняется в соответствии с правовыми обязательствами и обязательствами перед клиентами. Кроме того, существуют значительные ограничения на просмотр системы и данных клиента, обработки в различных операционных системах. Конфиденциальные данные, а также данные клиента, не переносятся из рабочей среды без письменного разрешения менеджера по инцидентам, записанного в соответствующем билете об инциденте.

Майкрософт проверяет, успешно ли ограничен риск для бизнеса и клиентов и реализованы ли исправительные меры. При необходимости предпринимаются шаги по устранению непосредственных угроз безопасности, связанных с событием.

Microsoft also completes an internal post-mortem for data breaches. As a part of this exercise, sufficiency of response and operating procedures are evaluated, and any updates that may be necessary to the Security Incident Response SOP or related processes are identified and implemented. Internal postmortems for data breaches are highly confidential records not available to customers. Postmortems may, however, be summarized and included in other customer event notifications. These reports are provided to external auditors for review as part of Azure's routine audit cycle.

## <a name="customer-notification"></a>Уведомление клиента

Microsoft Azure уведомляет клиентов и регулирующие органы о нарушениях безопасности данных. Майкрософт полагается на сложное внутреннее деление в работе Azure. Журналы потоков данных также надежны. В результате большинство инцидентов затрагивают только отдельных клиентов. Цель — предоставить клиентам точное, своевременное и требующее действия уведомление при нарушении безопасности данных.

After the declaration of a CRSPI, the notification process takes place as expeditiously as possible while still considering the security risks of moving quickly. Generally, the process of drafting notifications occurs as the incident investigation is ongoing. Customer notices are delivered in no more than 72 hours from the time we declared a breach *except* in the following circumstances:

- Microsoft believes that the act of performing a notification increases the risk to other customers. For example, the act of notifying may tip off an adversary causing an inability to remediate.
- Другие необычные или экстремальные обстоятельства, проверенные юридическим отделом корпорации Майкрософт CELA и исполнительным менеджером по вопросам инцидентов.
- The 72-hour timeline may leave some incident details available. These are provided to customers and regulatory authorities as the investigation proceeds.

Microsoft Azure предоставляет клиентам детальную информацию, что позволяет проводить внутренние расследования, а также помогает выполнять обязательства перед пользователями, не задерживая при этом отправку уведомлений.

Уведомление о нарушении безопасности персональных данных будет доставлено клиенту любым способом, который выберет Майкрософт, включая электронную почту. Уведомление о нарушении безопасности данных будет доставлено контактным лицам по вопросам безопасности из списка, предоставляемого Azure Defender, который можно настроить, следуя [рекомендациям по реализации](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details). Если контактная информация не приведена в Azure Defender, уведомление отправляется одному или нескольким администраторам в подписке на Azure. Чтобы уведомление было успешно доставлено, клиент должен проверить контактную информацию администраторов на всех порталах подписок и веб-служб.

Команда Microsoft Azure или Azure для государственных организаций также может уведомить дополнительный персонал Майкрософт, например службу поддержки пользователей и менеджеров по работе с клиентами или менеджеров по технической поддержке. Эти люди взаимодействуют с клиентом и ускоряют процесс исправления.

## <a name="microsoft-dynamics-365-built-in-security-features"></a>Встроенные функции безопасности Microsoft Dynamics 365

Microsoft Dynamics 365 использует преимущества инфраструктуры облачных служб и встроенные функции безопасности, чтобы обеспечить защиту данных за счет соответствующих мер и механизмов. Кроме того, Dynamics 365 предоставляет оперативный доступ к данным, а также возможность совместной работы благодаря конфиденциальности и целостности данных в следующих областях: [удостоверение безопасности, защита данных, безопасность на основе ролей и управление угрозами](https://www.microsoft.com/trustcenter/security/dynamics365-security).

В предложении Microsoft Dynamics 365 применяются те же технические и организационные меры, которые служба поддержки Microsoft Azure предпринимает для защиты от нарушений безопасности данных. Следовательно, вся информация, изложенная в документе «Нарушение безопасности данных Microsoft Azure», также относится к службе Microsoft Dynamics 365.

## <a name="learn-more"></a>Подробнее

[Центр управления безопасностью (Майкрософт)](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
