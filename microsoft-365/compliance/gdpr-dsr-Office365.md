---
title: Запросы субъектов данных Office 365 в рамках GDPR и CCPA
description: В этой статье рассказывается о правах пользователей в рамках GDPR и CCPA, а также о том, как с помощью Office 365 организации могут находить данные и выполнять действия над ними в ответ на запросы субъектов данных.
keywords: Office 365, DSR, Microsoft 365, Microsoft 365 для образования, документация по Microsoft 365, GDPR, CCPA
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
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 00ad2290a252ad014e9b364d9aa5ce59f94c6516
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817648"
---
# <a name="office-365-data-subject-requests-for-the-gdpr-and-ccpa"></a>Запросы субъектов данных Office 365., определенные в GDPR и CCPA

## <a name="introduction-to-dsrs"></a>Общие сведения о запросах субъектов данных

The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as *data subjects*) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the *data controller* or just *controller*). Personal data is defined broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of it, requesting changes to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called a *Data Subject Request* or DSR. The controller is obligated to promptly consider each DSR and provide a substantive response either by taking the requested action or by providing an explanation for why the DSR cannot be accommodated by the controller. A controller should consult with its own legal or compliance advisers regarding the proper disposition of any given DSR.

Аналогичным образом, Калифорнийский закон о защите прав потребителей (CCPA) предоставляет права и обязанности в отношении конфиденциальности для калифорнийских потребителей, включая права, аналогичные правам субъектов данных GDPR, такие как право на удаление, доступ и получение (переносимость) их личной информации. CCPA также предусматривает определенное раскрытие информации, защиту от дискриминации при избрании прав на осуществление и требования «отказаться / подписаться» для определенных передач данных, классифицированных как «продажи». Широкое определение продаж включает обмен данными для встречного удовлетворения. Дополнительные сведения о CCPA см. в статьях [Закон Калифорнии о конфиденциальности данных](offering-ccpa.md) и [Вопросы и ответы о законе Калифорнии о конфиденциальности данных](ccpa-faq.md).

В руководстве рассматривается порядок использования продуктов, служб и средств администрирования Office 365, позволяющих вам находить персональные данные или персональную информацию и выполнять с ними действия в ответ на запросы DSR. В частности, это включает инструкции по поиску персональных данных или персональной информации, которые находятся в облаке Майкрософт, получению к ним доступа и выполнению в отношении них действий. Вот краткий обзор процессов, описанных в этом руководстве:

- **Обнаружение.** Используйте средства поиска и обнаружения, чтобы легко находить клиентские данные, которые могут быть предметом DSR. Собрав соответствующие документы, можно выполнить одно или несколько из описанных в следующих шагах действий DSR, чтобы ответить на запрос. В качестве альтернативы вы можете определить, что запрос не соответствует рекомендациям вашей организации по реагированию на DSR.
- **Доступ.** Получение персональных данных, размещенных в облаке Майкрософт, и предоставление копии этих данных субъекту данных.
- **Уточнение.** Внесение изменений или выполнение других запрошенных действий с персональными данными (если это возможно).
- **Ограничение:** Ограничьте обработку персональных данных, либо удалив лицензии на различные облачные службы Microsoft, либо по возможности отключив нужные службы. Вы также можете удалить данные из облака корпорации Майкрософт, сохранив их в локальной среде или в другом расположении.
- **Удаление.** Безвозвратное удаление персональных данных, хранящихся в облаке Майкрософт.
- **Экспорт и получение (переносимость).** Предоставление электронной копии персональных данных или личных сведений (в машиночитаемом формате) субъекту данных. В рамках CCPA персональные данные — это любая информация, относящаяся к идентифицированному или идентифицируемому лицу. Нет различия между личными, общественными или рабочими ролями человека. Определение термина "личные сведения" в общих чертах совпадает с определением термина "персональные данные" в GDPR. Кроме того, CCPA также распространяется на данные о семье и домашнем хозяйстве. Дополнительные сведения о CCPA см. в статьях [Закон Калифорнии о конфиденциальности данных](offering-ccpa.md) и [Вопросы и ответы о законе Калифорнии о конфиденциальности данных](ccpa-faq.md).

### <a name="terminology"></a>Терминология

Ниже приведены определения терминов из GDPR, релевантные для данного руководства.

- **Управляющий** — физическое или юридическое лицо, орган государственной власти, агентство или другое лицо, которое отдельно от других или вместе с ними определяет цели и средства обработки персональных данных. Если цели и средства такой обработки данных определены законом Союза или государства-участника, в этом законе может быть указан управляющий или определенные критерии для его назначения.
- **Персональные данные и субъект данных** — любая информация, связанная с идентифицированным или идентифицируемым физическим лицом ("субъектом данных"). Идентифицируемым физическим лицом считается человек, чью личность можно прямо или косвенно установить, в частности с помощью идентификатора, такого как имя, идентификационный номер, данные о местоположении, идентификатор в сети, либо с использованием одного или нескольких факторов, связанных с физическими, физиологическими, генетическими, умственными, экономическими, культурными или социальными характеристиками этого физического лица.
- **Обработчик** — физическое или юридическое лицо, орган государственной власти, агентство или другое лицо, которое обрабатывает персональные данные от лица управляющего.
- **Данные клиента** — все данные, включая текстовые, звуковые, видеофайлы или файлы изображений, а также программное обеспечение, которые предоставляются корпорации Майкрософт клиентом или от его имени через корпоративную службу. К данным клиента относятся (1) информация, позволяющая идентифицировать конечных пользователей (например, их имена и контактные данные в Azure Active Directory), и контент клиента, отправляемый или создаваемый им в определенных службах (например, контент в документах Word и Excel или в тексте сообщения электронной почты Exchange Online; контент, добавленный на сайт SharePoint Online или сохраненный в учетной записи OneDrive для бизнеса).
- **Системные журналы** — журналы и соответствующие данные, созданные корпорацией Майкрософт, которые помогают ей предоставлять пользователям корпоративные службы. Системные журналы в основном содержат псевдонимизированные данные, например уникальные идентификаторы, которые созданы системой и по которым невозможно установить личность конкретного человека, но можно предоставлять пользователям корпоративные службы. Системные журналы также могут содержать сведения, позволяющие идентифицировать конечных пользователей, например имя пользователя.

### <a name="how-to-use-this-guide"></a>Как пользоваться руководством

Чтобы упростить поиск данных, относящихся к вашему варианту использования, данное руководство разделено на четыре части.

- **[Часть 1. Реагирование на запросы субъектов данных в отношении данных клиентов.](#part-1-responding-to-dsrs-for-customer-data)** *Данные клиента* — это данные, которые создаются и хранятся в Office 365 в ходе повседневной работы компании. К примерам наиболее распространенных приложений Office 365, позволяющих создавать данные, относятся Word, Excel, PowerPoint, Outlook и OneNote. В состав Office 365 также входят такие приложения, как SharePoint Online, Teams и Forms, упрощающие совместную работу. В первой части данного руководства описывается, как находить данные, получать или запрещать доступ к ним, а также исправлять, удалять и экспортировать данные из приложений Office 365, которые использовались для создания и хранения данных в веб-службах Office 365. В ней указаны продукты и службы, для которых обработчиком данных вашей организации является корпорация Майкрософт, благодаря чему администратор клиента может отправлять запросы субъекта данных.
- **[Часть 2. Реагирование на запросы субъектов данных, относящиеся к аналитическим данным, созданным в Office 365.](#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365)** Office 365 предоставляет определенные аналитические сведения с помощью таких служб, как Delve, MyAnalytics и "Рабочая аналитика". Создание этих аналитических данных и реагирование на связанные с ними запросы субъектов данных описываются во второй части данного руководства.
- **[Часть 3. Реагирование на запросы субъектов данных в отношении системных журналов.](#part-3-responding-to-dsrs-for-system-generated-logs)** При использовании корпоративных служб Office 365 корпорация Майкрософт создает некоторые сведения, например журналы служб, в которых описывается использование или производительность функций веб-служб. Большинство данных, создаваемых службами, содержит псевдонимизированные идентификаторы, созданные корпорацией Майкрософт. Поэтому в данном документе эта категория называется *системными журналами*. Такие данные невозможно связать с конкретным субъектом без использования дополнительных сведений, некоторые из которых могут попадать под определение персональных данных в GDPR. В третьей части данного руководства рассматривается доступ к системным журналам, а также их удаление и экспорт.
- **[Часть 4. Дополнительные ресурсы по работе с запросами субъектов данных.](#part-4-additional-resources-to-assist-you-with-dsrs)** В четвертой части данного руководства описан ряд сценариев, в которых корпорация Майкрософт выступает в роли управляющего данными при использовании определенных продуктов и служб Office 365.

>[!NOTE]
>In most cases, when users in your organization use Microsoft Office 365 products and services, you are the data controller and Microsoft is the processor. As a data controller, you are responsible for responding to the data subject directly. To assist you with this, Parts 1-3 of this guide detail the technical capabilities available to your organization to respond to a DSR request. In some limited scenarios, however, Microsoft will be the data controller when people use certain Office 365 products and services. In these cases, the information in Part 4 provides guidance on how data subjects can submit DSR requests to Microsoft.

### <a name="office-365-national-clouds"></a>Национальные облачные развертывания Office 365

The Microsoft Office 365 services are also available in the following national cloud environments: [Office 365 Germany](https://docs.microsoft.com/microsoft-365/admin/admin-overview/learn-about-office-365-germany), [Office 365 operated by 21Vianet (China)](https://docs.microsoft.com/microsoft-365/admin/services-in-china/services-in-china), and [Office 365 US Government](https://www.microsoft.com/microsoft-365/government/compare-office-365-government-plans). Most of the guidance for managing data subject requests described in this document applies to these national cloud environments. However, due to the isolated nature of these environments, there are some exceptions. Where notable for a given subsection, these exceptions are called out in a corresponding note.

### <a name="hybrid-deployments"></a>Гибридные развертывания

Your organization may consist of Microsoft offerings that are a combination of cloud-based services and on-premises server products. In general, a hybrid deployment is typically the sharing of user accounts (identity management) and resources (such as mailboxes, web sites, and data) that exist in the cloud and on-premises. Common hybrid scenarios include:

- гибридные развертывания Exchange, где у одних пользователей почтовые ящики размещаются в локальной среде, а у других — в Exchange Online;
- гибридные развертывания SharePoint, где сайты и файловые серверы находятся в локальной среде, а учетные записи OneDrive для бизнеса — в Office 365;
- локальная система управления удостоверениями (Active Directory), синхронизированная с Azure Activity Directory — базовой службой каталогов в Office 365.

When responding to a DSR request, you may have to determine if data that's responsive to a DSR request is in the Microsoft cloud or in your on-premise organization, and then take the appropriate steps to respond to that request. The Office 365 Data Subject Request Guide (this guide) provides guidance for responding to cloud-based data. For guidance for data in your on-premises organization, see [GDPR for Office on-premises Servers](https://docs.microsoft.com/Office365/Enterprise/gdpr-for-office-servers).

## <a name="part-1-responding-to-dsrs-for-customer-data"></a>Часть 1. Реагирование на запросы субъектов данных в отношении данных клиентов

Руководство по реагированию на запросы субъектов данных в отношении данных клиента разделено на четыре указанных ниже раздела:

- [Использование средства обнаружения электронных данных "Поиск контента" для реагирования на запросы субъектов данных](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs)
- [Использование функций, имеющихся в приложениях, для реагирования на запросы субъектов данных](#using-in-app-functionality-to-respond-to-dsrs)
- [Реагирование на запросы субъектов данных на уточнение данных](#responding-to-dsr-rectification-requests)
- [Реагирование на запросы субъектов данных на запрет доступа к данным](#responding-to-dsr-restriction-requests)

### <a name="how-to-determine-the-office-365-applications-that-may-be-in-scope-for-a-dsr-for-customer-data"></a>Определение приложений Office 365, которые могут входить в область действия запросов субъектов данных в отношении данных клиента

Чтобы понять, где искать персональные данные или какие данные искать, необходимо определить приложения Office 365, которые пользователи в вашей организации могут использовать для создания и хранения данных в Office 365. Знание этого сужает приложения Office 365, которые входят в область действия DSR, и помогает вам определить, как искать и получать доступ к личным данным, связанным с DSR. В частности, это означает, можете ли вы использовать инструмент поиска контента или вам придется использовать функциональные возможности приложения, в котором были созданы данные.

A quick way to identify the Office 365 applications that people in your organization are using to create Customer Data is to determine which applications are included in your organization's Microsoft 365 for business subscription. To do this, you can access user accounts in the Office 365 admin portal and look at the product licensing information. See [Assign licenses to users](../admin/manage/assign-licenses-to-users.md).

## <a name="using-the-content-search-ediscovery-tool-to-respond-to-dsrs"></a>Использование средства обнаружения электронных данных "Поиск контента" для реагирования на запросы субъектов данных

When looking for personal data within the larger set of data your organization creates and stores using in Office 365, you may want to first consider which applications people have most likely used to author the data you're looking for. Microsoft estimates that over 90% of an organization's data that is stored in Office 365 is authored in Word, Excel, PowerPoint, OneNote, and Outlook. Documents authored in these Office applications, even if purchased through Microsoft 365 Apps for enterprise or an Office perpetual license, are most likely stored on a SharePoint Online site, in a user's OneDrive for Business account, or in a user's Exchange Online mailbox. That means you can use the Content Search eDiscovery tool to search (and perform other DSR-related actions) across SharePoint Online sites, OneDrive for Business accounts, and Exchange Online mailboxes (including the sites and mailboxes associated with Microsoft 365 Groups, Microsoft Teams, EDU Assignments) to find documents and mailbox items that may be relevant to the DSR you're investigating. You can also use the Content Search tool to discover Customer Data authored in other Office 365 applications.

В таблице ниже перечислены приложения Office 365, применяемые для создания содержимого, которое можно обнаружить с помощью средства "Поиск контента". В этом разделе руководства по работе с запросами субъектов данных имеются рекомендации о том, как обнаруживать, экспортировать и удалять данные, созданные с помощью этих приложений Office 365, а также получать к ним доступ.

***Таблица 1. Приложения, в которых можно использовать средство "Поиск контента" для поиска данных клиента***

| | |
| :---: | :---:|
![Значок календаря](../media/O365-DSR-Doc-Final_image3.png) <br> Календарь | ![Значок SharePoint](../media/o365-sharepoint-64x64.png) <br> SharePoint  |
| ![Значок Excel](../media/o365-excel-64x64.png) <br> Excel | ![Значок Skype для бизнеса](../media/o365-skypeforbusiness-64x64.png) <br> Skype для бизнеса |
| ![Значок Office Lens](../media/o365-lens-64x64.png) <br> Office Lens | ![Значок задач](../media/O365-DSR-Doc-Final_image8.png) <br> Задачи |
| ![Значок OneDrive](../media/o365-OneDrive-64x64.png) <br> OneDrive для бизнеса |![Значок Teams](../media/o365-teams-64x64.png) <br> Teams |
| ![Значок OneNote](../media/o365-onenote-64x64.png) <br> OneNote| ![Значок To-Do](../media/o365-todo-64x64.png) <br> To-Do |
| ![Значок Outlook](../media/o365-outlook-64x64.png) <br> Outlook и Exchange | ![Значок "Видео"](../media/O365-DSR-Doc-Final_image14.png) <br> Видео |
| ![Значок "Люди"](../media/O365-DSR-Doc-Final_image15.png) <br> Люди | ![Значок Visio](../media/o365-visio-64x64.png) <br> Visio |
| ![Значок PowerPoint](../media/o365-powerpoint-64x64.png) <br> PowerPoint | ![Значок Word](../media/o365-word-64x64.png) <br> Word
||

>[!NOTE]
>The Content Search eDiscovery tool is not available in [Office 365 operated by 21Vianet (China)](https://docs.microsoft.com/microsoft-365/admin/services-in-china/services-in-china). This means you won't able to use this tool to search for and export Customer Data in the Office 365 applications shown in Table 1. However, you can use the In-Place eDiscovery tool in Exchange Online to search for content in user mailboxes. You can also use the eDiscovery Center in SharePoint Online to search for content in SharePoint sites and OneDrive accounts. Alternatively, you can ask a document owner to help you find and make changes or deletions to content or export it if necessary. For more information, see:</br><br> * [Создать поиск электронных данных на месте](https://docs.microsoft.com/exchange/create-in-place-ediscovery-search-exchange-2013-help)<br> * [Настройка центра электронных данных в SharePoint Online](https://support.office.com/article/Set-up-an-eDiscovery-Center-in-SharePoint-Online-A18F8975-AA7F-43B4-A7D6-001D14744D8E)

### <a name="using-content-search-to-find-personal-data"></a>Поиск персональных данных с помощью средства "Поиск контента"

Первый этап при реагировании на запросы субъектов данных — поиск персональных данных, соответствующих запросу субъекта данных. Это состоит из использования инструментов eDiscovery Office 365 для поиска личных данных (среди всех данных вашей организации в Office 365) или перехода непосредственно к собственному приложению, в котором эти данные были созданы. На этом этапе (поиск и проверка необходимых персональных данных) вы сможете определить, соответствует ли запрос субъекта данных требованиям вашей организации касательно принятия или отклонения запросов субъектов данных. Например, после нахождения и проверки обсуждаемых личных данных вы можете решить, что запрос не соответствует требованиям вашей организации, поскольку это может отрицательно сказаться на правах и свободах других лиц или поскольку личные данные содержатся в вашей деловой записи. организация имеет законную деловую заинтересованность в сохранении.

As previously stated, Microsoft estimates that over 90% of an organization's data is created with Office applications, such as Word and Excel. This means that you can use the Content Search in the Security & Compliance Center to search for most DSR-related data.

This guide assumes that you or the person searching for personal data that may be responsive to a DSR request is familiar with or has experience using the Content Search tool in the Security & Compliance Center. For general guidance on using Content Search, see [Content Search in Office 365](https://docs.microsoft.com/microsoft-365/compliance/content-search). Be sure that the person running the searches has been assigned the necessary permissions in the Security & Compliance Center. This person should be added as a member of the eDiscovery Manager role group in the Security & Compliance Center; see [Assign eDiscovery permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions). Consider adding other people in your organization who are involved in investigating DSRs to the eDiscovery Manager role group, so they can perform the necessary actions in the Content Search tool such as previewing and exporting search results. However, unless you set up compliance boundaries (as described [here](#set-up-compliance-boundaries-to-limit-the-scope-of-content-searches)) be aware that an eDiscovery Manager can search all content locations in your organization, including ones that may not be related to a DSR investigation.

После того как вы найдете нужные данные, вы можете выполнить действия, необходимые для выполнения запроса субъекта данных.

>[!NOTE]
>В Office 365 Germany Центр безопасности и соответствия требованиям расположен по адресу https://protection.office.de.

#### <a name="searching-content-locations"></a>Поиск в расположениях контента

С помощью средства "Поиск контента" вы можете выполнять поиск в расположениях контента указанных ниже типов.

- Почтовые ящики Exchange Online. Этот тип включает почтовые ящики, сопоставленные с группами Microsoft 365 и Microsoft Teams
- Общедоступные папки Exchange Online
- Сайты SharePoint Online. Этот тип включает сайты, сопоставленные с группами Microsoft 365 и Microsoft Teams
- учетные записи OneDrive для бизнеса;

>[!NOTE]
>This guide assumes that all data that might be relevant to a DSR investigation is stored in Office 365; in other words, stored in the Microsoft cloud. Data stored on a user's local computer or on-premises on your organization's file servers is outside the scope of a DSR investigation for data stored in Office 365. For guidance about responding to DSR requests for data in on-premises organizations, see [GDPR for Office on-premises Servers](https://docs.microsoft.com/Office365/Enterprise/gdpr-for-office-servers).

#### <a name="tips-for-searching-content-locations"></a>Советы по поиску в расположениях контента

- Начните работу с поиска во всех расположениях контента в вашей организации (которые вы можете включить в одну операцию поиска). Это позволит быстро определить, в каких расположениях контента содержатся элементы, соответствующие вашему поисковому запросу. Затем вы можете повторно выполнить поиск и сузить область поиска до определенных расположений, содержащих релевантные элементы.
- Use search statistics to identify the top locations that contain items that match your search query. See [View keyword statistics for Content Search results](https://docs.microsoft.com/microsoft-365/compliance/view-keyword-statistics-for-content-search).
- В журнале аудита найдите последние действия над файлами и папками, выполненные пользователем, который является объектом запроса субъекта данных. Операция поиска в журнале аудита возвратит список записей аудита, содержащих имена и расположения ресурсов, с которыми пользователь недавно взаимодействовал. Вы, возможно, сможете использовать эту информацию для создания запроса на поиск контента. См. статью [Поиск в журнале аудита в Центре безопасности и соответствия требованиям](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

#### <a name="building-search-queries-to-find-personal-data"></a>Создание поисковых запросов для поиска персональных данных

DSR, который вы исследуете, скорее всего, содержит идентификаторы, которые вы можете использовать в поисковом запросе по ключевым словам для поиска личных данных. Ниже перечислены некоторые стандартные идентификаторы, которые можно использовать в поисковых запросах при поиске персональных данных.

- Электронный адрес или псевдоним
- Номер телефона
- Почтовый адрес
- Номер удостоверения сотрудника
- Номер удостоверения государственного образца или аналог номера социального страхования для участника ЕС

DSR, который вы исследуете, скорее всего, будет иметь идентификатор и другие данные о личных данных, которые являются предметом запроса, который вы можете использовать в поисковом запросе.

Поиск только по электронному адресу или номеру удостоверения сотрудника, возможно, возвратит большое количество результатов. Чтобы сузить область поиска (чтобы при его выполнении были возвращены результаты, наиболее релевантные запросу субъекта данных), вы можете добавить дополнительные условия в поисковый запрос. Когда вы добавляете условие, система связывает ключевое слово и условие поиска логическим оператором **AND** (И). Это означает, что в результатах поиска будут возвращены только те элементы, которые соответствуют *и ключевому слову, и условию*.

The following table lists some conditions you can use to narrow the scope of a search. The table also lists the values that you can use for each condition to search for specific document types and mailbox items.

***Таблица 2. Сужение области поиска с помощью условий***

||||
| :--- | :--- |:--- |
|**Условие**|**Описание** |**Пример значений условия**|
| Тип файла | Расширение документа или файла. Используйте это условие для поиска документов Office и файлов, созданных в приложениях Office 365. Используйте это условие при поиске документов, размещенных на сайтах SharePoint Online и в учетных записях OneDrive для бизнеса.<br/>Свойство соответствующего документа представляет собой тип файла. <br/>Полный список расширений файлов, поиск которых вы можете выполнять, см. в статье "Расширения имен файлов для обхода и анализируемые типы файлов в SharePoint, используемые по умолчанию"(https://technet.microsoft.com/library/jj219530.aspx).|&nbsp;&bull;&nbsp;&nbsp;csv — поиск файлов данных с разделителями-запятыми (CSV-файлов); файлы Excel можно сохранить в формате CSV, а CSV-файлы можно без труда импортировать в Excel.<br><br>&bull;&nbsp;&nbsp;docx — поиск файлов Word. <br><br>&bull;&nbsp;&nbsp;mpp — поиск файлов Project.<br/><br>&bull;&nbsp;&nbsp;one — поиск файлов OneNote. <br><br>&bull;&nbsp;&nbsp;pdf — поиск файлов, сохраненных в формате PDF. <br><br>&bull;&nbsp;&nbsp;pptx — поиск файлов PowerPoint. <br><br>&bull;&nbsp;&nbsp;xlxs — поиск файлов Excel. <br><br>&bull;&nbsp;&nbsp;vsd — поиск файлов Visio. <br><br>&bull;&nbsp;&nbsp;wmv — поиск видеофайлов Windows Media. <br>|
| Тип сообщения | Тип электронных писем, которые необходимо найти. Используйте это условие, чтобы выполнять в почтовых ящиках поиск контактов (Люди), собраний (Календарь), задач или бесед через Skype для бизнеса. Соответствующее свойство электронного письма — *kind* (Тип).|&bull;&nbsp;&nbsp;*contacts — поиск в списке "Мои контакты" (Люди) почтового ящика. <br><br>&bull;&nbsp;&nbsp;* email — поиск в электронных письмах. <br><br>&bull;&nbsp;&nbsp;*im — поиск в беседах через Skype для бизнеса.<br><br>&bull;&nbsp;&nbsp;* meetings — поиск во встречах и приглашениях на собрания (Календарь). <br><br>&bull;&nbsp;&nbsp;*tasks — поиск в списке "Мои задачи" (Задачи); при использовании этого значения операция поиска также возвращает задачи, созданные в Microsoft To-Do.<br>|
| Тег соответствия требованиям |The label assigned to an email message or a document. Labels are used to classify email and documents for data governance and enforce retention rules based on the classification defined by the label. Use this condition to search for items that have been automatically or manually assigned a label.<br/>This is a useful condition for DSR investigations because your organization may be using labels to classify content related to data privacy or that contains personal data or sensitive information. See the "Using Content Search to find all content with a specific label applied to it" section in [Overview of labels in Office 365.](https://docs.microsoft.com/microsoft-365/compliance/labels)|Тег compliance означает "персональные данные".|
||||

There are many more email and document properties and search conditions that you can use to build more complex search queries. See the following sections in the [Keyword queries and search conditions for Content Search](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions) help topic for more information.

- [Свойства электронных писем, по которым можно выполнять поиск](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions)
- [Свойства сайтов (документов), по которым можно выполнять поиск](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions)
- [Условия поиска](https://docs.microsoft.com/microsoft-365/compliance/keyword-queries-and-search-conditions)

#### <a name="searching-for-personal-data-in-sharepoint-lists-discussions-and-forms"></a>Поиск персональных данных в списках SharePoint, обсуждениях и формах

In addition to searching for personal data in documents, you can also use Content Search to search for other types of data that's created by using native SharePoint Online apps. This includes data created by using SharePoint lists, discussions, and forms. When you run a Content Search and search SharePoint Online sites (or OneDrive for Business accounts) data from lists, discussions, and forms that match the search criteria will be returned in the search results.

##### <a name="examples-of-search-queries"></a>Примеры поисковых запросов

Ниже приведены примеры поисковых запросов, в которых используются ключевые слова и условия для поиска персональных данных при реагировании на запросы субъектов данных. В примерах показаны две версии запроса: один с синтаксисом ключевых слов (в котором условие включено в поле "Ключевое слово") и второй, представляющий собой версию запроса с условиями в графическом пользовательском интерфейсе.

##### <a name="example-1"></a>Пример 1

В этом примере система возвращает файлы Excel, размещенные на сайтах SharePoint Online и в учетных записях OneDrive для бизнеса и содержащие указанный электронный адрес. Система может возвратить файл, только если в метаданных файла указан электронный адрес.

***Синтаксис ключевых слов***

```Query
pilar@contoso.com AND filetype="xlxs"
```

***Графический пользовательский интерфейс***

![диалоговое окно ключевого слова](../media/O365-DSR-Doc_image18.png)

##### <a name="example-2"></a>Пример 2

В этом примере система возвращает файлы Excel или Word, размещенные на сайтах SharePoint Online и в учетных записях OneDrive для бизнеса и содержащие указанный номер удостоверения или дату рождения сотрудника.

(98765 OR "01-20-1990") AND (filetype="xlxs" OR filetype="docx")

***Графический пользовательский интерфейс***

![диалоговое окно ключевого слова](../media/O365-DSR-Doc_image19.png)

##### <a name="example-3"></a>Пример 3

В этом примере система возвращает электронные письма, содержащие указанный идентификационный номер, представляющий собой номер социального страхования для Франции (INSEE)

```Query
"1600330345678 97" AND kind="email"
```

***Графический пользовательский интерфейс***

![диалоговое окно ключевого слова](../media/O365-DSR-Doc_image20.png)

#### <a name="working-with-partially-indexed-items-in-content-search"></a>Работа с частично индексированными элементами в средстве «Поиск контента»

Частично индексированные элементы (также называемые *неиндексированными элементами*) — это элементы в почтовых ящиках Exchange Online и документы на сайтах SharePoint Online и OneDrive для бизнеса, которые по какой-либо причине не были полностью индексированы для поиска. Это означает, что вам не удастся найти их с помощью средства "Поиск контента". Большинство электронных писем и документов на сайтах успешно проиндексированы, так как они попадают в [пределы индексирования для Office 365](https://docs.microsoft.com/microsoft-365/compliance/limits-for-content-search). Причины, по которым сообщения или файлы электронной почты не индексируются для поиска, включают:

- Тип файла [не распознан или не поддерживается для индексирования](https://docs.microsoft.com/microsoft-365/compliance/partially-indexed-items-in-content-search). Бывают случаи, когда тип файла поддерживается для индексирования, но возникает ошибка индексирования для конкретного файла.
- В электронных письмах имеется вложение в виде файла, для которого нет допустимого обработчика, например файла изображения (это наиболее частая причина частичной индексации элементов электронных писем).
- Файлы, вложенные в электронные письма, слишком велики либо их слишком много.

We recommend that you learn more about partially indexed items so that you can work with them when responding to DSR requests. For more information, see:

- [Частично индексированные элементы в средстве "Поиск контента" в Office 365](https://docs.microsoft.com/microsoft-365/compliance/partially-indexed-items-in-content-search)
- [Исследование частично индексированных элементов в функции обнаружения электронных данных в Office 365](https://docs.microsoft.com/microsoft-365/compliance/investigating-partially-indexed-items-in-ediscovery)
- [Экспорт неиндексированных элементов](export-search-results.md)

#### <a name="tips-for-working-with-partially-indexed-items"></a>Советы по работе с частично индексированными элементами

It's possible that data responsive to a DSR investigation may be in a partially indexed item. Here's some suggestions for working with partially indexed items:

- После запуска поиска в разделе статистики поиска отображается оценочное количество частично индексированных элементов. Эта оценка не включает частично проиндексированные элементы в SharePoint Online и OneDrive для бизнеса. Чтобы получить сведения о частично индексированных элементах, экспортируйте отчеты для средства "Поиск контента". В отчете **Unindexed Items.csv** содержатся сведения о неиндексированных элементах, в том числе об их расположении, URL-адресах (если элементы находятся в SharePoint Online или OneDrive для бизнеса) и строке темы (для сообщений) или имени для документов. Дополнительные сведения см. в статье [Экспорт отчета средства "Поиск контента"](https://docs.microsoft.com/microsoft-365/compliance/export-a-content-search-report).

- Статистические данные и список частично индексированных элементов, которые система возвращает в результатах средства "Поиск контента", — это все частично индексированные элементы из расположений контента, в которых выполняется поиск.

- Чтобы получить частично индексированные элементы, которые, возможно, соответствуют требованиям расследования, связанного c запросом субъекта данных, вы можете выполнить одно из указанных ниже действий.

##### <a name="export-all-partially-indexed-items"></a>Экспорт всех частично индексированных элементов

Вы можете экспортировать результаты средства "Поиск контента" и частично индексированные элементы из расположения контента, в котором выполнялся поиск. Вы также можете экспортировать только частично индексированные элементы. Затем вы можете открыть их в соответствующем приложении и проверить контент. Этот вариант следует использовать для экспорта элементов из SharePoint Online и OneDrive для бизнеса. См. статью [Экспорт результатов поиска контента из Центра безопасности и соответствия требованиям](export-search-results.md).

##### <a name="export-a-specific-set-of-partially-indexed-items-from-mailboxes"></a>Экспорт определенного набора частично индексированных элементов из почтовых ящиков

Вместо того чтобы экспортировать все частично индексированные элементы почтовых ящиков, найденные в результате выполнения операции поиска, вы можете повторно запустить средство "Поиск контента", чтобы найти частично индексированные элементы из определенного списка, а затем экспортировать их. Вы можете сделать это только для элементов почтовых ящиков. См. статью [Подготовка CSV-файла для целевого поиска контента в Office 365](https://docs.microsoft.com/microsoft-365/compliance/csv-file-for-an-id-list-content-search).

### <a name="next-steps"></a>Дальнейшие действия

После того как вы найдете персональные данные, относящиеся к запросу субъекта данных, сохраните параметры средства "Поиск контента", использовавшиеся для поиска необходимых данных. Скорее всего, вам потребуется повторно использовать этот поиск, чтобы выполнить другие действия в процессе реагирования на запрос субъекта данных, например [получить копию этих данных](#providing-a-copy-of-personal-data), [экспортировать](#exporting-personal-data) или [безвозвратно удалить](#deleting-personal-data) их.

### <a name="additional-considerations-for-selected-applications"></a>Дополнительные рекомендации для отдельных приложений

В разделах ниже описаны действия, которые следует учитывать при поиске данных в указанных ниже приложениях Office 365.

- [Office Lens](#office-lens)
- [Параметры интерфейса OneDrive для бизнеса и SharePoint Online](#onedrive-for-business-and-sharepoint-online-experience-settings)
- [Microsoft Teams для образования](#microsoft-teams-for-education)
- [Microsoft To-Do](#microsoft-to-do)
- [Skype для бизнеса](#skype-for-business)

#### <a name="office-lens"></a>Office Lens

Пользователь, применяющий Office Lens (приложение для камеры, поддерживаемое устройствами с iOS, Android и Windows), может делать фотографии досок, печатных документов, визитных карточек и других объектов с большим количеством текста. В Office Lens используется технология распознавания текста, считывающая текст с изображения и сохраняющая его в документе Office, например в виде файла Word, PowerPoint или OneNote либо в виде PDF-файла. Затем пользователь может отправить файл, содержащий текст с изображения, в свою учетную запись OneDrive для бизнеса в Office 365. Это означает, что вы можете использовать средство "Поиск контента" для поиска, удаления и экспорта данных в файлах, созданных на основе изображений в Office Lens, а также для получения доступа к ним. Дополнительные сведения об Office Lens см. в указанных ниже статьях.

- [Office Lens для iOS](https://support.microsoft.com/ru-RU/office/microsoft-office-lens-for-ios-fbdca5f4-1b1b-4391-a931-dc1c2582397b)
- [Office Lens для Android](https://support.office.com/article/Office-Lens-for-Android-ec124207-0049-4201-afaf-b5874a8e6f2b)
- [Office Lens для Windows](https://support.microsoft.com/ru-RU/office/office-lens-for-windows-577ec09d-8da2-4029-8bb7-12f8114f472a)

#### <a name="onedrive-for-business-and-sharepoint-online-experience-settings"></a>Параметры интерфейса OneDrive для бизнеса и SharePoint Online

In addition to user-created files stored in OneDrive for Business accounts and SharePoint Online sites, these services store information about the user that is used to enable various experiences. Users still in your organization can access much of this information by using in-product functionality. The following information provides guidance on how to access, view, and export OneDrive for Business and SharePoint Online application data.

##### <a name="sharepoint-user-profiles"></a>Профили пользователей SharePoint

С помощью своих профилей Delve пользователи могут настраивать свойства, хранящиеся в профилях пользователей SharePoint Online, в том числе сведения о днях рождения, номера мобильных телефонов (и другие контактные данные), сведения о себе, о проектах, навыках, знаниях, образовании, интересах и хобби.

###### <a name="end-users"></a>Пользователи

End users can discover, access, and rectify SharePoint Online user profile data using the Delve profile experience. See [View and update your profile in Office Delve](https://support.office.com/article/view-and-update-your-profile-in-office-delve-4e84343b-eedf-45a1-aeb9-8627ccca14ba) for more details.

Кроме того, чтобы получить доступ к данным профиля SharePoint, пользователь может перейти на **страницу редактирования профиля** в своей учетной записи OneDrive для бизнеса. Чтобы перейти на эту страницу, добавьте имя **EditProfile.aspx** к URL-адресу учетной записи OneDrive для бизнеса. Например, для пользователя <strong>user1@contoso.com</strong> учетная запись OneDrive для бизнеса будет расположена по следующему адресу:

```URL
`https://contoso-my.sharepoint.com/personal/user1\_contoso\_com/\_layouts/15/OneDrive.aspx`
```

URL-адрес страницы редактирования профиля будет таким:

```URL
`https://contoso-my.sharepoint.com/personal/user1\_contoso\_com/\_layouts/15/EditProfile.aspx`
```

Свойства, полученные из Azure Active Directory, нельзя изменить в SharePoint Online. Тем не менее пользователи могут перейти на свою страницу **Учетная запись**, выбрав свою **фотографию** в заголовке Office 365, а затем щелкнув **Моя учетная запись**. Чтобы изменить здесь свойства, может потребоваться помощь администраторов по обнаружению и уточнению свойств профиля пользователя, а также по доступу к ним.

###### <a name="admins"></a>Администраторы

В Центре администрирования SharePoint администратор может просматривать и изменять свойства профилей. Перейдите в **Центр администрирования SharePoint** и откройте вкладку **Профили пользователей**. Выберите **Управление профилями пользователей**, введите имя пользователя и нажмите кнопку **Найти**. Администратор может щелкнуть правой кнопкой мыши любого пользователя и выбрать пункт **Изменить мой профиль**. Свойства, полученные из Azure Active Directory, нельзя изменить в SharePoint Online.

An admin can export all User Profile properties for a user by using the **Export-SPOUserProfile** cmdlet in SharePoint Online PowerShell. See  [Export-SPOUserProfile](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spouserprofile?view=sharepoint-ps).

Дополнительные сведения о профилях пользователей см. в статье [Управление профилями пользователей в Центре администрирования SharePoint](https://docs.microsoft.com/sharepoint/manage-user-profiles).

##### <a name="user-information-list-on-sharepoint-online-sites"></a>Список сведений о пользователях на сайтах SharePoint Online

Часть профиля пользователя SharePoint синхронизируется со списком сведений о пользователях на каждом сайте, который он посещает или к которому ему предоставили доступ. Это используется в некоторых интерфейсах SharePoint Online, например в столбцах "Люди" в библиотеках документов, для отображения базовых сведений о пользователе, таких как имя создателя документа. Данные в списке сведений о пользователях соответствуют данным, хранящимся в профиле пользователя SharePoint, и автоматически исправляются при изменении источника. Что касается удаленных пользователей, эти данные остаются на посещенных ими сайтах в целях обеспечения целостности данных в полях столбцов SharePoint. 

Admins can control which properties are replicable inside the SharePoint admin center. To do this:

1. Перейдите в **Центр администрирования SharePoint** и откройте вкладку **профили пользователей**.
2. Нажмите **Управление свойствами пользователя**. Появится список свойств.
3. Щелкните правой кнопкой мыши любое свойство, выберите пункт **Изменить** и настраивайте различные параметры.
4. В разделе **Параметры политики** есть свойство "реплицируемый", указывающее, будет ли свойство представлено в списке сведений о пользователях. Это свойство можно настроить не для всех свойств.

An admin can export all User information properties for a user on a given site by using the **Export-SPOUserInfo** cmdlet in SharePoint Online PowerShell. See [Export-SPOUserInfo](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spouserinfo?view=sharepoint-ps).

##### <a name="onedrive-for-business-experience-settings"></a>Параметры интерфейса OneDrive для бизнеса

A user's OneDrive for Business experience stores information to help the user find and navigate content of interest to them. Most of this information can be accessed by end users using in-product features. An admin can export the information using a [PowerShell Script](https://docs.microsoft.com/powershell/scripting/overview) and [SharePoint Client-Side Object Model (CSOM)](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-client-library-code) commands.

Дополнительные сведения о параметрах, их хранении и экспорте см. в статье [Экспорт параметров интерфейса OneDrive для бизнеса](https://docs.microsoft.com/sharepoint/export-odfb-lists).

##### <a name="onedrive-for-business-and-sharepoint-online-search"></a>Поиск в OneDrive для бизнеса и SharePoint Online

The in-app search experience in OneDrive for Business and SharePoint Online stores a user's search queries for 30 days to increase relevance of search results. An admin can export search queries for a user by using the **Export-SPOQueryLogs** cmdlet in SharePoint Online PowerShell. See [Export-SPOQueryLogs](https://docs.microsoft.com/powershell/module/sharepoint-online/export-spoquerylogs?view=sharepoint-ps).

#### <a name="microsoft-teams-for-education"></a>Microsoft Teams для образования

Microsoft Teams for Education offers two additional collaboration features that teachers and students can use that creates and stores personal data: Assignments and OneNote Class Notebook. You can use Content Search to discover data in both.

##### <a name="assignments"></a>Задания

Students files associated with an Assignment are stored in a document library in the corresponding Teams SharePoint Online site. IT admins can use the Content Search tool to search for student files that are related to assignments. For example, an admin could search all SharePoint Online sites in the organization and use the student's name and class or assignment name in the search query to find data relevant to a DSR.

There's other data related to Assignments that isn't stored in the class team SharePoint Online site, which means it's not discoverable with Content Search. This includes:

- Файлы, которые преподаватели назначают учащимся в рамках задания
- Оценки учащихся и обратная связь со стороны преподавателя
- Список документов, переданных в качестве заданий учащимся
- Метаданные задания

Чтобы найти данные этого типа, релевантные для запроса субъекта данных, ИТ-администратору или владельцу данных (например, преподавателю) может потребоваться перейти к Заданиям в группе класса.

##### <a name="onenote-class-notebook"></a>Записная книжка OneNote для занятий

The OneNote Class Notebook is stored in the class team SharePoint Online site. Every student in a class has a private notebook that's shared with the teacher. There's also a content library where a teacher can share documents with students, and a collaboration space for all students in the class. Data related to these capabilities is discoverable with Content Search.

Ниже приведены рекомендации по поиску данных в записной книжке для занятий.

1. Запустите средство "Поиск контента", используя указанные ниже критерии поиска.

   - Поиск на всех сайтах SharePoint Online

   - Включите название команды класса в качестве ключевого слова для поиска; например, «Биология 9С».

2. Просмотрите результаты поиска и найдите элемент, который соответствует записной книжке для занятий.
3. Select that item, and then copy the folder path that's displayed in the details pane. This is the root folder for the Class Notebook.
4. Edit the search that you created in step 1 and replace the class name in the keyword query with the folder path of the Class Notebook and precede the folder path with the **path** site property; for example, **path:"<https://contosoedu.onmicrosoft.com/sites/9C> Biology/SiteAssets/9C Biology Notebook/"**. Be sure to include the quotation marks and the trailing forward slash.
5. Добавьте условие поиска, выберите условие File Type (Тип файла) и используйте его для значения типа файла. В результатах поиска будут возвращены все файлы OneNote. Полученный в результате синтаксис ключевого слова будет выглядеть приблизительно так:[](#building-search-queries-to-find-personal-data)

    ```Query
   path:"<https://contosoedu.onmicrosoft.com/sites/9C> Biology/SiteAssets/9C Biology Notebook/" AND filetype="one"
   ```

6.  Повторно запустите средство "Поиск контента". Результаты поиска должны содержать все файлы OneNote для записной книжки для занятий из группы класса.

#### <a name="microsoft-to-do"></a>Microsoft To-Do

Задачи (называемые *задачами*, которые сохраняются в *списках дел*) в Microsoft To Do сохраняются как задачи в почтовом ящике пользователя Exchange Online. Это означает, что вы можете использовать средство "Поиск контента" для поиска, открытия, удаления и экспорта задач. Дополнительные сведения см. в статье [Настройка Microsoft To-Do](https://support.microsoft.com/ru-RU/office/set-up-microsoft-to-do-490c1a8c-2333-4952-8125-841afadb9620).

#### <a name="skype-for-business"></a>Skype для бизнеса

Ниже приведены сведения о том, как получать доступ к персональным данным в Skype для бизнеса, а также просматривать и экспортировать их.

- Files attached to a meeting are retained in the actual meeting for 180 days and then become inaccessible. These files can be accessed by meeting participants by joining the meeting from the meeting request and then viewing or downloading the attached file. See the "Use the attachments in the meeting" section in [Preload attachments for a Skype for Business meeting](https://support.microsoft.com/ru-RU/office/preload-attachments-for-a-skype-for-business-meeting-fd3d9f9d-b448-4754-b813-02e49393f251).
- Conversations in Skype for Business are retained in the Conversation History folder in user mailboxes. You can use Content Search to search mailboxes for data in Skype conversations.
- A data subject can export their contacts in Skype for Business. To do this, they would right-click a contact group in Skype for Business and click **Copy**. Then they can paste the list of email addresses into a text or Word document.
- If the Exchange Online mailbox of a meeting participant is placed on Litigation Hold or assigned to an Office 365 retention policy, files attached to a meeting are retained in the participants mailbox. You can use Content Search to search for those files in the participant's mailbox if the retention period for the file has not expired. For more information about retaining files, see [Retaining large files attached to a Skype for Business meeting](https://docs.microsoft.com/skypeforbusiness/set-up-policies-in-your-organization/retaining-large-files-attached-to-a-meeting).

## <a name="providing-a-copy-of-personal-data"></a>Предоставление копии персональных данных

After you've found personal data that is potentially responsive to a DSR, it's up to you and your organization to decide which data to provide the data subject. For example, you can provide them with a copy of the actual document, an appropriately redacted version, or a screenshot of the portions that you've deemed appropriate to share. For each of these responses to an access request, you'll have to retrieve a copy of the document or other item that contains the responsive data.

Когда вы предоставляете копию данных субъекту данных, вам может потребоваться удалить или отредактировать персональную информацию о других субъектах данных или конфиденциальные сведения.

### <a name="using-content-search-to-get-a-copy-of-personal-data"></a>Получение копии персональных данных с помощью средства "Поиск контента"

Есть два способа использовать инструмент поиска контента, чтобы получить копию документа или элемента почтового ящика, который вы нашли после выполнения поиска.

- Preview the search results and then download a copy of the document or item. This is a good way to download a few items or files.
- Экспортируйте результаты поиска, а затем скачайте копию всех элементов, возвращенных операцией поиска. Этот метод более сложный, но это хороший способ загрузить множество элементов, которые реагируют на DSR. В экспортируемые результаты поиска также будут включены полезные отчеты. Вы можете использовать эти отчеты для получения дополнительной информации о каждом элементе. Отчет **Results.csv** полезен, так как в нем содержится много сведений об экспортированных элементах, например о точных расположениях элементов (пример: почтовый ящик для электронных писем или URL-адрес для документов или списков, размещенных на сайтах SharePoint Online и OneDrive для бизнеса). С помощью этих сведений вы сможете определить владельца элемента, если вам потребуется связаться с ним в процессе расследования, связанного с запросом субъекта данных. Дополнительные сведения об отчетах, включаемых в экспортируемые результаты поиска, см. в статье [Экспорт отчета средства "Поиск контента"](https://docs.microsoft.com/microsoft-365/compliance/export-a-content-search-report).

#### <a name="preview-and-download-items"></a>Просмотр и скачивание элементов

После того, как вы запустите новый поиск или откроете существующий поиск, вы можете просмотреть каждый элемент, который соответствует поисковому запросу, чтобы убедиться, что он связан с исследуемым DSR. К этим элементам относятся списки и веб-страницы SharePoint, возвращенные в результатах поиска. Вы также можете скачать исходный файл (если вам необходимо предоставить его субъекту данных). В обоих случаях вы можете сделать снимок экрана, чтобы удовлетворить запрос субъекта данных на получение информации.

Некоторые типы предметов не могут быть предварительно просмотрены. Если для какого-либо элемента или типа файла не поддерживается функция просмотра, вы можете скачать элемент на свой локальный компьютер, на сопоставленный сетевой диск или в другое расположение в сети. Вы можете просматривать только [файлы поддерживаемых типов](https://docs.microsoft.com/microsoft-365/compliance/content-search).

Чтобы просмотреть и скачать элементы, выполните указанные ниже действия.

1. Откройте средство "Поиск контента" в Центре безопасности и соответствия требованиям.
2. Если результаты не отображаются, щелкните **Просмотр результатов**.
3. Чтобы просмотреть элемент, щелкните его.
4. Click **Download original file** to download the item to your local computer. You'll also have to download items that can't be previewed.

Дополнительные сведения о просмотре результатов поиска см. в разделе [Предварительный просмотр результатов поиска](https://docs.microsoft.com/microsoft-365/compliance/content-search).

#### <a name="export-and-download-items"></a>Экспорт и скачивание элементов

You can also export the results of a content search to get a copy of email messages, documents, lists, and web pages containing the personal data, though this method is more involved than previewing items. See the next section for details about [exporting the results of a Content Search](#export-and-download-content-using-content-search).

## <a name="exporting-personal-data"></a>Экспорт персональных данных

The "right of data portability" allows a data subject to request an electronic copy of personal data that's in a "structured, commonly used, machine-readable format", and to request that your organization transmit these electronic files to another data controller. Microsoft supports this right in two ways:

- Предлагая приложения Office 365, сохраняющие данные в пригодном для использования на компьютерах и широко распространенном формате. Дополнительные сведения о форматах файлов Office см. в статье [Форматы файлов Office: технические документы](https://msdn.microsoft.com/library/office/cc313105(v=office.12).aspx).
- Предоставление вашей организации разрешения на экспорт данных в форматах файлов соответствующих приложений или в форматах (например, CSV, TXT и JSON), которые можно без труда импортировать в другое приложение.

Чтобы выполнить запрос субъекта данных, вы можете экспортировать документы Office в форматах файлов соответствующих приложений и экспортировать данные из других приложений Office 365.

### <a name="export-and-download-content-using-content-search"></a>Экспорт и скачивание контента помощью средства "Поиск контента"

When you export the results of a Content Search, email items can be downloaded as PST files or as individual messages (.msg files). When you export documents and lists from SharePoint Online and OneDrive for Business sites, copies in the native file formats are exported. For example, SharePoint lists are exported as CSV files and Web pages are exported as .aspx or html files.

>[!NOTE]
>Для экспорта элементов почтового ящика из почтового ящика пользователя с помощью поиска контента необходимо, чтобы пользователю (из почтового ящика которого вы экспортируете элементы) была назначена лицензия Exchange Online Plan 2. 

Чтобы экспортировать и скачать элементы, выполните указанные ниже действия.

1. Откройте средство "Поиск контента" в Центре безопасности и соответствия требованиям.
2. На всплывающей странице поиска щелкните ![значок для скачивания](../media/o365-dsr_image21.png) **Дополнительно**, а затем — **Экспорт результатов**. Вы также можете экспортировать отчет.
3. Complete the sections on the **Export results** fly out page. Be sure to use the scroll bar to view all export options.
4. Вернитесь на страницу средства "Поиск контента" в Центре безопасности и соответствия требованиям и откройте вкладку **Экспорт**.
5. Обновите страницу, нажав кнопку **Обновить**.
6. В столбце **Имя** щелкните задание экспорта, которое вы создали. Имя задания экспорта — это имя операции поиска контента, после которого следует слово **\_Export** (Экспорт).
7. На всплывающей странице экспорта в разделе **Ключ экспорта** щелкните **Копировать в буфер обмена**. Этот ключ потребуется для скачивания результатов поиска в действии 10.
8. В верхней части всплывающей страницы щелкните ![значок для скачивания](../media/o365-dsr_image21.png) **Скачать результаты**.
9. Если вам будет предложено установить **средство экспорта службы обнаружения электронных данных Microsoft Office 365**, щелкните **Установить**.
10. В **средстве экспорта службы обнаружения электронных данных** в соответствующем поле вставьте ключ экспорта, который вы скопировали в действии 7.
11. Нажмите кнопку **Обзор** и укажите расположение, в которое вы хотите скачать файлы результатов поиска.
12. Нажмите кнопку **Запустить**, чтобы скачать результаты поиска на свой компьютер.

When the export process is complete, you can access the files in the location on your local computer where they were downloaded. Results of a content search are downloaded to a folder named after the Content Search. Documents from sites are copied to a subfolder named **SharePoint**. Mailbox items are copied to subfolder named **Exchange**.

Подробные пошаговые инструкции см. в статье [Экспорт результатов поиска контента из Центра безопасности и соответствия требованиям](export-search-results.md).

### <a name="downloading-documents-and-lists-from-sharepoint-online-and-onedrive-for-business"></a>Скачивание документов и списков из SharePoint Online и OneDrive для бизнеса

Another way to export data from SharePoint Online and OneDrive for Business is to download documents and lists directly from a SharePoint Online site or a OneDrive for Business account. You would have to get assigned the permissions to access a site, and then go to the site and download the contents. See:

- [Скачивание файлов и папок из OneDrive или SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)
- [Экспорт списков SharePoint в Excel](https://support.office.com/article/export-to-excel-from-sharepoint-bfb2ea48-6118-4fa9-abb6-cced9424e5d9)

For some DSR export requests, you may want to allow the data subject to download content themselves. This enables the data subject to go to a SharePoint Online site or shared folder and click **Sync** to sync all contents in the document library or selected folders. See:

- [Предоставление пользователям возможности синхронизировать файлы SharePoint с помощью нового клиента синхронизации OneDrive](https://docs.microsoft.com/sharepoint/let-users-use-new-onedrive-sync-client)
- [Синхронизация файлов SharePoint с помощью нового клиента синхронизации OneDrive](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-client-6de9ede8-5b6e-4503-80b2-6190f3354a88)

## <a name="deleting-personal-data"></a>Удаление персональных данных

«Право на удаление» путем удаления персональных данных из данных клиентов организации является ключевой защитой в GDPR. Удаление персональных данных подразумевает полное удаление документов или файлов либо удаление определенных данных в документах или файлах (эти действие и процесс аналогичны действиям и процессам, описанным в разделе "Уточнение" данного руководства).

Когда вы ведете расследование или подготавливаете персональные данные в ответ на запрос субъекта данных, необходимо понимать несколько важных аспектов работы функций удаления (и хранения) в Office 365.

- **Обратимое и необратимое удаление.** В службах Office 365, например в Exchange Online, SharePoint Online и OneDrive для бизнеса, используются понятия *обратимого* и *необратимого удаления*, от которых зависит возможность восстановления удаленного элемента (обычно в течение ограниченного периода) до момента его безвозвратного удаления из облака Майкрософт без возможности восстановления. В этом контексте пользователь или администратор может восстановить обратимо удаленный элемент в течение определенного периода времени до момента необратимого удаления элемента. После необратимого удаления элемента он помечается для безвозвратного удаления и удаляется соответствующей службой Office 365. Ниже описано, как работают операции обратимого и необратимого удаления элементов в почтовых ящиках и на сайтах (независимо от того, кто удаляет их, владелец или администратор).

    - **Почтовые ящики.** Обратимое удаление элемента выполняется, когда элемент удаляют из папки "Удаленные" либо когда пользователь удаляет его, нажав клавиши **SHIFT+DELETE**. После обратимого удаления элемента система перемещает его в папку "Элементы с возможностью восстановления" в почтовом ящике. На этом этапе пользователь может восстановить элемент до истечения срока его хранения (в Office 365 удаленные элементы хранятся 14 дней, но администратор может увеличить этот срок до 30 дней). По истечении срока хранения система выполняет необратимое удаление элемента и перемещает его в скрытую папку (называемую *Очистка*). Элемент будет безвозвратно удален (очищен) из Office 365 при следующей обработке почтового ящика (обработка почтовых ящиков выполняется раз в семь дней).

    - **Сайты SharePoint Online и OneDrive для бизнеса**. При удалении файла или документа система перемещает его в корзину сайта (называемую *первой корзиной*), которая аналогична корзине в ОС Windows. Элемент остается в корзине в течение 93 дней (период хранения удаленного элемента для сайтов в Office 365). По окончании этого периода система автоматически перемещает элемент в корзину семейства веб-сайтов, которая называется *второй корзиной*. (Обратите внимание, что пользователи или администраторы с соответствующими правами могут удалять элементы из первой корзины). На этом этапе элемент становится обратимо удаленным; его может восстановить администратор семейства веб-сайтов в SharePoint Online либо пользователь или администратор OneDrive для бизнеса. После удаления элемента из второй корзины (вручную или автоматически) он становится необратимо удаленным и недоступным для пользователя или администратора. Продолжительность периода хранения равна 93 дням и для первой, и для второй корзины. То есть период хранения для второй корзины начинается при первом удалении элемента. Таким образом, максимальное суммарное время хранения в обеих корзинах составляет 93 дня.

>[!NOTE]
>Понимая, какие действия приводят к обратимому и необратимому удалению элемента, вы сможете определять, как удалять данные способом, соответствующим требованиям GDPR, в ответ на запрос на удаление.

- **Правовые ограничения и политики хранения**. В Office 365 «почтовые ящики» и сайты могут быть заблокированы. Вкратце, это означает, что если почтовый ящик или сайт находится на удержании, никакие элементы не подлежат безвозвратному (необратимому) удалению, пока не закончится период хранения для элемента либо пока удержание не будет отменено. Это важно в контексте удаления контента клиентов в ответ на запросы субъектов данных: если элемент необратимо удален из расположения контента, находящегося на удержании, элемент не будет безвозвратно удален из Office 365. Это означает, что ИТ-администратор сможет восстановить этот элемент. Если в вашей организации есть требование или политика, подразумевающие безвозвратное удаление данных в Office 365 без возможности восстановления в ответ на запрос субъекта данных, для безвозвратного удаления данных в Office 365 потребуется отменить удержание для соответствующего почтового ящика или сайта. Скорее всего, в рекомендациях вашей организации по реагированию на DSR имеется процесс, позволяющий определить, имеет ли приоритет конкретный запрос на удаление DSR или законное удержание. Если удержание отменено для удаления элементов, после удаления необходимых элементов можно снова включить его.

### <a name="deleting-documents-in-sharepoint-online-and-onedrive-for-business"></a>Удаление документов в SharePoint Online и OneDrive для бизнеса

После обнаружения документа на сайте SharePoint Online или в учетной записи OneDrive для бизнеса (используя рекомендации в разделе "Обнаружение" этого руководства), который нужно удалить, потребуется назначить специалисту по конфиденциальности данных или ИТ-администратору необходимые разрешения для доступа к сайту и удаления документа. Если это допустимо, можно также проинструктировать владельца документа о том, как удалить документ.

Вот процесс высокого уровня для удаления документов с сайтов.

1. Перейдите на сайт и найдите нужный документ.
2. Delete the document. When you delete a document from a site, it's sent to the first-stage Recycle Bin.
3. Go to the first-stage Recycle Bin (the site Recycle Bin) and delete the same document you deleted in the previous step. The document is sent to the second-stage Recycle Bin. **At this point, the document is soft-deleted**.
4. Go to the second-stage Recycle Bin (which is the site collection Recycle Bin) and delete the same document that you deleted from the first-stage Recycle Bin. **At this point, the document is hard-deleted.**

>[!IMPORTANT]
>You can't delete a document that is located on a site that is on hold (with one of the retention or legal hold features in Office 365). In the case where a DSR delete request takes precedence over a legal hold, the hold would have to be removed from the site before a document could be permanently deleted.

Подробные описания процедур представлены в перечисленных ниже статьях.

- [Удаление файла, папки или ссылки из библиотеки документов SharePoint](https://support.microsoft.com/ru-RU/office/delete-a-file-folder-or-link-from-a-sharepoint-document-library-71f3c90a-0d24-4d80-8b66-f88234b79a52)
- [Удаление элементов из корзины сайта SharePoint и ее очистка](https://support.microsoft.com/ru-RU/office/delete-items-or-empty-the-recycle-bin-of-a-sharepoint-site-2e713599-d13e-40d6-96dc-66f0a366f74e)
- [Удаление элементов из корзины семейства веб-сайтов](https://support.microsoft.com/ru-RU/office/delete-items-from-the-site-collection-recycle-bin-dd5c00c2-aef6-4458-9d04-80b185077653)
- Раздел "Получение доступа к документам бывшего сотрудника в OneDrive для бизнеса" в статье [Получение доступа к данным бывшего пользователя и создание их резервной копии](https://docs.microsoft.com/microsoft-365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data)
- [Удаление файлов и папок в OneDrive для бизнеса](https://support.office.com/article/Delete-files-or-folders-in-OneDrive-21fe345a-e488-4fa7-932b-f053c1bebe8a)
- [Удаление списка в SharePoint](https://support.microsoft.com/ru-RU/office/delete-a-list-in-sharepoint-2a7bca5b-b8fd-4e5b-8f4b-2ac034f3070d)
- [Удаление элементов списка в SharePoint Online](https://support.office.com/article/delete-list-items-in-sharepoint-online-db722233-4a38-4889-a6cf-4b33fe5c60c0)

### <a name="deleting-a-sharepoint-site"></a>Удаление сайта SharePoint

You may determine that the best way to respond to a DSR delete request is to delete an entire SharePoint site, which will delete all that data located in the site. You can do this by running cmdlets in SharePoint Online PowerShell.

- С помощью командлета [Remove-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-sposite?view=sharepoint-ps) можно удалить сайт и переместить его в корзину SharePoint Online (обратимое удаление).
- С помощью командлета [Remove-SPODeletedSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spodeletedsite?view=sharepoint-ps) можно безвозвратно удалить сайт (необратимое удаление).

Вы не можете удалить сайт, который находится на удержании eDiscovery или назначен политике хранения. Чтобы можно было удалить такой сайт, сначала требуется отменить удержание службы обнаружения электронных данных или политику хранения.

### <a name="deleting-a-onedrive-for-business-site"></a>Удаление сайта OneDrive для бизнеса

Similarly, you may determine to delete a user's OneDrive for Business site in response to a DSR deletion request. If you delete the user's Office 365 account, their OneDrive for Business site is retained (and restorable) for 30 days. After 30 days, it's moved to the SharePoint Online Recycle Bin (soft-deleted), and then after 93 days, it's permanently deleted (hard-deleted). To accelerate this process, you can use the [Remove-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-sposite?view=sharepoint-ps) cmdlet to move the OneDrive for Business site to the Recycle Bin and then use the [Remove-SPODeletedSite](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spodeletedsite?view=sharepoint-ps) cmdlet to permanently delete it. As with sites in SharePoint Online, you can't delete a user's OneDrive for Business site if it was assigned to an eDiscovery hold or a retention policy before the user's account was deleted.

### <a name="deleting-onedrive-for-business-and-sharepoint-online-experience-settings"></a>Удаление параметров интерфейса OneDrive для бизнеса и SharePoint Online

Помимо созданных пользователями файлов в учетных записях OneDrive для бизнеса и на сайтах SharePoint Online хранятся сведения о пользователе, которые применяются для включения различных интерфейсов. Эта возможность была описана выше в данном документе. Сведения о том, как получать доступ к данным приложений в OneDrive для бизнеса и SharePoint Online, а также просматривать и экспортировать их, см. в подразделе [Дополнительные рекомендации для отдельных приложений](#additional-considerations-for-selected-applications) раздела [Использование средства обнаружения электронных данных "Поиск контента" для реагирования на запросы субъектов данных](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs).

#### <a name="deleting-a-sharepoint-user-profile"></a>Удаление профиля пользователя SharePoint

The SharePoint user profile will be permanently deleted 30 days after the user account is deleted in Azure Active Directory. However, you can hard-delete the user account, which will remove the SharePoint user profile. For more information, see the [Deleting a user section in this guide](#deleting-a-user).

An admin can expedite the deletion of the User Profile for a user by using the **Remove-SPOUserProfile** cmdlet in SharePoint Online PowerShell. See [Remove-SPOUserProfile](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spouserprofile?view=sharepoint-ps). This requires the user to be at least soft-deleted in Azure Active Directory.

#### <a name="deleting-user-information-lists-on-sharepoint-online-sites"></a>Удаление списков сведений о пользователях на сайтах SharePoint Online

For users that have left the organization, this data remains in the sites they interacted with for referential integrity of SharePoint column fields. An admin can delete all User information properties for a user on a given site by using the **Remove-SPOUserInfo** command in SharePoint Online PowerShell. See [Remove-SPOUserInfo](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spouserinfo?view=sharepoint-ps) for information about running this PowerShell cmdlet.

По умолчанию эта команда сохранит отображаемое имя пользователя и удалит такие свойства, как номер телефона, электронный адрес, навыки и опыт работы или другие свойства, скопированные из профиля пользователя SharePoint Online. С помощью параметра **RedactUser** администратор может указать другое отображаемое имя пользователя в списке сведений о пользователях. Это повлияет на некоторые аспекты работы пользователя и приведет к потере данных при просмотре журнала файлов на сайте.

Finally, the redaction capability will not remove all metadata or content referencing a user from documents. The way to achieve redaction of file content and metadata is described in the [Making changes to content in OneDrive for Business and SharePoint Online](#making-changes-to-content-in-onedrive-for-business-and-sharepoint-online) section in this guide. This method consists of downloading, deleting, and then uploading a redacted copy of the file.

#### <a name="deleting-onedrive-for-business-experience-settings"></a>Удаление параметров интерфейса OneDrive для бизнеса

The recommended way to delete all OneDrive for Business experience settings and information is to remove the user's OneDrive for Business site, after reassigning any retained files to other users. An admin can delete these lists using [PowerShell Script](https://docs.microsoft.com/powershell/scripting/overview) and [SharePoint Client-Side Object Model (CSOM)](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-client-library-code) commands. See [Deleting OneDrive for Business experience settings](https://docs.microsoft.com/sharepoint/delete-odfb-lists) for more information about the settings, how they are stored, and how to delete them.

#### <a name="onedrive-for-business-and-sharepoint-online-search-queries"></a>Поисковые запросы в OneDrive для бизнеса и SharePoint Online

Поисковые запросы пользователя, созданные в поиске OneDrive для бизнеса и SharePoint Online, автоматически удаляются через 30 дней после создания запроса пользователем.

### <a name="deleting-items-in-exchange-online-mailboxes"></a>Удаление элементов в почтовых ящиках Exchange Online

Чтобы выполнить запрос субъекта данных на удаление, вам может потребоваться удалить элементы в почтовых ящиках Exchange Online. ИТ-администратор может удалять элементы в почтовых ящиках двумя способами в зависимости от того, как необходимо удалить элементы, обратимо или необратимо. Как и документы на сайтах SharePoint Online или OneDrive для бизнеса, элементы в почтовом ящике, находящемся в режиме ожидания, не могут быть окончательно удалены из Office 365. Прежде чем удалять элементы, требуется отменить удержание. И снова, вам потребуется определить, что имеет преимущество — удержание почтового ящика или запрос субъекта данных на удаление.

#### <a name="soft-delete-mailbox-items"></a>Обратимое удаление элементов почтовых ящиков

С помощью действий средства "Поиск контента" вы можете обратимо удалять элементы, возвращенные средством "Поиск контента". Как указано выше, система перемещает обратимо удаленные элементы в папку "Элементы с возможностью восстановления" в почтовом ящике.

Ниже кратко описан этот процесс.

1. Создайте и запустите операцию в средстве "Поиск контента", чтобы найти элементы, которые нужно удалить из почтового ящика пользователя. Возможно, придется повторно запустить поиск и сузить область результатов поиска, чтобы в них были только те элементы, которые нужно удалить.
2. С помощью команды **New-ComplianceSearchAction** **-Purge** в Office 365 PowerShell обратимо удалите элемент, возвращенный операцией поиска контента, созданной в предыдущем действии.

Подробные инструкции см. в статье [Поиск и удаление электронных писем в вашей организации](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization).

#### <a name="hard-delete-mailbox-items"></a>Необратимое удаление элементов почтовых ящиков

If you have to hard-delete mailbox items in response to the DSR deletion request, you can use the **Search-Mailbox -DeleteContent** command in Exchange Online PowerShell. If you use this method, consider using Content Search to develop and refine a search query so that only the items that are to be deleted are returned in the search. Then you can use that query syntax when you run the **Search-Mailbox -DeleteContent** command.

Подробные инструкции см. в статье [Поиск и удаление сообщений](https://technet.microsoft.com/library/ff459253(v=exchg.150).aspx).

#### <a name="hard-delete-items-in-a-mailbox-on-hold"></a>Необратимое удаление элементов в почтовом ящике, поставленном на удержание

As previously explained, if you hard-delete items in a mailbox on hold, items are not removed from the mailbox. They are moved to a hidden folder in the Recoverable Items folder (the **Purges** folder) and will remain there until the hold duration for the item expires or until the hold is removed from the mailbox. If either of those things happen, the items will be purged from Office 365 the next time that the mailbox is processed.

Your organization might determine that items being permanently deleted when the hold duration expires meets the requirements for a DSR deletion request. However, if you determine that mailbox items must be immediately purged from Office 365, you would have to remove the hold from the mailbox and then hard-deleted the items from the mailbox. For detailed instructions, see [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](https://docs.microsoft.com/microsoft-365/compliance/delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold).

>[!NOTE]
>Чтобы необратимо удалить элементы почтового ящика для выполнения запроса субъекта данных на удаление путем выполнения процедуры, описанной в предыдущем разделе, вам, возможно, придется обратимо удалить эти элементы, когда почтовый ящик будет все еще находиться на удержании, чтобы система переместила элементы в папку "Элементы с возможностью восстановления".

## <a name="deleting-a-user"></a>Удаление пользователя

In addition to deleting personal data in response to a DSR deletion request, a data subject's "right to be forgotten" may also be fulfilled by deleting their user account. Here are some reasons that you might want to delete a user:

- Субъект данных больше не работает в вашей организации (или находится в процессе увольнения).
- The data subject has requested that you delete system-generated logs that have been collected about them. Examples of data in system-generated logs include Office 365 app and service usage data, information about search requests performed by the data subject, and data generated by product and services as a product of system functionality and interaction by users or other systems. For more information, see [Part 3: Responding to DSRs for system-generated Logs](#part-3-responding-to-dsrs-for-system-generated-logs) in this guide.
- Необходимо на постоянной основе запретить субъекту данных обработку данных в Office 365 и доступ к ним (в противоположность временному запрету доступа c помощью методов, описанных в разделе [Реагирование на запросы субъектов данных на запрет доступа к данным](#responding-to-dsr-restriction-requests).

После удаления учетной записи пользователя:

- Пользователь больше не сможет входить в Office 365 или получать доступ к каким-либо ресурсам вашей организации в службах Майкрософт, например к своей учетной записи OneDrive для бизнеса, сайтам SharePoint Online или почтовому ящику Exchange Online.
- Персональные данные, например электронный адрес, псевдоним, номер телефона и почтовый адрес, сопоставленные с учетной записью пользователя, будут удалены.
- Из некоторых приложений Office 365 удаляется информация о пользователе. Например, в Microsoft Flow удаленный пользователь будет удален из списка владельцев общего потока.
- Журналы, созданные системой, со сведениями о субъекте данных, кроме данных, которые могут скомпрометировать безопасность или надежность службы, будут удалены через 30 дней после удаления учетной записи пользователя. Дополнительные сведения см. в разделе [Удаление системных журналов](#deleting-system-generated-logs).

>[!IMPORTANT]
>After you delete a user account, that person will lose the ability to sign in to Office 365 and the ability to sign in to any products or services for which he or she formerly relied upon for a work or school account. That person would also be unable to initiate any DSR requests through Microsoft directly in instances where Microsoft is the data controller. For more information, see the [Product and services authenticated with an Org ID for which Microsoft is a data controller](#product-and-services-authenticated-with-an-org-id-for-which-microsoft-is-a-data-controller) section in Part 4 of this guide.

>[!NOTE]
>In the event that you are a customer currently engaged in FastTrack migrations, deleting the user account will not delete the data copy held by the Microsoft FastTrack team, which is held for the sole purpose of completing the migration. If, during the migration, you would like the Microsoft FastTrack team to also delete the data copy, you can [submit a request](https://go.microsoft.com/fwlink/?linkid=874544). In the ordinary course of business, Microsoft FastTrack will delete all data copies once the migration is complete.

Аналогично операциям обратимого и необратимого удаления данных, описанным в предыдущем разделе об удалении персональных данных, когда вы удаляете учетную запись пользователя, она также может быть в состоянии обратимого или необратимого удаления.

- Когда вы изначально удаляете учетную запись пользователя (удалив пользователя в Центре администрирования или на портале Azure), происходит обратимое удаление учетной записи, и система перемещает ее в корзину в Azure на срок до 30 дней. На этом этапе учетную запись пользователя можно восстановить.
- If you permanently deleted the user account, the user account is hard-deleted and removed from the Recycle Bin in Azure. At this point, the user account can't be restored, and any data associated with the user account will be permanently removed from the Microsoft cloud. Hard-deleting an account deletes system-generated logs about the data subject, except for data that may compromise the security or stability of the service.

Вот общее описание процедуры удаления пользователя из вашей организации.

1. Перейдите в Центр администрирования или на портал Azure и найдите нужного пользователя.

2. Delete the user. When you initially delete the user, the user's account is sent to the Recycle Bin. At this point, the user is soft-deleted. The account is retained in the soft-deleted for 30 days, which allows you to restore the account. After 30 days, the account is automatically hard-deleted. For specific instructions, see [Delete users from Azure AD](https://docs.microsoft.com/azure/active-directory/add-users-azure-active-directory).<br><br> Вы также можете обратимо удалить учетную запись пользователя в Центре администрирования. См. статью [Удаление пользователя из организации](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user).

3. Если вы не хотите ждать 30 дней до необратимого удаления учетной записи пользователя, можно вручную необратимо удалить ее. Чтобы сделать это на портале Azure, перейдите в список недавно удаленных пользователей и безвозвратно удалите пользователя. На этом этапе пользователь будет необратимо удален. Инструкции см. в разделе "Безвозвратное удаление недавно удаленного пользователя" в статье [Восстановление удаленного пользователя в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-users-restore).

На портале администрирования Office 365 невозможно необратимо удалить пользователя.

>[!NOTE]
>In Office 365 operated by 21Vianet (China), you can't permanently delete a user as previously described. To permanently delete a user, you can submit a request via the Office 365 admin portal at this [URL](https://portal.partner.microsoftonline.cn/AdminPortal/Home#/homepage). Go to **Commerce** and then select **Subscription** -> **Privacy** ->  **GDPR** and enter the required information.

### <a name="removing-exchange-online-data"></a>Удаление данных в Exchange Online

При удалении пользователя необходимо понимать, что происходит с почтовым ящиком пользователя в Exchange Online. После необратимого удаления учетной записи пользователя (в действии 3 описанного выше процесса) почтовый ящик удаленного пользователя не будет автоматически удален из Office 365. С момента необратимого удаления учетной записи пользователя до ее безвозвратного удаления из Office 365 может пройти до 60 дней. Ниже описаны жизненный цикл почтового ящика после удаления учетной записи пользователя и состояние данных в почтовом ящике в этот период.

- **Дни 1–30**: почтовый ящик можно полностью восстановить, восстановив обратимо удаленную учетную запись пользователя.
- **Дни 31–60**: в течение 30 дней после необратимого удаления учетной записи пользователя администратор вашей организации может восстановить данные, хранящиеся в почтовом ящике, и импортировать их в другой почтовый ящик. Благодаря этому организации могут при необходимости восстанавливать данные в почтовом ящике.
- **Дни 61–90**: у администратора больше нет возможности восстановить данные в почтовом ящике. Данные в почтовом ящике будут помечены для безвозвратного удаления, и в течение последующих 30 дней будут удалены из Office 365.

Если вы считаете, что этот жизненный цикл почтового ящика не соответствует требованиям вашей организации в части реагирования на запросы субъектов данных на удаление, вы можете [обратиться в службу поддержки Майкрософт](https://support.microsoft.com/) (*после* того как необратимо удалите учетную запись пользователя) и отправить запрос на ручное инициирование процесса безвозвратного удаления данных в почтовом ящике. Этот процесс безвозвратного удаления данных в почтовом ящике запускается автоматически после 61-го дня жизненного цикла, поэтому, начиная с этого дня, нет смысла обращаться в Майкрософт с таким запросом.

## <a name="using-in-app-functionality-to-respond-to-dsrs"></a>Использование функций, имеющихся в приложениях, для реагирования на запросы субъектов данных

While most Customer Data is authored and produced using the applications described in the previous section, Office 365 also offers many other applications that customers can use to produce and store Customer Data. However, Content Search doesn't currently have the ability to find data authored in these other Office 365 applications. To find data generated by these applications, you or the data owner must use in-product functionality or features to find data that may be relevant to a DSR. The following table lists these Office 365 applications. Click the application icon to go the section in this guide that describes how to respond to DSR requests for data authored in the application.

***Таблица 3. Приложения, в которых можно использовать встроенные функции для поиска данных клиента***

||||
|:-----:|:-----:|:-----:|:-----:|
| ![Значок Access](../media/o365-access-64x64.png) <br> [Access](#access) | ![Значок Office](../media/O365-DSR-Doc_image22.png) <br> [Бизнес-приложение <br> для Office 365](#business-apps-for-office-365) | ![Значок Office](../media/O365-DSR-Doc_image22.png) <br> [Образование](#education)|
| ![Значок Flow](../media/o365-flow-64x64.png) <br> [Flow](#flow) | ![Значок Forms](../media/o365-forms-64x64.png) <br> [Forms](#forms) |![Значок Kaizala](../media/o365-kaizala-64x64.png) <br> [Kaizala](#kaizala) |
| ![Значок Планировщика](../media/o365-planner-64x64.png) <br> [Планировщик](#planner) |![Значок PowerApps](../media/o365-powerapps-64x64.png) <br> [Power Apps](#powerapps) |![Значок Power BI](../media/o365-powerbi-64x64.png) <br> [Power BI](#power-bi) |
|![Значок Project](../media/o365-project-64x64.png) <br> [Project](#project-online) |![Значок Publisher](../media/o365-publisher-64x64.png) <br> [Publisher](#publisher) |![Значок Stream](../media/o365-stream-64x64.png) <br> [Stream](#stream) |![Значок Sway](../media/o365-sway-64x64.png) <br> [Sway](#sway) | ![Значок Доски](../media/O365-DSR-Doc_image36.png) <br> [Доска](#whiteboard) |
|![Значок Yammer](../media/o365-yammer-64x64.png) <br> [Yammer](#yammer) |
|||

### <a name="access"></a>Access

В следующих разделах описано, как использовать встроенные функции Microsoft Access для поиска, просмотра, экспорта и удаления персональных данных.

##### <a name="discover"></a>Обнаружение

There are several ways that you can search for records in an Access database that might be responsive to a DSR request. For a DSR investigation, you can search for records that related to the data subject or search for records that contain specific data. For example, you could either search or go to a record that corresponds to the data subject. Or you can search for records that contain specific data, such as personal data about the data subject. For more information, see:

- [Поиск записей в базе данных Access](https://support.microsoft.com/ru-RU/office/find-records-in-an-access-database-705220b7-0255-4ef9-9349-6bd7442d1b7e) 
- [Создание простого запроса на выборку](https://support.office.com/article/create-a-simple-select-query-de8b1c8d-14e9-4b25-8e22-70888d54de59)

##### <a name="access"></a>Доступ

After you find the records or fields that are relevant to the DSR request, you can take a screenshot of the data or export it to an Excel file, Word file, or a text file. You can also create and print a report based on a record source, or a select query that you created to find the data. See:

- [Общие сведения об отчетах в Access](https://support.office.com/article/introduction-to-reports-in-access-e0869f59-7536-4d19-8e05-7158dcd3681c)
- [Экспорт данных в Excel](https://support.office.com/article/export-data-to-excel-64e974e6-ae43-4301-a53e-20463655b1a9)
- [Экспорт данных в документ Word](https://support.microsoft.com/ru-RU/office/export-access-data-to-a-word-document-6e954c8e-2243-4cb9-8544-607e5b7bfc12)
- [Экспорт данных в текстовый файл](https://support.microsoft.com/ru-RU/office/export-data-to-a-text-file-f72dfc38-a8a0-4c5b-8c2c-bf2950814140)

##### <a name="export"></a>Экспорт

Как упоминалось ранее, вы можете экспортировать данные из базы данных Access в различные форматы файлов. Выбор формата файла для экспорта можно определить по конкретному запросу DSR на экспорт от субъекта данных. Список статей о том, как экспортировать данные Access в различных форматах файлов, представлен в разделе [Импорт и экспорт](https://support.microsoft.com/ru-RU/office/import-and-export-c060505b-d8ac-4499-8879-733e56c6106f).

##### <a name="delete"></a>Удаление

Вы можете удалить всю запись или только поле из базы данных Access. Самый быстрый способ удалить запись из базы данных Access — открыть таблицу в режиме таблицы, выбрать запись (строку) или только данные в поле, которое требуется удалить, а затем нажать кнопку "Удалить". Вы также можете использовать созданный запрос на выборку для поиска данных, а затем преобразовать его в запрос на удаление. См. следующие статьи:

- [Удаление одной или нескольких записей из базы данных](https://support.office.com/article/ways-to-add-edit-and-delete-records-5e90a80c-106d-4c55-996e-07d7200980ce)
- [Создание и запуск запроса на удаление](https://support.office.com/article/create-and-run-a-delete-query-6da65fe1-0fc7-4a64-8ef0-c052cd4c3ec5)

### <a name="business-apps-for-office-365"></a>Бизнес-приложения для Office 365

В этом разделе описано, как использовать встроенные функции каждого из перечисленных ниже бизнес-приложений для Office 365, чтобы отвечать на запросы субъектов данных.

- [Bookings](#bookings)
- [Listings](#listings)
- [Connections](#connections)
- [Outlook Customer Manager](#outlook-customer-manager)
- [Invoicing](#invoicing)

#### <a name="bookings"></a>Bookings

В следующих разделах описано, как использовать встроенные функции Microsoft Bookings для поиска, просмотра, экспорта и удаления персональных данных. Это относится как к автономному приложению Bookings, так и к его версии, открываемой через Business Center.

Microsoft Bookings allows administrators and users or staff, with a Bookings license in their organization, to set up booking pages so customers can schedule and make changes to appointments, receive confirmation emails, updates, cancellation, and reminders email. Business owners and their staff can also book events on behalf of their customers with Bookings. 

Клиенты, администраторы и сотрудники могут создавать данные следующих типов.

- **Контактные данные клиентов, партнеров и друзей.** Эти данные содержат имя, номер телефона, электронный адрес, почтовый адрес и примечания.

    - С помощью клиентов Bookings для Интернета, iOS и Android можно вручную создавать контакты для всех пользователей.
    
    - Контакты для всех можно импортировать с мобильного устройства C1 в Bookings с помощью клиентов Bookings для iOS и Android.
    
    - Контакты также создаются автоматически во время создания бронирования с помощью рабочего процесса бронирования для любого забронированного участника - независимо от того, создано ли бронирование пользователем от имени клиента или оно было создано клиентом с помощью страницы бронирования владельца.

- **Резервируемые события.** Это встречи владельца предприятия или соответствующего персонала с клиентом, создаваемые либо владельцем предприятия, либо клиентом на общедоступной странице резервирования владельца. Эти данные включают имя, почтовый адрес, электронный адрес, номер телефона и другие сведения о клиенте, которые владелец предприятия собирает во время резервирования.

- **Подтверждение, отмена или обновление по электронной почте.** Это электронные сообщения, создаваемые и отправляемые системой в связи с определенными резервируемыми событиями. Они содержат персональные данные сотрудников, которым поручено оказание соответствующей услуги, а также персональные данные клиента, указанные либо владельцем предприятия, либо клиентом во время резервирования.

Весь контент клиентов хранится в том же почтовом ящике Exchange Online, где размещается служба Bookings организации. Этот контент хранится, пока владелец предприятия и клиент пользуются службой, если они не запросят удаление данных в явной форме или не покинут службу. Этот контент можно удалить с помощью пользовательского интерфейса продукта, с помощью командлета или путем удаления соответствующего почтового ящика резервирования. После запуска удаления данные удаляются в течение периода времени, установленного владельцем предприятия. 

Если клиент решит покинуть службу, его контент будет удален спустя 90 дней. Дополнительные сведения о том, когда удаляется содержимое почтовых ящиков после удаления учетных записей пользователей, см. в разделе [Удаление данных Exchange Online](#removing-exchange-online-data).

#### <a name="end-user-identifiable-information"></a>Личные сведения пользователей

End user Identifiable Information (EUII) includes personal and contact information about the staff that gets scheduled in Bookings. It's added to the Staff details pages when the business owner sets up Bookings and makes updates after the setup. It contains staff member's name, initials, email address, and phone number. This data is stored in the Exchange Online mailbox that hosts Bookings.

This data is retained for as long as the staff member is active in the service unless it's explicitly deleted the business owner or an admin using the in-app UI or by deleting the relevant booking mailbox. When the admin initiates the deletion of staff's details, or if the staff member leaves the service, their details are deleted in accordance with the Exchange Online mailbox's content retention policies set by the business owner or admin.

##### <a name="discoveraccess"></a>Обнаружение и доступ

Bookings собирает и сохраняет данные следующих типов.

- **Данные бизнес-профиля.** Данные клиентов об использовании Bookings в компании собираются через форму бизнес-информации Bookings и синхронизируются с бизнес-профилем в Business Center, если клиент использует Bookings совместно с Business Center. Единственные данные EUII, сопоставляемые с этими данными, — это электронный адрес C1. На этот адрес отправляются уведомления о новых резервированиях и сообщения с обновлениями.
- **Контакты клиента.** Контакты можно вручную создавать в клиентах Bookings для Интернета, iOS и Android либо импортировать с мобильного устройства. Кроме того, контакты автоматически создаются при использовании страницы самостоятельного резервирования. Они содержат EUII и хранятся в почтовом ящике Bookings.
- **Сведения о персонале.** Контент клиентов включает данные о сотрудниках, уполномоченных оказывать услуги, созданные с помощью клиентов Bookings для Интернета, iOS или Android. Сведения о персонале могут содержать имя, электронный адрес и номер телефона.
- **Резервируемые события.** Это встречи с клиентами и связанный с ними контент, созданный компанией с помощью веб-клиента либо приложения для Android или iOS либо созданный клиентом при помощи общедоступной страницы резервирования (или страницы Facebook). Эти события могут включать имя, почтовый адрес, электронный адрес, номер телефона и сведения о встрече.
- **Приглашения на собрания, электронные сообщения для подтверждения, отмены или обновления, а также напоминания по электронной почте.** Это электронные сообщения, отправляемые системой в связи с резервированием. Они содержат данные о сотрудниках и клиентах, указанные во время резервирования.

##### <a name="export"></a>Экспорт

To export data corresponding to the business owner, staff and customers, you can use the Business center privacy portal. See [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>Удаление

По запросу субъекта данных на удаление можно удалять данные Bookings перечисленных ниже типов.

- **Данные бизнес-профиля и контакты.** Вы можете удалить почтовый ящик Bookings в Центре администрирования. После удаления почтового ящика его можно восстановить в течение 30 дней. Спустя 30 дней учетная запись и соответствующий почтовый ящик безвозвратно удаляются. Дополнительные сведения об удалении учетной записи см. в разделе [Удаление пользователя](#deleting-a-user).
- **Сведения о персонале.** Вы можете удалять сотрудников с помощью панели мониторинга Bookings. Чтобы необратимо удалить сотрудника, вы можете удалить его учетную запись Office 365.
- **Резервирование событий:** вы можете удалить их из календаря резервирования, в результате чего данные клиента будут удалены.
- **Приглашения на собрания, электронные сообщения для подтверждения, отмены или обновления, а также напоминания по электронной почте.** Вы можете удалять их из календаря Bookings. При этом удаляются сведения о клиентах.

Business owners and admins can also delete their customer's data by using the Business center privacy portal. See [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

Additionally, you can delete business owner and staff data, you can delete the corresponding user account. See the section  [Deleting a user](#deleting-a-user).

#### <a name="listings"></a>Listings

В следующих разделах описано, как использовать встроенные функции Microsoft Listings для поиска, просмотра, экспорта и удаления персональных данных.

##### <a name="discover"></a>Обнаружение

Владелец Listings может подключить свое предприятие к Google, Bing, Yelp и Facebook, чтобы просматривать объединенное представление оценок и отзывов. Listings собирает и сохраняет данные следующих типов.

- Отзывы и оценки Google
- Отзывы и оценки Bing
- Отзывы и оценки Yelp
- Отзывы и оценки Facebook

##### <a name="access"></a>Доступ
Владелец Listings может войти в панель мониторинга Listings, чтобы просмотреть отзывы и оценки для своего предприятия.

##### <a name="export"></a>Экспорт

To export business owner, staff and customer data, use the Business center privacy portal. See [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>Удаление

If a Listings owner would like to delete their Listings information, they can disconnect from the provider on the Listings page. After they disconnect, their Listings information will be deleted.

#### <a name="connections"></a>Connections

В следующих разделах описано, как использовать встроенные функции Microsoft Connections для поиска, просмотра, экспорта и удаления персональных данных.

##### <a name="discover"></a>Обнаружение

Connections собирает и сохраняет данные следующих типов. 

- Клиенты и контакты, созданные с помощью веб-клиента или мобильного приложения (iOS, Android) либо через приложение при отправке маркетинговых материалов бизнес-контакту. Данные клиентов могут включать имя, почтовый адрес, электронный адрес и налоговые идентификационные номера. Контакты совместно используются всеми приложениями Business Center.
- Клиенты могут регистрироваться на соответствующей странице Connections и сохранять свои персональные данные.
- Ссылки из кампаний электронной почты

##### <a name="access"></a>Access

Владелец Connections может войти в панель мониторинга Connections и просмотреть отправленные им кампании электронной почты.

##### <a name="export"></a>Экспорт

To export business owner, staff and customer data, use the Business center privacy portal. See [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>Удалить

After a Connections owner sends an email campaign, they can't delete the campaign. If there are any draft campaigns they want to delete, they can sign in to the Connections dashboard and delete the draft campaigns.

#### <a name="outlook-customer-manager"></a>Outlook Customer Manager

В следующих разделах описано, как использовать встроенные функции Outlook Customer Manager для поиска, просмотра, экспорта и удаления персональных данных.

##### <a name="discover"></a>Обнаружение

Outlook Customer Manager собирает и сохраняет сведения о пользователях как для владельца Outlook Customer Manager, так и для своих клиентов и бизнес-контактов.

- Owner data. This includes name, address, and email address. Documents and files that an owner shares with a customer are stored in OneDrive for Business, SharePoint Online, and as tasks in Outlook.
- Customer and business contact data. Customer data can include name, address, and email address. Customer and contact data is created by the business in Outlook or Outlook web app. Contacts are shared across Business center. Documents and files that a customer shares with a business are stored in OneDrive for Business, SharePoint Online, and as tasks in Outlook.

Outlook Customer Manager также сохраняет действия и аналитические данные о клиентах в Exchange.

##### <a name="access"></a>Access

Владельцы диспетчера клиентов Outlook могут войти в Outlook или веб-приложение Outlook, а затем перейти на панель мониторинга диспетчера клиентов Outlook, чтобы увидеть их взаимодействия с клиентами.

##### <a name="export"></a>Экспорт

To export business owner and customer data, use the Outlook Customer Manager privacy portal. For details. See [Export or delete user data using the Outlook Customer Manager privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>Удаление

To delete customer data, use the Outlook Customer Manager privacy portal. See [Export or delete user data using the Outlook Customer Manager privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

#### <a name="invoicing"></a>Invoicing

В следующих разделах описано, как использовать встроенные функции Microsoft Invoicing для поиска, просмотра, экспорта и удаления персональных данных.

##### <a name="discover"></a>Обнаружение

Invoicing собирает и сохраняет данные перечисленных ниже типов.

- **Контакты.** Компания создает их при составлении накладной или предложения с расценками для клиента или бизнес-контакта. Контакты совместно используются всеми приложениями в Business Center. Данные клиентов включают имя, почтовый адрес, электронный адрес и налоговые идентификационные номера.
- **Накладные**. Они создаются и отправляются клиентам, представляя как долг, так и налоговую задолженность.
- **Предложения с расценками.** Компания также может отправлять клиентам предложения с расценками. Если клиент принимает предложение, оно преобразуется в накладную. Смета преобразуется в счет-фактуру после принятия клиентом. Записи сметы не сохраняются после преобразования в счет-фактуру.

##### <a name="access"></a>Access

Пользователи могут перейти на панель «Счета-фактуры» в своем бизнес-центре, чтобы просмотреть черновики созданных ими счетов-фактур и счета-фактуры, которые были видны клиентам.

##### <a name="export"></a>Экспорт

To export customer invoicing data, use the Business center privacy portal. See [Export or delete user data using Business center privacy portal](https://support.office.com/article/export-or-delete-user-data-using-business-center-privacy-portal-eb48e2c1-4c91-4421-988d-5de497d1e8d8).

##### <a name="delete"></a>Удалить

After an invoice is created and sent, it can't be deleted due to accounting laws. The Invoicing owner can request that Microsoft delete some or all their information from Office 365.

Alternatively, you can delete the invoicing owner's user account in Office 365. See the section [Deleting a user](#deleting-a-user).

### <a name="education"></a>Образование

В этом разделе описано, как использовать встроенные функции перечисленных ниже приложений Microsoft Education для реагирования на запросы субъектов данных.

- Задания
- Записная книжка для занятий

#### <a name="assignments"></a>Задания

В следующих разделах описано, как использовать встроенные функции средства "Задания" для поиска, просмотра, экспорта и удаления персональных данных.

##### <a name="discoveraccess"></a>Обнаружение и доступ

Assignments stores information that is generated both by teachers and students. Some of this information is store in SharePoint and some is stored in a non-SharePoint location.

##### <a name="finding-assignments-data-stored-in-sharepoint"></a>Поиск данных о заданиях, хранящихся в SharePoint

Students files associated with a Submission for Assignment are stored in a document library (named **Student Work**) and files associated with Assignments that are created by teachers and (accessible by students) are stored in a different document library (named **Class Files**). Both document libraries are in the corresponding Class Team SharePoint site.

Администратор может использовать средство "Поиск контента" в Центре безопасности и соответствия требованиям для поиска файлов учащихся (в библиотеках "Работы учащихся" и "Файлы классов"), связанных с работами по заданиями, а также файлов, связанных с заданиями. Например, администратор может выполнить поиск по всем сайтам SharePoint в организации и использовать имя ученика и класс или имя назначения в поисковом запросе, чтобы найти данные, относящиеся к запросу DSR.

Кроме того, администратор может искать файлы преподавателей, связанные с заданиями для файлов, которые преподаватель распространил среди учащихся. Например, администратор может выполнять поиск по всем сайтам SharePoint в организации и использовать имя преподавателя и название класса или задания в запросе на поиск данных, которые относятся к запросу DSR.

Дополнительные сведения см. в указанных ниже статьях.

- [Документация по заданиям для администраторов](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-admin-documentation)
- [Использование средства обнаружения электронных данных «Поиск контента» для реагирования на запросы субъектов данных](#using-the-content-search-ediscovery-tool-to-respond-to-dsrs) (в данном руководстве)

##### <a name="finding-assignments-data-not-stored-in-sharepoint"></a>Поиск данных о заданиях, не хранящихся в SharePoint

Ниже перечислены типы данных о заданиях, которые не хранятся на сайте SharePoint группы класса, и поэтому не обнаруживаются средством «Поиск контента». Сюда входят следующие пункты:

- Оценки учащихся и отзывы преподавателя
- Список документов, переданных каждым учащимся для заданий
- Сведения о заданиях, например конечная дата выполнения задания

To find data, an admin or a teacher would have to go into the Assignment in the Class Team site to find data that may be relevant to a DSR request. An admin can add themselves as an owner to the class and view all the assignments for that class team.

Даже если учащийся больше не состоит в классе, его данные все еще могут храниться в классе с отметкой о том, что учащийся больше не входит в список класса. В этом случае учащийся, отправляющий запрос субъекта данных, должен предоставить администратору список классов, в которые он был зачислен.

##### <a name="export"></a>Экспорт

Вы можете экспортировать данные заданий для конкретного учащегося для всех классов, в которые он зачислен, с помощью сценария PowerShell для получения списка классов для учащегося, а затем с помощью сценария PowerShell выполнить экспорт данных. См. следующие статьи:

- [Настройка заданий в Teams](https://docs.microsoft.com/microsoft-365/education/deploy/configure-assignments-for-teams)
- [Получить список классов для конкретного учащегося](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-get)
- [Экспорт данных учащихся и преподавателей из средства «Задания»](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-export)

If the student has been removed from the Team Class site, the admin can add the student back to the site before running the export script. Or the admin can use the input file for the script to identify every class that the student was ever enrolled in. You can also use the Assignment export script to export submissions data for all assignments that a teacher has access to.

##### <a name="delete"></a>Delete

Вы можете удалить данные заданий для конкретного учащегося для всех классов, в которые он зачислен, с помощью сценария PowerShell для получения списка классов для учащегося, а затем с помощью сценария PowerShell выполнить удаление данных. Это следует сделать перед удалением учащегося из класса. См. следующие статьи:

- [Настройка заданий в Teams](https://docs.microsoft.com/microsoft-365/education/deploy/configure-assignments-for-teams)
- [Получить список классов для конкретного учащегося](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-get)
- [Удаление данных учащихся из средства «Задания»](https://docs.microsoft.com/microsoft-365/education/deploy/assignments-script-delete)

If the student has been removed from the Team Class site, the admin can add the student back to the site before running the export script. Or the admin can use the input file for the script to identify every class that the student was ever enrolled in. You can't use the Assignments deletion script to delete teacher data because all Assignments are shared across the Class Team site. As an alternative, an admin would have to add themselves to the Class Team site and then delete a specific Assignment.

#### <a name="class-notebook"></a>Записная книжка для занятий

Поиск содержимого записной книжки для занятий рассматривается ранее в этом руководстве. См. раздел [Записная книжка OneNote для занятий](#onenote-class-notebook). Вы также можете использовать средство "Поиск контента", чтобы экспортировать данные из записной книжки для занятий. Кроме того, администратор или субъект данных может экспортировать данные из записной книжки для занятий. См. статью [Сохранение копии записной книжки для занятий](https://support.office.com/article/44733e18-0ef1-4d4b-be51-fc2ac5bfe9ec).

### <a name="flow"></a>Flow

В разделах ниже рассказывается, как с помощью функций, встроенных в Microsoft Flow, искать, экспортировать и удалять персональные данные, а также получать доступ к ним.

#### <a name="discover"></a>Обнаружение

People can use Flow to perform data-related tasks such as synchronizing files between applications, copying files from one Office 365 service to another, and collecting data from one Office 365 app and storing it in another. For example, a user could set up a Flow to save Outlook email attachments to their OneDrive for Business account. In this example, you could use the Content Search tool to search the user's mailbox for the email message that contained the attachment or search their OneDrive for Business account for the file. This is an example where data handled by Flow might be discoverable in the Office 365 services connected by a Flow workflow.

Additionally, people can use Flow to copy or upload files from Office 365 to an external service, such as Dropbox. In these cases, a DSR request concerning the data in an external service would have to be submitted to the external service, who is processing the data in this type of scenario.

Если администратор получает запрос субъекта данных, он может добавить себя в качестве владельца потоков пользователя. Благодаря этому администратор может выполнять ряд функций, в том числе экспортировать определения потоков и журналы выполнения, а также переназначать разрешения для потоков. См. статью [Управление потоками в Центре администрирования](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/).

Чтобы администратор мог добавить себя в качестве владельца потока, необходима учетная запись с указанными ниже разрешениями.

- Лицензия на план 2 для Flow или PowerApps (платная или пробная)

- [Глобальный администратор ](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)

    или

- [Глобальный администратор Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)

Имея такие привилегии, c помощью Центра администрирования Flow администратор может получать доступ ко всем потокам в организации.

Чтобы добавить себя в качестве владельца потока, выполните указанные ниже действия.

1. Перейдите по ссылке <https://admin.flow.microsoft.com>.
2. Войдите в систему с помощью своих учетных данных Office 365.
3. На странице **Окружения** щелкните среду для потоков, к которым вы хотите получить доступ. У организаций есть среда, используемая по умолчанию.
4. On the page for the environment that you selected, click **Resources**, and then click **Flows.** A list of all flows in the environment is displayed.
5. Нажмите **Показать сведения** для потока, в который вы хотите добавить себя в качестве участника.
6. В разделе **Владельцы**, щелкните **Управление общим доступом**.
7. На всплывающем элементе **Поделиться** добавьте себя в качестве участника и сохраните изменения.

После назначения себя владельцем выберите **Flow** \> **Мои потоки** \> **Командные потоки**, чтобы получить доступ к потоку. Здесь вы можете скачать журнал выполнения или экспортировать поток. См. следующие статьи:

- [Скачивание журнала выполнения потока](https://flow.microsoft.com/blog/download-history-recurrence/)
- [Экспорт и импорт потоков в средах с упаковкой](https://flow.microsoft.com/blog/import-export-bap-packages/)

#### <a name="access"></a>Доступ

Пользователь может получить доступ к определениям и журналам выполнения своих потоков.

- **Определения потоков.** Пользователь может экспортировать определения потоков (в виде пакета Flow в формате JSON в сжатом файле). См. статью [Экспорт и импорт потоков в средах с упаковкой](https://flow.microsoft.com/blog/import-export-bap-packages/).
- **Журналы выполнения потоков.** Пользователь может скачать журнал выполнения каждого из своих потоков. Журнал выполнения потока скачивается в виде CSV-файла, который можно открыть в Excel для фильтрации или поиска. Пользователи также могут скачивать журнал выполнения нескольких потоков. См. статью [Загрузка журнала выполнения потока](https://flow.microsoft.com/blog/download-history-recurrence/).

#### <a name="delete"></a>Удалить

Администратор может добавить себя в качестве владельца потоков пользователя в центре администрирования Flow. Если пользователь покидает организацию, а его учетная запись Office 365 удаляется, то потоки, принадлежащие только ему, будут сохранены. Это поможет вашей организации передать потоки новым владельцам, избежав помех в работе компании для тех потоков, которые можно использовать для общих бизнес-процессов. Затем администратору необходимо определить, следует ли удалить потоки, принадлежавшие этому пользователю, или назначить их новым владельцам, а затем выполнить соответствующие действия.

Если в организации используются общие потоки, то при удалении пользователя из организации его имя будет удалено из списков владельцев потоков.

#### <a name="export"></a>Экспорт

An admin can export the definition and run history of a user's flows. To do this, an admin must add themselves as an owner of the user's flow in the Flow admin center

- **Определения потоков.** После того как администратор назначит себя владельцем потока, он может перейти в раздел **Поток** \> **Мои потоки** \> **Потоки групп** и экспортировать определение потока (которое будет экспортировано в виде пакета Flow в формате JSON в сжатом файле). См. статью [Экспорт и импорт потоков в средах с упаковкой](https://flow.microsoft.com/blog/import-export-bap-packages/).

- **Журналы выполнения потоков.** Аналогичным образом, администратор должен добавить себя в качестве владельца потока, чтобы экспортировать журнал его выполнения. Журнал выполнения потока скачивается в виде CSV-файла, поэтому для фильтрации или поиска можно использовать Excel. Вы также можете скачать журнал выполнения нескольких потоков, если они принадлежат вам. См. статью [Загрузка журнала выполнения потока](https://flow.microsoft.com/blog/download-history-recurrence/).

#### <a name="connections-and-custom-connectors-in-flow"></a>Подключения и настраиваемые соединители в Flow

При использовании подключений пользователям необходимо указывать учетные данные для подключения к API, приложениям SaaS и специальным системам. Владельцем таких подключений является создавший их пользователь, а [управлять](https://docs.microsoft.com/flow/add-manage-connections) ими можно в продукте. После переназначения потоков администратор с помощью командлетов PowerShell может отобразить и удалить эти подключения в рамках процесса удаления данных пользователя.

Настраиваемые соединители позволяют организациям расширить возможности Flow путем подключения к системам, в которых готовые соединители недоступны. Создатель настраиваемого соединителя может [поделиться](https://docs.microsoft.com/flow/register-custom-api) своим соединителем с другими пользователями в организации. После получения запроса субъекта данных на удаление администратор должен рассмотреть вопрос переназначения владельцев этих соединителей, чтобы не допустить нарушения работы организации. Чтобы ускорить этот процесс, администратор с помощью командлетов PowerShell может отобразить, переназначить или удалить настраиваемые соединители.

### <a name="forms"></a>Forms

В следующих разделах описано, как использовать встроенные функции Microsoft Forms для поиска, просмотра, экспорта и удаления персональных данных.

#### <a name="discover"></a>Обнаружение

Forms users can go to <https://forms.office.com> and select **My forms** to see the Forms they've created. They can also select **Shared with me** to view Forms others have shared via a link. If there are many Forms to sort through, users can use the in-product search bar to search for Forms by title or author. To determine whether Microsoft Forms is a place where personal data responsive to your DSR is likely to reside, you can ask the Data Subject to search his or her **Shared with me** list to determine which users ("Forms owners") have sent Forms to the Data Subject. You can then ask the forms owners to select **Share** in the top navigation bar and send you a link to a specific form so you can view it and further determine whether it is material to your DSR.

#### <a name="access"></a>Access

После нахождения релевантных форм вы можете получить доступ к ответам форм на вкладке **Ответы**. Узнайте, как [проверить результаты теста](https://support.microsoft.com/ru-RU/office/check-and-share-your-quiz-results-c4a9b45c-d62f-4eb7-b5db-ad81892c7c07) или [результаты заполнения форм](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af). Чтобы проверить результаты ответов в Excel, откройте вкладку **Ответы** и щелкните **Открыть в Excel**. Если вы хотите отправить копию формы субъекту данных, вы можете сделать либо снимки экрана с релевантными вопросами и ответами, показанными в приложении в формате RTF, либо отправить субъекту данных копию результатов в формате Excel. Если вы используете Excel и хотите поделиться с субъектом данных только отдельными фрагментами результатов опросов, вы можете удалить определенные строки или столбцы либо отредактировать остальные разделы перед передачей результатов. Кроме того, вы можете щелкнуть **Поделиться \> Получить ссылку для дублирования** (в разделе "Поделиться как шаблоном"), чтобы предоставить субъекту данных реплику всей формы.

#### <a name="delete"></a>Удалить

Any survey, quiz, questionnaire, or poll can be permanently deleted by its owner. If you would like to honor a DSR "forget me" and delete a form in its entirety, find the Form in the list of forms, select the series of dots (ellipsis) in the upper right corner of the form preview window, and then click **Delete**. Once a Form is deleted, it can't be retrieved. For information, see [Delete a Form](https://support.microsoft.com/ru-RU/office/delete-a-form-2207e468-ce1b-4c4a-a256-caf631d87af0).

#### <a name="export"></a>Экспорт

Чтобы экспортировать вопросы и ответы из формы в файл Excel, откройте форму, перейдите на вкладку **Ответы** и затем щелкните **Открыть в Excel**.

### <a name="kaizala"></a>Kaizala

В следующих разделах описано, как использовать встроенные функции Microsoft Kaizala для поиска, просмотра, экспорта и удаления персональных данных.

#### <a name="discover"></a>Обнаружение

A user's organizational data, which is data that is shared in organizational groups, can be accessed by an admin from the Kaizala management portal. Organizational data is retained for a duration of time determined by your organization's retention policies. In addition to user data, Kaizala servers also store the following types of organizational data:

- Список членов, входящих в группы организации
- Данные сообщений в группах организации, то есть сообщения и ответы, доступные в организационных группах
- Список пользователей в организации
- Данные об использовании продуктов и служб для всех пользователей в организации.
- Действия Kaizala, созданные организацией
- Данные соединителей Kaizala

A user's consumer data can be accessed by the data subject using the Kaizala mobile app for consumer data. Consumer data includes the following types of data:

- Данные, принадлежащие закрытым группам в Kaizala (хранящиеся на серверах Kaizala в течение 90 дней)
- Информация о профиле пользователя и контакты пользователя
- Список участников тех групп, в которых состоит пользователь
- Сообщения и ответы и группах, доступные из других групп
- Список контактов пользователя (хранится на сервисе Kaizala)
- Транзакции, совершенные пользователем в Kaizala (применимо только к пользователям Kaizala в Индии)
- Данные об использовании продуктов и служб пользователем

#### <a name="access"></a>Access

Kaizala users can go to their mobile device to see Kaizala content they've created on their device. To determine whether Kaizala mobile apps is a place where personal data responsive to a DSR is likely to reside, you can ask the data subject to search their Kaizala app for the requested information.

#### <a name="export"></a>Экспорт

When users in your organization use Kaizala, consumer data is generated, and organizational data may be generated if the user participates in an organization group. Admins can export a user's organizational data from the Kaizala management portal. Kaizala consumer users can export their private data from the Kaizala mobile app. In both cases, note that product and service usage data is also export when an admin or user exports Kaizala data. For details, see:

- [Экспорт или удаление организационных данных пользователя в Kaizala](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)
- [Экспорт или удаление данных в мобильном приложении Kaizala](https://docs.microsoft.com/office365/kaizala/export-or-delete-your-data)

#### <a name="delete"></a>Удалить

A Kaizala admin can remove a Kaizala user's account in the Kaizala management portal. After a user account is deleted, the user is removed from all groups that belong to your organization and organizational data is deleted from their device. 

To remove all private data from the user's mobile device, the Kaizala user can delete their Kaizala account. After the account is deleted, all related Kaizala content including, chats, photos, and other data will be deleted from the device.

Дополнительные сведения см. в следующих статьях:

- [Экспорт или удаление организационных данных пользователя в Kaizala](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)
- [Экспорт или удаление данных в мобильном приложении Kaizala](https://docs.microsoft.com/office365/kaizala/export-or-delete-your-data)

### <a name="planner"></a>Планировщик

В следующих разделах описано, как использовать встроенные функции Планировщика (Майкрософт) для поиска, просмотра, экспорта и удаления персональных данных.

#### <a name="discover"></a>Поиск

Планы в Планировщике сопоставлены с группой Microsoft 365, а файлы для групп Microsoft 365 хранятся на сайте SharePoint Online этой группы. Это означает, что вы можете использовать средство "Поиск контента", чтобы найти файлы Планировщика на сайте группы Microsoft 365. Для этого нужен URL-адрес группы Microsoft 365. Советы о том, как получить информацию о группах Microsoft 365 для поиска файлов Планировщика на соответствующем сайте SharePoint Online, см. в разделе [Поиск в Microsoft Teams и группах Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search) справочной статьи "Поиск содержимого в Office 365".

#### <a name="access"></a>Access

Как было указано выше, вы можете выполнять поиск на базовом сайте SharePoint Online и в почтовом ящике, сопоставленными с планом. Затем вы можете проверить или скачать результаты поиска, связанные с данными доступа.

#### <a name="delete"></a>Удалить

You can manually delete a user's personally information by either giving yourself permissions to access the plans the user is part of or signing in as the user to make the changes. See [Delete user data in Microsoft Planner](https://support.office.com/article/delete-user-data-in-microsoft-planner-4349ded2-1891-4896-8e27-05fd40f3929f).

#### <a name="export"></a>Экспорт

You can use a PowerShell script to export a user's data from Planner. When you export the data, a separate JSON file is export for each plan that the user is a part of. See [Export user data from Microsoft Planner](https://support.office.com/article/export-user-data-from-microsoft-planner-91258c96-b353-4da1-b6d9-d78e4809cf08).

### <a name="power-bi"></a>Power BI

В следующих разделах описано, как использовать встроенные функции Microsoft Power BI для поиска, просмотра, экспорта и удаления персональных данных.

#### <a name="discover"></a>Обнаружение
You can search for content in the different workspaces in Power BI, including dashboards, reports, workbooks, and datasets. Each type of workspace contains a search field that you can use to search that workspace. See [Searching, finding, and sorting content in Power BI service](https://docs.microsoft.com/power-bi/service-navigation-search-filter-sort).

#### <a name="access"></a>Доступ

Вы можете распечатать панели мониторинга, отчеты и визуальные элементы из отчетов в Power BI, чтобы создать их бумажные копии. Вы не можете распечатать целые отчеты; Вы можете печатать только одну страницу за раз. Для этого откройте отчет, с помощью поля поиска найдите необходимые данные и напечатайте страницу. См. статью [Печать из службы Power BI](https://docs.microsoft.com/power-bi/service-print).

#### <a name="delete"></a>Удаление

Сведения о том, как удалить панели мониторинга, отчеты и книги, см. в статье [Удаление содержимого в службе Power BI](https://docs.microsoft.com/power-bi/service-delete).

Deleting a dashboard, report, or workbook doesn't delete the underlying dataset. Because Power BI relies on a live connection to the underlying source data to be complete and accurate, deleting personal data must be done there. (For example, if you created a Power BI report that is connected to Dynamics 365 for Sales as the live data source, you would have to make any corrections to the data in Dynamics 365 for Sales.)

После удаления данных вы можете воспользоваться функциями [обновления данных по расписанию](https://docs.microsoft.com/power-bi/refresh-scheduled-refresh) в Power BI, чтобы обновить набор данных, хранящийся в этом приложении. После этого удаленные данные больше не будут отражены ни в каких отчетах и панелях мониторинга Power BI, в которых они ранее использовались. Чтобы выполнить требования GDPR, у вас должны быть политики обновления данных с необходимой периодичностью.

#### <a name="export"></a>Экспорт

Чтобы упростить выполнение запроса на переносимость данных, вы можете экспортировать панели мониторинга и отчеты в Power BI.

- You can export the underlying data for dashboards and reports to a static Excel file. See the video in [Printing from Power BI service](https://docs.microsoft.com/power-bi/service-print). Using Excel, you can then edit the personal data to be included in the portability request, and save it in a commonly used, machine-readable format such as .csv or .xml.
- You can export (download) a report from the Power BI service in Office 365 to a .pbix file if it was originally published using Power BI Desktop. You can then import this file to Power BI Desktop and publish (export) it to the Power BI service of another organization. See [Export a report from Power BI service to Desktop](https://docs.microsoft.com/power-bi/service-export-to-pbix).

### <a name="powerapps"></a>PowerApps

В следующих разделах описано, как использовать встроенные функции Microsoft Power Apps для поиска, просмотра, экспорта и удаления персональных данных. Ниже показано, как администратор может передать приложения и зависимые от них ресурсы новым владельцам, чтобы не допустить нарушения работы организации.

#### <a name="discover"></a>Обнаружение

PowerApps — это служба для создания приложений, которыми можно делиться и которые можно использовать в организации. При создании или выполнении приложения пользователю приходится сохранять в службе PowerApps ресурсы и данные нескольких типов, включая приложения, среды, подключения, настраиваемые соединители и разрешения.

Чтобы упростить выполнение запроса субъекта данных, связанного с PowerApps, вы можете использовать операции администрирования в [Центре администрирования PowerApps](https://admin.powerapps.com/) и [командлеты PowerShell для администрирования PowerApps](https://go.microsoft.com/fwlink/?linkid=871804). Для доступа к этим средствам потребуется учетная запись с указанными ниже разрешениями.

- Платная или пробная лицензия на план 2 для PowerApps. Оформить подписку на 30-дневную пробную лицензию можно [здесь](https://web.powerapps.com/trial).
- [Глобальный администратор](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) или
- [Глобальный администратор Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal)

Дополнительные сведения о том, как искать персональные данные, см. в разделе [Обнаружение персональных данных в PowerApps](https://go.microsoft.com/fwlink/?linkid=871880).

Служба PowerApps также включает службу Common Data Service для приложений, благодаря которой пользователи могут хранить данные в стандартных и настраиваемых объектах в базе данных Common Data Service. Вы можете просматривать данные, хранящиеся в этих объектах, на [портале PowerApps Maker](https://web.powerapps.com) и с помощью имеющихся в продукте функций [расширенного поиска](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search) выполнять поиск определенных данных в объекте. Дополнительные сведения об обнаружении персональных данных в Common Data Service см. в разделе [Обнаружение персональных данных в Common Data Service](https://go.microsoft.com/fwlink/?linkid=871881).

#### <a name="access"></a>Доступ

Администраторы могут назначать себе привилегии на выполнение приложений и на доступ к приложениям и связанным с ними ресурсам (в том числе к потокам, подключениям и настраиваемым соединителям) в [Центре администрирования PowerApps](https://admin.powerapps.com/) или с помощью [командлетов PowerShell для администрирования PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

After you have access to the user's app, you can use a web browser to open the app. After you open an app, you can take a screenshot of the data. See [Use PowerApps in a web browser](https://docs.microsoft.com/powerapps/run-app-browser).

#### <a name="delete"></a>Удалить

PowerApps дает пользователям возможность создавать бизнес-приложения, которые могут быть критически важными для повседневных операций в организации. Поэтому когда пользователь увольняется из организации, и вы удаляете его учетную запись в Office 365, администратору потребуется решить, удалять ли приложения, владельцем которых является пользователь, или переназначить их другим владельцам. Это поможет вашей организации передать приложения новым владельцам, избежав помех в работе компании для тех приложений, которые можно использовать для общих бизнес-процессов.

Что касается общих данных, например приложений, администраторы должны решить, следует ли безвозвратно удалять общие данные этого пользователя или оставить их, переназначив данные себе или другим пользователям в организации. См. раздел [Удаление персональных данных в PowerApps](https://go.microsoft.com/fwlink/?linkid=871883).

Any data that was stored by a user in an entity in a Common Data Service For Apps database will also need to be reviewed and (if desired) deleted by an admin using the in-product capabilities. See [Delete Common Data Service user personal data](https://go.microsoft.com/fwlink/?linkid=871886).

#### <a name="export"></a>Экспорт

Admins have the ability to export personal data stored for a user within the PowerApps service using the [PowerApps Admin Center](https://admin.powerapps.com/) and [PowerApps Admin PowerShell cmdlets](https://go.microsoft.com/fwlink/?linkid=871804). See [Export PowerApps personal data](https://go.microsoft.com/fwlink/?linkid=871883).

You can also use the in-product search capabilities of [Advanced Find](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search) to search for a user's personal data in any entity. For details about exporting personal data in the Common Data Service, see [Export Common Data Service personal data](https://go.microsoft.com/fwlink/?linkid=871889).

#### <a name="connections-and-custom-connectors-in-powerapps"></a>Подключения и настраиваемые соединители в PowerApps

При использовании подключений пользователям необходимо указывать учетные данные для подключения к API, приложениям SaaS и специальным системам. Владельцем таких подключений является создавший их пользователь, а [управлять](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection) ими можно в продукте. После переназначения PowerApps администратор с помощью командлетов PowerShell может отобразить и удалить эти подключения в рамках процесса удаления данных пользователя.

Настраиваемые соединители позволяют организациям расширить возможности PowerApps путем подключения к системам, в которых готовые соединители недоступны. Создатель настраиваемого соединителя может [поделиться](https://docs.microsoft.com/connectors/custom-connectors/use-custom-connector-powerapps) своим соединителем с другими пользователями в организации. После получения запроса субъекта данных на удаление администратор должен рассмотреть вопрос переназначения владельцев этих соединителей, чтобы не допустить нарушения работы организации. Чтобы ускорить этот процесс, администратор с помощью командлетов PowerShell может отобразить, переназначить или удалить настраиваемые соединители.

### <a name="project-online"></a>Project Online

В следующих разделах описано, как использовать встроенные функции Microsoft Project Online для поиска, просмотра, экспорта и удаления персональных данных.

#### <a name="discover-and-access"></a>Обнаружение и доступ

C помощью средства "Поиск контента" вы можете выполнять поиск на сайте SharePoint Online, сопоставленном с проектом (при создании проекта имеется возможность создать сопоставленный сайт SharePoint Online). Средство "Поиск контента" не выполняет поиск данных в реальном проекте в Microsoft Project Online, а только на сопоставленном сайте. Средство "Поиск контента" выполняет поиск метаданных о проекте, например о людях, упомянутых в теме, и это может помочь вам найти проект (а также получить к нему доступ), содержащий данные, относящиеся к запросу субъекта данных.

>[!TIP]
>The URL for the site collection in your organization where sites associated with Projects is **https://\<your org\>.sharepoint.com/sites/pwa**; for example, **https://contoso.sharepoint.com/pwa**. You can use this specific site collection as the location of your content search and then the name of the Project in the search query. Additionally, an IT admin can use the Site Collections page in the SharePoint admin center to get a list of PWA site collections in the organization.

#### <a name="delete"></a>Удалить

You can delete information about a user from your Project Online environment. See [Delete user data from Project Online](https://support.office.com/article/delete-user-data-from-project-online-252fa593-9c25-47ed-b861-643fe8bf1cb7).

#### <a name="export"></a>Экспорт

You can a specific user's content from your Project Online environment. This data is exported to multiple files in the JSON format. For step-by instructions see, [Export user data from Project Online](https://support.office.com/article/export-user-data-from-project-online-27f3838d-3dbe-4b98-80dc-df55f851154d). For detailed information about the files that are exported, see [Project Online export json object definitions](https://support.office.com/article/project-online-export-json-object-definitions-ce5faeae-9af4-4696-b847-a1f4f20327c7).

### <a name="publisher"></a>Publisher

В разделах ниже рассказывается, как с помощью функций, встроенных в Microsoft Publisher, искать, экспортировать и удалять персональные данные, а также получать доступ к ним.

#### <a name="discover"></a>Обнаружение

С помощью функции поиска в приложении вы можете находить текст в файле Publisher точно так же, как в большинстве приложений Office. См. статью [Поиск и замена текста](https://support.office.com/article/find-and-replace-text-bfe54275-b7c7-4d0f-904d-a2f38d322268).

#### <a name="access"></a>Доступ

После того как вы найдете данные, вы можете сделать снимок экрана с ними или экспортировать их в файл Word или текстовый файл, чтобы предоставить его субъекту данных. Вы также можете сохранить публикацию в виде файла Word, PDF или XPS. См. следующие статьи:

  - [Сохранение публикации как документа Word](https://support.microsoft.com/ru-RU/office/save-a-publication-as-a-word-document-b5eaaae5-6f1b-48c1-bebc-44460376b693)
  - [Сохранение публикации в виде PDF- или XPS-файла или ее преобразование в формат PDF или XPS в Publisher](https://support.microsoft.com/ru-RU/office/save-as-or-convert-a-publication-to-pdf-or-xps-using-publisher-657332d0-d2c2-464a-9870-e9b3d22e6469)

#### <a name="export"></a>Экспорт

Вы можете предоставить субъекту данных фактический файл Publisher или, как было указано ранее, сохранить публикацию в виде файла Word, PDF или XPS. См. следующие статьи:

  - [Сохранение публикации как документа Word](https://support.microsoft.com/ru-RU/office/save-a-publication-as-a-word-document-b5eaaae5-6f1b-48c1-bebc-44460376b693)
  - [Сохранение публикации в виде PDF- или XPS-файла или ее преобразование в формат PDF или XPS в Publisher](https://support.microsoft.com/ru-RU/office/save-as-or-convert-a-publication-to-pdf-or-xps-using-publisher-657332d0-d2c2-464a-9870-e9b3d22e6469)

#### <a name="delete"></a>Удаление

Вы можете удалить контент из публикации, удалить целые страницы или удалить весь файл Publisher. См. статью [Добавление и удаление страниц](https://support.office.com/article/add-or-delete-pages-daf71e39-86e0-4bbc-a186-d5ec70450b08).

### <a name="stream"></a>Stream

В следующих разделах описано, как использовать встроенные функции Microsoft Stream для поиска, просмотра, экспорта и удаления персональных данных.

#### <a name="discover"></a>Обнаружение

Для обнаружения создаваемого или отправляемого в Stream содержимого, которое может относиться к запросу субъекта данных, администратор Stream может создать отчет о пользователе, чтобы определить какие видео, описания видео, группы, каналы и комментарии отправил, создал или опубликовал пользователь Stream. Инструкции по созданию отчета см. в статье [Управление данными пользователей в Microsoft Stream](https://docs.microsoft.com/stream/managing-user-data). Полученный отчет представлен в формате HTML и содержит гиперссылки для перехода к видео, которые могут вас заинтересовать. Если вы хотите просмотреть видео с особым набором разрешений и не входите в число пользователей, для которых оно изначально было предназначено, можно использовать режим администратора. См. статью [Возможности администратора в Microsoft Stream](https://docs.microsoft.com/stream/manage-content-permissions).  

#### <a name="access"></a>Access

Depending on the nature of the data subject request, a copy of the report described above can be used help satisfy a data subject request. The user report includes the Stream user's name and unique ID, a list of videos the user uploaded, a list of videos the user has access to, a list of channels the user created, a list of all the groups the user is a member of, and a list of all comments the user left on videos. The report further shows whether the user viewed each video listed in the user report. If you would like to provide the data subject with access to a video to satisfy a DSR request, you can share the video.

#### <a name="export"></a>Экспорт

См. раздел "Доступ" для Stream. 

#### <a name="delete"></a>Удаление

To delete or edit videos or any other Stream content, a Stream admin can select view in admin mode to perform the necessary function. See [Admin capabilities in Microsoft Stream](https://docs.microsoft.com/stream/manage-content-permissions). If a user has left the organization and would like to have their name removed from appearing next to videos that they uploaded, you can remove their name or replace it with another. See [Managing deleted users in Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users).

### <a name="sway"></a>Sway

В следующих разделах описано, как использовать встроенные функции Microsoft Sway для поиска, просмотра, экспорта и удаления персональных данных.

#### <a name="discover"></a>Обнаружение

Контент, созданный с помощью Sway (расположенный по адресу [www.sway.com](https://sway.office.com/)), может просматривать только владелец контента и пользователи, которым автор разрешил просматривать свой документ Sway. См. статью [Параметры конфиденциальности в Sway](https://support.microsoft.com/ru-RU/office/privacy-settings-in-sway-394b551c-be6f-4bd7-a70a-f318d72bf217). Чтобы определить, является ли Sway местом, в котором, вероятно, будут находиться персональные данные, отвечающие вашему DSR, вы можете попросить Субъекта данных и пользователей организации, которые, вероятно, сгенерировали контент о Субъекте данных, выполнить поиск своих Sway и поделиться с вами любыми Sway, которые могут содержать личные данные в ответ на запрос субъекта данных. Сведения о том, как поделиться документом Sway, см. в разделе "Предоставление доступа к Sway из учетной записи организации" в статье [Общий доступ к Sway](https://support.microsoft.com/ru-RU/office/share-your-sway-1cf853b8-ef7e-46b0-b704-003e58d28998).

#### <a name="access"></a>Access

Если вы нашли персональные данные в Sway, которыми нужно поделиться с субъектом данных, вы можете предоставить ему доступ к данным одним из нескольких способов. Вы можете предоставить субъекту данных копию веб-версии документа Sway (как описано выше). Вы можете сделать снимки экрана релевантной части документа Sway, которой нужно поделиться. Кроме того, вы можете распечатать или скачать документ Sway в Word либо преобразовать его в формат PDF. Как скачать Sway более подробно описано в разделе «Экспорт» ниже.

#### <a name="delete"></a>Удалить

To learn how to delete a Sway, go to the "How do I delete my Sway?" section in [Privacy settings in Sway](https://support.microsoft.com/ru-RU/office/privacy-settings-in-sway-394b551c-be6f-4bd7-a70a-f318d72bf217).

#### <a name="export"></a>Экспорт

Чтобы экспортировать документ Sway, откройте документ Sway, который вы хотите скачать, щелкните многоточие в правом верхнем углу, щелкните **Экспорт**, а затем выберите **Word** или **PDF**.

### <a name="whiteboard"></a>Доска

В следующих разделах описано, как использовать встроенные функции Доски (Майкрософт) для поиска, просмотра, экспорта и удаления персональных данных.

- [Доска (Майкрософт) 2016 на Surface Hub](#whiteboard-2016-on-surface-hub)
- [Доска на других платформах](#whiteboard-for-pc-surface-hub-and-other-platforms)

#### <a name="whiteboard-2016-on-surface-hub"></a>Доска 2016 на Surface Hub

В этом разделе описывается реагирование на запроса DSR для данных, созданных с помощью встроенного приложения "Доска 2016" на Surface Hub.

##### <a name="discover"></a>Обнаружение

Whiteboard files (.wbx files) are stored in users' OneDrive for Business account. You can ask the data subject or other users if whiteboards they created may contain personal data responsive to a DSR request. They can share a whiteboard with you, or you can get a copy of it to give to the data subject.

Чтобы просматривать и передавать доски, выполните указанные ниже действия. 

1. Give yourself access to the user's OneDrive for Business account. See the "Get access to the former employee's OneDrive for Business documents" section in [Get access to and back up a former user's data](https://docs.microsoft.com/microsoft-365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data).
2. Перейдите к папке "Данные приложения доски" в учетной записи OneDrive для бизнеса и скопируйте WBX-файлы досок, которые требуется передать.
3. Предоставьте себе доступ к учетной записи субъекта данных в OneDrive для бизнеса, а затем перейдите к папке "Данные приложения доски".
4. Вставьте WBX-файлы, скопированные на предыдущем этапе.

##### <a name="access"></a>Access

Если вы найдете персональные данные на доске, относящейся к запросу доступа DSR, вы можете предоставить субъекту данных доступ к этой доске несколькими способами:

- сделать снимки экрана с соответствующими частями доски;
- Upload a copy of the .wbx file to the data subject's OneDrive for Business account. See the previous section for steps on accessing and transferring .wbx files.
- экспортировать копию доски в виде PNG-файла.

##### <a name="export"></a>Экспорт

Если вы получили копию доски, ее можно экспортировать. 

1. Запустите приложение "Доска" на Surface Hub.
2. Tap the Share button and then select Export a copy.
You can export a whiteboard to a OneNote (.one) file or to an image (.png) file.

##### <a name="delete"></a>Удалить

Вы можете предоставить себе доступ к учетной записи пользователя в OneDrive для бизнеса, а затем удалить доски.

1. Give yourself access to the data subject's OneDrive for Business account. See the "Get access to the former employee's OneDrive for Business documents" section in [Get access to and back up a former user's data](https://docs.microsoft.com/microsoft-365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data)
2. Перейдите в папку "Данные приложения доски" и удалите ее содержимое.

#### <a name="whiteboard-for-pc-surface-hub-and-other-platforms"></a>Доска для компьютера с Windows, Surface Hub и других платформ

If an admin receives a DSR request for data in the new Whiteboard app, they can use Whiteboard PowerShell to add themselves (or other users) as an owner of a user's whiteboards. This enables an admin to perform actions including accessing, exporting, and deleting whiteboards. Use either the **Set-WhiteboardOwner** cmdlet to add yourself or another user as the owner of a whiteboard or use the **Invoke-TransferAllWhiteboards** cmdlet to transfer the ownership of all whiteboards for a specific user to a new owner. For information about using these cmdlets and installing the Whiteboard PowerShell module, see Microsoft Whiteboard cmdlet reference.
After you or another person has ownership of a whiteboard, see [Microsoft Whiteboard cmdlet reference](https://docs.microsoft.com/powershell/module/whiteboard/?view=whiteboard-ps).

Подробное руководство по доступу, экспорту и удалению досок после получения вами или другим пользователем прав владения доской см. в [статье о поддержке доски](https://go.microsoft.com/fwlink/?linkid=872780).

### <a name="yammer"></a>Yammer

В следующих разделах описано, как использовать встроенные функции Microsoft Yammer для поиска, просмотра, экспорта и удаления персональных данных.

#### <a name="discover"></a>Поиск

В Центре администрирования Yammer проверенный администратор Yammer (глобальный администратор или проверенный администратор, настроенный в Yammer) может экспортировать данные, принадлежащие определенному пользователю. В экспортируемые данные включаются сообщения и файлы, опубликованные и измененные пользователем, а также сведения о темах и группах, созданных пользователем. Когда выполняется экспорт данных для конкретного пользователя, администратор также получит входящее сообщение с данными об активности учетной записи пользователя, которые они могут предоставить пользователю, если они того пожелают. Подробные сведения см. в статье [Yammer корпоративный: конфиденциальность](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise).

Экспортируемые данные, зависящие от пользователя, предназначены для одной сети, поэтому если пользователь находится во внешней сети Yammer, администратору придется экспортировать данные для этой внешней сети и для домашней сети.

Чтобы получить доступ к данным, не включенным в экспорт данных, можно сделать снимки экрана с данными профиля, параметрами, сведениями об участии в группах, сообщениях с закладками пользователя, а также о пользователях и темах, на которые подписан пользователь. Эту информацию могут собирать и пользователи, и администраторы. Дополнительные сведения см. в статье [Yammer корпоративный: конфиденциальность](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise).

#### <a name="access"></a>Доступ

You can view data in the exported files, including the full text of messages and the contents of files. You can also click links in the exported files to go directly to the posted messages and files in Yammer, and to groups, and topics the user created, messages the user liked, messages where the user is @mentioned, polls the user has voted on, and links the user has added.

Экспортируемые данные для пользователя не включают указанные ниже элементы.

- Профиль пользователя
    - If the user has a Yammer identity, the user has full control of their profile. For information on how to view and modify the profile, see [Change my Yammer profile and settings](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851).
    
    - If the user has an Office 365 identity, the Yammer user profile is pulled automatically from Office 365, which gets the profile information from Azure Active Directory (AAD). Yammer users can temporarily change their profiles in Yammer, but these changes are overwritten when there is a change in AAD, so you must view and change directory data in AAD. See [Manage Yammer users across their lifecycle from Office 365](https://docs.microsoft.com/yammer/manage-yammer-users/manage-users-across-their-lifecycle) and [Add or change profile information for a user in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-users-profile-azure-portal).

-   Параметры пользователя

- The user can view and change their own settings. For information on how to view and modify user settings, see [Change my Yammer profile and settings](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851). An admin can view this information and take screenshots, but can't change it. Go to Yammer settings \> **People**, and then click the name of the user.<br/>
    - Членство в группах и сообщения с закладками пользователя, а также пользователи и темы, на которые он подписан.
    
    - The user can view this information. For information on how, see [Tips for staying organized in Yammer](https://support.office.com/article/tips-for-staying-organized-in-yammer-40ae9666-75c0-4254-a84c-d87a9542f380). An admin can view this information and take screenshots, but can't change it. Go to Yammer settings \> **People**, and then click the name of the user.

#### <a name="export"></a>Экспорт

For instructions for how to export data, see [Manage GDPR data subject requests in Yammer Enterprise](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise). You must run a per-user export for each Yammer network the user is a member of.

В Yammer есть параметры хранения данных, в зависимости от которых система обратимо или необратимо удаляет данные, когда пользователь удаляет сообщение или файл. Если выбран вариант обратимого удаления, удаленные пользователем данные будут включены в экспорт. Если в параметре хранения данных в Yammer настроено необратимое удаление, удаленная информация больше не хранится в Yammer, и, соответственно, не будет включена в экспорт.

#### <a name="delete"></a>Удаление

Yammer allows verified admins to execute a GDPR-compliant delete via the Yammer admin center if they receive a DSR. This option is called Erase User, and it suspends the user for 14 days and then removes all their personal data, excluding files and messages. If the user is a guest user, this must be done for each external network the guest user is a member of.

>[!NOTE]
>If an admin wants to remove the files and messages of a user during the 14-day window, they will have to perform a user level export to identify the files and messages, and then decide which ones to delete either by in-product deletion or by using a PowerShell script. After the 14-day window, the admin can no longer associate the user with their files or messages.

When a user is deleted with the Erase User option, notification is sent to the Yammer Inbox of all network admins and verified admins. The Erase User option deletes the user's Yammer profile, but does not delete their Office 365 or Azure Active Directory profile.

Подробные инструкции для процесса удаления пользователя см. в статье [Управление запросами субъекта данных GDPR в Yammer корпоративный](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise).

## <a name="responding-to-dsr-rectification-requests"></a>Реагирование на запросы субъектов данных на уточнение данных

Если субъект данных попросил уточнить персональные данные, хранящиеся в вашей организации в Office 365, вам и вашей организации необходимо определить, допустимо ли выполнять этот запрос. Если вы решите выполнить запрос, процесс уточнения данных может включать ряд действий, например изменение, редактирование или удаление персональных данных из документа или элемента другого типа. Наиболее целесообразный способ сделать это — попросить владельца данных или документа внести запрашиваемые изменения с помощью соответствующего приложения Office 365. Альтернативный вариант — попросить ИТ-администратора в вашей организации внести изменения. Для этого ИТ-администратору (или другим сотрудникам в вашей организации с соответствующими привилегиями, например администратору семейства веб-сайтов SharePoint Online), вероятно, потребуется назначить себе или другому пользователю, работающему над выполнением запроса субъекта данных, необходимые разрешения на доступ к документу или расположению контента, в котором хранится документ, и внести изменения непосредственно в документ.

### <a name="requesting-that-the-data-owner-to-make-the-approved-change"></a>Запрос к владельцу данных на внесение утвержденного изменения

The most direct way to rectify personal data is to ask the data owner to make the change. After you locate the data that is the subject of the DSR, you can provide the following information so that they can make the change.

- Расположение и имя файла (для документов и других файлов) элемента, в который необходимо внести изменения. Поиск необходимых данных входит в [процесс обнаружения данных](#using-content-search-to-find-personal-data), рассмотренный ранее.
- Утвержденные изменения, которые должен внести владелец данных

Возможно, вы решите реализовать процесс подтверждения, при использовании которого вы или другой человек, участвующий в расследовании при подготовке ответа на запрос субъекта данных, должны проверить, внесено ли запрошенное изменение.

### <a name="gaining-access-to-a-sharepoint-online-site-or-onedrive-for-business-account-to-make-changes"></a>Получение доступа к сайту SharePoint Online или учетной записи OneDrive для бизнеса для внесения изменений

If it's not feasible for the data owner to implement the data subject's request for rectification, an IT admin or SharePoint admin in your organization can get access to the content location and make the required changes. Or, an admin can assign you or another data privacy officer the necessary permissions.

#### <a name="sharepoint-online"></a>SharePoint Online

Сведения о том, как назначить разрешения администратора или владельца сайта SharePoint Online вам или другому пользователю, чтобы можно было получить доступ к необходимому документу и изменить его, см. в статьях ниже.

- [Управление администраторами семейства веб-сайтов](https://docs.microsoft.com/sharepoint/manage-site-collection-administrators)

- [Управление разрешениями для списка или библиотеки SharePoint](https://support.office.com/article/Edit-and-manage-permissions-for-a-SharePoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782)

#### <a name="onedrive-for-business"></a>OneDrive для бизнеса

Глобальный администратор может получить доступ к учетной записи пользователя в OneDrive для бизнеса.

1. Войдите в систему Office 365, используя свои учетные данные глобального администратора.
2. Перейдите в Центр администрирования.
3. Перейдите в раздел **Активные пользователи** и выберите необходимого пользователя.
4. Разверните пункт **Параметры OneDrive для бизнеса** в области сведений и щелкните **Доступ к файлам**.
5. Щелкните URL-адрес, чтобы перейти к учетной записи пользователя в OneDrive для бизнеса.

### <a name="gaining-access-to-an-exchange-online-mailbox-to-make-changes-to-data"></a>Получение доступа к почтовому ящику Exchange Online для внесения изменений в данные

A global admin can assign themselves the permissions necessary to open and edit (or delete) items in another user's mailbox, as if they were the mailbox owner. A global admin can also assign these permissions to another user. Specifically, the global admin needs to add the **Read and manage** permission, which is the Full Access permission in Exchange Online. For details, see:

- [Предоставление разрешений для почтового ящика другому пользователю Office 365: справка для администраторов](https://docs.microsoft.com/microsoft-365/admin/add-users/give-mailbox-permissions-to-another-user)
- [Доступ к почтовому ящику другого пользователя](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081)

Если почтовый ящик пользователя находится на удержании по юридическим причинам либо для него включена политика хранения, все версии почтового ящика будут храниться до завершения срока хранения или отмены удержания для почтового ящика. Это означает, что если изменить элемент почтового ящика по запросу субъекта данных на уточнение данных, копия исходного элемента (до внесения изменений) будет сохранена в скрытой папке в папке "Элементы с возможностью восстановления" в почтовом ящике пользователя.

### <a name="making-changes-to-content-in-onedrive-for-business-and-sharepoint-online"></a>Внесение изменений в контент в OneDrive для бизнеса и в SharePoint Online

Admins or data owners can make changes to SharePoint Online documents, lists, and pages. Keep the following things in mind when making changes to SharePoint content:

- При обновлении документа будет сохранена его новая версия с изменениями. Более ранние версии документа не будут изменены. Это означает, что данные, указанные в запросе субъекта данных на уточнение, могут присутствовать в более ранних версиях темы. Более ранние версии темы можно удалить, а затем безвозвратно удалить из Office 365. См. раздел [Удаление документов в SharePoint Online и в OneDrive для бизнеса](#deleting-documents-in-sharepoint-online-and-onedrive-for-business) в этом руководстве.
- Чтобы полностью отредактировать файл в SharePoint для удаления всех следов субъекта данных из файла, включая все версии файла и все записанные данные о действиях, совершенных субъектом данных, вам потребуется выполнить указанные ниже действия.

    1. Скачайте копию файла на свой компьютер.
    2. Permanently delete the file from SharePoint Online, by deleting the file, and then deleting if from the first-stage and second-stage Recycle Bin. See the [Deleting documents in SharePoint Online and OneDrive for Business](#deleting-documents-in-sharepoint-online-and-onedrive-for-business) section in this guide.
    3. Внесите необходимые изменения в копию документа на своем компьютере.
    4. Отправьте измененный файл в исходное расположение SharePoint Online.

- Data in SharePoint lists can be edited. See [Add, edit, or delete list items](https://support.microsoft.com/ru-RU/office/add-edit-or-delete-list-items-a4b31f53-f044-470e-9823-4526594bacde).

ИТ-администраторы также могут исправлять определенные персональные свойства, связанные с документом.

User information from the SharePoint User Profile or Office 365 is often associated with OneDrive for Business and SharePoint Online documents to represent that person. For example, a user's name in a Created By or Modified By People column for a document or list item. This user information can be rectified in several ways, depending on the source:

- Уточнение свойств пользователя в его локальной службе Active Directory. Для клиентов, синхронизирующих свойства пользователей, например отображаемые имена, имена пользователей и т. д., из локального каталога AD, эти свойства необходимо уточнить в локальном каталоге. Надлежащим образом сопоставленные свойства попадут в Office 365, а затем в OneDrive для бизнеса и SharePoint Online.
- Уточнение свойств пользователя в Центре администрирования. Изменения, внесенные в сведения об учетной записи, будут автоматически отражены в интерфейсах OneDrive для бизнеса и SharePoint Online. Сведения см. в статье [Добавление или изменение данных профиля пользователя в Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=864809). Вам не удастся изменить свойства из Office 365 в SharePoint.
- Rectify user properties in the SharePoint user profile experience of the SharePoint admin center. In the user profiles tab of the SharePoint admin center, admins can click **Manage user profiles**, and look up any user's properties. Then they can choose to Edit the user's properties.
- Rectify user properties in a custom source. Custom SharePoint profile properties may be syncing from a custom source via Microsoft Identity Manager (MIM) or another method.

Это повлияет не на все интерфейсы, в которых может храниться более старая информация. Пример: имя пользователя в виде текста в документе.

### <a name="making-changes-to-content-in-power-bi"></a>Внесение изменений в контент в Power BI

Power BI relies on the underlying source data used in its dashboards and reports to be complete and accurate, so correcting inaccurate or incomplete source data must be done there. For example, if you created a Power BI report that is connected to Dynamics 365 for Sales as the live data source, you would have to make any corrections to the data in Dynamics 365 for Sales.

After those changes are made, you can take advantage of the [scheduled data refresh](https://docs.microsoft.com/power-bi/refresh-scheduled-refresh) capabilities to update the dataset that is stored in Power BI so that the revised data is reflected in the dependent Power BI assets. To help comply with GDPR requirements, you should have policies in place to ensure that you are refreshing your data at an appropriate cadence.

### <a name="making-changes-to-content-in-yammer"></a>Внесение изменений в контент в Yammer

For messages, a user can edit a given message to rectify any inaccuracies. They can request a list of all their messages from a Yammer verified admin, and then click a link in the file to review each message.

For files, a user can edit a given file to rectify any inaccuracies. They can request a list of all the files they posted from a Yammer verified admin, and then access the files in Yammer. Files that are exported into the Files folder can be viewed by searching for the file by number. For example, for a file named 12345678.ppx in the export, use the Search box in Yammer to search for 1235678.ppx. Or, go to <strong>https://www.yammer.com/\<network\_name\>/\#/files/\<file\_number\></strong>; for example, <strong>https://www.yammer.com/contosomkt.onmicrosoft.com/\#/files/12345678</strong>.

При работе с данными, доступ к которым пользователь может получить с помощью своего профиля и параметров, пользователь может внести любые изменения.

- Профиль пользователя

    - If the user has a Yammer identity, the user has full control of their profile. For information on how to view and modify the profile, see [Change my Yammer profile and settings](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851).
    - Если у пользователя есть удостоверение Office 365, система автоматически получает профиль пользователя в Yammer из Office 365, который, в свою очередь, получает сведения профиля из Azure Active Directory (AAD). Пользователи Yammer могут временно изменять свои профили в Yammer, но эти изменения будут перезаписаны при внесении изменений в AAD, поэтому лучше просматривать и изменять данные каталога в AAD. Пользователь должен запросить выполнение обновлений AAD. См. статьи [Управление пользователями Yammer в течение их жизненного цикла из Office 365](https://docs.microsoft.com/yammer/manage-yammer-users/manage-users-across-their-lifecycle) и [Добавление или изменение данных профиля пользователя в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-users-profile-azure-portal).

- Параметры пользователя

    - The user can change their own settings. For information on how to view and modify user settings, see [Change my Yammer profile and settings](https://support.office.com/article/change-my-yammer-profile-and-settings-a3aeca0e-de34-4897-9b59-de6516542851).
    - The user's group membership, bookmarked messages, followed users, and followed topics. The user can change this information; see [Tips for staying organized in Yammer](https://support.office.com/article/tips-for-staying-organized-in-yammer-40ae9666-75c0-4254-a84c-d87a9542f380).

## <a name="responding-to-dsr-restriction-requests"></a>Реагирование на запросы субъектов данных на запрет доступа к данным

Ниже описаны способы запрета обработки данных в Office 365:

- Удалите лицензию приложения в Office 365, чтобы запретить пользователям доступ к данным через приложение
- Запретите пользователям доступ к их учетным записям OneDrive для бизнеса.
- Отключите функцию обработки данных в службе Office 365.
- Временно удалите данные из SharePoint Online и OneDrive для бизнеса и сохраните их в локальной среде.
- Временно запретите любой доступ на сайт SharePoint Online.
- Запретите пользователям входить в Office 365.

Если позже ваша организация решит больше не применять запрет, вы можете отменить его, выполнив действия, обратные выполнявшимся для применения запрета. То есть повторно назначьте лицензии, снова включите службу или разрешите пользователям входить в Office 365.

### <a name="removing-the-license-for-an-office-365-application"></a>Удаление лицензии для приложения Office 365

Как указано ранее, лицензии для всех приложений Office 365, включенных в подписку Microsoft 365 для бизнеса вашей организации, по умолчанию назначаются всем пользователям. Если необходимо запретить доступ к данным, соответствующим запросу субъекта данных, на портале администрирования Office 365 ИТ-администратор может временно отключить лицензию пользователя на какое-либо приложение. Если затем пользователь попытается использовать это приложение, отобразится уведомление об отсутствии лицензии на продукт или сообщение о том, что у пользователя больше нет доступа к этому приложению. Дополнительные сведения см. в статье [Удаление лицензий пользователей в Office 365 для бизнеса](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user).

**Примечания.**

- Чтобы запретить пользователю доступ к Yammer, необходимо сначала [принудительно выполнить идентификацию Office 365 для пользователя Yammer](https://docs.microsoft.com/yammer/configure-your-yammer-network/enforce-office-365-identity), а затем удалить лицензию пользователя на Yammer.

- В сценариях, в которых используется Power BI Embedded, вы можете запретить доступ к приложению независимого поставщика программного обеспечения, в которое внедрен контент.

### <a name="preventing-users-from-accessing-their-onedrive-for-business-account"></a>Запрет доступа пользователей к их учетным записям OneDrive для бизнеса

Если удалить лицензию пользователя на SharePoint Online, у пользователя по-прежнему будет доступ к его учетной записи OneDrive для бизнеса (если она существует). Вам также придется удалить разрешение пользователя на доступ к его учетной записи OneDrive для бизнеса. Для этого исключите пользователя из числа владельцев семейства веб-сайтов его учетной записи OneDrive для бизнеса. В частности, вам необходимо удалить пользователя из групп "Главный администратор семейства веб-сайтов" и "Администраторы семейства веб-сайтов" в его профиле пользователя. См. раздел "Добавление и удаление администраторов в учетной записи OneDrive для бизнеса" в статье [Управление профилями пользователей в Центре администрирования SharePoint](https://docs.microsoft.com/sharepoint/manage-user-profiles).

### <a name="turning-off-an-office-365-service"></a>Отключение службы Office 365

Еще один способ выполнить запрос субъекта данных на запрет обработки данных — отключить соответствующую службу Office 365. Это затронет всех пользователей в организации, и они не смогут использовать эту службу или получать доступ к данным в ней.

The most expedient way to turn off a service is to use Office 365 PowerShell and remove the corresponding user license from all users in the organization. This will in effect restrict anyone from access data in that service. For detailed instructions, see [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and follow the procedures to disable Office 365 services for users from a single licensing plan.

>[!NOTE]
>For Yammer, in additional to removing the Yammer license from user accounts, you also must disable users' ability to sign in to Yammer with Yammer credentials (by enforcing the use of their Office 365 credentials when signing in). For detailed instructions, see [Turn off Yammer access for Microsoft 365 users](https://support.office.com/article/Turn-off-Yammer-access-for-Office-365-users-1f79bfad-f713-4143-aa5d-5584985ce53a).

### <a name="temporarily-removing-data-from-sharepoint-online-or-onedrive-for-business-sites"></a>Временное удаление данных с сайтов SharePoint Online или OneDrive для бизнеса

Another way to restrict the processing of personal data is to temporarily remove it from Office 365 in response to a DSR. When your organization determines that the restriction no longer applies, you can import the data back into Office 365.

Так как большая часть документов Office находится в SharePoint Online или OneDrive для бизнеса, ниже в общих чертах описан процесс удаления документов с сайтов и их повторного импортирования.

1. Get a copy of the document that is the subject of the restriction request. You may have to request either access to the site or ask a global admin or a site collection administrator to provide you with a copy of the document.
2. Сохраните документ в локальном расположении (например, на файловом сервере или в общей папке) либо в другом расположении, отличном от вашего клиента Office 365 в облаке Майкрософт.
3. Permanently delete (purge) the original document from Office 365. This is a 3-step process:

    a.  Delete the original copy of the document. When you delete a document from a site, it's sent to the site Recycle Bin (also called the *first-stage Recycle Bin*).

    b.  Go to the site Recycle Bin and delete that copy of the document. When you delete a document from the site Recycle Bin, it's sent to the site collection Recycle Bin (also called the *second-stage Recycle Bin*). See [Delete a file, folder, or link from a SharePoint document library](https://support.microsoft.com/ru-RU/office/delete-a-file-folder-or-link-from-a-sharepoint-document-library-71f3c90a-0d24-4d80-8b66-f88234b79a52).

    c.  Go to the site collection Recycle Bin and delete that copy of the document, which permanently removes it from Office 365. See [Delete items from the site collection recycle bin](https://support.microsoft.com/ru-RU/office/delete-items-from-the-site-collection-recycle-bin-dd5c00c2-aef6-4458-9d04-80b185077653).

4. После отмены запрета можно снова отправить документ, хранящийся в локальном расположении, на сайт в Office 365.

>[!IMPORTANT]
>The preceding procedure won't work if the document is located on a site that is on hold (with one of the retention or legal hold features in Office 365). In the case where a restriction request for a DSR takes precedence over a legal hold, the hold would have to be removed from the site before a document could be permanently deleted. Additionally, the document history for deleted documents is permanently removed.

### <a name="temporarily-restricting-access-to-sharepoint-online-sites"></a>Временный запрет доступа на сайты SharePoint Online

Администратор SharePoint Online может временно запретить всем пользователям доступ к семейству веб-сайтов SharePoint Online, заблокировав семейство веб-сайтов (с помощью команды **Set-SPOSite -LockState** в SharePoint Online PowerShell). Это предотвращает доступ пользователей к семейству сайтов и любому содержимому или данным, которые находятся на сайте. Если затем вы снова захотите разрешить пользователям доступ к сайту, администратор может разблокировать сайт. Сведения о том, как выполнять этот командлет PowerShell, см. в статье [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite).

### <a name="preventing-a-user-from-signing-in-to-office-365"></a>Запрет пользователям входить в Office 365

An IT admin can also prevent a user from signing into Office 365, which would prevent the user from accessing any Office 365 online service or processing any data stored in Office 365. See [Block a former employee's access to Office 365 data](https://docs.microsoft.com/microsoft-365/admin/add-users/remove-former-employee).

## <a name="part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365"></a>Часть 2. Реагирование на запросы субъектов данных, относящиеся к аналитическим данным, созданным в Office 365

Пакет служб Office 365 от Майкрософт включает веб-службы, которые предоставляют аналитические данные пользователям и организациям, использующим эти службы.

- Delve и MyAnalytics предоставляют аналитические данные отдельным пользователям.
- Workplace Analytics предоставляет аналитические данные организациям.

Эти службы описаны в разделах ниже.

### <a name="delve"></a>Delve

В Delve пользователи могут управлять своими профилями Office 365 и обнаруживать людей и документы, которые могут быть релевантны для них. Для пользователей отображаются только те документы, к которым у них есть доступ. Список полезных статей о Delve см. в статье [Office Delve](https://support.office.com/article/What-is-Office-Delve-1315665a-c6af-4409-a28d-49f8916878ca).

#### <a name="access-and-export"></a>Доступ и экспорт

Admins can't access or export a users' Delve data. This means that users have to access and export Delve data themselves. Most of the data types can be accessed and exported directly from Delve, but some data types are only available through other services.

##### <a name="data-available-in-the-delve-user-interface"></a>Данные, доступные в пользовательском интерфейсе Delve

- **Данные профиля.** Это сведения о профиле из глобального списка адресов вашей организации в Azure Active Directory и дополнительные сведения, которые пользователи указали о себе. Пользователь может получить доступ к данным профиля в Delve или экспортировать их, выбрав пункты **Моя страница** \> **Обновить профиль**. Пользователь может скопировать контент непосредственно со страницы.
- **Данные блога.** Это записи блога, опубликованные пользователем. Чтобы получить доступ к записям блога или экспортировать их, пользователь может щелкнуть **Моя страница** \> **Все записи**. Пользователь может либо скопировать контент непосредственно со страницы, либо сделать снимок экрана.
- **Последние данные о людях.** Это люди в организации, которые по мнению Delve наиболее важны для пользователя в данный момент. Если пользователь щелкнет **Моя страница** \> **Просмотреть все** в области "Выберите пользователя, чтобы увидеть, над чем он работает", Delve показывает человека, наиболее релевантного для пользователя на данный момент.

##### <a name="data-available-through-an-export-link-in-delve"></a>Данные, доступные по ссылке для экспорта в Delve

- **Данные списков пользователей.** Это люди, сведения о которых пользователь просматривал в Delve. Список **Люди** отображается в расположенной слева области домашней страницы. Пользователи могут экспортировать полный список людей, сведения о которых они просматривали в Delve.
- **Данные избранных элементов.** Это доски и документы, которые пользователь пометил как избранные. На странице **Избранное** отображаются доски и документы, которые пользователь добавил в избранные. Пользователи могут экспортировать список своих текущих избранных досок и документов.
- **Данные о параметрах компонентов.** Это конфигурации или действия Delve, создаваемые в результате работы пользователя с Delve. Пользователи могут экспортировать полный список этих параметров.

To access or export the above data, the user can click the gear icon in the upper-right corner in Delve, and then click **Feature settings** > **Export data**. Information is exported in JSON format.

##### <a name="data-thats-available-through-other-services"></a>Данные, доступные через другие службы

- **Данные популярных документов.** Это документы и вложения в электронные письма, которые могут быть интересны пользователю. Delve динамически организует эти документы и сообщения электронной почты на основе действий пользователя и людей, с которыми он работает в Office 365. Когда пользователь открывает Delve или щелкает **Главная**, Delve отображает документы или вложения, самые релевантные для пользователя на данный момент. Чтобы получить доступ к фактическим документам и вложениям либо экспортировать их, пользователь может перейти в службу Office 365, в которой доступен документ или вложение (например, Office.com, SharePoint Online, OneDrive для бизнеса или Exchange Online).
- **Данные последних документов и вложений в электронные письма.** Это последние документы и вложения в электронные письма, которые изменял пользователь. Если пользователь щелкнет **Моя страница** \> **Просмотреть все** в области "Просмотрите недавние документы и вложения", Delve отобразит последние на данный момент документы и вложения в электронные письма, которые изменял пользователь. Чтобы получить доступ к фактическим документам и вложениям либо экспортировать их, пользователь может перейти в службу Office 365, в которой доступен документ или вложение, например в Office.com, SharePoint Online, OneDrive для бизнеса или Exchange Online.
- **Данные документов от окружающих вас людей.** Это документы, которые компонент Delve посчитал наиболее интересными для пользователя на данный момент. Если пользователь щелкнет **Моя страница** \> **Просмотреть все** в области "Обнаружить документы пользователей, находящихся рядом с вами", Delve отображает документы, наиболее релевантные для пользователя на данный момент. Чтобы получить доступ к фактическим документам или экспортировать их, пользователь может перейти в службу Office 365, в которой доступен документ или вложение (например, в Office.com, SharePoint Online, OneDrive для бизнеса или Exchange Online).

#### <a name="rectify"></a>Уточнение

Пользователи могут изменять указанную ниже информацию в Delve.

- **Данные профиля.** Пользователь может изменить сведения о себе, выбрав пункты **Моя страница** \> **Обновить профиль**. В зависимости от параметров вашей организации в глобальном списке адресов у пользователей может не быть возможности изменять сведения в их профилях, например имена или должности.
- **Параметры компонентов.** Чтобы изменить необходимые параметры, пользователь может щелкнуть значок с шестеренкой в правом верхнем углу Delve, а затем выбрать пункт **Параметры компонента** \>.

#### <a name="restrict"></a>Ограничение

To restrict processing in Delve for your organization, you can turn off the Office Graph. Learn more [here](https://docs.microsoft.com/sharepoint/delve-for-office-365-admins).

#### <a name="delete"></a>Удаление

Пользователи могут удалять указанную ниже информацию в Delve.

- **Данные профиля.** Пользователь может удалить данные профиля, выбрав пункты **Моя страница** \> **Обновить профиль**. В зависимости от настроек вашей организации в глобальном списке адресов пользователи могут не иметь возможности удалить всю информацию своего профиля, такую как имя или должность.
- **Документы и вложения в электронные письма.** Чтобы удалить документ или вложение, пользователь должен перейти в службу, в которой хранится этот документ или вложение (например, в службу SharePoint Online, OneDrive для бизнеса или Exchange Online), и удалить документ там.

### <a name="myanalytics"></a>MyAnalytics

MyAnalytics provides statistics to users to help them understand how they spend their time at work. To help your users better understand the data that is presented to them in their personal dashboard and how that data is calculated, direct your users to the [MyAnalytics personal dashboard](https://docs.microsoft.com/workplace-analytics/myanalytics/use/dashboard-2) help topic.

#### <a name="access-and-export"></a>Доступ и экспорт

Если в вашей организации используется MyAnalytics, корпорация Майкрософт создает аналитические данные обо всех пользователях. Все идеи MyAnalytics получены из электронной почты и заголовков собраний в почтовом ящике пользователя. Пользователи могут просмотреть аналитические данные о том, на что они тратят свое рабочее время, на [информационной панели MyAnalytics](https://delve.office.com) (предварительно войдя в свою учетную запись Office 365). Если требуется сохранить постоянные копии своих данных, они могут делать снимки экрана с аналитическими данными MyAnalytics.

#### <a name="rectify"></a>Уточнение

All insights generated by MyAnalytics are derived from the user's mail and calendar items. Therefore, there is nothing to rectify other than the source email or calendar items.

#### <a name="restrict"></a>Запрет

To restrict processing for a specific user, you can opt them out of MyAnalytics. To see how, see [Configure MyAnalytics user settings](https://docs.microsoft.com/workplace-analytics/myanalytics/setup/configure-myanalytics).

#### <a name="delete"></a>Удалить

All mailbox content, including MyAnalytics data, is purged when a user account is "hard-deleted" from Active Directory. For more information, see the [Deleting a user](#deleting-a-user) section in this guide.

### <a name="workplace-analytics"></a>Рабочая аналитика

Workplace Analytics allows organizations to augment Office 365 data with their own business data to gain insights about organizational productivity, collaboration patterns, and employee engagement. [This article](https://docs.microsoft.com/workplace-analytics/index-orig) explains the control that your organization has over the data that Workplace Analytics processes and who has access to that data.

Чтобы упростить выполнение запросов субъектов данных в Workplace Analytics, выполните указанные ниже действия: 

1. Determine whether your organization is using Workplace Analytics. For more information, see [Assign licenses to users](../admin/manage/assign-licenses-to-users.md). If your organization is not using Workplace Analytics, there is no further action.

2. Если в вашей организации используется Workplace Analytics, посмотрите, кому из пользователей в организации назначена роль администратора Workplace Analytics. Кроме того, необходимо определить, есть ли лицензия на Workplace Analytics у почтового ящика субъекта данных. При необходимости попросите своего администратора Workplace Analytics обратиться в службу поддержки Майкрософт за помощью в выполнении указанных ниже запросов субъектов данных. 

#### <a name="access-and-export"></a>Доступ и экспорт

Созданные вами отчеты с аналитическими данными в Workplace Analytics могут содержать персональные данные пользователей, которым ваша организация предоставила лицензии на Workplace Analytics. Это зависит от того, какие сведения ваша организация использовала для дополнения данных из Office 365. Ваш администратор Workplace Analytics должен просмотреть эти отчеты, чтобы определить, содержат ли они личные данные пользователя. Если отчет содержит личные данные пользователя, вам необходимо решить, хотите ли вы предоставить копию этого отчета пользователю. В Workplace Analytics можно экспортировать этот отчет. 

#### <a name="rectify"></a>Уточнение

Как указано выше, в Workplace Analytics используются данные Office 365 в сочетании с данными организации, предоставляемыми для создания интересующих вас отчетов. Данные Office 365 не могут быть исправлены; это основано на электронной почте пользователя и действиях календаря. Но вы можете уточнить данные организации, отправленные в Workplace Analytics для создания отчета. Для этого вам потребуется уточнить исходные данные, отправить их и повторно создать отчет Workplace Analytics.

#### <a name="restrict"></a>Запрет

Чтобы запретить обработку для определенного пользователя, вы можете удалить его лицензию на Workplace Analytics.

#### <a name="delete"></a>Удалить

If a data subject would like to be removed from a Workplace Analytics report or set of reports, you can delete the report. It is your responsibility to delete users from any organizational data that you used to generate the report, and reupload the data. All data about the user is removed when a user account is "hard-deleted" from Azure Active Directory. 

Для удаления персональных данных субъекта данных глобальный администратор должен выполнить следующие действия: 

1. Удалить лицензию Workplace Analytics для субъекта данных.
2. Delete the Azure Active Directory (AAD) entry for the data subject. (For more information, see [Delete a user](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory#delete-a-user).)
3. Contact support and have support open a ticket for a Data Subject Rights (DSR) user-delete request. In this ticket, identify the data subject by using their User Principal Name (UPN).
4. Экспортировать копию данных о персонале из системы по работе с персоналом компании (см. [Экспорт данных](https://docs.microsoft.com/workplace-analytics/setup/prepare-organizational-data)), удалить информацию субъекта данных из файла данных о персонале, а затем загрузить измененный файл данных в форме CSV-файла в Workplace Analytics (см. статью [Загрузка данных организации](https://docs.microsoft.com/workplace-analytics/setup/upload-organizational-data)).

## <a name="part-3-responding-to-dsrs-for-system-generated-logs"></a>Часть 3. Реагирование на запросы субъектов данных в отношении системных журналов

Microsoft also provides you with the ability to access, export, and delete system-generated logs that may be deemed personal under the GDPR's broad definition of "personal data." Examples of system-generated logs that may be deemed personal under GDPR include:

- Данные об использовании продуктов и служб, например журналы о действиях пользователей
- Данные запросов и поисковых запросов пользователей
- Данные, созданные продуктами и службами на основе сведений о работе системы и взаимодействии с пользователями и другими системами

Возможность запрещать доступ к данным или уточнять их в системных журналах не поддерживается. Данные в системных журналах основаны на фактических действиях в облаке Майкрософт и диагностических данных. Изменение таких данных приведет к нарушению архивных записей о действиях и увеличит риски мошенничества и угроз безопасности.

### <a name="accessing-and-exporting-system-generated-logs"></a>Получение доступа к журналам, создаваемым системой, и их экспорт

Администратор клиента — это единственный сотрудник организации, которому доступны системные журналы, относящиеся к работе пользователя со службами и приложениями Office 365. Данные, полученные по запросу на экспорт, будут предоставлены в машиночитаемом формате в виде файлов, с помощью которых пользователь сможет узнать, к каким службам относятся данные. Как упоминалось выше, полученные данные не будут включать данные, которые могут нарушить безопасность или стабильность службы.

Получение доступа к системным журналам и их экспорт:

1. Войдите на портал Azure и выберите **Все службы**.
2. Введите "политика" в фильтр и выберите **Политика**.
3. В колонке **Политика** выберите **Конфиденциальность пользователей** > **Управление запросами пользователей** > **Добавить запрос на экспорт**.
4. Создайте **запрос на экспорт данных**:

    - **Пользователь**. Введите электронный адрес пользователя Azure Active Directory, запросившего экспорт.
    - **Подписка**. Выберите учетную запись, используемую для создания отчетов об использовании ресурсов и выставления счетов за услуги. Кроме того, это расположение учетной записи хранения Azure.
    - **Учетная запись хранения.** Выберите расположение службы хранилища Azure (хранилища BLOB-объектов). Дополнительные сведения см. в статье "Общие сведения о службе хранилища Azure — хранилище BLOB-объектов".
    - **Контейнер.** Создайте новый (или выберите существующий) контейнер в качестве места хранения экспортируемых конфиденциальных данных пользователя.

5. Нажмите **Создать**.

Запрос на экспорт переходит в состояние **Ожидание**. Состояние отчета можно просматривать в колонке **Конфиденциальность пользователей** > **Обзор**.

>[!IMPORTANT]
>Так как персональные данные могут поступать из нескольких систем, экспорт может занять до одного месяца.

### <a name="notify-about-exporting-or-deleting-issues"></a>Уведомление о проблемах при экспорте или удалении

Если при экспорте или удалении данных из портала Azure возникают проблемы, перейдите на портал Azure, выберите колонку **Справка и поддержка** и отправьте новый запрос в разделе **Управление подписками** > **Другие запросы на обеспечение безопасности и соответствия** > **Конфиденциальность и запросы GDPR**.

>[!NOTE]
 >При экспорте данных из портала Azure системные данные для некоторых приложений не экспортируются. Сведения о том, как экспортировать данные этих приложений см. в статье [Дополнительные действия по экспорту данных системных журналов](https://docs.microsoft.com/microsoft-365/compliance/gdpr-system-generated-log-data).

Ниже обобщены сведения о доступе к системным журналам и их экспорте.

- **Сколько времени занимает выполнение запроса на экспорт с помощью портала Azure?** Это может зависеть от ряда факторов. Обычно это занимает день или два, но может потребоваться до 30 дней.
- **В каком формате будут представлены выходные данные?** Выходные данные предоставляются в виде структурированных файлов, пригодных для использования на компьютерах, например XML-, CSV- или JSON-файлов.
- **У кого есть доступ к порталу Azure для отправки запросов на доступ к системным данным?** Доступ к порталу Azure есть у глобальных администраторов Office 365.
- **Какие данные возвращаются в результатах экспорта?** Результаты содержат системные журналы, хранящиеся в службах Майкрософт. Экспортируемые данные извлекаются из различных служб Майкрософт, включая Office 365, Azure и Dynamics. Результаты не включают данные, которые могут нарушить безопасность и стабильность службы.
- **Каким образом данные возвращаются пользователю?** Данные экспортируются в ваше расположение в службе хранилища Azure. Администраторы организации определяют порядок отображения или возврата данных пользователям.
- **Как выглядят данные в системных журналах?** Ниже приведен пример данных в формате JSON:

    ```JSON
    [{
    "DateTime": "2017-04-28T12:09:29-07:00",
    "AppName": "SharePoint",
    "Action": "OpenFile",
    "IP": "154.192.13.131",
    "DevicePlatform": "Windows 1.0.1607"
    }]
    ```

Кроме того, можно получить данные об использовании самых популярных продуктов и служб Майкрософт, например Exchange Online, SharePoint Online, Skype для бизнеса, Yammer и групп Office 365. Для этого выполните поиск необходимых данных в журнале аудита Office 365 в Центре безопасности и соответствия требованиям. Дополнительные сведения см. в разделе [Используйте средство поиска в журналах аудита Office 365 в расследованиях, связанных с запросами субъектов данных](#use-the-audit-log-search-tool-in-dsr-investigations) в приложении А. Использование журнала аудита может быть полезным, так как можно назначать другим людям в вашей организации (например, специалисту по соответствию требованиям) разрешение на поиск в журналах аудита для доступа к этим данным.

### <a name="deleting-system-generated-logs"></a>Удаление системных журналов

To delete system-generated logs retrieved through an access request, you must remove the user from the service and permanently delete their Azure Active Directory account. For instructions about permanently delete a user, see the [Deleting a user section](#deleting-a-user) in this guide. It's important to note that permanently deleting a user account is irreversible once initiated.

При окончательном удалении учетной записи пользователя данные пользователя удаляются из системных журналов (кроме данных, которые могут скомпрометировать безопасность или надежность службы) почти для всех служб Office 365 в течение 30 дней. 

Исключение из этого 30-дневного периода составляет служба Exchange Online, в которой для необратимого удаления учетной записи пользователя требуется больше 30 дней. Это связано с критической важностью контента в Exchange Online и предназначено для предотвращения случайной потери данных. Служба Exchange Online намеренно разработана так, чтобы удерживать данные на срок до 60 дней после окончательного удаления учетных записей пользователей. Чтобы необратимо удалить данные пользователя в Exchange Online в 30-дневный период, окончательно удалите учетную запись пользователя в Azure Active Directory, а затем обратитесь [в службу поддержки Майкрософт](https://support.microsoft.com/) и попросите вручную удалить данные пользователя в Exchange Online вне запланированного процесса удаления. Дополнительные сведения см. в разделе [Удаление данных в Exchange Online](#removing-exchange-online-data) выше.

Deleting a user's account will not remove system-generated logs for Yammer and Kaizala. To remove the data from these applications, see one of the following:

- Yammer — [Управление запросами субъекта данных GDPR в Yammer корпоративный](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)
- Kaizala - [Экспорт или удаление данных пользователя в организации в Kaizala](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)

#### <a name="national-clouds"></a>Национальные облачные развертывания

Для экспорта данных системных журналов в следующие национальные облачные развертывания глобальный ИТ-администратор должен выполнить указанные ниже действия.

- **Office 365 Germany**: выполните описанные выше действия.
- **Office 365 для государственных организаций США**: [перейдите на портал администрирования Office 365](https://portal.office365.us) и отправьте запрос в службу поддержки Майкрософт.
- **Office 365 под управлением 21Vianet (Китай)**: [откройте портал администрирования Office 365 под управлением 21Vianet](https://portal.partner.microsoftonline.cn/AdminPortal/Home#/homepage), перейдите к разделу **Коммерция** > **Подписка** > **Конфиденциальность** > **GDPR** и укажите нужные сведения.

## <a name="part-4-additional-resources-to-assist-you-with-dsrs"></a>Часть 4. Дополнительные ресурсы по работе с запросами субъектов данных

### <a name="dsr-guides-for-other-microsoft-enterprise-services"></a>Руководства по выполнению запросов субъектов данных для других корпоративных служб Майкрософт

В данном руководстве описано, как находить персональные данные и что делать с ними при ответах на запросы субъектов данных, если вы используете продукты, службы и средства администрирования Office 365. Аналогичные руководства для других корпоративных служб Майкрософт см. на портале [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/).

### <a name="microsoft-support"></a>Служба поддержки Майкрософт

"Support Data" is the data you and your users provide to Microsoft if your organization or your users engage with Microsoft to receive product support related to Office 365 or other Microsoft products and services (for example, to troubleshoot unexpected product behavior). Some of this data may contain personal data. For more information, see [Microsoft Support and Professional Services Data Subject Requests for the GDPR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-prof-services).

### <a name="product-and-services-authenticated-with-an-org-id-for-which-microsoft-is-a-data-controller"></a>Продукты и службы, прошедшие проверку подлинности с помощью идентификатора организации, для которой Майкрософт является управляющим данными

В частях 1–3 данного руководства рассматриваются продукты и службы, при использовании которых Майкрософт является обработчиком данных для вашей организации, благодаря чему вашему администратору клиента доступна функция запросов субъектов данных. Существуют различные обстоятельства, когда пользователи вашей организации могут использовать свою служебную или школьную учетную запись (также называемую «Azure Active Directory ID» или «AAD») для входа в продукты и службы Microsoft, для которых Microsoft является контроллером данных. Для всех таких продуктов и услуг вашим пользователям потребуется инициировать собственные запросы субъектов данных напрямую в Майкрософт, и Майкрософт выполнит эти запросы и предоставит результаты непосредственно пользователям. По умолчанию продукты и службы, при использовании которых требуется хранить созданный пользователями контент, позволяют пользователям получать доступ к созданному пользователями контенту, а также экспортировать, уточнять и удалять его в рамках унаследованной функциональности продуктов. Ниже перечислены некоторые сценарии, в которых может применяться такая схема.

- **Дополнительные подключенные сетевые службы.** В приложениях Microsoft 365 для предприятий пользователям доступны некоторые дополнительные подключенные сетевые службы. Список служб и соответствующих пользовательских средств управления представлен [здесь](https://support.office.com/article/microsoft-s-other-connected-services-92c234f1-dc91-4dc1-925d-6c90fc3816d8). Вы можете решить, следует ли разрешить пользователям использовать эти службы. Дополнительные сведения см. в статье [Как администраторы могут управлять службами контроллера в приложениях Microsoft 365 для предприятий](https://docs.microsoft.com/DeployOffice/manage-controller-services-office-365-proplus). Если эти дополнительные службы обрабатывают персональные данные, управляющим данными для этих служб является Майкрософт.
- **Отзывы пользователей.** Если ваши пользователи захотят оставить отзывы продуктах и службах Майкрософт, корпорация Майкрософт является управляющим для соответствующих данных, при условии что они содержат персональные данные. Корпорация Майкрософт обязуется исполнять запросы субъектов данных в отношении собранных ею отзывов (включая отзывы, которыми управляют субобработчики Майкрософт) за исключением тех случаев, когда корпорация Майкрософт предупреждала пользователей, что не следует отправлять персональные данные, в ходе сбора отзывов. Исключения: если в ходе сбора отзывов корпорация Майкрософт предупредила пользователей, что не следует указывать персональные данные, Майкрософт рассчитывает на эту инструкцию и будет предполагать, что персональные данные не были предоставлены. Пользователям, создавшим отдельные учетные записи с помощью служб от сторонних поставщиков, требуется отправлять свои запросы субъектов данных непосредственно этим поставщикам.
- **Windows с проверкой подлинности при помощи рабочей или учебной учетной записи.** Если ваша организация приобрела лицензии на ОС Windows, а ваши пользователи проходят проверку подлинности в предоставленной организацией ОС Windows с помощью своих рабочих или учебных учетных записей, Майкрософт выступает в качестве управляющего данными.
- **Продукты или службы, приобретенные пользователями.** Если вы разрешаете пользователям по их собственной инициативе приобретать продукты или службы Майкрософт, в которых для проверки подлинности используется AAD (например, надстройки Office или приложения, доступные в Microsoft Store), корпорация Майкрософт может быть управляющим данными. При использовании такого продукта или службы Майкрософт для инициирования запроса субъекта данных пользователям требуется обращаться напрямую в корпорацию Майкрософт.

>[!IMPORTANT]
>If you delete a user as enabled via Azure Active Directory, your (former) user will lose the ability to sign in to any products or services for which he or she formerly relied upon for a work or school account. Additionally, Microsoft will no longer be able to authenticate the user in connection with a DSR request for products or services for which Microsoft is a data controller. If you wish to enable a user to initiate DSRs against such services, it is important you instruct your user to do so before you delete the user's AAD account.

### <a name="personal-accounts"></a>Личные учетные записи

Если ваши пользователи применяли учетные записи Майкрософт (то есть личные) для приобретения продуктов и служб в корпорации Майкрософт для личного использования, для которых корпорация Майкрософт является управляющим данными, эти пользователи могут инициировать запросы субъектов данных с помощью [панели мониторинга конфиденциальности (Майкрософт)](https://account.microsoft.com/account/privacy).

### <a name="third-party-products"></a>Сторонние продукты

Если ваша организация или пользователи, действующие от своего лица, приобретали продукты или службы сторонних разработчиков и использовали свои рабочие или учебные учетные записи Майкрософт для проверки подлинности, то все запросы субъектов данных следует перенаправлять соответствующей третьей стороне.

## <a name="appendix-a-preparing-for-dsr-investigations"></a>Приложение А. Подготовка к расследованиям для ответа на запросы субъектов данных

Чтобы подготовить свою организацию к выполнению расследований для ответов на запросы субъектов данных с помощью служб Office 365, учтите изложенные ниже рекомендации.

- Для управления расследованиями по запросам субъектов данных используйте средство для работы с делами обнаружения электронных в Центре безопасности и соответствия требованиям
- Настройка границ соответствия требованиям для ограничения области операций средства "Поиск контента"
- Используйте средство поиска в журналах аудита в расследованиях по запросам субъектов данных

### <a name="use-the-dsr-case-tool-to-manage-dsr-investigations"></a>Используйте средство для работы с делами запросов субъектов данных для управления расследованиями для ответа на запросы субъектов данных.

We recommend that you use the DSR case tool in Security & Compliance Center to manage DSR investigations. By using the DSR case tool, you can:

- Создавать отдельные дела для каждого расследования для ответа на запросы субъектов данных.

- Применять встроенные средства для поиска всего контента, связанного с определенным субъектом данных. Когда вы создаете дело и запускаете операцию поиска, система выполняет поиск в указанных ниже расположениях.

   - Все почтовые ящики в организации (в том числе связанные с Microsoft Teams и группами Microsoft 365).
   - Все сайты SharePoint Online и учетные записи OneDrive для бизнеса в организации.
   - Все сайты Microsoft Teams и сайты групп Microsoft 365 в вашей организации
   - Все общедоступные папки в Exchange Online.

- Измените поисковый запрос, используемый по умолчанию, и повторно выполните поиск, чтобы уменьшить количество результатов поиска.

- Вы можете управлять доступом различных пользователей к делу, добавляя их в качестве участников дела. Только участники дела могут получать доступ к делу. Для них в списке дел на странице дел запросов субъектов данных в Центре безопасности и соответствия требованиям отображаются только дела, участниками которых они являются. Кроме того, вы можете назначать различные разрешения различным участникам одного и того же дела. Например, вы можете разрешить одним участникам только просматривать дело и результаты действий средства "Поиск контента", а другим — создавать операции поиска и экспортировать результаты поиска.

- Создайте задания экспорта, чтобы экспортировать результаты поиска для ответа на соответствующий запрос субъекта данных. Вы можете экспортировать весь контент, возвращенный средством "Поиск контента". Также можно экспортировать другие данные Office 365, связанные с субъектом данных.

- Создайте задания экспорта, чтобы экспортировать результаты поиска для ответа на соответствующий запрос субъекта данных. Вы можете экспортировать весь контент, возвращенный средством "Поиск контента". Вы также можете экспортировать системные журналы для службы перемещаемых параметров Office.

- По завершении процесса расследования, связанного с запросом субъекта данных, вы можете удалить соответствующие дела. В результате будут удалены все операции поиска контента и задания экспорта, связанные с делом.

Сведения о том, как приступить к работе с делами запросов субъектов данных, см. в статье [Управление запросами субъектов данных, определенными в GDPR, с помощью средства управления делами DSR в Центре безопасности и соответствия требованиям](https://docs.microsoft.com/microsoft-365/compliance/manage-gdpr-data-subject-requests-with-the-dsr-case-tool).

>[!IMPORTANT]
>An eDiscovery Administrator can view and manage all DSR cases in your organization. For more information about the different roles related to eDiscovery, see [Assign eDiscovery permissions to potential case members](https://docs.microsoft.com/Office365/SecurityCompliance/assign-ediscovery-permissions).

### <a name="set-up-compliance-boundaries-to-limit-the-scope-of-content-searches"></a>Настройка границ соответствия требованиям для ограничения области операций средства "Поиск контента"

Compliance Boundaries are implemented by using the search permissions filtering functionality in the Security & Compliance Center. Compliance Boundaries create logical search boundaries within an organization that control/limit which content locations (for example Exchange Online mailboxes and SharePoint Online sites) that an IT admin or compliance officer can search. Compliance Boundaries are useful for multi-national organizations that need to respect geographical boundaries, governmental organizations that need to separate different agencies, and business organizations that segregated into business unit or department. For all these scenarios, Compliance Boundaries can be used in DSR investigations to limit which mailboxes and sites can be searched by people involved in the investigation.

Вы можете использовать границы соответствия вместе с делами обнаружения электронных данных, чтобы ограничить перечень расположений контента, в которых можно выполнять поиск в рамках расследования, и разрешить поиск только в расположениях, связанных с определенным агентством или бизнес-единицей.

Вот общий обзор того, как реализовать границы соответствия (вместе со случаями eDiscovery) для расследований DSR.

1. Определите агентства в вашей организации, которые будут назначены в качестве границ соответствия.

2. Determine which user object attribute in Azure Active Directory will be used to define the compliance boundary. For example, you might choose the Country, CountryCode, or Department attribute, so that members of the admin role group that you create in the next step can only search the content locations of the users that have a specific value for that attribute. This is how you limit who can search for content in a specific agency.

>[!NOTE]
>В данный момент вам необходимо выполнить дополнительное действие для OneDrive для бизнеса и создать запрос в службу поддержки Майкрософт, чтобы синхронизировать атрибуты с учетными записями OneDrive для бизнеса.

4. Create an admin role group in the Security & Compliance Center for each compliance boundary. We recommend that you create these role groups by copying the built-in eDiscovery Manager role group and then removing any roles as necessary.

5. Добавьте участников в каждую группу ролей в качестве руководителей службы обнаружения электронных данных.  Участники отвечают за расследования и ответы на запросы субъектов данных. Обычно в качестве участников назначают ИТ-администраторов, специалистов по конфиденциальности данных, руководителей по соответствию требованиям и представителей отдела кадров.

6. Создайте фильтр разрешений поиска для каждой границы соответствия, чтобы участники соответствующей группы ролей "Администратор" могли выполнять поиск только в тех почтовых ящиках и на тех сайтах пользователей, которые находятся внутри агентства или границы соответствия. Благодаря фильтру разрешений поиска участники соответствующей группы ролей смогут выполнять поиск только в тех расположениях контента, для которых значение атрибута объекта пользователя соответствует необходимому агентству или границе соответствия.

Пошаговые инструкции см. в статье [Настройка границ соответствия для расследований дел обнаружения электронных данных в Office 365](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries).

### <a name="use-the-audit-log-search-tool-in-dsr-investigations"></a>Используйте средство поиска в журналах аудита в расследованиях по запросам субъектов данных

IT admins can use the audit log search tool in the Security & Compliance Center to identity documents, files, and other Office 365 resources that users have created, accessed, changed, or deleted. Searching for this kind activity can be useful in DSR investigations. For example, in SharePoint Online and OneDrive for Business, auditing events are logged when users perform these activities:

- Получают доступ к файлу
- Изменяют файл
- Перемещают файл
- Отправляют или скачивают файл

В журнале аудита вы можете искать определенные действия, типы действий, действия, выполненные определенным пользователем, и применять другие критерии поиска. Помимо действий в SharePoint Online и OneDrive для бизнеса вы можете выполнять поиск действий в Flow, Power BI и Microsoft Teams. Записи аудита хранятся 90 дней. Следовательно, вы не сможете искать действия пользователей, которые произошли более 90 дней назад. Полный список действий, подвергаемых аудиту, и сведения о том, как выполнять поиск в журнале аудита, см. в статье [Поиск в журнале аудита в Центре безопасности и соответствия требованиям](search-the-audit-log-in-security-and-compliance.md).

>[!TIP]
>Чтобы обойти ограничение в 90 дней, рассмотренное выше, и вести хронологическую историю записей аудита вашей организации, вы можете экспортировать все операции по регулярному расписанию (например, каждые 30 дней), чтобы иметь постоянную запись записей аудита вашей организации.

## <a name="appendix-b-change-log"></a>Приложении Б. Журнал изменений

В таблице ниже перечислены изменения в руководстве по запросам субъектов данных Office 365, начиная с его первой публикации 25 мая 2018 г.

|Дата  |Раздел или приложение |Изменение  |
|:---------|:---------|:---------|
|18.09.2018 | [Доска](#whiteboard) |Whiteboard Preview is no longer in preview and has been released to general availability. Therefore, the section on Whiteboard Preview was renamed to "Whiteboard for PC, Surface Hub, and other platforms"; procedures to access, export, and delete data were removed from this section and replaced with a link to the Whiteboard support article.|
|11/08/2018 | [Workplace Analytics](#workplace-analytics) |Добавлены пошаговые инструкции в раздел «Удаление» относительно удаления субъекта данных в службе Workplace Analytics и удаления информации о субъекте данных из отчета Workplace Analytics.|
|11/12/2018| Все| Устранены неработающие закладки и битые ссылки на внешние статьи.|
|9.01.2019| StaffHub |В разделе "Удаление" обновлено описание того, что произойдет, если безвозвратно удалить учетную запись пользователя.|
|08.05.2019| [Publisher](#publisher)|Добавлен контент об ответе на запросы субъектов данных (DSR) для Publisher.|
|11.07.2019| [MyAnalytics](#myanalytics)|Возможность использования администратором средства для работы с делами DSR в Центре безопасности и соответствия требованиям с целью экспорта данных MyAnalytics была удалена, поскольку теперь все пользователи могут просматривать свои данные в приложении MyAnalytics. |
|11.6.2019|[Образование](#education)|Ссылки на новые разделы, посвященные использованию сценариев PowerShell, позволяют получить список классов для конкретного учащегося, а затем экспортировать или удалить их данные.|
|28.01.2020| Все | Из документа удалено упоминание StaffHub. Приложение StaffHub больше недоступно. |
||||
