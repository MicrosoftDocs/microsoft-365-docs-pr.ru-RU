---
title: Общие сведения о хранении, зависящем от возникновения события
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-may2020
- seo-marvel-jun2020
description: Как правило, в рамках решения для управления записями можно настроить метку хранения, чтобы начать период хранения, который зависит от возникновения указанного вами события.
ms.openlocfilehash: 1e716cc886e8378308054d4f2eedf961045f4486
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817808"
---
# <a name="overview-of-event-driven-retention"></a>Общие сведения о хранении, зависящем от возникновения события

>*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*

When you retain content, the retention period is often based on the age of the content - for example, you might retain documents for seven years after they're created and then delete them. But with retention labels in Microsoft 365, you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.
  
Метки с хранением, зависящим от возникновения события, можно использовать, например, в таких случаях:
  
- **Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization. After 10 years elapse, all documents related to the hiring, performance, and termination of that employee need to be disposed. The event that triggers the 10-year retention period is the employee leaving the organization. 
    
- **Contract expiration** Suppose that all records related to contracts need to be retained for five years from the time the contract expires. The event that triggers the five-year retention period is the expiration of the contract. 
    
- **Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period. 
    
Event-driven retention is typically used as part of a records-management process. This means that:
  
- Labels based on events also usually classify content as a record. For more information, see [Using Content Search to find all content with a specific retention label applied to it](labels.md#using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it).
    
- Документ, который был объявлен записью, но для которого событие-триггер еще не наступило, хранится в течение неограниченного времени (окончательно удалить записи невозможно), пока событие не активирует период его хранения.
    
- Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose the content. For more information, see [Disposition of content](disposition.md).
    
У меток на основе событий те же возможности, что и у всех других меток хранения в Microsoft 365. Дополнительную информацию см. в статье [Сведения о метках хранения](labels.md).

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a>Взаимосвязь между типами событий, метками, событиями и идентификаторами ресурсов

Чтобы успешно использовать управляемое событиями хранение, важно понимать взаимосвязь между типами событий, метками хранения, событиями и идентификаторами активов, как показано на диаграммах и в следующем пояснении: 
  
![Схема взаимосвязей между типами событий, метками, событиями и идентификаторами ресурсов](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![Схема взаимосвязей между типами событий, метками, событиями и идентификаторами ресурсов](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. Вы создаете метки хранения для разных типов контента, а затем связываете их с типом события. Например, метки хранения для различных типов файлов и записей продукта связаны с типом события с именем Product Lifetime, поскольку эти записи должны храниться в течение 10 лет с момента окончания срока действия продукта.
    
2. Пользователи (обычно менеджеры записей) применяют эти метки хранения к контенту и (для документов SharePoint и OneDrive) вводят идентификатор ресурса для каждого элемента. В этом примере идентификатор актива - это название продукта или код, используемый организацией. Таким образом, каждой записи продукта присваивается метка хранения, и каждая запись имеет свойство, которое содержит идентификатор актива. Диаграмма представляет **весь контент** для всех записей продукта в организации, и каждый элемент имеет идентификатор актива продукта, чья запись это. 
    
3. Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:
    
  - Идентификатор ресурса (для документов SharePoint и OneDrive).
    
  - Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.
    
  - The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.
    
4. После создания события эта дата события синхронизируется со всем контентом, который имеет метку хранения этого типа и которая содержит указанный идентификатор актива или ключевое слово. Как и любая метка хранения, эта синхронизация может занять до 7 дней. На предыдущей диаграмме все элементы, обведенные красным, имеют период хранения, инициируемый этим событием. Другими словами, когда срок действия этого продукта истекает, это событие запускает период хранения для записей этого продукта.
    
Важно понимать, что если вы не укажете идентификатор ресурса или ключевые слова для события, у **всего содержимого**, которому присвоена метка события такого типа, будет период хранения, определяемый событием. Это означает, что на предыдущей диаграмме все содержимое начало бы сохраняться. Это может быть не то, что вы намерены. 
  
Наконец, помните, что каждая метка хранения имеет свои собственные настройки хранения. В этом примере все они указывают 10 лет, но для события возможно инициировать метки хранения, где каждая метка имеет свой период хранения.
  
## <a name="how-to-set-up-event-driven-retention"></a>Настройка хранения, зависящего от возникновения события

Рабочий процесс высокого уровня для удержания на основе событий:
  
![Схема, иллюстрирующая рабочий процесс для настройки хранения, зависящего от возникновения события](../media/event-based-retention-process.png)
  
> [!TIP]
> Подробный сценарий использования управляемых свойств в SharePoint для автоматического применения меток хранения и реализации хранения, зависящего от возникновения события, см. в статье [Управление жизненным циклом документов SharePoint с метками хранения](auto-apply-retention-labels-scenario.md).

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a>Шаг 1. Создайте метку, период хранения которой зависит от возникновения события

В Центре соответствия требованиям Microsoft 365 на панели навигации слева выберите **Управление информацией** > **Метки** > **Создать метку**. Если элемент **Управление информацией** не отображается в области навигации, прокрутите вниз и выберите **Показать все**.
  
When you create the label, turn on retention, and then choose the option shown below to retain or delete the content based on an event. This means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page. 
  
Обратите внимание, что управляемое событиями хранение обычно используется для контента, который классифицируется как запись. По этой причине, когда вы создаете метки хранения на основе события, вы обычно выбираете опцию **Использовать метку, чтобы классифицировать контент как "Запись"**.
  
Обратите внимание также на то, что для хранения, зависящего от возникновения события, требуются настройки, согласно которым будет выполняться:
  
- хранение содержимого;
    
- автоматическое удаление содержимого или активация проверки перед ликвидацией в конце периода хранения.
    
![Возможность создать метку на основе события](../media/a4902281-5196-4194-9737-f30231d95861.png)
  
### <a name="step-2-choose-an-event-type-for-that-label"></a>Шаг 2. Выберите тип события для такой метки

После того как вы выберете для метки параметр, позволяющий связать ее с **событием**, вы увидите команду **Выбрать тип события**. Тип события — это просто общее описание события, которое нужно связать с меткой.
  
Например, если вы создадите тип события с именем Product Lifetime, вы создадите метки хранения на основе событий с именами, которые описывают, к каким типам контента вы хотите применить метки, например «Файлы разработки продукта» или «Бизнес продукта». записи решений ".
  
Обратите внимание, что после выбора типа события и создания метки хранения тип события не может быть изменен.
  
![Возможности создания или выбора типа события](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a>Шаг 3. Публикация или автоматическое применение меток хранения на основе событий

Метку хранения на основе события, как и любую другую метку хранения, необходимо [автоматически применить к событию или опубликовать](create-retention-labels.md), чтобы ее можно было применять вручную.

> [!NOTE]
> Если выбрать метку хранения на основе события на вкладке **Управление записями** > **План хранения** или **Управление информацией** > **Метки**, кнопка **Автоматически применить метку** будет недоступна.
> 
> Вместо этой кнопки используйте параметр **Автоматически применить метку**, расположенный над списком меток или политик в одном из следующих расположений:
> - **Управление записями** >  вкладка **Политики меток**
> - **Управление информацией** >  вкладка **Метки** или вкладка **Политики меток**


![Возможности публиковать или автоматически применять метки хранения](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a>Шаг 4. Введите идентификатор ресурса

After an event-driven label is applied to content, you can enter an asset ID for each item. For example, your organization might use:
  
- коды продуктов для хранения содержимого, касающегося только определенного продукта;
    
- коды проектов для хранения содержимого, касающегося только определенного проекта;
    
- идентификаторы сотрудников для хранения содержимого, касающегося только конкретного лица.
    
Важно понимать, что идентификатор ресурса — это лишь одно из свойств документа в SharePoint и OneDrive для бизнеса. Ваша организация может уже использовать другие свойства и идентификаторы документов для классификации содержимого. Если это так, вы также можете использовать эти свойства и значения при создании события — см. следующий шаг 6. Важно то, что необходимо использовать определенное сочетание "свойство:значение" в свойствах документа, чтобы связать элемент с типом события.
  
![Текстовое поле для ввода идентификатора ресурса](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a>Шаг 5. Создайте событие

When a particular instance of that event type occurs - for example, a product reaches its end of life - go to the **Records management** > **Events** page in the Microsoft 365 compliance center and create an event. You need to manually trigger an event by creating it.
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a>Шаг 6. Выберите тип события, который использовался для метки из описания шага 2

Когда вы создаете событие, выберите тот же тип события, который используется меткой хранения на шаге 2, например Product Lifetime. Период хранения будет инициирован только для контента с метками хранения, примененными к нему с таким типом события.
  
![Возможность выбора типа события в параметрах события](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a>Шаг 7. Введите ключевые слова или идентификатор ресурса

Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content or keywords for Exchange content. For asset IDs, retention will be enforced only on content with the specified property:value pair. If an asset ID is not entered, **all content** with labels of that event type get the same retention date applied to them. 
  
Важно понимать, что идентификатор ресурса — это лишь одно из свойств документа в SharePoint и OneDrive для бизнеса. Если вы используете свойство Asset ID, в поле для идентификаторов ресурсов следует ввести ComplianceAssetID:\<value\>, как показано ниже.
  
Your organization might have applied other properties and IDs to the documents related to this event type. For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ". In this case, you'd enter ProductID:XYZ in the box for asset IDs shown below.
  
For Exchange items, you can include keywords. You can refine your query by using search operators like AND, OR, and NOT. For more information on operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).
  
Наконец, выберите дату, когда произошло событие; эта дата используется как начало срока хранения. После создания события эта дата события синхронизируется со всем содержимым с меткой хранения этого типа события, идентификатором ресурса и ключевыми словами. Как и любая метка хранения, эта синхронизация может занять до 7 дней.
  
![Страница параметров события](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)
  
## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a>Использование средства "Поиск контента" для поиска всего содержимого с определенной меткой или определенным идентификатором ресурса

После назначения меток хранения контенту можно использовать поиск контента, чтобы найти весь контент, классифицированный с определенной меткой хранения или содержащий определенный идентификатор ресурса.
  
Применение запросов на поиск содержимого:
  
- Чтобы найти все содержимое с определенной меткой хранения, выберите условие **Метка соответствия**, затем введите полное имя метки или часть имени метки и используйте подстановочный знак. 
    
- Чтобы найти все содержимое с определенным идентификатором ресурса, введите свойство **ComplianceAssetID** и значение (например, ComplianceAssetID:\<value\>). 
    
Дополнительные сведения см. в статье [Запросы по ключевым словам и условия для средства "Поиск контента"](keyword-queries-and-search-conditions.md).
  
## <a name="permissions"></a>Разрешения

To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group. 
  
Дополнительные сведения см. в статье [Предоставление пользователям доступа к Центру безопасности и соответствия требованиям Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
## <a name="automate-events-by-using-powershell"></a>Автоматизация событий с помощью PowerShell

In the admin center, you can only create events manually; it's not possible to automatically trigger an event when it occurs. However, you can use a Rest API to trigger events automatically; for more information, see [Automate event-based retention](automate-event-driven-retention.md).

Кроме того, с помощью сценария PowerShell можно автоматизировать хранение на основе событий из бизнес-приложений. Командлеты PowerShell, доступные для хранения на основе событий:
  
- [Get-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [New-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [Remove-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [Set-ComplianceRetentionEventType](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [Get-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [New-ComplianceRetentionEvent](https://go.microsoft.com/fwlink/?linkid=873003)
    

