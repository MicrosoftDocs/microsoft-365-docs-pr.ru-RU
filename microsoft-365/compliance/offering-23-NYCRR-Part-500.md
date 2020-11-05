---
title: Раздел 23 NYCRR (часть 500)
description: Корпорация Майкрософт подготовила руководство, в котором рассказывается, как Azure, Office 365 и Power BI могут помочь финансовым учреждениям обеспечить соответствие требованиям 23 NYCRR 500.
keywords: Microsoft 365, соответствие требованиям, предложения
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: fa76fefbeea2c8fc0226a85d5b12599839eba8ca
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920411"
---
# <a name="title-23-nycrr-part-500"></a>Раздел 23 NYCRR (часть 500)

## <a name="title-23-nycrr-part-500-overview"></a>Обзор раздела 23 NYCRR (часть 500)

In response to the significant and ever-increasing threats to the cybersecurity of information and financial systems, in 2017, the State of New York Department of Financial Services imposed a new set of cybersecurity requirements on financial institutions that are licensed or authorized to do business in the state. This regulation — Title 23 New York Codes, Rules, and Regulation Part 500: Cybersecurity Requirements for Financial Services Companies — is designed to protect customer data and the information technology systems of financial institutions such as state-chartered, private, and international banks, mortgage brokers, and insurance companies.

## <a name="microsoft-and-title-23-nycrr-part-500"></a>Корпорация Майкрософт и раздел 23 NYCRR (часть 500)

Microsoft provides a comprehensive guide, [Microsoft Cloud Services: Supporting Compliance with NYDFS Cybersecurity Requirements](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=f7e56dc6-4e52-4e9a-af06-aa41d5851d36&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides), for financial services regulated under Title 23 NYCRR Part 500. It explains in depth how Azure, Office 365, and Power BI cloud services support compliance with the requirements. Financial institutions that seek to operate in the global financial center of New York must meet them, so compliance is critical for many institutions.

Используйте следующее руководство, чтобы оперативно обеспечить соответствие требованиям раздела 23 NYCRR (часть 500): "Облачные службы Майкрософт: [поддержка соответствия требованиям NYDFS к кибербезопасности](https://go.microsoft.com/fwlink/p/?linkid=2098969)".

Нормативы Нью-Йорка устанавливают для каждого финансового учреждения перечисленные ниже требования.

- **Develop and maintain a robust cybersecurity program** starting with an assessment of the institution’s specific risk profile and then designing a program that addresses them. The [Microsoft Cloud Financial Services Compliance Program](https://www.microsoft.com/download/confirmation.aspx?id=55332) was created to help financial services assess the risks of using Microsoft cloud services. It includes direct engagement with our engineers and corporate risk officers and access to our compliance and security experts.
- **Implement a comprehensive cybersecurity policy** that addresses information security, data governance and classification, access controls, business continuity, and the like. Microsoft offers guidance for developing this policy with in-depth information about our certifications and risk assessments; business continuity and disaster recovery metrics; and diagnostics for logging and auditing.
- **Designate a chief information security officer** (CISO) to manage the cybersecurity program and enforce policy. To help your CISO, Microsoft provides in-depth cybersecurity information about Microsoft cloud deployments through [Azure Defender*](https://azure.microsoft.com/services/security-center/?v=17.23h), [Office 365 Advanced Threat Analytics](https://docs.microsoft.com/advanced-threat-analytics/), and [Power BI Security](https://go.microsoft.com/fwlink/?LinkId=829185).
- **Monitor and test the effectiveness of its cybersecurity program** : Microsoft provides information from audits of its cybersecurity practices that include continuous monitoring, periodic penetration testing, and vulnerability assessments. Customers can conduct their own tests without advance permission from Microsoft.
- **Maintain an audit trail.** Built-in audit functionalities of Azure, Office 365, and Power BI customers generate information that can be used to reconstruct financial transactions and develop audit trail information.
- **Ограничение доступа к информационным системам, содержащим непубличную информацию.** Службы Azure, Office 365 и Power BI предусматривают встроенный процесс управления доступом на основе ролей (RBAC), строгие требования к безопасности и доступу для каждого администратора Майкрософт, а также аудит каждого запроса на расширенные права доступа.
- **Внедрение процедур для оценки и тестирования безопасности внешних приложений.** Что касается разработчиков, использующих Visual Studio, [правила безопасности](https://docs.microsoft.com/visualstudio/code-quality/security-rules-rule-set-for-managed-code) для управляемого кода помогают обеспечить обнаружение и устранение угроз кибербезопасности перед развертыванием кода.
- **Use periodic risk assessments to design and enhance cybersecurity programs** : For customers, Microsoft aggregates information about security threats, provides roadmaps of change management, and regularly updates information about subcontractors. Microsoft also regularly conducts risk assessments of its own services, the results of which are available to customers.
- **Use qualified personnel to manage cybersecurity risks and oversee cybersecurity functions** : Microsoft employs stringent procedures for our employee access to your customer data. If we hire subcontractors, we remain responsible for service delivery, and ensure that subcontractors fully comply with Microsoft privacy and security commitments, including requirements for handling sensitive data, background checks, and non-disclosure agreements.
- **Реализация политик и процедур для обеспечения безопасности информации, хранящейся у сторонних поставщиков.** Azure, Office 365 и Power BI предоставляют многофакторную проверку подлинности для всех входящих подключений к сетям компании. В этих службах реализованы средства управления (включая шифрование) для защиты непубличной информации, передаваемой по внешним сетям, и неактивных данных. Кроме того, предоставляются [условия использования Microsoft Online Services](https://aka.ms/Online-Services-Terms), которые обеспечивают уведомление клиентов, расследование инцидентов и устранение рисков инцидентов безопасности.
- **Реализация политик и процедур хранения и удаления данных.** Вы всегда можете получать доступ к своим данных, хранящимся в Azure, Office 365 и Power BI, и извлекать их.
- **Monitor the activity of authorized users, detect unauthorized access, and offer regular cybersecurity awareness training to employees** : Azure, Office 365, and Power BI include outside-in monitoring to raise alerts about incidents, and extensive diagnostics for logging and auditing. [Microsoft Virtual Academy](https://mva.microsoft.com/) offers online training that covers the cybersecurity of Microsoft cloud services.
- **Develop plans to respond to and recover from cybersecurity incidents** : Microsoft helps you prepare for cybersecurity incidents using a defensive strategy to detect, predict, and prevent security breaches before they occur. When developing your own plans, you can draw on our incident management plan for responding to cybersecurity breaches.

## <a name="microsoft-in-scope-cloud-services"></a>Облачные службы Майкрософт, к которым применима оценка

- [Azure](https://aka.ms/AzureCompliance)
- Intune
- [Office 365](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- Облачная служба Power BI в виде автономной службы или в составе плана либо набора Office 365

## <a name="frequently-asked-questions"></a>Вопросы и ответы

**На какие учреждения распространяется этот норматив?**

Ознакомьтесь со страницей [За кем мы наблюдаем](https://go.microsoft.com/fwlink/p/?linkid=2099374) Департамента финансовых услуг Нью-Йорка, чтобы определить, распространяется ли этот норматив на ваше учреждение.

## <a name="resources"></a>Ресурсы

- [Рекомендованные ресурсы](https://www.microsoft.com/trustcenter/compliance/NYCRR)
- [Раздел 23 NYCRR (часть 500) Департамента финансовых услуг Нью-Йорка: требования к кибербезопасности для финансовых учреждений](https://go.microsoft.com/fwlink/p/?linkid=2098976)
- [Вопросы и ответы: раздел 23 NYCRR (часть 500) — кибербезопасность](https://go.microsoft.com/fwlink/p/?linkid=2098977)
- [Облачные службы Майкрософт: поддержка соответствия требованиям NYDFS к кибербезопасности](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=f7e56dc6-4e52-4e9a-af06-aa41d5851d36&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)
- [Соответствие требованиям в центре управления безопасностью Майкрософт](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="other-microsoft-resources-for-financial-services"></a>Другие ресурсы Майкрософт для финансовых услуг

- [Облачные службы Майкрософт для бизнеса и финансовые услуги](https://www.microsoft.com/trustcenter/cloudservices/financialservices)
- [Программа Microsoft Cloud Financial Services Compliance Program](https://www.microsoft.com/download/confirmation.aspx?id=55332)
- [Соответствие финансовых услуг требованиям в Azure](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Общая ответственность в облачных вычислениях](https://aka.ms/sharedresponsibility)- 
