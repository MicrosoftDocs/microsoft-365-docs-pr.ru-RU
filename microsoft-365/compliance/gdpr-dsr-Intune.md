---
title: Запросы субъектов данных Intune в рамках GDPR и CCPA
description: Узнайте, как находить и обрабатывать личные данные и отвечать на запросы DSR и CCPA от клиентов, использующих Microsoft Intune.
keywords: Microsoft 365, Microsoft 365 для образования, документация по Microsoft 365, GDPR, CCPA
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
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
hideEdit: true
titleSuffix: Microsoft GDPR
ms.openlocfilehash: a9dd161edd740aa97e97afa02a6c53933a6ac211
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817658"
---
# <a name="intune-data-subject-requests-for-the-gdpr-and-ccpa"></a>Запросы субъектов данных Intune в рамках GDPR и CCPA

The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as *data subjects*) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the *data controller* or just *controller*). Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of personal data, requesting corrections to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called a *Data Subject Request* or DSR.

Аналогичным образом, Калифорнийский закон о защите прав потребителей (CCPA) предоставляет права и обязанности в отношении конфиденциальности для калифорнийских потребителей, включая права, аналогичные правам субъектов данных GDPR, такие как право на удаление, доступ и получение (переносимость) их личной информации.  CCPA также предусматривает определенное раскрытие информации, защиту от дискриминации при избрании прав на осуществление и требования «отказаться / подписаться» для определенных передач данных, классифицированных как «продажи». Широкое определение продаж включает обмен данными для встречного удовлетворения. Дополнительные сведения о CCPA см. в статьях [Закон Калифорнии о конфиденциальности данных](offering-ccpa.md) и [Вопросы и ответы о законе Калифорнии о конфиденциальности данных](ccpa-faq.md).

В руководстве рассматривается использование продуктов, служб и средств администрирования Майкрософт, позволяющих управляющим находить персональные данные и выполнять с ними действия в ответ на запросы DSR. В частности, это включает инструкции по поиску персональных данных или личных сведений, которые находятся в облаке Майкрософт, получению к ним доступа и выполнению в отношении них действий. Вот краткий обзор процессов, описанных в этом руководстве:

- **Обнаружение.** Используйте средства поиска и обнаружения, чтобы легко находить клиентские данные, которые могут быть предметом DSR. Собрав соответствующие документы, можно выполнить одно или несколько из описанных в следующих шагах действий DSR, чтобы ответить на запрос. В качестве альтернативы вы можете определить, что запрос не соответствует рекомендациям вашей организации по реагированию на DSR.
- **Доступ.** Получение персональных данных, размещенных в облаке Майкрософт, и предоставление копии этих данных субъекту данных.
- **Уточнение.** Внесение изменений или выполнение других запрошенных действий с персональными данными (если это возможно).
- **Ограничение.** Ограничение обработки персональных данных путем удаления лицензий на использование различных служб Azure либо путем выключения соответствующих служб, если это возможно. Вы также можете удалить данные из облака корпорации Майкрософт, сохранив их в локальной среде или в другом расположении.
- **Удаление.** Безвозвратное удаление персональных данных, хранящихся в облаке Майкрософт.
- **Экспорт и получение (переносимость).** Предоставление электронной копии персональных данных или личных сведений (в машиночитаемом формате) субъекту данных. В рамках CCPA персональные данные — это любая информация, относящаяся к идентифицированному или идентифицируемому лицу. Нет различия между личными, общественными или рабочими ролями человека. Определение термина "личные сведения" в общих чертах совпадает с определением термина "персональные данные" в GDPR. Кроме того, CCPA также распространяется на данные о семье и домашнем хозяйстве. Дополнительные сведения о CCPA см. в статьях [Закон Калифорнии о конфиденциальности данных](offering-ccpa.md) и [Вопросы и ответы о законе Калифорнии о конфиденциальности данных](ccpa-faq.md).

В каждом разделе этого руководства описываются методы, которыми управляющая данными организация может реагировать на запрос персональных данных в облаке Майкрософт.

#### <a name="terminology"></a>Терминология

Ниже представлены определения терминов, относящихся к данному руководству.

- **Управляющий** — физическое или юридическое лицо, орган государственной власти, агентство или другое лицо, которое отдельно от других или вместе с ними определяет цели и средства обработки персональных данных. Если цели и средства такой обработки данных определены законом Союза или государства-участника, в этом законе может быть указан управляющий или определенные критерии для его назначения.
- **Персональные данные и субъект данных** — любая информация, связанная с идентифицированным или идентифицируемым физическим лицом ("субъектом данных"). Идентифицируемым физическим лицом считается человек, чью личность можно прямо или косвенно установить, в частности с помощью идентификатора, такого как имя, идентификационный номер, данные о местоположении, идентификатор в сети, либо с использованием одного или нескольких факторов, связанных с физическими, физиологическими, генетическими, умственными, экономическими, культурными или социальными характеристиками этого физического лица.
- **Обработчик** — физическое или юридическое лицо, орган государственной власти, агентство или другое лицо, которое обрабатывает персональные данные от лица управляющего.
- **Данные клиента** — все данные, включая текстовые, звуковые, видеофайлы или файлы изображений, а также программное обеспечение, которые предоставляются корпорации Майкрософт клиентом или от его имени через корпоративную службу. К данным клиента относятся (1) информация, позволяющая идентифицировать пользователей (например, их имена и контактные данные в Azure Active Directory), и контент клиента, отправляемый или создаваемый им в определенных службах (например, контент в учетной записи службы хранилища Azure либо базе данных Azure SQL или образ виртуальной машины Azure).
- **Системные журналы** — журналы и соответствующие данные, созданные корпорацией Майкрософт, которые помогают ей предоставлять пользователям корпоративные службы. Системные журналы в основном содержат псевдонимизированные данные, например уникальные идентификаторы. Как правило, это сгенерированное системой число, по которому невозможно установить личность конкретного человека, но можно предоставлять пользователям корпоративные службы. Системные журналы также могут содержать сведения, позволяющие идентифицировать пользователей, например имя.

#### <a name="how-to-use-this-guide"></a>Как пользоваться руководством

Это руководство состоит из двух частей:

- **Часть 1. Ответ на запросы субъекта данных в отношении данных клиента.** В 1-ой части этого руководства описывается, как просматривать, исправлять, ограничивать, удалять и экспортировать данные из приложений, в которых вы создавали данные. В этой части подробно описывается выполнение запросов DSR в отношении контента клиента, а также информации, позволяющей идентифицировать пользователей.
- **Часть 2. Ответ на запросы субъекта данных в отношении системных журналов**. Когда вы используете корпоративные службы Майкрософт, корпорация Майкрософт создает определенную информацию, известную как системные журналы, чтобы предоставлять эту службу. Во 2-й части этого руководства рассказывается, как просматривать, удалять и экспортировать такие сведения для Azure.

### <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-intune"></a>Общие сведения о запросах субъектов данных Azure Active Directory и Microsoft Intune

When considering services provided to enterprise customers, execution of DSRs must always be understood within the context of a specific Azure Active Directory (AAD) tenant. Notably, DSRs are always executed within a given AAD tenant. If a user is participating in multiple tenants, it is important to emphasize that a given DSR is *only* executed within the context of the specific tenant the request was received within. This is critical to understand as it means the execution of a DSR by one enterprise customer **will not** impact the data of an adjacent enterprise customer.

The same also applies for Microsoft Intune provided to an enterprise customer: execution of a DSR against an Intune account *associated with an AAD tenant* **will only** pertain to data within the tenant. In addition, it is important to understand the following when handling Intune accounts within a tenant:

- If an Intune user creates an Azure subscription, the subscription will be handled as if it were an AAD tenant. Consequently, DSRs are scoped within the tenant as described above.
- If an Azure subscription created via an Intune account is deleted, **it will not affect** the actual Intune account. Again, as noted above, DSRs executing within the Azure subscription are limited to the scope of the tenant itself.

DSRs against an Intune account itself, **outside a given tenant**, are executed via the Consumer Privacy Dashboard. Please refer to the Windows Data Subject Request Guide for further details.

## <a name="part-1-dsr-guide-for-customer-data"></a>Часть 1. Руководство по запросам субъектов данных в отношении данных клиентов

### <a name="executing-dsrs-against-customer-data"></a>Выполнение запросов данных клиента

Microsoft provides the ability to access, delete, and export certain Customer Data through the Azure Portal and also directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services (also referred to as *in-product experiences*). Details regarding such in-product experiences are described in the respective services' reference documentation.

>[!IMPORTANT]  
>Services supporting in-product DSRs require direct usage of the service's application programming interface (API) or user interface (UI), describing applicable CRUD (create, read, update, delete) operations. Consequently, execution of DSRs within a given service must be done in addition to execution of a DSR within the Azure Portal in order to complete a full request for a given data subject. Please refer to specific services' reference documentation for further details.

### <a name="step-1-discover"></a>Шаг 1. Обнаружение

The first step in responding to a DSR is to find the personal data that is the subject of the request. This first step - finding and reviewing the personal data at issue - will help you determine whether a DSR meets your organization's requirements for honoring or declining a DSR. For example, after finding and reviewing the personal data at issue, you may determine the request doesn't meet your organization's requirements because doing so may adversely affect the rights and freedoms of others.

After you find the data, you can then perform the specific action to satisfy the request by the data subject. For details, see the following:

- [Сбор данных](https://docs.microsoft.com/intune/privacy-data-collect)
- [Хранение и обработка данных](https://docs.microsoft.com/intune/privacy-data-store-process)
- [Просмотр персональных данных](https://docs.microsoft.com/intune/privacy-data-view-correct#view-personal-data)

### <a name="step-2-access"></a>Шаг 2. Доступ

After you've found Customer Data containing personal data that is potentially responsive to a DSR, it is up to you and your organization to decide which data to provide to the data subject. You can provide them with a copy of the actual document, an appropriately redacted version, or a screenshot of the portions you have deemed appropriate to share. For each of these responses to an access request, you will have to retrieve a copy of the document or other item that contains the responsive data.

Когда вы предоставляете копию данных субъекту данных, вам может потребоваться удалить или отредактировать персональную информацию о других субъектах данных или конфиденциальные сведения.

Ниже рассказывается, как получить копию данных в ответ на запрос доступа DSR.

#### <a name="azure-active-directory"></a>Azure Active Directory

Корпорация Майкрософт предоставляет портал и внутренние интерфейсы, с помощью которых администратор клиента может управлять запросами DSR на доступ. Запросы DSR на доступ позволяют получить доступ к персональным данным пользователя, включая: (а) личные сведения пользователя и (б) системные журналы.

#### <a name="service-specific-interfaces"></a>Интерфейсы служб

В Microsoft Intune имеется возможность [обнаруживать данные клиентов](#step-1-discover) непосредственно в пользовательских интерфейсах или существующих API.

### <a name="step-3-rectify"></a>Шаг 3. Исправление

If a data subject has asked you to rectify the personal data that resides in your organization's data, you and your organization will have to determine whether it's appropriate to honor the request. Rectifying the data may include taking actions such as editing, redacting, or removing personal data from a document or other type or item.

As a data processor, Microsoft does not offer the ability to correct system-generated logs as it reflects factual activities and constitutes a historical record of events within Microsoft services. With respect to Intune, admins can't update device or app specific information. If an end user wants to correct any personal data (like the device name), they must do so directly on their device. Such changes are synchronized the next time they connect to Intune.

### <a name="step-4-restrict"></a>Шаг 4. Ограничение

Субъект данных может отправить вам запрос на ограничение обработки своих персональных данных.  Мы предоставляем портал Azure и существующие интерфейсы прикладного программирования (API) или пользовательские интерфейсы (UI). С их помощью администратор клиента корпоративного клиента может управлять такими запросами субъектов данных, сочетая операции экспорта и удаления данных. Дополнительные сведения см в статье [Обработка персональных данных](https://docs.microsoft.com/intune/privacy-data-store-process#processing-personal-data).

### <a name="step-5-delete"></a>Шаг 5. Удаление

The "right to erasure" by the removal of personal data from an organization's Customer Data is a key protection in the GDPR. Removing personal data includes removing all personal data and system-generated logs, except audit log information. For details, see [Delete end user personal data](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#delete-end-user-personal-data).

## <a name="part-2-system-generated-logs"></a>Часть 2. Системные журналы

Audit logs provide tenant admins with a record of activities that generate a change in Microsoft Intune. Audit logs are available for many manage activities and typically create, update (edit), delete, and assign actions. Remote tasks that generate audit events can also be reviewed. These audit logs may contain personal data from users whose devices are enrolled in Intune. Admins can't delete audit logs. For details, see [Audit personal data](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#audit-personal-data).

## <a name="notify-about-exporting-or-deleting-issues"></a>Уведомление о проблемах при экспорте или удалении

Если при экспорте или удалении данных из портала Azure возникают проблемы, перейдите на портал Azure, выберите колонку **Справка и поддержка** и отправьте новый запрос в разделе **Управление подпиской > Другие запросы на обеспечение безопасности и соответствия > Конфиденциальность и запросы GDPR**.

## <a name="learn-more"></a>Дополнительные сведения

- [Центр управления безопасностью (Майкрософт)](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
