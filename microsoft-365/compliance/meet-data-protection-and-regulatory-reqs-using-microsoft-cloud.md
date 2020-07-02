---
title: Соответствие требованиям защиты данных и нормативным требованиям с помощью Compliance Manager для облачных сервисов Microsoft
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 429e686f-d8a6-455e-a2b6-3791d763f000
description: Получите сведения о том, как использовать Менеджер по управлению соответствием на портале Microsoft Service Trust Portal для соблюдения требований к защите данных и нормативных требований.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aedadc682bd45f363f1e97599383dd901c3eae7f
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016260"
---
# <a name="microsoft-compliance-manager-classic"></a>Диспетчер соответствия требованиям Майкрософт (классический)

> [!NOTE]
> В этой документации описана предыдущая версия этого продукта. Пользователям *настоятельно рекомендуется не использовать эту версию диспетчера соответствия требованиям*. **Если вы используете текущую предварительную версию диспетчера соответствия требованиям, ознакомьтесь с [документацией для диспетчера соответствия требованиям (предварительной версии)](working-with-compliance-manager.md).**

 *Диспетчер соответствия требованиям недоступен в планах Office 365 под управлением 21Vianet, Office 365 Germany, Office 365 U.S. Government Community High (GCC High) и Office 365 Department of Defense.*
  
Диспетчер соответствия требованиям — это основанное на рабочих процессах средство оценки рисков, представленное на портале Microsoft [Service Trust Portal](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-service-trust-portal), которое позволяет отслеживать, назначать и проверять действия, направленные на обеспечение соответствия организации нормативным требованиям в профессиональных и облачных службах (Майкрософт), таких как Microsoft Office 365, Microsoft Dynamics 365 и Microsoft Azure. 

Диспетчер соответствия требованиям:
  
- совмещает подробные сведения, предоставленные корпорацией Майкрософт аудиторам и управляющим органам в рамках различных независимых проверок облачных служб (Майкрософт) на соответствие различным стандартам (например, ISO 27001, ISO 27018 и NIST), и сведения, собранные корпорацией Майкрософт для собственного использования, чтобы обеспечить соответствие требованиям нормативов (например, HIPAA и Общего регламента ЕС по защите данных, или GDPR), с данными, полученными вами в ходе самостоятельной оценки соответствия вашей организации этим стандартам и нормативам;
    
- позволяет назначать, отслеживать и записывать действия, связанные с оценкой и обеспечением соответствия требованиям, помогая координировать работу команд в организации для достижения ее целей;
    
- предоставляет рейтинг соответствия требованиям, помогающий отслеживать ваш прогресс и расставлять приоритеты средств аудита, чтобы снизить риск для организации;
    
- предоставляет надежный репозиторий для отправки и контроля свидетельств и других артефактов, которые связаны с действиями, направленными на обеспечение соответствия требованиям;
    
- предоставляет подробные отчеты в Microsoft Excel, где документируются выполняемые вами и корпорацией Майкрософт действия, направленные на обеспечение соответствия требованиям. Эти сведения можно предоставлять аудиторам, управляющим органам и другим заинтересованным лицам.

Краткую демонстрацию возможностей диспетчера соответствия требованиям см. в [этом видеоролике](https://www.youtube.com/watch?v=r1vs8NdSXKQ).

    
> [!IMPORTANT]
> Compliance Manager is a dashboard that provides a summary of your data protection and compliance stature and recommendations to improve data protection and compliance. The Customer Actions provided in Compliance Manager are recommendations; it is up to each organization to evaluate the effectiveness of these recommendations in their respective regulatory environment prior to implementation. Recommendations found in Compliance Manager should not be interpreted as a guarantee of compliance.

    
## <a name="what-is-compliance-manager"></a>Что такое диспетчер соответствия требованиям?

Compliance Manager is a workflow-based risk assessment tool designed to help you manage regulatory compliance within the shared responsibility model of the cloud. Compliance Manager provides you with a dashboard view of standards and regulations and assessments that contain Microsoft's control implementation details and test results and customer control implementation guidance and tracking for your organization to enter. Compliance Manager provides certification assessment control definitions, guidance on implementation and testing of controls, risk-weighted scoring of controls, role-based access management, and an in-place control action assignment workflow to track control implementation, testing status and evidence management. Compliance Manager optimizes compliance workload by enabling customers to logically group assessments together and apply assessment control testing to identical or related controls, reducing the duplication of effort that might otherwise be required to satisfy identical control requirements across different certifications.

## <a name="assessments-in-compliance-manager"></a>Оценки в диспетчере соответствия требованиям

The core component of Compliance Manager is called an *Assessment*. An Assessment is an assessment of a Microsoft service against a certification standard or data protection regulation (such as ISO 27001:2013, and the GDPR). Assessments help you to discern your organization's data protection and compliance posture against the selected industry standard for the selected Microsoft cloud service. Assessments are completed by the implementation of the controls that map to the certification standard being assessed. 
  
Структура оценки основана на обязанностях, разделяемых между корпорацией Майкрософт и вашей организацией, чтобы оценить угрозы безопасности и риски несоответствия в облаке, а также реализовать средства защиты данных, предписываемые стандартом соответствия, стандартом защиты данных, нормативом или законом.
  
Оценка состоит из нескольких компонентов:
  
- **Службы в области.** Каждая оценка применяется к определенному набору служб Майкрософт, указанных в разделе "Облачные службы в области". 
    
- **Microsoft-Managed Controls** - For each cloud service, Microsoft implements and manages a set of  *controls*  as part of Microsoft's compliance with various standards and regulations. These controls are organized into  *control families*  that align with the structure from the corresponding certification or regulation that the Assessment is aligned to. For each Microsoft-managed control, Compliance Manager provides details about how Microsoft implemented the control, along with how and when that implementation was tested and validated by an independent third-party auditor. 
    
    Ниже приведен пример трех средств контроля под управлением Майкрософт из семейства **Безопасность** для оценки соответствия службы Office 365 требованиям GDPR. 

    ![Сведения о средствах контроля под управлением Майкрософт в диспетчере соответствия требованиям](../media/d1351212-1ebf-424e-91b8-930c2b2edef1.png)
  
  a. Specifies the following information from the certification or regulation that maps to the Microsoft-managed control.

  - **Идентификатор средства контроля.** Номер раздела или статьи стандарта сертификации или норматива, которому соответствует средство контроля.
    
  - **Заголовок.** Заголовок из соответствующего стандарта сертификации или норматива.
    
  - **Идентификатор статьи.** Это поле указывается только для оценок соблюдения GDPR, так как в нем указывается номер соответствующей статьи GDPR.
    
  - **Описание.** Текст стандарта сертификации или норматива, соответствующего выбранному средству контроля под управлением Майкрософт.

  b. The Compliance Score for the control, which indicates the level of risk (due to non-compliance or control failure) associated with each Microsoft-managed control. See [Understanding the Compliance Score](#understanding-the-compliance-score) for more information. Note that Compliance Scores are rated from 1 to 10 and are color-coded. Yellow indicates low risk controls, orange indicates medium-risk controls, and red indicated high-risk controls. 
    
  c. Information about the implementation status of a control, the date the control was tested, who performed the test, and the test result.
    
  d. For each control, you can click **More** to see additional information, including details about Microsoft's implementation of the control and details about how the control was tested and validated by an independent third-party auditor. 
    
- **Customer-Managed Controls** - This is the collection of controls that are managed by your organization. Your organization is responsible for implementing these controls as part of your compliance process for a given standard or regulation. Customer-managed controls are also organized into control families for the corresponding certification or regulation. Use the customer-managed controls to implement the recommended actions suggested by Microsoft as part of your compliance activities. Your organization can use the prescriptive guidance and recommended Customer Actions in each customer-managed control to manage the implementation and assessment process for that control.
    
    Customer-managed controls in Assessments also have built-in workflow management functionality that you can use to manage and track your organization's progress towards completing the Assessment. For example, a Compliance Officer in your organization can assign an Action Item to an IT admin who has the responsibility and necessary permissions to perform the actions that are recommended for the control. When that work is complete, the IT admin can upload evidence of their implementation tasks (for example, screenshots of configuration or policy settings) and then assign the Action Item back to the Compliance Officer to evaluate the collected evidence, test the implementation of the control, and record the implementation date and test results in Compliance Manager. For more information, see the [Managing the assessment process](#managing-the-assessment-process) section in the article. 
  
## <a name="permissions-and-role-based-access-control"></a>Разрешения и управление доступом на основе ролей

Диспетчер соответствия требованиям использует модель разрешений с управлением доступом на основе ролей. Только пользователи, которым назначена роль пользователя, могут получить доступ к диспетчеру соответствия требованиям, а действия, разрешенные каждому пользователю, ограничиваются типом роли.
  
Обратите внимание, что больше не существует используемой по умолчанию роли **Гостевой доступ**. Каждому пользователю должна быть назначена роль для доступа и работы в диспетчере соответствия требованиям.
  
The following table describes each Compliance Manager permission and what it allows the user do. The table also indicates the role that each permission is assigned to.
  
||**Читатель в диспетчере соответствия требованиям**|**Участник в диспетчере соответствия требованиям**|**Аудитор в диспетчере соответствия требованиям**|**Администратор диспетчера соответствия требованиям**|**Администратор портала**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Чтение данных.** Пользователи могут читать данные, но не могут редактировать их.  <br/> |![Флажок](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Галочка](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Галочка](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Галочка](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Флажок](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>|
|**Изменение данных.** Пользователи могут редактировать все поля, кроме полей "Результат теста" и "Дата теста".  <br/> ||![Флажок](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>|![Галочка](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Галочка](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Флажок](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|**Изменение результатов тестов.** Пользователи могут редактировать поля "Результат теста" и "Дата теста".  <br/> ||<br/> |![Флажок](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Галочка](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Флажок](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|**Управление оценками.** Пользователи могут создавать, архивировать и удалять оценки.  <br/> |||<br/> |![Флажок](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |![Флажок](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
|**Manage users** - Users can add other users in their organization to the Reader, Contributor, Assessor, and Administrator roles. Only those users with the Global Administrator role in your organization can add or remove users from the Portal Admin role.  <br/> ||||<br/> |![Флажок](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
   
## <a name="understanding-the-compliance-score"></a>Общие сведения о рейтинге соответствия требованиям

На информационной панели диспетчера соответствия требованиям в правом верхнем углу плитки отображается общий рейтинг Office 365. Это общий рейтинг соответствия требованиям, который включает баллы, полученные по результатам оценки всех средств контроля, помеченных при оценке как внедренные и протестированные. При добавлении оценки можно заметить, что рейтинг соответствия требованиям уже частично заполнен. Это связано с тем, что баллы для средств контроля, управляемых Майкрософт, уже отражены в рейтинге, после того, как они были реализованы Майкрософт и протестированы независимыми сторонними организациями.
  
![Информационная панель диспетчера соответствия требованиям: общий рейтинг соответствия требованиям](../media/756091aa-1afd-4aff-93ab-c6f6824f2add.png)
  
Остальные баллы начисляются за успешную оценку клиентских средств контроля, а также реализацию и тестирование средств контроля под управлением клиента, каждому из которых назначается определенное значение, прибавляемое к общему рейтингу соответствия требованиям. 
  
Для каждой оценки показан рейтинг соответствия требованиям, который помогает определить уровень риска (из-за несоответствия или сбоя), связанный с каждым средством контроля (включая средства контроля, управляемые Майкрософт или клиентом). Каждому средству контроля, управляемому клиентом, назначается максимальное количество баллов (называемое *рейтингом серьезности) по шкале от 1 до 10. Чем больше фактор риска средства контроля, тем больше баллов ему назначается. 
  
Например, представленное ниже средство контроля оценки "Управление доступом пользователей" имеет очень высокий ранг серьезности риска, поэтому отображается значение 10.
  
![Диспетчер соответствия требованиям: средство контроля оценки с высокой серьезностью (10 баллов)](../media/174ecb2c-aaed-436e-9950-74da7dadf5db.png)
  
 С другой стороны, представленное ниже средство контроля оценки "Резервное копирование" имеет низкий ранг серьезности риска, поэтому отображается значение 3. 
  
![Диспетчер соответствия требованиям: средство контроля оценки с низкой серьезностью (3 балла)](../media/11749f20-5f22-40c2-bbc1-eaccbf29e2ae.png)
  
The Compliance Manager assigns a default severity ranking to each control. Risk rankings are calculated based on the following criteria:
  
- Предотвращает ли средство контроля возникновение инцидентов (самый высокий рейтинг), обнаруживает ли возникшие инциденты или исправляет их воздействие (самый низкий рейтинг). Что касается рейтинга серьезности, обязательному средству контроля, предотвращающему угрозы, назначается наибольшее число баллов, а средствам контроля, отвечающим за обнаружение и исправление воздействия угроз (независимо от того, являются они обязательными или дискреционными), назначается наименьшее число.
    
- Является ли средство контроля (после его реализации) обязательным, что не позволяет пользователям обходить его (например, необходимость сбрасывать пароли, а также соблюдать требования к длине пароля и символам), или необязательным (например, бизнес-правила, требующие блокировать экран, когда пользователь отсутствует на рабочем месте)?
    
- Controls related to risks to data confidentiality, integrity, and availability, whether these risks come from internal or external threats, and whether the threat is malicious or accidental. For example, controls that would help prevent an external attacker from breaching that network and gaining access to personally identifiable information would be assigned more points than a control related to preventing an employee from accidentally mis-configuring a network router setting that results in a network outage).
    
- Риски, связанные с юридическими и внешними факторами, например контрактами, нормативами и обязательствами перед общественностью, для каждого средства контроля.
    
The displayed Compliance Score values for the control are applied  *in their entirety*  to the Total Compliance Score on a pass/fail basis--either the control is implemented and passes the subsequent assessment test or it does not; there is no partial credit for a partial implementation. Only when the control has its **Implementation Status** set to **Implemented** or **Alternative Implementation** and the **Test Result** is set to **Passed** are the assigned points added to the Total Compliance Score. 
  
Основная функция рейтинга соответствия требованиям заключается в том, что он помогает определить, реализации каких средств контроля необходимо уделять внимание в первую очередь (он обозначает средства, с отсутствием внедрения которых связан наибольший риск). Кроме того, если средства контроля связаны с другими средствами (в той же оценке или в другой оценке этой группы), успешное прохождение проверки одним из средств может существенно упростить работу по проверке другого благодаря синхронизации результатов тестирования.
  
Например, на приведенном ниже изображении показано, что оценка "Office 365 — GDPR" в настоящее время выполнена на 46 %. При этом оценено 51 из 111 средств контроля, а общий рейтинг соответствия требованиям составляет 289 баллов из 600 возможных.
  
![Диспетчер соответствия требованиям: сводка по оценкам](../media/595eedae-e3e0-4d1f-8cf5-7c1c9f4fd1e8.png)
  
В рамках оценки средство контроля GDPR 7.5.5 связано с 5 другими (7.4.1, 7.4.3, 7.4.4, 7.4.8 и 7.4.9), каждое из которых имеет средний или высокий рейтинг серьезности (от 6 до 8). Используя фильтр оценок, мы выбрали все эти средства контроля, показав их в представлении оценки. Как видно, ни одно из них не проходило оценку. 
  
![Представление оценок в диспетчере соответствия требованиям: фильтр средств контроля, ни одно из них не оценено](../media/b2ae7120-2d7a-4247-b0a9-f5f65433395f.jpg) As those 6 controls are related, the completion of any one them will result in a synchronization of those test results across the related controls within this assessment (just as it will for any related controls in an assessment that is in the same assessment grouping). Upon completion of the implementation and testing of GDPR control 7.5.5, the control detail area refreshes to show that all 6 controls have been assessed, with a corresponding increase in the number of assessed controls to 57 and 51% assessed, and a change in total Compliance Score of +40. 
  
![Представление оценок в диспетчере соответствия требованиям: синхронизированные результаты оценки средств контроля](../media/e9da2b30-053a-4d40-ace9-ae1b39cdaf66.jpg)
  
Это диалоговое окно подтверждения обновления появится, если вы собираетесь изменить состояние реализации связанного средства контроля так, что это повлияет на остальные связанные средства контроля.
  
![Оценка в диспетчере соответствия требованиям: диалоговое окно подтверждения обновления связанных средств контроля](../media/8be25bd2-1aee-455f-8aa4-10b1184ca4c3.png)
  
> [!NOTE]
> Currently, only Assessments for Office 365 cloud services include a Compliance Score. Assessments for Azure and Dynamics show an assessment status. 

## <a name="compliance-score-methodology"></a>Принцип вычисления рейтинга

Рейтинг соответствия требованиям, как и Оценка безопасности (Майкрософт), подобен другим системам оценивания с учетом поведения. Организация может повышать свой рейтинг соответствия требованиям, выполняя действия, связанные с защитой данных, обеспечением конфиденциальности и безопасности.
  
> [!NOTE]
> The Compliance Score does not express an absolute measure of organizational compliance with any particular standard or regulation. It expresses the extent to which you have adopted controls which can reduce the risks to personal data and individual privacy. No service can guarantee that you are compliant with a standard or regulation, and the Compliance Score should not be interpreted as a guarantee in any way. 
  
Assessments in Compliance Manager are based on the shared responsibility model for cloud computing. In the shared responsibility model, Microsoft and each customer share responsibility for the protection of the customer's data when that data is stored in our cloud.
  
Как показано ниже в оценке GDPR для Office 365, корпорация Майкрософт и клиенты несут ответственность за выполнение различных действий, направленных на выполнение требований оцениваемого стандарта или нормативного акта. Чтобы выявить необходимые действия и составить представление о них, в диспетчере соответствия требованиям все стандарты и нормативные акты рассматриваются как платформы контроля. Таким образом, действия, выполняемые корпорацией Майкрософт и клиентами для каждой оценки, включают внедрение и проверку различных средств контроля.
  
![Диспетчер соответствия требованиям: оценка GDPR](../media/123f8126-85b8-4baa-9c4e-c6295cf4a5ca.png)
  
Ниже представлен базовый рабочий процесс для типичного действия.
  
1. The Compliance, Risk, Privacy, and/or Data Protection Officer of an organization assigns the task to someone in the organization to implement a control. That person could be:

    - владелец бизнес-политики;
    
    - специалист по внедрению ИТ;
    
    - другой сотрудник организации, отвечающий за выполнение задачи.
    
2. That individual performs the tasks necessary to implement the control, uploads evidence of implementation into Compliance Manager, and marks the control(s) tied to the Action as implemented. Once these tasks are completed, they assign the Action to an Assessor for validation. Assessors can be:
    
    - внутренними, то есть выполнять проверку средств контроля в рамках организации;
    
    - внешними, то есть изучать, проверять и сертифицировать соответствие требованиям. Например, это могут быть сторонние независимые организации, выполняющие аудит облачных служб (Майкрософт).
    
3. Аудитор проверяет средства контроля, изучает свидетельства, помечает средства контроля как оцененные и записывает результаты оценки (например, "Пройдено").
    
После оценки всех средств контроля, связанных с оценкой, оценка считается выполненной.
  
Every Assessment in Compliance Manager comes pre-loaded with information that provides details about the Actions taken by Microsoft to satisfy the requirements of the controls for which Microsoft is responsible. This information includes details about how Microsoft has implemented each control and how and when Microsoft's implementation was assessed and verified by a third-party auditor. For this reason, the Microsoft Managed Controls for each Assessment are marked as Assessed, and the Compliance Score for the Assessment reflects this.
  
Each Assessment includes a total Compliance Score based on the shared responsibility model. Microsoft's implementation and testing of controls for Office 365 contributes a portion of the total possible points associated with a GDPR assessment. As the customer implements and tests each of the customer Actions, the Compliance Score for the Assessment will increase by the value assigned to the control. 
  
 ### <a name="risk-based-scoring-methodology"></a>Принцип оценивания с учетом рисков
  
Compliance Manager uses a risk-based scoring methodology with a scale from 1-10 that assigns a higher value to controls that represent a higher risk in the event the control fails or is non-compliant. The scoring system used by Compliance Score is based on several key factors, such as:
  
- характер средства контроля;
    
- уровень риска для средства контроля с учетом типов угроз;
    
- внешние факторы, влияющие на средство контроля.
    
![Диспетчер соответствия требованиям: принцип вычисления рейтинга](../media/e48764c4-828e-44b0-8636-fb3c352f2bac.png)
  
 ### <a name="essence-of-the-control"></a>Характер средства контроля
  
Характер средства контроля основан на том, является ли оно обязательным, а также на его назначении (предотвращении, обнаружении или исправлении).
  
 ### <a name="mandatory-or-discretionary"></a>Обязательное или дискреционное
  
 *Mandatory controls*  are controls that cannot be bypassed either intentionally or accidentally. An example of a common mandatory control is a centrally-managed password policy that sets requirements for password length, complexity, and expiration. Users must comply with these requirements in order to access the system. 
  
 *Discretionary controls*  rely upon users to understand policy and act accordingly. For example, a policy requiring users to lock their computer when they leave it is a discretionary control because it relies on the user. 
  
 ### <a name="preventative-detective-or-corrective"></a>Профилактическое, обнаруживающее или корректирующее
  
 *Preventative controls*  are those that prevent specific risks. For example, protecting information at rest using encryption is a preventative control against attacks, breaches, etc. Separation of duties is a preventative control to manage conflict of interest and to guard against fraud. 
  
 *Detective controls*  are those that actively monitor systems to identify irregular conditions or behaviors that represent risk or that can be used to detect intrusions or determine if a breach has occurred. System access auditing and privileged administrative actions auditing are types of detective monitoring controls; regulatory compliance audits are a type of detective control used to find process issues. 
  
 *Corrective controls*  are those that try to keep the adverse effects of a security incident to a minimum, take corrective action to reduce the immediate effect, and reverse the damage, if possible. Privacy incident response is a corrective control to limit damage and restore systems to an operational state after a breach. 
  
Оценивая каждое средство контроля по этим критериям, мы определяем его характер и назначаем ему значение, соответствующее представляемому им уровню риска.
  
 **Угроза**
  
|<br>|<br>|<br>|
|:-----|:-----|:-----|
||**Обязательное** <br/> |**Необязательное** <br/> |
|**Профилактическое** <br/> |Высокая степень риска  <br/> |Средняя степень риска  <br/> |
|**Обнаруживающее** <br/> |Средняя степень риска  <br/> |Низкая степень риска  <br/> |
|**Корректирующее** <br/> |Средняя степень риска  <br/> |Низкая степень риска  <br/> |
   
Угроза — это что-либо, представляющее риск для фундаментального и общепринятого стандарта безопасности (три принципа защиты данных CIA: конфиденциальность, целостность и доступность):
  
- Конфиденциальность означает, что информацию могут считывать и толковать только доверенные, уполномоченные лица.
    
- Целостность означает, что информация не была изменена или удалена неуполномоченными лицами.
    
- Доступность означает, что к информации можно в любой момент получить доступ с высоким качеством обслуживания.
    
A failure of any of these characteristics is considered a compromise of the system as a whole. Threats can come from both internal and external sources, and an actor's intent can be accidental or malicious. These factors are estimated in a threat matrix that assigns threat levels of either High, Moderate, or Low to each combination of scenarios.

|<br>|**Внутренняя**<br/>|<br>|**Внешняя**<br/>|<br>|<br>|<br>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||*Злоумышленная*<br/>|*Непреднамеренная*<br/>|*Злоумышленная*<br/>|*Непреднамеренная*<br/>|||
|**Конфиденциальность**<br/>|(В, С или Н)  <br/> |(В, С или Н)  <br/> |(В, С или Н)  <br/> |(В, С или Н)|
|**Целостность**<br/>|(В, С или Н)  <br/> |(В, С или Н)  <br/> |(В, С или Н)  <br/> |(В, С или Н)|
|**Доступность**<br/>|(В, С или Н)  <br/> |(В, С или Н)  <br/> |(В, С или Н)  <br/> |(В, С или Н)|
   
 **Внешние драйверы**
  
|**Контракты**|**Нормативы**|**Обязательства перед общественностью**|
|:-----|:-----|:-----|
|(В, С или Н)  <br/> |(В, С или Н)  <br/> |(В, С или Н)  <br/> |
   
Внешние факторы, такие как применимые нормативы, контракты и обязательства перед общественностью, могут влиять на средства контроля, призванные защищать данные и предотвращать нарушения безопасности данных, а каждому из этих факторов назначается высокая, средняя или низкая степень риска.
  
Предполагаемое количество возникающих рисков высокой, средней или низкой степени риска в 15 возможных сценариях (критерии ЦРУ/угрозы и юридические/внешние факторы), совмещается в целях оценки риска, где вероятность и количество рисков определенной степени считаются значительными и учитываются при вычислении ранга серьезности средства контроля.
  
С учетом ранга серьезности средства контроля ему назначается рейтинг соответствия требованиям — число от 1 (низкий) до 10 (высокий). Выделяются следующие категории риска:
  
|**Уровень риска**|**Значение рейтинга**|
|:-----|:-----|
|Низкий  <br/> |1–3  <br/> |
|Средний  <br/> |6  <br/> |
|Высокий  <br/> |8  <br/> |
|Критический  <br/> |10  <br/> |
   
Отдавая приоритет средствам контроля с самым высоким рейтингом, организация сможет сосредоточиться на наиболее рискованных элементах и получать больше баллов в общем рейтинге соответствия требованиям по завершении оценки каждого средства контроля.
  
### <a name="summary-of-scoring-methodology"></a>Заключение
  
The Compliance Score is a core component of the way that Compliance Manager helps organizations understand and manage their compliance. The Compliance Score for an assessment is an expression of the company's compliance with a given standard or regulation as a number, where the higher the score (up to the maximum number of points allocated for the Assessment), the better the company's compliance posture. Understanding the compliance scoring methodology in which assessment controls are assigned risk severity values between 1- 10 (low to high), and how completed control assessments add to the total compliance score is crucial to organizations for prioritizing their actions.

## <a name="grouping-assessments"></a>Группировка оценок

При создании оценки можно создать для нее группу или присвоить ее существующей группе. Группы также помогают логически организовать оценки и использовать общую информацию и задачи рабочего процесса для оценок с одинаковыми или связанными средствами контроля, управляемыми клиентом.
  
For example, you could group Assessments by year or teams, departments, or agencies within your organization or group them by year. Here are some examples of groups and the Assessments they might contain.
  
- Оценки GDPR — 2018 г.
    
  - Office 365 + GDPR
    
  - Azure + GDPR
    
  - Dynamics + GDPR
    
- Оценки Azure — 2018 г.
    
  - Azure + GDPR
    
  - Azure + ISO 27001:2013
    
  - Azure + ISO 27018:2014
    
- Оценки безопасности и конфиденциальности данных
    
  - Office 365 + ISO 27001:2013
    
  - Office 365 + ISO 27018:2014
    
  - Azure + ISO 27001:2013
    
  - Azure + ISO 27018:2014
    
> [!TIP]
> Рекомендуем определить стратегию группировки для своей организации, прежде чем добавлять новые оценки. 
  
На группировку оценок распространяются следующие требования:
  
- Имена групп (также называемые *идентификаторами групп) должны быть уникальными в рамках организации. 
    
- Groups can contain Assessments for the same certification/regulation, but each group can only contain one Assessment for a specific cloud service/certification pair. For example, a group can't contain two Assessments for Office 365 and GDPR. Similarly, a group can contain multiple Assessments for the same cloud service as long as the corresponding certification/regulation for each one is different.
    
После добавления оценки в группу последнюю невозможно изменить. Вы можете переименовать группу оценок, после чего во всех оценках будет использоваться новое имя группы. Также можно создать новую оценку и новую группу оценок, а затем скопировать в нее сведения из существующей оценки (при этом создается дубликат оценки в другой группе). При архивации оценки нарушается связь между этой оценкой и группой оценок. Дальнейшие обновления других связанных оценок больше не отражаются в архивированной оценке.
  
Как было сказано выше, одним из основных преимуществ применения групп является использование одного средства контроля, управляемого пользователем (а следовательно, и одинаковых действий клиента), для разных оценок в одной группе. Таким образом, при внесении сведений о реализации, тестировании и статусе для средства контроля в одной оценке они будут синхронизироваться с тем же средством контроля в других оценках в группе. Другими словами, если для оценок используется одно и то же средство контроля и эти оценки находятся в одной группе, вам достаточно управлять процессом оценки для средства контроля только в одной оценке. Результаты для этого средства контроля будут автоматически синхронизированы с другими оценками. Например, в стандартах ISO 27001 и ISO 27018 имеется средство контроля политик паролей. Если для статуса тестирования средства контроля указать значение "Пройдено" в одной оценке, состояние этого средства обновится, т. е. примет значение "Пройдено", и в другой оценке, если только обе эти оценки принадлежат к одной группе оценок.
  
Например, рассмотрим два связанных средства контроля, которые относятся к шифрованию данных в общедоступных сетях: 6.10.1.2 в оценке "Office 365 — GDPR" и SC-13 в оценке "Office 365 — NIST" 800-53. Это связанные средства контроля в двух различных оценках, относящихся к группе по умолчанию. Изначально ни одна из этих оценок не была пройдена, как показано на панели мониторинга диспетчера соответствия требованиям.
  
![Информационная панель в диспетчере соответствия требованиям: сгруппированные оценки — до](../media/dc0126a3-415c-4fbe-a020-1806dd1caebd.png)
  
Выбрав оценку **Office 365 — GDPR** и применив фильтр для просмотра средства контроля GDPR 6.10.1.2, мы увидим, что средство контроля SC-13 для стандарта NIST 800-53 указано в качестве связанного.
  
![Оценка в диспетчере соответствия требованиям — общие средства контроля](../media/aafb106e-0abc-4918-8038-de11cf326dfe.png)
  
 Здесь показано завершение реализации и тестирования средства контроля GDPR 6.10.1.2. 
  
![Диспетчер соответствия требованиям: средство контроля оценки GDPR 6.10.1.2 — проверка пройдена](../media/ee9e83b6-9d51-4b3b-85eb-96bec0fef2e1.png)
  
Перейдем к связанному средству контроля в оценке из этой группы и увидим, что средство контроля NIST 800-53 SC-13 также отмечено как завершенное, а указаны те же дата и время. При этом не потребовалось дополнительных усилий для реализации или тестирования.
  
![Оценка в диспетчере соответствия требованиям — средство контроля NIST 800-53 SC(13) проверено](../media/b5933592-db5a-4fdd-9be2-bba777646a88.png)
  
Снова открыв информационную панель, мы увидим, что для каждой оценки завершена проверка одного средства контроля, а общий рейтинг соответствия требованиям для каждой оценки увеличился на 8 (рейтинг соответствия требованиям для этого общего средства контроля).
  
![Информационная панель в диспетчере соответствия требованиям — синхронизация хода выполнения сгруппированной оценки](../media/727f1203-b98d-4a03-a7af-e9236f4c5534.png)

## <a name="administrative-functions"></a>Административные функции

Некоторые административные функции доступны только учетной записи администратора клиента и будут видны, только если войти от имени глобального администратора.
  
> [!NOTE]
> The Access to Restricted Documents permission in the drop-down list will allow administrators to give users access to restricted documents that Microsoft shares on the Service Trust Portal. The Restricted Documents feature isn't available, but is coming soon. 
  
### <a name="assigning-compliance-manager-roles-to-users"></a>Назначение пользователям ролей в диспетчере соответствия требованиям

Each Compliance Manager role has slightly different permissions. You can view the permissions assigned to each role, see which users are in which roles, and add or remove users from that role through the Service Trust Portal by selecting the **Admin** menu item, and then choosing **Settings**. 
  
![Меню "Администратор" на портале STP — выбранные параметры](../media/65a82b1b-d462-452f-988b-7e4263bd638e.png)
  
Чтобы добавить или удалить пользователей из роли в диспетчере соответствия требованиям, выполните указанные ниже действия.
  
1. Перейдите по ссылке [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com).
    
2. Войдите с помощью учетной записи глобального администратора Azure Active Directory.
    
3. В верхней строке меню Service Trust Portal выберите пункт **Администратор**, а затем — **Параметры**. 
    
4. В раскрывающемся списке **Выберите роль** щелкните нужную роль. 
    
5. Пользователи, добавленные к каждой роли, указаны на странице **Выбор роли**. 
    
6. To add users to this role, click **Add**. In the **Add Users** dialog, click the user field. You can scroll through the list of available users or begin typing the user name to filter the list based on your search term. Click the user to add that account to the **Add Users** list to be provisioned with that role. If you would like to add multiple users concurrently, begin typing a user name to filter the list, and then click the user to add to the list. Click **Save** to provision the selected role to these users. 
    
    ![Подготовка ролей в диспетчере соответствия требованиям — добавление пользователей](../media/2f386f82-2bf8-4e95-ab41-1724b752b508.png)
  
7. Чтобы удалить пользователей из этой роли, выберите их и нажмите кнопку **Удалить**. 
    
    ![Подготовка ролей в диспетчере соответствия требованиям — удаление пользователей](../media/17004def-604f-471d-a54d-f678fcc01c1e.png)
 
## <a name="user-privacy-settings"></a>Параметры конфиденциальности пользователей

Certain regulations require that an organization must be able to delete user history data. To enable this, Compliance Manager provides the **User Privacy Settings** functions, that allow administrators to: 
  
- [искать пользователей;](#search-for-a-user)

- [экспортировать отчет о журнале данных учетных записей;](#export-a-report-of-account-data-history)

- [переназначать поручения;](#reassign-action-items)

- [удалять журналы данных пользователей.](#delete-user-data-history)
    
![Администрирование диспетчера соответствия требованиям — параметры конфиденциальности пользователей](../media/067d6c6a-712a-4dc2-9b99-de2fa4417dc3.png)
  
### <a name="search-for-a-user"></a>Поиск пользователя

Чтобы найти учетную запись, выполните указанные ниже действия.
  
1. Укажите адрес электронной почты пользователя, введя его псевдоним (текст слева от символа @) и выбрав имя домена в списке справа. В случае клиента с несколькими зарегистрированными доменами рекомендуем перепроверить имя домена в адресе электронной почты.
    
2. Правильно указав имя пользователя, нажмите кнопку **Поиск**. 
    
3. If the user account is not found, the error message 'User not found' will be displayed on the page. Check the user's email address information, make corrections as necessary and click **Search** to try again. 
    
4. Если учетная запись пользователя найдена, подпись кнопки **Поиск** изменится на **Очистить**. Это означает, что найденная учетная запись пользователя является рабочим контекстом для дополнительных функций, которые показаны ниже, а работа этих функций будет распространяться на данную учетную запись. 
    
5. Чтобы очистить результаты поиска и найти другого пользователя, нажмите кнопку **Очистить**. 
    
### <a name="export-a-report-of-account-data-history"></a>Экспорт отчета о журнале данных учетной записи

Когда учетная запись пользователя найдена, вы можете создать отчет о связанных с ней зависимостях. Эти сведения помогут вам переназначить открытые элементы действий или получить доступ к ранее отправленным доказательствам. 
  
 Чтобы создать и экспортировать отчет, выполните указанные ниже действия.
  
1. Нажмите кнопку **Экспорт**, чтобы создать и скачать отчет об элементах действий средств контроля в диспетчере соответствия требованиям, которые сейчас назначены найденной учетной записи пользователя, и список документов, отправленных этим пользователем. Если назначенные действия и отправленные документы отсутствуют, появится сообщение о том, что таких данных нет. 
    
2. Отчет скачивается в фоновом режиме активного окна браузера. Если всплывающее окно загрузки не отображается, следует проверить журнал загрузок браузера.
    
3. Откройте документ, чтобы просмотреть данные отчета.
    
> [!NOTE]
> This is not a historical report that retains and displays state changes to action item assignment history. The generated report is a snapshot of the control action items assigned at the time that the report is run (date and time stamp written into the report). For instance, any subsequent reassignment of action items will result in different snapshot report data if this report is generated again for the same user. 
  
### <a name="reassign-action-items"></a>Переназначение поручений

This function enables an organization to remove any active or outstanding dependencies on the user account by reassigning all action item ownership (which includes both active and completed action items) from the returned user account to a new user selected below. This action does not change document upload history for the returned user account. 
  
 Чтобы переназначить поручения другому пользователю, выполните указанные ниже действия.
  
1. Щелкните поле ввода, чтобы найти и выбрать другого пользователя в организации, которому следует назначить поручения найденного пользователя.
    
2. Нажмите **Заменить**, чтобы переназначить все поручения найденного пользователя новому выбранному пользователю. 
    
3. Откроется диалоговое окно подтверждения с текстом "Все элементы действий управления будут переназначены выбранному пользователю. Это действие невозможно отменить. Продолжить?"
    
4. Если вы хотите продолжить, нажмите кнопку **ОК**. В противном случае нажмите кнопку **Отмена**. 
    
> [!NOTE]
> All action items (both active and completed) will be assigned to the newly selected user. However, this action does not affect the document upload history; any documents uploaded by the previously assigned user will still show the date/time and name of the previously assigned user. 
  
Changing the document upload history to remove the previously assigned user will have to be done as a manual process. In that case, the administrator will need to:
  
1. Открыть загруженный ранее отчет об экспорте.
  
2. Определить нужное поручение и перейти к нему.
  
3. Выбрать **Управление документами**, чтобы перейти к репозиторию свидетельств для этого средства контроля. 
  
4. Скачать документ.
  
5. Удалить документ их репозитория свидетельств.
  
6. Re-upload the document. The document will now have a new upload date, time and Uploaded By username. 
  
### <a name="delete-user-data-history"></a>Удаление журнала данных пользователя

This sets control action items to 'unassigned' for all action items assigned to the returned user. This also sets uploaded by value to 'user removed' for any documents uploaded by the returned user
  
 Чтобы удалить журнал поручений и отправки документов для учетной записи, выполните указанные ниже действия.
  
1. Нажмите кнопку **Удалить**. 

    A confirmation dialog will be displayed, stating "This will remove all control action item assignments and the document upload history for the selected user. This action cannot be undone. Are you sure you want to continue?"
    
3. Если вы хотите продолжить, нажмите кнопку **ОК**. В противном случае нажмите кнопку **Отмена**. 
  
## <a name="using-compliance-manager"></a>Использование диспетчера соответствия требованиям

Диспетчер соответствия требованиям предоставляет инструменты, с помощью которых можно назначать, отслеживать и записывать действия, связанные с оценкой и обеспечением соответствия требованиям, помогая координировать работу команд в организации для достижения ее целей.
  
![Информационная панель в диспетчере соответствия требованиям: верхнее меню — обновленное меню администрирования](../media/134d7577-cd70-4124-bcfd-d3feb248952b.png)

## <a name="accessing-compliance-manager"></a>Доступ к диспетчеру соответствия требованиям

You access Compliance Manager from the Service Trust Portal. Anyone with a Microsoft account or Azure Active Directory organizational account can access Compliance Manager.
  
![Диспетчер соответствия требованиям — доступ к диспетчеру соответствия требованиям из меню STP](../media/14be4cac-2380-49bc-9b36-210da8cafdfa.png)
  
1. Перейдите по ссылке [https://servicetrust.microsoft.com](https://servicetrust.microsoft.com/).
    
2. Войдите с помощью учетной записи пользователя Azure Active Directory (Azure AD).
    
3. На портале Service Trust Portal выберите **Диспетчер соответствия требованиям**. 
    
4. When the Non-Disclosure Agreement is displayed, read it, and then click **Agree** to continue. You'll only have to do this once, and then the Compliance Manager dashboard is displayed. 

    Чтобы помочь вам приступить к работе, мы добавили по умолчанию следующие оценки:
    
    ![Стандартные оценки в диспетчере соответствия требованиям](../media/8c59b45a-706a-4362-a7ba-2cb782931bf7.png)
    
5. Нажмите значок ![Значок справки в диспетчере соответствия требованиям](../media/c1b3092f-6ac7-43ab-b1c4-63a54598450c.png) **Справка**, чтобы просмотреть краткий обзор диспетчера соответствия требованиям. 
  
## <a name="viewing-action-items"></a>Просмотр поручений

В диспетчере соответствия требованиям есть удобное представление всех назначенных вам поручений, связанных со средствами контроля, в котором можно легко и быстро выполнять нужные действия. Можно просмотреть все поручения или выбрать те из них, которые связаны с определенной сертификацией, открыв соответствующую вкладку. Например, на приведенном ниже рисунке выбрана вкладка GDPR, на которой показаны средства контроля, связанные с оценкой GDPR.
  
![Диспетчер соответствия требованиям — список поручений с выбранной вкладкой GDPR](../media/ba960f5c-becb-4d95-a000-d08ec77b7b46.png)
  
Чтобы просмотреть свои поручения, выполните указанные ниже действия.
  
1. Откройте информационную панель диспетчера соответствия требованиям
    
2. Перейдите по ссылке **Поручения**, и страница обновится, после чего вы увидите назначенные вам поручения. 
    
    By default, all action items are shown. If you have action items across multiple certifications, the names of the certifications will be listed in tabs across the top of the assessment control. To see the action items for a specific certification, click that tab.

## <a name="adding-an-assessment"></a>Добавление оценки

Чтобы добавить оценку в диспетчер соответствия требованиям, выполните указанные ниже действия.
  
1. На информационной панели в диспетчере соответствия требованиям нажмите ![Значок добавления](../media/ITPro-EAC-AddIcon.gif) **Добавить оценку**. 
    
2. In the **Add an Assessment** window, you can create a new group to add the Assessment to or you can add it to an existing group (the built-in group is named "Initial Group".) Depending on the option you choose, either type the name of a new group or select an existing group from the drop-down list. For more information, see [Grouping Assessments](#grouping-assessments).
    
    При создании группы также можно скопировать информацию из существующей группы в новую оценку. Это означает, что информация из полей "Сведения о реализации", "План тестирования" и "Отклик функции управления" средств контроля, управляемых клиентом, для оценок в группе, из которой вы копируете сведения, копируется в те же (или связанные) средства контроля, управляемые клиентом, в новой оценке. Если вы добавляете новую оценку в существующую группу, общая информация об оценках в этой группе копируется в новую оценку. Дополнительные сведения см. в разделе [Копирование информации из существующих оценок](#copying-information-from-existing-assessments).
    
3. Нажмите кнопку **Далее** и выполните указанные ниже действия.
    
    а. Выберите облачную службу Майкрософт для оценки соответствия требованиям в раскрывающемся списке **Выбор продукта**. 
    
    б. Выберите сертификацию для оценки выбранной облачной службы в раскрывающемся списке **Выбор сертификации**. 
    
4. Нажмите **Добавить на панель мониторинга**, чтобы создать оценку. Она будет добавлена на информационную панель диспетчера соответствия требованиям в качестве новой плитки в конце списка имеющихся плиток. 
    
    **Плитка оценки** на информационной панели в диспетчере соответствия требованиям содержит названия группы и оценки (последнее автоматически создается путем объединения имени службы с выбранным стандартом сертификации), даты ее создания и последнего изменения, общий рейтинг соответствия требованиям (представляющий собой сумму значений риска для всех реализованных, протестированных и прошедших оценку средств контроля), а также индикаторы хода выполнения вдоль нижнего края, показывающие количество средств контроля, прошедших оценку. 
    
5. Нажмите имя оценки, чтобы открыть ее и просмотреть сведения о ней.
    
6. Откройте меню **Действия**, чтобы просмотреть назначенные вам поручения, переименовать группу оценок, экспортировать отчет об оценивании или архивировать оценку. 
    
    ![Диспетчер соответствия требованиям — плитка оценки](../media/abf35c11-9757-45c1-aa14-91178f67a18c.png)

## <a name="copying-information-from-existing-assessments"></a>Копирование сведений из имеющихся оценок

Как было сказано выше, при создании группы оценок можно скопировать информацию об оценках из существующей группы в новую оценку. Это позволяет применить оценку и выполненную работу по тестированию для таких же средств контроля, управляемых клиентом, в новой оценке. Например, если у вас есть группа для всех оценок в организации, связанных со стандартом GDPR, вы можете скопировать общую информацию из существующих сведений об оценке во время добавления новой оценки в группу.
  
Вы можете скопировать в новую оценку следующие сведения от клиента:
  
- Assessment Users. An Assessment user is a user who the control is assigned to.
    
- Состояние, дата и результаты тестирования.
    
- Сведения о реализации и плане тестирования.
    
Аналогичным образом синхронизируется информация из общих средств контроля, управляемых клиентом, в одной группе оценок. Также синхронизируется информация в связанных средствах контроля, управляемых клиентом, в той же оценке.

## <a name="viewing-assessments"></a>Просмотр оценок

1. Найдите плитку нужной оценки, а затем щелкните ее имя, чтобы открыть оценку и просмотреть связанные с ней средства контроля под управлением Майкрософт и клиента, а также список облачных служб, на которые распространяется оценка. Ниже приведен пример оценки для Office 365 и GDPR.
    
    ![Представление оценки в диспетчере соответствия требованиям — полноэкранный режим с выносками](../media/169a02eb-e805-412d-b9e7-89561aa7ad1d.png)
  
1. В этом разделе показаны сводные данные об оценке, в том числе имя группы и оценки, а также количество средств контроля.
    
2. This section shows the Assessment Filter controls. For a more detailed explanation of how to use the Assessment Filter controls see the [Managing the assessment process](#managing-the-assessment-process) section. 
    
3. В этом разделе показаны отдельные облачные службы, на которые распространяется оценка.
    
4. Этот раздел содержит средства контроля, управляемые Майкрософт. Связанные средства контроля сгруппированы в семейства. Щелкните семейство, чтобы развернуть его и отобразить отдельные средства контроля.
    
5. Этот раздел содержит клиентские средства контроля, которые также организованы в семейства. Щелкните семейство, чтобы развернуть его и отобразить отдельные средства контроля.
    
6. Общее число средств контроля в семействе и количество оцениваемых средств. Примечательная особенность диспетчера соответствия требованиям — возможность отслеживать ход оценки средств контроля, управляемых клиентом. Дополнительные сведения см. в разделе [Сведения о рейтинге соответствия требованиям](#understanding-the-compliance-score). 

## <a name="managing-the-assessment-process"></a>Управление процессом оценки

Создатель оценки изначально является ее единственным пользователем. Для каждого клиентского средства контроля можно назначить поручение сотруднику организации, чтобы он стал пользователем оценки и смог выполнять рекомендуемые действия, а также собирать и добавлять доказательства. При назначении поручения вы можете отправить сообщение электронной почты, в котором указаны рекомендуемые действия и приоритет. Уведомление включает ссылку на панель мониторинга **Поручения**, где перечислены все поручения, назначенные этому лицу. 
  
Ниже представлен список задач, которые можно выполнять с помощью функций рабочих процессов в диспетчере соответствия требованиям.
  
![Рабочий процесс оценки с выносками в диспетчере соответствия требованиям](../media/9e5ae34d-b55e-4452-a021-e0e5b10218f5.png)
  
1. **Использование параметров фильтра для поиска определенных средств контроля оценки.** Диспетчер соответствия требованиям предоставляет **параметры фильтра**, позволяющие указывать детальные условия для выбора отображаемых средств контроля, помогая точно выделять определенные области вашей деятельности по обеспечению соответствия требованиям. 
    
    Щелкните значок воронки в правой части страницы, чтобы показать или скрыть **параметры фильтрации**. Укажите условия фильтрации, и ниже будут выведены только средства контроля, которые соответствуют им. ![Оценки в диспетчере соответствия требованиям: фильтрация средств контроля](../media/d44e1b4b-d928-4778-8a3a-6231edde9ca0.png)
  
    - **Статьи**: фильтрует данные по названию статьи и возвращает только средства контроля, связанные с ней. Например, если ввести "Article (5)", появится список статей, названия которых включают в себя эту строку, например Article (5)(1)(a), Article (5)(1)(b), Article (5)(1)(c) и т. д. При выборе статьи Article (5)(1)(c) будут выведены средства контроля, связанные с этой статьей. Это поле множественного выбора, в котором значения соединяются с помощью оператора ИЛИ, то есть если выбрать статью Article (5)(1)(a) и добавить Article (5)(1)(c), фильтр вернет средства контроля, связанные с любой из этих статей. 
    
      ![Представление оценки в диспетчере соответствия требованиям — фильтр по названию статьи](../media/8b0507a0-589d-484a-bc60-80a3debe3ddb.png)
  
    - **Средства контроля.** Возвращает список средств контроля, названия которых соответствуют фильтру. Например, если ввести 7.3, возвращается список выбора с такими элементами, как 7.3.1, 7.3.4, 7.3.5 и т. д. Это поле множественного выбора, в котором используется оператор ИЛИ с несколькими значениями. Например, если выбрать значение 7.3.1, а затем добавить значение 7.3.4, то фильтр вернет средства контроля, связанные со средством контроля 7.3.1 или 7.3.4. 
    
      ![Диспетчер соответствия требованиям, представление оценок — поле множественного выбора для фильтра средств контроля](../media/c4fc25e8-2376-4f2d-b605-f9c3d90413bf.png)
  
    - **Назначенные пользователи.** Возвращает список средств контроля, назначенных выбранному пользователю. 
    
    - **Состояние.** Возвращает список средств контроля с выбранным состоянием. 
    
    - **Результат тестирования.** Возвращает список средств контроля с выбранным результатом тестирования. 
    
    As you apply filter conditions, the view of applicable controls will change to correspond to your filter conditions. Expand the control family sections to show the control details below. 
    
    ![Представление оценки в диспетчере соответствия требованиям: фильтр по результату тестирования для статьи](../media/e6485d45-d47f-4b25-8b1c-b3c2ee4a8328.png)
  
2. If after selecting the desired filters no results are shown, that means there are no controls that correspond to the specified filter conditions. For instance, if you select a particular **Assigned User** and then choose a **Control** name that does correspond to the control assigned to that user, no assessments will be shown in the page below. 
    
3. **Assign an Action Item to a user** - You can assign an Action Item to a person to implement the requirements of a certification/regulation, or to test, verify, and document your organization's implementation requirements. When you assign an Action Item, you can choose to send an email to the person that contains details including the recommended Customer Actions and the Action Item priority. You can also unassign or reassign an Action Item to a different person. 
    
4. **Управление документами**. Для клиентских средств контроля также можно управлять документами, которые относятся к задачам реализации, тестирования и проверки. Любой пользователь с разрешением на изменение данных в диспетчере соответствия требованиям может добавить документы, нажав кнопку **Управление документами**. После добавления документа можно нажать кнопку **Управление документами**, чтобы просмотреть или скачать файлы. 
    
5. **Предоставление сведений о реализации и тестировании.** Каждое средство контроля под управлением клиента также содержит редактируемое поле, где пользователи могут добавлять сведения о реализации, которые описывают принятые в организации меры по обеспечению соответствия требованиям стандарта сертификации или норматива, а также проверке и документированию соответствия требованиям в организации.
    
6. **Set Status** - Set the Status for each item as part of the assessment process. Available status values are **Implemented**, **Alternative Implementation**, **Planned**, and **Not in Scope**. 
    
7. **Ввод даты и результатов тестирования.** Пользователь с ролью аудитора может подтвердить правильность тестирования, изучить сведения о реализации, план тестирования, результаты тестирования и все добавленные доказательства, а затем указать дату и результат тестирования. Доступные результаты тестирования: **Passed** (Пройдено), **Failed-Low Risk** (Не пройдено, низкий риск), **Failed-Medium Risk** (Не пройдено, средний риск) и **Failed-High Risk** (Не пройдено, высокий риск). 

## <a name="managing-action-items"></a>Управление поручениями

Сотрудники, которые участвуют в процессе оценки, могут просматривать в диспетчере клиентские средства контроля для всех оценок, пользователями которых они являются. Когда пользователь входит в диспетчер соответствия требованиям и открывает панель мониторинга **Поручения**, отображается список поручений, назначенных ему. В зависимости от роли пользователя он может ввести сведения о реализации или тестировании, обновить статус или назначить поручения. 
  
As certification controls are generally implemented by one person and tested by another, the control action item can be initially assigned to one person for implementation, and once that is complete, that person can reassign the control action item to the next person for control testing and uploading of evidence. This assignment/reassignment of control actions can be performed by any users who have a Compliance Manager role with sufficient permissions, allowing for central management of control assignments, or decentralized routing of control action items, from implementer to tester as appropriate.
  
Чтобы назначить поручение, выполните указанные ниже действия.
  
1. На информационной панели в диспетчере соответствия требованиям найдите плитку нужной оценки и щелкните ее название, чтобы перейти на страницу сведений об оценке.
    
2. Вы можете выбрать **Фильтр** и использовать элементы управления фильтром, чтобы найти нужное средство контроля. 
    
3. Вы также можете прокрутить вниз до раздела "Средства контроля под управлением клиента", развернуть семейство средств контроля и прокручивать список, пока не найдете нужное средство.
    
4. В столбце **Назначенный пользователь** нажмите кнопку **Назначить**. 
    
5. In the Assign Action Item dialog box, click the **Assign To** field to populate the list of users to whom the action can be assigned. You can scroll through the list to find the target user or start typing in the field to search for the username. 
    
6. Выберите пользователя, чтобы назначить ему это поручение.
    
7. Если вы хотите отправить пользователю уведомление электронной почты, убедитесь, что установлен флажок **Отправить уведомление по электронной почте**. 
    
8. Введите примечания, которые должны отображаться для этого пользователя, и нажмите кнопку **Назначить**. 
 
    Пользователь получит уведомление о том, что ему назначено поручение, и предоставленные вами примечания.
    
The notes that are associated with the action item are persisted in the notes section, available for the next time the action item is assigned. These notes are not read-only, can be edited, replaced or removed by the person assigning the action item.

## <a name="exporting-information-from-an-assessment"></a>Экспорт сведений из оценки

Оценку можно экспортировать в файл Excel, предназначенный для заинтересованных лиц в вашей организации, а также аудиторов и контролирующих органов. Такой отчет, представляющий собой моментальный снимок оценки на дату и время его создания, содержит сведения о средствах контроля, управляемых Майкрософт и клиентом, в том числе о состоянии их реализации, дате и результатах тестирования, а также ссылки на добавленные документы доказательств. Рекомендуется экспортировать отчет об оценке перед ее архивацией, так как в архивированных оценках не сохраняются ссылки на добавленные документы.
  
Чтобы экспортировать отчет об оценке, выполните указанные ниже действия.
  
- На информационной панели нажмите **Действия** на плитке нужной оценки, а затем выберите **Экспорт в Excel**

  или
    
- Если открыта страница сведений об оценке, нажмите кнопку **Экспорт в Excel**, расположенную в правом верхнем углу страницы над рейтингом соответствия требованиям для этой оценки.
    
The assessment report will be downloaded in your browser session. If you don't see a popup informing you of this, you may wish to check your browser's downloads folder.

## <a name="archiving-an-assessment"></a>Архивация оценки

When you have completed an Assessment and no longer need it for compliance purposes, you can archive it. When an Assessment is archived, it is removed from Assessments dashboard.
  
> [!NOTE]
> When an Assessment is Archived, it cannot be 'unarchived' or restored to a read-write in progress state. Please note that Archived Assessments do not retain their links to uploaded evidence documents, so it is highly recommended that you perform an Export of the Assessment before archiving it, as the exported assessment report will contain links to the evidence documents, enabling you to continue to access them. 
  
Чтобы архивировать оценку, выполните указанные ниже действия.
  
1. На плитке нужной оценки на информационной панели нажмите **Действия**. 
    
2. Выберите команду **Архивировать оценку**. 
 
    Откроется диалоговое окно **Архивирование оценок**, где предлагается подтвердить архивацию оценки.
    
4. Если вы хотите продолжить архивацию, нажмите **Архивировать**. В противном случае нажмите кнопку **Отмена**. 
    
Чтобы просмотреть архивированные оценки, выполните указанные ниже действия.
  
1. На информационной панели в диспетчере соответствия требованиям установите флажок **Показать архивированные**. 
    
    Архивированные оценки появятся в новом разделе под остальными активными оценками под заголовком **Архивированные оценки**.
    
3. Выберите имя нужной оценки.
    
При просмотре архивированной оценки все элементы управления, обычно доступные для редактирования (т. е. "Реализация", "Результаты тестирования"), будут неактивны, а кнопка **Управление документами** не будет отображаться.

## <a name="using-search"></a>Использование поиска

![Service Trust Portal: поле для ввода поисковых запросов](../media/7c5cd817-3d62-420b-adb4-76e33fef941f.png)
  
Click the magnifying glass in the upper right-hand corner of the page by to expand the Search input field, enter your search terms and press Enter. The Search control will appear, with the search term in the search pane input field, and search results will appear beneath.
  
By default, Search returns Document results, and you can use the Filter By dropdown lists to refine the list of documents displayed, to add or remove search results from view. You can use multiple filter attributes at the same time to narrow the returned documents to specific cloud services, categories of compliance or security practices, regions of the world, or industries. Click the document name link to download the document.
  
![Service Trust Portal: поиск документов с примененным фильтром](../media/86b754e1-c63c-4514-89ac-d014bf334140.png)
  
Щелкните ссылку диспетчера соответствия требованиям, чтобы отобразить результаты поиска для средств контроля оценки диспетчера соответствия требованиям. В списке результатов поиска показана дата создания оценки, имя группы оценки, применяемая облачная служба и под чьим управлением (Майкрософт или клиента) находятся средства контроля.
  
![Service Trust Portal: поиск по средствам контроля в диспетчере соответствия требованиям](../media/bafb811a-68ce-40b5-ad16-058498fe5439.png)
  
> [!NOTE]
> Отчеты и документы Service Trust Portal доступны для скачивания в течение как минимум двенадцати месяцев после публикации или до тех пор, пока не станет доступна новая версия документа. 
 
## <a name="localization-support"></a>Поддержка локализации

Service Trust Portal enables you to view the page content in different languages. To change the page language, simply click on the globe icon in the lower left corner of the page and select the language of your choice. 
  
![Service Trust Portal: локализованные варианты содержимого](../media/b50c677e-a886-4267-9eca-915d880ead7a.png)


## <a name="change-log-for-customer-managed-controls"></a>Журнал изменений средств контроля под управлением клиента

Диспетчер соответствия требованиям рассчитан на регулярное обновление в соответствии с изменениями нормативных требований и наших облачных служб. Эти обновления включают изменения правил, которыми управляет клиент. Журнал изменений позволяет понимать, какое влияние они оказывают, а также содержит подробные сведения о добавленном или измененном содержимом и влиянии этих изменений на существующие оценки. В целом выделяют два типа изменений:
  
- A **Major** change is a significant change to a Customer Action, such as the addition or removal of a control or specific numbered steps, or a change in the guidance around responsibilities, recommendations, or evidence. For Major changes, we recommend that you re-evaluate your implementation and/or assessment of the affected control.
    
- A **Minor** change is an insignificant change to a Customer Actions, such as fixing a typo or formatting issues, or updating or correcting hyperlinks. Minor changes generally do not require the control to be re-evaluated; however, we do recommend that you review the updated Customer Action.
  
### <a name="customer-managed-controls---change-log-for-july-2018"></a>Средства контроля под управлением клиента — журнал изменений за июль 2018 г.

|**ИД средства контроля**|**Оценка**|**Тип изменения**|**Описание изменения**|**Рекомендуемые действия для клиентов**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|45 C.F.R. § 164.308(a)(7)(ii)(A)<br/> |Office 365: HIPAA|Значительное|Добавлено средство контроля HITECH к оценке HIPAA для Office 365 |Проверьте добавленное средство контроля и рекомендуемые действия клиента.<br/> |
|45 C.F.R.  164.312(a)(6)(ii)|Office 365: HIPAA|Значительное|Добавлено средство контроля HITECH к оценке HIPAA для Office 365|Проверьте добавленное средство контроля и рекомендуемые действия клиента.<br/>|
45 C.F.R. § 164.312(c)(1)| Office 365: HIPAA|Значительное| Добавлено средство контроля HITECH к оценке HIPAA для Office 365 |Проверьте добавленное средство контроля и рекомендуемые действия клиента.<br/> |
45 C.F.R.  § 164.316(b)(2)(iii)| Office 365: HIPAA|Значительное|Добавлено средство контроля HITECH к оценке HIPAA для Office 365|Проверьте добавленное средство контроля и рекомендуемые действия клиента.<br/>|
|

### <a name="customer-managed-controls---change-log-for-april-2018"></a>Средства контроля под управлением клиента — журнал изменений за апрель 2018 г.

|**GDPR**|**HIPAA**|**ISO 27001**|**ISO 27018**|**NIST 800-53**|**NIST 800-171**|**Тип изменения**|**Описание изменения**|**Рекомендуемые действия для клиентов**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|6.13.2  <br/> |||C.16.1.1  <br/> |||Значительное  <br/> |Предыдущий номер: 6.12.1.1.  <br/> В рекомендации добавлены подробности.  <br/> |Повторно оцените средство контроля: ознакомьтесь с обновленными рекомендациями по действиям клиента и выполните рекомендации по реализации и оценке средства контроля.  <br/> |
||||||3.1.6  <br/> |Значительное  <br/> |В рекомендации добавлены действия по включению аудита и поиску в журнале аудита.  <br/> |Ознакомьтесь с обновленными рекомендациями по действиям клиента.  <br/> |
|6.8.2  <br/> |||A.10.2  <br/> |||Значительное  <br/> |Предыдущий номер: 6.7.2.9.  <br/> Добавлены новые рекомендации и поручения.  <br/> |Повторно оцените средство контроля: ознакомьтесь с обновленными рекомендациями по действиям клиента и выполните рекомендации по реализации и оценке средства контроля.  <br/> |
|6.6.4  <br/> |45 C.F.R. § 164.312(a)(2)(i)  <br/>           45 C.F.R. § 164.312(d)  <br/> |A.9.4.2  <br/> ||IA-2  <br/> |3.5.1  <br/> |Значительное  <br/> |Предыдущий номер: 6.5.2.3.  <br/> Добавлены новые рекомендации и поручения.  <br/> |Повторно оцените средство контроля: ознакомьтесь с обновленными рекомендациями по действиям клиента и выполните рекомендации по реализации и оценке средства контроля.  <br/> |
|6.13.1  <br/> |45 C.F.R. § 164.308(a)(1)(i)  <br/> |A.16.1  <br/> |C.16.1  <br/> |IR-4(a)  <br/> |3.6.1  <br/> |Значительное  <br/> |Предыдущий номер: 6.12.1.  <br/> Добавлены новые рекомендации и поручения.  <br/> |Повторно оцените средство контроля: ознакомьтесь с обновленными рекомендациями по действиям клиента и выполните рекомендации по реализации и оценке средства контроля.  <br/> |
|6.7  <br/> ||||||Значительное  <br/> |Предыдущий номер: 6.6.1.1.  <br/> Добавлены новые рекомендации и поручения.  <br/> |Повторно оцените средство контроля: ознакомьтесь с обновленными рекомендациями по действиям клиента и выполните рекомендации по реализации и оценке средства контроля.  <br/> |
|6.6.5  <br/> |||A.10.8  <br/> |IA-3  <br/> |3.5.2  <br/> |Значительное  <br/> |Предыдущий номер: 6.5.4.2.  <br/> Добавлены новые рекомендации и поручения.  <br/> |Повторно оцените средство контроля: ознакомьтесь с обновленными рекомендациями по действиям клиента и выполните рекомендации по реализации и оценке средства контроля.  <br/> |
|6.15.1  <br/> ||||||Значительное  <br/> |Предыдущий номер: 6.14.1.3.  <br/> Добавлены новые рекомендации и поручения.  <br/> |Повторно оцените средство контроля: ознакомьтесь с обновленными рекомендациями по действиям клиента и выполните рекомендации по реализации и оценке средства контроля.  <br/> |
|||||AC-2(h)(2)  <br/> ||Незначительное  <br/> |Добавлена ссылка на колонку "Включить аудит".  <br/> |Никаких действий не требуется.  <br/> |
|||||AC-2(7)(b)  <br/> ||Незначительное  <br/> |Добавлена ссылка на колонку "Включить аудит".  <br/> |Никаких действий не требуется.  <br/> |
|||||AC-2(h)(1)  <br/> ||Незначительное  <br/> |Добавлена ссылка на колонку "Включить аудит".  <br/> |Никаких действий не требуется.  <br/> |
||45 C.F.R. § 164.308(a)(5)(ii)(C)  <br/> |||AC-2(g)  <br/> ||Незначительное  <br/> |Добавлена ссылка на колонку "Включить аудит".  <br/> |Никаких действий не требуется.  <br/> |
|||||AC-2(12)  <br/> ||Незначительное  <br/> |Добавлена ссылка на колонку "Включить аудит".  <br/> |Никаких действий не требуется.  <br/> |
||45 C.F.R. § 164.312(b)  <br/> |A.12.4.3  <br/> ||AU-2(d)  <br/> ||Незначительное  <br/> |Добавлена ссылка на колонку "Включить аудит".  <br/> |Никаких действий не требуется.  <br/> |
|||||AC-2(4)  <br/> ||Незначительное  <br/> |Добавлена ссылка на колонку "Включить аудит".  <br/> |Никаких действий не требуется.  <br/> |
||||||3.1.7  <br/> |Незначительное  <br/> |Добавлена ссылка на колонку "Включить аудит".  <br/> |Никаких действий не требуется.  <br/> |
|||A.16.1.7  <br/> |C.12.4.2, часть 2  <br/> |||Незначительное  <br/> |Добавлена ссылка на колонку "Включить аудит".  <br/> |Никаких действий не требуется.  <br/> |
|||||AC-2(h)(3)  <br/> ||Незначительное  <br/> |Добавлена ссылка на колонку "Включить аудит".  <br/> |Никаких действий не требуется.  <br/> |
|||A.12.4.2  <br/> ||||Незначительное  <br/> |Добавлена ссылка на колонку "Включить аудит".  <br/> |Никаких действий не требуется.  <br/> |
|||A.7.2.8  <br/> ||||Незначительное  <br/> |Добавлены ссылки на колонку "Поиск контента" и портал DSR.  <br/> |Никаких действий не требуется.  <br/> |
||45 C.F.R. § 164.308(a)(3)(ii)(C)  <br/> |||||Незначительное  <br/> |Добавлены ссылки на колонку "Включить аудит" и справочные статьи по роли администратора Office 365.  <br/> |Никаких действий не требуется.  <br/> |
|5.2.1  <br/> ||||||Незначительное  <br/> |Предыдущий номер: 5.2.2.  <br/> В рекомендациях уточнены обязанности клиента.  <br/> |Ознакомьтесь с обновленными рекомендациями по действиям клиента.  <br/> |
|6.11.1  <br/> |45 C.F.R. § 164.312(e)(2)(ii)  <br/> |A.10.1.1          A.10.1.2          A.18.1.5  <br/> |C.10.1.1  <br/> |SC-13  <br/> |3.13.11  <br/> |Незначительное  <br/> |Предыдущий номер: 6.10.1.2.  <br/> Исправлена опечатка.  <br/> |Никаких действий не требуется.  <br/> |
|7.5.1  <br/> ||||||Незначительное  <br/> |Предыдущий номер: A.7.4.1.  <br/> Исправлена опечатка.  <br/> |Никаких действий не требуется.  <br/> |
|||A.8.2.3  <br/> |||3.1.3  <br/> |Незначительное  <br/> |Удалено лишнее предложение.  <br/> |Никаких действий не требуется.  <br/> |
||45 C.F.R. § 164.308(a)(4)(i)  <br/> |A.6.1.2  <br/> ||AC-5(a)  <br/> |3.1.2          3.1.4  <br/> |Незначительное  <br/> |Добавлены новые рекомендации и поручения.  <br/> |Ознакомьтесь с обновленными рекомендациями по действиям клиента.  <br/> |
||45 C.F.R. § 164.308(a)(7)(ii)(E)  <br/> |||RA-2(a)  <br/> ||Незначительное  <br/> |Ссылка на раздел справки, посвященный службе импорта, обновлена с использованием FWLink.  <br/> |Никаких действий не требуется.  <br/> |
|

### <a name="gdpr-assessment-control-id-change-reference---change-log-for-february-2018"></a>Справка по изменению ИД средств контроля GDPR: журнал изменений за февраль 2018 г. 

|**Предыдущий ИД средства контроля (предварительная версия за ноябрь 2017 г.)**|**Новый ИД средства контроля (общедоступный выпуск за февраль 2018 г.)**|
|:-----|:-----|
|5.2.2  <br/> |5.2.1  <br/> |
|5.2.3  <br/> |5.2.2  <br/> |
|5.2.4  <br/> |5.2.3  <br/> |
|6.1.1.1  <br/> |6.2  <br/> |
|6.10.1.2  <br/> |6.11.1  <br/> |
|6.10.2.5  <br/> |6.11.2  <br/> |
|6.11.1.2  <br/> |6.12  <br/> |
|6.12.1  <br/> |6.13.1  <br/> |
|6.12.1.1  <br/> |6.13.2  <br/> |
|6.12.1.5  <br/> |6.13.3  <br/> |
|6.14.1.3  <br/> |6.15.1  <br/> |
|6.14.2.1  <br/> |6.15.2  <br/> |
|6.14.2.3  <br/> |6.15.3  <br/> |
|6.2.1.1  <br/> |6.3  <br/> |
|6.3.2.2  <br/> |6.4  <br/> |
|6.4.3.1  <br/> |6.5.2  <br/> |
|6.4.3.2  <br/> |6.8.1  <br/> |
|6.4.3.3  <br/> |6.5.3  <br/> |
|6.5.2  <br/> |6.6.1  <br/> |
|6.5.2.1  <br/> |6.6.2  <br/> |
|6.5.2.2  <br/> |6.6.3  <br/> |
|6.5.2.3  <br/> |6.6.4  <br/> |
|6.5.4.2  <br/> |6.6.5  <br/> |
|6.6.1.1  <br/> |6.7  <br/>   |
|6.7.2.7  <br/> |6.8.1  <br/> |
|6.7.2.9  <br/> |6.8.2  <br/> |
|6.8.1.4  <br/> |6.9.1  <br/> |
|6.8.4.1  <br/> |6.9.3  <br/> |
|6.8.4.2  <br/> |6.9.4  <br/> |
|6.9.2.1  <br/> |6.10.1  <br/>|
|6.9.2.3  <br/> |6.10.2  <br/>|
|A.7.1.1  <br/> |7.2.1  <br/> |
|A.7.1.2  <br/> |7.2.2  <br/> |
|A.7.1.3  <br/> |7.2.3  <br/> |
|A.7.1.4  <br/> |7.2.4  <br/> |
|A.7.1.5  <br/> |7.2.5  <br/> |
|A.7.1.6  <br/> |7.2.6  <br/> |
|A.7.1.7  <br/> |7.2.7  <br/> |
|A.7.2.1  <br/> |7.3.1  <br/> |
|A.7.2.10 <br/> |7.3.9  <br/> |
|A.7.2.11 <br/> |7.3.10  <br/>|
|A.7.2.2  <br/> |7.3.2  <br/> |
|A.7.2.3  <br/> |7.3.3  <br/> |
|A.7.2.4  <br/> |7.3.4  <br/> |
|A.7.2.5  <br/> |7.3.5  <br/> |
|A.7.2.6  <br/> |7.3.6  <br/> |
|A.7.2.7  <br/> |7.3.7  <br/> |
|A.7.2.8  <br/> |7.3.8  <br/> |
|A.7.3.1  <br/> |7.4.1  <br/> |
|A.7.3.10 <br/> |7.4.10  <br/>|
|A.7.3.2  <br/> |7.4.2  <br/> |
|A.7.3.3  <br/> |7.4.3  <br/> |
|A.7.3.4  <br/> |7.4.4  <br/> |
|A.7.3.5  <br/> |7.4.5  <br/> |
|A.7.3.6  <br/> |7.4.6  <br/> |
|A.7.3.7  <br/> |7.4.7  <br/> |
|A.7.3.8  <br/> |7.4.8  <br/> |
|A.7.3.9  <br/> |7.4.9  <br/> |
|A.7.4.1  <br/> |7.5.1  <br/> |
|A.7.4.2  <br/> |7.5.2  <br/> |
|A.7.4.3  <br/> |7.5.3  <br/> |
|A.7.4.4  <br/> |7.5.4  <br/> |
|A.7.4.5  <br/> |7.5.5  <br/> |
|B.8.1.1  <br/> |8.2.1  <br/> |
|B.8.1.2  <br/> |8.2.2  <br/> |
|B.8.1.3  <br/> |8.2.3  <br/> |
|B.8.1.4  <br/> |8.2.4  <br/> |
|B.8.1.5  <br/> |8.2.5  <br/> |
|B.8.1.6  <br/> |8.2.6  <br/> |
|B.8.2.1  <br/> |8.3.1  <br/> |
|B.8.3.1  <br/> |8.4.1  <br/> |
|B.8.3.2  <br/> |8.4.2  <br/> |
|B.8.3.3  <br/> |8.4.3  <br/> |
|B.8.4.1  <br/> |8.5.1  <br/> |
|B.8.4.2  <br/> |8.5.2  <br/> |
|B.8.4.3  <br/> |8.5.4  <br/> |
|B.8.4.4  <br/> |8.5.5  <br/> |
|B.8.4.5  <br/> |8.5.3  <br/> |
|B.8.4.6  <br/> |8.5.6  <br/> |
|B.8.4.7  <br/> |8.5.7  <br/> |
|B.8.4.8  <br/> |8.5.8  <br/> |
|
   
## <a name="see-also"></a>См. также

- [Интерактивное руководство по диспетчеру соответствия требованиям](https://content.cloudguides.com/guides/Compliance%20Manager)

- [Объявление об общедоступном выпуске диспетчера соответствия требованиям](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Announcing-Compliance-Manager-general-availability/ba-p/161922)

- [Microsoft 365 предоставляет стратегию защиты информации, чтобы помочь обеспечить соблюдение GDPR](https://blogs.office.com/2018/02/22/microsoft-365-provides-an-information-protection-strategy-to-help-with-the-gdpr)
