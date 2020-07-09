---
title: Хранение, зависящее от возникновения события
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: В этой статье описывается, как настроить операции бизнес-процесса, чтобы автоматизировать хранение с помощью событий, используя REST API Microsoft 365.
ms.openlocfilehash: c97106597733460caeab8d1d398ff81e23dd2727
ms.sourcegitcommit: dc5de2064706137256307f100b8dc61e9797bd1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "45068118"
---
# <a name="automate-event-based-retention"></a>Автоматизация хранения на основе событий

>*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*

The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to an organization's success.

To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.

To ensure compliant disposal of content, it's imperative to know when an event takes place. With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.

Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.

## <a name="about-event-based-retention"></a>О хранении на основе событий

An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.

For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:

- **The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled. For example, you might retain documents for seven years after they're created and then delete them.

- **The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.

The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention. To learn more, see [Overview of event-driven retention](event-driven-retention.md).

## <a name="set-up-event-based-retention"></a>Настройка хранении на основе событий

В этом разделе описываются действия, которые необходимо выполнить до момента подготовки хранения содержимого.

### <a name="identify-roles"></a>Определение ролей

Определите различные роли в организации, которые будут выполнять задачи управления записями и будут обеспечивать эффективное хранение деловых документов.

  | Пользователь | Роль |
  | - | - |
  | Администратор | Создает типы событий хранения, метки хранения и репозитории записей в SharePoint |
  | Управляющий записями                                  | Предоставляет указания по политикам и расписанию хранения, а также сведения о соответствии требованиям   |
  | Системный администратор (компания)                          | Настраивает внешние системы для работы с Microsoft 365 и управляет ими                       |
  | Информационный работник                               | Управляет жизненным циклом своих бизнес-процессов (отдела кадров, финансового отдела, ИТ-отдела и т. д.)                 |

### <a name="set-up-the-security--compliance-center"></a>Настройка Центра безопасности и соответствия требованиям
  
1. Администратор соответствия требованиям создает тип события — например, увольняется сотрудник, истекает срок действия договора или завершается производство продукта (см. пошаговое описание процесса в статье [Хранение на основе событий](event-driven-retention.md).
    
2. Администратор соответствия требованиям создает метку хранения на основе некоего события и связывает ее с типом события.
    
    Существует четыре типа триггеров меток хранения:
            
    1. Дата создания
                
    2. Дата последнего изменения
                
    3. Дата метки (когда содержимому была присвоена метка)
                
    4. На основе события
    
3. Администратор соответствия требованиям публикует метку хранения.

### <a name="set-up-sharepoint"></a>Настройка SharePoint
   
Чтобы создать репозиторий записей, администратор соответствия требованиям выполняет следующие действия:

1. Создает сайт SharePoint.

2. Выполняет одно из указанных ниже действий:
        
   - Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).
          
   - Настройка набора документов в SharePoint. Дополнительные сведения см. в статье [Общие сведения о наборах документов](https://support.microsoft.com/ru-RU/office/introduction-to-document-sets-3dbcd93e-0bed-46b7-b1ba-b31de2bcd234).
      
3. Назначает ИД ресурса для каждого набора документов сотрудников. ИД ресурса — это наименование продукта или код, который используется организацией, например код сотрудника может быть кодом ресурса. При назначении ИД ресурса папке, каждый элемент в этой папке автоматически наследует тот же самый ИД ресурса. Это означает, что срок хранения всех элементов может быть вызван тем же событием.

## <a name="ways-to-trigger-event-based-retention"></a>Способы запуска хранения на основе события

Существует два способа запуска хранения на основе события:

- **Использование пользовательского интерфейса центра администрирования ** С помощью этого процесса можно уменьшить объем содержимого, сохраняемого за один раз, или запускать хранение реже, например, раз в месяц или раз в год. Дополнительные сведения об использовании этого метода см. в статье [Обзор хранения на основе события](event-driven-retention.md). Тем не менее, этот способ запуска хранения может потребовать значительных временных затрат и подвержен ошибкам, что препятствует масштабированию. Таким образом, автоматизированное беспрепятственное решение для запуска хранения может повысить безопасность и улучшить соответствие требованиям в отношении данных.

- **Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.

Существует два способа использования REST API:

- **Microsoft Flow или подобное приложение** можно использовать для автоматического запуска события. Microsoft Flow является оркестратором подключения к другим системам. Использование Microsoft Flow не требует настраиваемого решения.

- **PowerShell или HTTP-клиент для вызова REST API**. Используйте PowerShell (версии 6 или выше) для вызова REST API Microsoft 365, чтобы создать события. 

Rest API — это конечная точка службы, поддерживающая наборы операций HTTP (методов), которые обеспечивают создание / получение / обновление / удаление доступа к ресурсам службы. Дополнительные сведения см. в статье [Компоненты запросов и ответов REST API](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse). В этом случае с помощью REST API Microsoft 365 можно создавать и получать события, используя операции (методы) POST и GET.

## <a name="example-scenarios"></a>Примеры сценариев

Давайте рассмотрим следующие сценарии.

### <a name="scenario-1-employees-leaving-the-organization"></a>Сценарий 1. Сотрудники увольняются из организации 

В организации создается и хранится множество документов, связанных с сотрудниками, для каждого сотрудника. Эти документы управляются и сохраняются в течение работы в организации каждого сотрудника. Тем не менее, когда работник покидает организацию или в случае его увольнения, организация обязана в соответствии с требованиями законодательства и бизнеса сохранять документы этого работника в течение определенного периода времени.

Если из организации ежедневно увольняется несколько сотрудников, необходимо запускать счетчики хранения сотен или даже тысяч документов каждый день.

Кроме того, для каждого сотрудника период хранения рассчитывается на основе типа записи сотрудника (дата увольнения сотрудника + количество дней, месяцев или лет). Например, у документов о зарплате и документов о премии одного и того же сотрудника могут быть разные периоды хранения.

На схеме далее показано, как может существовать несколько меток, связанных с одним событием. Здесь все файлы под меткой “Компенсации работника” и все файлы под меткой “Льготы сотрудников” связаны с одним событием — уход сотрудника из организации. Каждый из этих различных файлов имеет различные счетчики хранения. Таким образом, когда сотрудник покидает организацию, эти файлы под каждой меткой имеют различный срок хранения. Запуск всех этих разных счетчиков хранения для каждого типа файла или метки для каждого сотрудника является очень сложной задачей. Представьте, что это необходимо выполнить для нескольких сотрудников.

![Схема типов событий, событий и меток](../media/automate-event-driven-retention-event-diagram-employee-leaving.png)

Поэтому автоматизированный процесс запуска всех этих различных счетчиков хранения для нескольких сотрудников должен работать быстро, быть безошибочным и очень эффективным.

**Настройка автоматизированного хранения на основе событий для этого сценария:**

![Схема ролей и действий для сценария, когда сотрудник увольняется из организации](../media/automate-event-driven-retention-employee-termination-diagram.png)

  - Администратор создает папки сотрудников в наборе документов, например "Евгения Артемьева", "Артем Кузнецов".

  - Администратор добавляет в каждую папку файлы сотрудников, например с данными о премиях и зарплате.

  - Администратор назначает идентификатор ресурса для каждой папки сотрудников. 

  - Администратор Центра безопасности и соответствия требованиям выполняет вход в Центр безопасности и соответствия требованиям.

  - Администратор безопасности и соответствия требованиям создает типы событий, связанные с сотрудником, например "Увольнение сотрудника" и "Прием сотрудника на работу".

  - Администратор безопасности и соответствия требованиям создает метку "Хранение для сотрудника".

  - Эта метка "Хранение для сотрудника" публикуется и вручную или автоматически применяется к файлам сотрудника в SharePoint

  - Система управления отдела кадров, например Workday, может работать совместно с Microsoft Flow для периодического управления файлами сотрудников

  - Если сотрудник увольняется из организации, Flow активирует REST API хранения на основе событий M365, который запустит счетчик хранения для файлов определенного сотрудника.

#### <a name="using-microsoft-flow"></a>Использование Microsoft Flow

Шаг 1. Создайте процесс создания события с помощью REST API Microsoft 365

![Использование Flow для создания события](../media/automate-event-driven-retention-flow-1.png)

![Использование Flow для вызова REST API](../media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a>Создание события

Пример кода для вызова REST API:

- **Метод**: POST
- **URL-адрес**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`
- **Заголовки**: Key = Content-Type, Value = application/atom+xml
- **Текст**:
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
- **Проверка подлинности**: обычная
- **Имя пользователя**: "Complianceuser"
- **Пароль**: "Compliancepassword"


##### <a name="available-parameters"></a>Доступные параметры


|Параметры|Описание|Примечания|
|--- |--- |--- |
|<d:Name></d:Name>|Указание уникального имени события.|Не может содержать начальные и конечные пробелы и следующие символы: % * \ & < \> \| # ? , : ;|
|<d:EventType></d:EventType>|Введите название типа события (или Guid).|Example: “Employee termination”. Event type has to be associated with a retention label.|
|<d:SharePointAssetIdQuery></d:SharePointAssetIdQuery>|Введите "ComplianceAssetId:" + код сотрудника|Пример: "ComplianceAssetId:12345"|
|<d:EventDateTime></d:EventDateTime>|Дата и время события|Формат: ГГГГ-ММ-ДДTчч:мм:ссZ. Пример: 2018-12-01T00:00:00Z
|

##### <a name="response-codes"></a>Коды ответа

| Код ответа | Описание       |
| ----------------- | --------------------- |
| 302               | Перенаправление              |
| 201               | Создано               |
| 403               | Сбой авторизации  |
| 401               | Сбой проверки подлинности |

##### <a name="get-events-based-on-time-range"></a>Получение событий на основе диапазона времени

- **Метод**: GET

- **URL-адрес**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`

- **Заголовки**: Key = Content-Type, Value = application/atom+xml

- **Проверка подлинности**: обычная

- **Имя пользователя**: "Complianceuser"

- **Пароль**: "Compliancepassword"


##### <a name="response-codes"></a>Коды ответа

| Код ответа | Описание                   |
| ----------------- | --------------------------------- |
| 200               | Все в порядке, список событий в формате atom+xml |
| 404               | Не найдено                         |
| 302               | Перенаправление                          |
| 401               | Сбой авторизации              |
| 403               | Сбой проверки подлинности             |

##### <a name="get-an-event-by-id"></a>Получение события по идентификатору

- **Метод**: GET

- **URL-адрес**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`

- **Заголовки**: Key = Content-Type, Value = application/atom+xml

- **Проверка подлинности**: обычная

- **Имя пользователя**: "Complianceuser"

- **Пароль**: "Compliancepassword"



##### <a name="response-codes"></a>Коды ответа

| Код ответа | Описание                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | Все в порядке, текст ответа содержит событие в формате atom+xml |
| 404               | Не найдено                                            |
| 302               | Перенаправление                                             |
| 401               | Сбой авторизации                                 |
| 403               | Сбой проверки подлинности                                |

##### <a name="get-an-event-by-name"></a>Получение события по имени

- **Метод**: GET

- **URL-адрес**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`

- **Заголовки**: Key = Content-Type, Value = application/atom+xml

- **Проверка подлинности**: обычная

- **Имя пользователя**: "Complianceuser"

- **Пароль**: "Compliancepassword"


##### <a name="response-codes"></a>Коды ответа

| Код ответа | Описание                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | Все в порядке, текст ответа содержит событие в формате atom+xml |
| 404               | Не найдено                                            |
| 302               | Перенаправление                                             |
| 401               | Сбой авторизации                                 |
| 403               | Сбой проверки подлинности                                |

#### <a name="using-powershell-version-6-or-later-or-any-http-client"></a>Использование PowerShell (версии 6 или более поздней) или любого HTTP-клиента

Шаг 1. Подключитесь к PowerShell.

Шаг 2. Запустите указанный ниже сценарий.

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```


#### <a name="verify-the-outcome-in-both-options"></a>Проверка результатов обоих вариантов

Шаг 1. Перейдите в Центр безопасности и соответствия требованиям.

Шаг 2. Выберите **События** в разделе **Управление информацией**.

Шаг 3. Убедитесь, что событие создано.

Аналогичным образом описанные выше варианты автоматизации хранения на основе событий можно использовать и для следующих сценариев.

### <a name="scenario-2-contracts-expiring"></a>Сценарий 2. Окончание действия договоров

Организация может иметь несколько записей для одного договора с клиентами, поставщиками и партнерами. Эти документы можно хранить в библиотеке документов, например в SharePoint. Окончание договора определяет начало срока хранения документов, связанных с договором. Например, все записи, связанные с договорами, нужно хранить в течение пяти лет с момента истечения срока действия договора. Событием, активирующим пятилетнее хранение, будет окончание срока действия договора.

Система управления отношениями с клиентами может работать совместно с Microsoft 365 и активировать хранение документов договора.

**Настройка автоматизированного хранения на основе событий для этого сценария:**

![Схема ролей и задач для сценария окончания действия договора](../media/automate-event-driven-retention-contract-expiration.png)

  - Администратор создает библиотеку SharePoint с различными папками для каждого типа договора.

  - Администратор добавляет файлы договора, например лицензионные соглашения, договоры о разработке, в папку каждого договора.

  - Администратор назначает идентификатор ресурса для каждой папки договора.

  - Администратор Центра безопасности и соответствия требованиям выполняет вход в Центр безопасности и соответствия требованиям.

  - Администратор безопасности и соответствия требованиям создает типы событий, связанные с договором, например "Создание договора" и "Завершение действия договора".

  - Администратор безопасности и соответствия требованиям создает метку "Завершение действия договора".

  - Эта метка "Завершение действия договора" публикуется и вручную или автоматически применяется к файлам договора в SharePoint

  - Система управления договорами может работать совместно с Microsoft Flow или аналогичным приложением для периодического управления файлами договоров.

  - Если срок действия договора завершается, Microsoft Flow активирует REST API хранения на основе событий M365, который запустит счетчик хранения для файлов определенного договора.

### <a name="scenario-3-end-of-product-manufacturing"></a>Сценарий 3. Прекращение производства продукта

A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.

Система планирования ресурсов предприятия (ERP) может работать совместно с Microsoft 365 и Microsoft Flow для активации хранения.

**Настройка автоматизированного хранения на основе событий для этого сценария:**

![Схема ролей и задач для сценария жизненного цикла продукта](../media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - Администратор создает папки продуктов в наборе документов, например "Продукт 1", "Продукт 2" и т. д.

  - Администратор добавляет файлы продуктов, например технические характеристики производства, цены продуктов и лицензирование продуктов, в каждую папку продукта.

  - Администратор назначает ИД ресурса для каждой папки продукта.

  - Администратор Центра безопасности и соответствия требованиям выполняет вход в Центр безопасности и соответствия требованиям.

  - Администратор безопасности и соответствия требованиям создает типы событий, связанные с сотрудником, например "Начало производства продукта" и "Окончание производства продукта".

  - Администратор безопасности и соответствия требованиям создает метку "Окончание производства продукта".

  - Эта метка "Завершение изготовление продукта" публикуется и вручную или автоматически применяется к файлам продукта в SharePoint.

  - Система ERP может работать совместно с Microsoft Flow или аналогичным приложением для периодического управления файлами продуктов.

  - Если изготовление продукта завершается, Microsoft Flow активирует REST API хранения на основе событий M365, который запустит счетчик хранения для файлов определенного продукта.

## <a name="appendix"></a>Приложение

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a>Использование результатов ответа 302 (перенаправление) для вызова REST API

1. Вызов события хранения POST с помощью URL-адреса REST API: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`
    
    Требуются разрешения глобального администратора.

2. Проверьте код ответа. Если получен код 302, получите URL-адрес перенаправления из свойства Location (Расположение) заголовка ответа.

3. Вызовите событие хранения POST еще раз с помощью URL-адреса перенаправления

## <a name="credits"></a>Сведения об авторах

Редактор статьи:

Antonio Maio<br/>MVP в сфере приложений и служб Microsoft Office<br/> Antonio.Maio@Protiviti.com
