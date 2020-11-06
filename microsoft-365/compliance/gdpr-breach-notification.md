---
title: Уведомление о нарушении
description: Узнайте, как службы Майкрософт обеспечивают защиту от нарушений безопасности персональных данных и как корпорация Майкрософт реагирует на такие нарушения и оповещает вас о них.
keywords: Microsoft 365, Microsoft 365 для образования, документация по Microsoft 365, GDPR
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
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: a671fc9234f76c63ff7336369c87e680a4432cc3
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920293"
---
# <a name="gdpr-breach-notification"></a>Уведомление о нарушении GDPR

The General Data Protection Regulation (GDPR) introduces new rules for organizations that offer goods and services to people in the European Union (EU), or that collect and analyze data for EU residents no matter where you or your enterprise are located. Additional details can be found in the [GDPR Summary topic](gdpr.md). This document leads you to information on the completion of Breach Notifications under the GDPR using Microsoft products and services.

## <a name="what-constitute-a-breach-of-personal-data-under-the-gdpr"></a>Что считается нарушением безопасности персональных данных согласно GDPR?

Personal data means any information related to an individual that can be used to identify them directly or indirectly. A personal data breach is 'a breach of security leading to the accidental or unlawful destruction, loss, alteration, unauthorized disclosure of, or access to, personal data transmitted, stored, or otherwise processed'.

## <a name="terminology"></a>Терминология

Полезные определения терминов GDPR, используемых в этом документе:

- *Управляющий данными (управляющий)* — юридическое лицо, орган государственной власти, агентство или другое лицо, которое отдельно от других или вместе с ними определяет цели и средства обработки персональных данных.  
- *Персональные данные* и *субъект данных* — все сведения, относящиеся к определенному или определяемому физическому лицу ("субъект данных"). Определяемым физическим лицом считается лицо, которого можно прямо или косвенно определить.  
- *Обработчик*  — физическое или юридическое лицо, орган государственной власти, агентство или другое лицо, которое обрабатывает персональные данные от лица управляющего.  
- *Данные клиента*  — это данные, которые создаются и хранятся в ходе повседневной работы компании.

## <a name="microsoft-and-breach-notification"></a>Майкрософт и уведомление о нарушении

Microsoft takes its obligations under the General Data Protection Regulation (GDPR) seriously. A security incident/data breach refers to events such as unlawful access to customer's data stored on Microsoft equipment or in Microsoft facilities, or unauthorized access to such that has the potential to result in the loss, disclosure, or alteration of customer data.

As a data processor, Microsoft ensures that service customers are able to meet the GDPR's breach notification requirements as data controllers. Our notification provides the information needed to make that assessment. Microsoft notifies customers of any personal data breach, except for those cases where personal data is confirmed to be unintelligible (for example, encrypted data where integrity of the keys is confirmed).

Data controllers are responsible for assessing risks to data privacy and determining whether a breach requires notification of a customer's DPA. Microsoft provides the information needed, along with your GDPR compliance policy, to make that assessment.

Initial notification includes a description of the nature of the breach, approximate user impact, and mitigation steps (if applicable). If our investigation is not complete at the time of initial notification, we will indicate next steps and timelines for subsequent communication. For more information about how Microsoft detects and responds to a breach of personal data, see [Data Breach Notification Under the GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRBreach) in the Service Trust Portal.

Подробные сведения об уведомлениях о нарушении для определенных продуктов и услуг Майкрософт приведены ниже.
  
1. **[Office 365](gdpr-breach-Office365.md)**  
    Microsoft invests extensively in systems, processes, and personnel to reduce the likelihood of personal data breach and to quickly detect and mitigate consequence of breach if it does occur. Additional details can be read at [Office 365 Investments in Data Security](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-office365#office-365-investments-in-data-security).

    A customer may become aware of a breach and wish to contact Microsoft. In this case, notify Microsoft Support, which will then interface with engineering teams for more information.

2. **[Azure и Dynamics 365](gdpr-breach-azure-dynamics.md)**  
    В корпорации Майкрософт круглосуточно действует глобальная служба реагирования на инциденты, чьей задачей является смягчение последствий атак на Microsoft Azure и Dynamics 365.

    - *Обнаружение нарушений* : поскольку и у корпорации Майкрософт, и у клиента есть обязательства по обеспечению безопасности, службы Azure используют модель общей ответственности в отношении безопасности и функционирования в целом. Корпорация Майкрософт не отслеживает инциденты безопасности в рамках сферы ответственности клиента и не реагирует на них. Реагирование клиента на инцидент может включать взаимодействие со [службой поддержки клиентов](https://azure.microsoft.com/support/options/) Azure при наличии соответствующих контрактов на обслуживание. Кроме того, Microsoft Azure предлагает различные службы (например, [Azure Defender](https://azure.microsoft.com/services/security-center/)), с помощью которых вы можете реагировать на инциденты безопасности.

        For a list of events that trigger a breach investigation in Microsoft Azure, see [Detection of Potential Breaches](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#detection-of-potential-breaches). [Azure and Breach Notification under the GDPR](gdpr-breach-azure-dynamics.md) further details how Microsoft investigates, manages, and responds to security incidents within Azure.

    - *Data Breach Response* : Microsoft determines appropriate priority and severity levels of a breach by investigating the functional impact, recoverability, and information impact of the incident. Priority and severity may change over the course of the investigation, based on new findings and conclusions. Microsoft's security response team works closely with global legal advisors to help ensure that forensics are performed in accordance with legal obligations and commitments to customers. These processes are detailed in [Azure's Data Breach Response](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#azures-data-breach-response).

    - *Customer Notification* : Microsoft Azure notifies customers and regulatory authorities of data breaches as required. Customer notices are delivered in no more than 72 hours from the time we declared a breach except for the following circumstances:

        - Майкрософт считает, что отправка уведомления увеличивает риск для других клиентов.
        - The 72-hour timeline may leave some incident details available. These details will be provided to you as the investigation proceeds.

        Дополнительные сведения можно найти в разделе [Уведомление клиента](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#customer-notification).

3. **[Служба поддержки и профессиональные услуги Майкрософт](gdpr-breach-Microsoft-Support-Professional-Services.md)**  
    The nature of professional services means that some data protection incidents may fall within the customer's realm of responsibility. When Microsoft Professional Services identifies a data protection incident, it follows documented industry standard response plan as outlined in [Scope & Limits of Data Protection Incident Response Process](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-microsoft-support-professional-services#scope--limits-of-data-protection-incident-response-process).

## <a name="breach-notification-admin-tools"></a>Средства администрирования уведомлений о нарушении

- **Укажите контактное лицо по вопросам конфиденциальности** : на [портале администрирования Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=2052736) администраторы клиентов могут определить, к какому сотруднику организации следует обращаться по вопросам конфиденциальности, если Майкрософт это понадобится.

## <a name="learn-more"></a>Дополнительные сведения

- [Центр управления безопасностью (Майкрософт)](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
