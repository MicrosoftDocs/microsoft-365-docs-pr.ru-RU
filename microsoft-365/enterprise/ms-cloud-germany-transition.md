---
title: Миграция с Microsoft Cloud для Германии (Microsoft Cloud Deutschland) в службы Office 365 в новых регионах центров обработки данных в Германии
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 07/09/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 'Сводка: понимание миграции с Microsoft Cloud для Германии (Microsoft Cloud Deutschland) в службы Office 365 в новых регионах центров обработки данных в Германии'
ms.openlocfilehash: cfbd3b7406f7c7824f736633e3a4dba6fa5c4bff
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693386"
---
# <a name="migration-from-microsoft-cloud-germany-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Миграция с Microsoft Cloud для Германии (Microsoft Cloud Deutschland) в службы Office 365 в новых регионах центров обработки данных в Германии


>[!Note]
>Эта статья относится только к разрешенным клиентам Microsoft Cloud для Германии/Deutschland.
>

## <a name="cloud-service-offerings-in-germany"></a>Предложения облачных служб в Германии

В августе 2018 г. мы объявили о своем намерении поставить полноценную платформу Microsoft Cloud (Azure, Office 365, Dynamics 365 и Power Platform) из новых облачных регионов в Германии, чтобы лучше обеспечить цифровые преобразования наших клиентов. В августе 2019 г. мы объявили о том, что находимся в процессе открытия новых облачных регионов в Германии. Мы объявили о доступности Azure в августе, а Office 365 стал доступен в декабре.  В первом квартале 2020 предполагается, что Dynamics 365 и Power Platform также станут доступными.  

Новые регионы предназначены для удовлетворения растущих потребностей немецких клиентов благодаря большей гибкости, новейшим интеллектуальным облачным сервисам, а также полному подключению к нашей глобальной облачной сети и хранению данных клиентов в пределах Германии.

## <a name="moving-to-the-new-german-regions"></a>Переход на новые регионы в Германии

Существующие клиенты Microsoft Cloud для Германии (Microsoft Cloud Deutschland) теперь могут начать миграцию своих клиентов Office 365, Dynamics 365 Customer Engagement и Power Platform BI.  Первым шагом является [согласие на миграцию под руководством корпорации Майкрософт](https://aka.ms/office365germanymoveoptin) в наши новые регионы центров обработки данных в Германии.

Для организаций, давших согласие на программу под руководством корпорации Майкрософт, предполагается, что миграция будет выполняться в 2020 году. В результате миграции основные данные клиента и подписки перемещаются в новые регионы в Германии. 

Указанные ниже службы будут перенесены в рамках программы под руководством корпорации Майкрософт:

- Azure Active Directory
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive для бизнеса
- Skype для бизнеса Online

В процессе миграции с Microsoft Cloud для Германии на регионы центров обработки данных в Германии существующие пользователи Skype для бизнеса Online перейдут в Microsoft Teams. Дополнительные сведения см. в статье [Начало перехода на Microsoft Teams](https://aka.ms/SkypeToTeams-Home).

- Группы Office 365
- Dynamics 365 / Power Platform

Предварительные требования и влияние миграции на эти службы описаны в статье [Dynamics 365 Customer engagement](https://aka.ms/d365ceoptin).

1 марта 2021 г. прекращается поддержка Office 365 Видео. Если вы решили перенести свой клиент Office 365 в новые регионы центров обработки данных в Германии, Office 365 Видео не будет поддерживаться после завершения миграции SharePoint Online. [Подробнее](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Как подготовиться к миграции на службы Office 365 в новых регионах центров обработки данных в Германии

Сначала необходимо сообщить корпорации Майкрософт о своем решении, чтобы у нас было ваше согласие на миграцию вашей подписки и данных из Microsoft Cloud для Германии / Deutschland в службы Office 365 в новых регионах центров обработки данных в Германии.  Инструкции приведены в статье [Процедура согласия](ms-cloud-germany-migration-opt-in.md).

- Всем мигрирующим пользователям необходимо проверить подключение к [URL-адресам и IP-адресам Office 365](urls-and-ip-address-ranges.md), которые включают в себя новые регионы центров обработки данных в Германии.
- Ознакомьтесь с описанием службы платформы Office 365, чтобы понять, какие функции и службы станут доступны вашей организации после завершения миграции в регион в Германии. 
- Во время миграции будут переходить платные подписки.  Мы не переносим пробные подписки.

Миграции клиента выполняются в виде серверных операций обслуживания, для которых требуется минимальное взаимодействие с клиентом.  В процессе миграции в Центре сообщений будет отображаться информация о любых дополнительные задачах, выполняемых клиентом, и об общем состоянии миграции.  Примером задач могут быть управляемые клиентом обновления DNS или реконфигурация гибридной настройки для гибридных клиентов Exchange.

## <a name="customer-experience-during-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Взаимодействие с клиентами в процессе миграции на службы Office 365 в новых регионах центров обработки данных в Германии

Миграция клиента призвана оказать минимальное влияние на конечных пользователей и администраторов.  Однако для каждой рабочей нагрузки следует учитывать ряд моментов.  

### <a name="azure-active-directory"></a>Azure Active Directory

Подписки на Office/Dynamics (на основе Microsoft Cloud для Германии) переносятся в регион в Германии с перемещением Azure Active Directory (Azure AD). Затем организация обновляется в соответствии с новыми глобальными подписками на службы. В ходе короткого процесса переноса подписки изменения в подписке будут заблокированы.

### <a name="exchange-online"></a>Exchange Online

Клиенты Exchange Online Hybrid должны повторно запустить мастер настройки гибридной конфигурации, чтобы обновить локальную конфигурацию Microsoft Cloud для Германии до перехода, и повторно выполнить мастер настройки гибридной конфигурации (HCW) после очистки в соответствии с глобальной службой. Для клиентов, использующих личные домены, могут потребоваться дополнительные обновления DNS.

Почтовые ящики переносятся в виде серверного процесса; пользователи в вашей организации могут находиться в Microsoft Cloud для Германии или в регионе в Германии во время перехода и быть частью одной организации Exchange (GAL)

### <a name="exchange-online-protection"></a>Exchange Online Protection

Серверные функции Exchange Online Protection скопированы в новый регион в Германии

### <a name="sharepoint-online"></a>SharePoint Online

После завершения миграции SharePoint Online в регион в Германии будут перестроены только индексы данных. Функции, зависящие от индексов поиска, могут быть затронуты в процессе переиндексации.

Существующие URL-адреса sharepoint.de сохраняются для перешедших организаций.

### <a name="onedrive-for-business"></a>OneDrive для бизнеса

После завершения миграции OneDrive для бизнеса в регион в Германии будут перестроены только индексы данных. Функции, зависящие от индексов поиска, могут быть затронуты в процессе переиндексации.

### <a name="skype-for-business-online"></a>Skype для бизнеса Online

Существующие клиенты Skype для бизнеса Online будут переходить в Microsoft Teams. Дополнительные сведения см. в статье [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home).

### <a name="office-365-video"></a>Office 365 Видео
Содержимое из Office 365 Видео будет перенесено в рамках миграции SharePoint Online. Но поддержка Office 365 Видео прекращается, и эта служба больше не будет поддерживаться после завершения миграции SharePoint Online в новые регионы центров обработки данных в Германии. Видеоролики не будут воспроизводиться в пользовательском интерфейсе Office 365 Видео после миграции SharePoint.

Microsoft Stream не будет разворачиваться в Microsoft Deutschland, и в настоящее время у нас нет временной шкалы для развертывания Microsoft Stream в новых регионах центров обработки данных в Германии. В результате в этом регионе не будут предоставлены средства для миграции Office 365 Видео в Microsoft Stream. Чтобы сохранить свое содержимое, вам потребуется вручную скачать или переместить содержимое до 1 марта 2021 г. [Подробнее](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)


## <a name="key-differences-between-microsoft-cloud-germany-microsoft-cloud-deutschland-and-office-365-services-in-the-new-german-datacenter-regions"></a>Основные различия между Microsoft Cloud для Германии (Microsoft Cloud Deutschland) и служб Office 365 в новых регионах центров обработки данных в Германии


|| Microsoft Cloud для Германии (Microsoft Cloud Deutschland) | Службы Office 365 в новых регионах центров обработки данных в Германии |
|:-------|:-----|:-----|
| Службы Microsoft 365, доступные для подписки только на один клиент Office 365 | 15 служб (см. раздел REF) | 29 служб (см. раздел REF) |
| Новые функции | Новые функции недоступны. | Новые функции будут доступны в рамках глобальных служб Office 365. |
| Доверенное лицо для данных | Да | Нет |
| Взаимодействие между клиентами и глобальными клиентами Office 365 | Нет | Да |
| Размещение данных клиента | Данные клиента будут храниться только в центрах обработки данных в Германии. | Корпорация Майкрософт будет хранить указанные ниже данные клиентов только в Германии: содержимое почтовых ящиков Exchange Online (тело сообщения электронной почты, элементы календаря и содержимое вложений в сообщения электронной почты), содержимое сайта SharePoint Online и файлы, хранящиеся на этом сайте, файлы, отправленные в OneDrive для бизнеса. |
| Применимые условия использования | [Условия предоставления услуг в Интернете](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) с [дополнением](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Условия использования веб-служб](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="frequently-asked-questions"></a>Вопросы и ответы

### <a name="is-migration-required"></a>Требуется ли миграция?

Корпорация Майкрософт предлагает миграцию клиентов Office 365 из Microsoft Cloud для Германии в службы Office 365 в новых регионах центров обработки данных в Германии без дополнительной оплаты.  Хотя мы настоятельно рекомендуем вам зарегистрироваться для миграции в новые регионы центров обработки данных в Германии, однако мы продолжим предоставлять необходимые обновления безопасности для региона Microsoft Cloud для Германии.  

Службы Office 365 в новых регионах центров обработки данных в Германии имеют дополнительные преимущества:

- Предложение конкурентоспособной рыночной цены для [Azure](https://azure.microsoft.com/pricing/calculator/), [Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), [Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/) и [Power BI](https://powerbi.microsoft.com/pricing/). 
- Они подключены к глобальной сети Майкрософт, предлагают сотни периферийных сетевых сайтов, расположений пиринга и точек выхода, чтобы обеспечить надежную работу пользователей в любой точке мира. 
- Помогают вам соответствовать местным требованиям о размещении данных в пределах Германии. 
- Вы получаете полнофункциональное глобальное облачное решение, в том числе новейшие версии наших служб и новых возможностей, включая Microsoft Teams и Office 365. Сравните продукты по регионам для [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), [Office 365](o365-data-locations.md)и [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).
- Предлагают полный набор функций, обеспечение безопасности корпоративного уровня и широкие возможности, которые помогают клиентам удовлетворить нормативные требования. 
- Доступны через существующие контракты веб-служб.

#### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>Какова доступность службы между различными предложениями облачных служб Office 365?

Указанные ниже 15 служб доступны в предложении облачной службы Microsoft Cloud для Германии (Microsoft Cloud Deutschland).  Мы не добавляем новые службы в Microsoft Cloud для Германии.

1. Exchange Online
2. Защищенное хранилище для пользователей (Exchange Online)
3. Группы (современные группы)
4. Профиль Delve
5. Exchange Online Protection
6. Расширенная защита от угроз (ATP)
7. Advanced eDiscovery
8. Расширенное управление данными
9. SharePoint Online
10. Защищенное хранилище для пользователей (SharePoint Online)
11. OneDrive для бизнеса
12. Skype для бизнеса
13. Word Online, Excel Online, PowerPoint, OneNote, Visio Online
14. Office 365 профессиональный плюс
15. Outlook Mobile

В настоящее время пакет служб Office 365 в новых регионах центров обработки данных в Германии включает 29 служб.  Новые функции и службы будут доступны в рамках глобальных служб Office 365 на постоянной основе.

1. Exchange Online
2. Защищенное хранилище для пользователей (Exchange Online)
3. Группы (современные группы)
4. Профиль Delve
5. MyAnalytics
6. Рабочая аналитика
7. Exchange Online Protection
8. Расширенная защита от угроз (ATP)
9. Advanced eDiscovery
10. Расширенное управление безопасностью
11. Управление правами на доступ к данным
12. Расширенное управление данными
13. SharePoint Online
14. Защищенное хранилище для пользователей (SharePoint Online)
15. OneDrive для бизнеса
16. Microsoft Stream
17. Skype для бизнеса (переход на Microsoft Teams в процессе миграции)
18. Облачная УАТС
19. Конференц-связь через ТСОП
20. Вызовы ТСОП
21. Microsoft Teams
22. Отчеты администратора / Отчеты об использовании
23. Word Online, Excel Online, PowerPoint, OneNote и Visio Online
24. Планировщик
25. Sway
26. Office 365 профессиональный плюс
27. Outlook Mobile
28. EMS E3 (Azure Active Directory Premium P1 + Intune + Служба управления правами)
29. Yammer Online

### <a name="when-will-migration-happen"></a>Когда произойдет миграция?

#### <a name="azure"></a>Azure 

Вы можете начать [миграцию](https://docs.microsoft.com/azure/germany/germany-migration-main) своих ресурсов Azure в другой регион уже сегодня. При наличии Azure с Office 365, Dynamics 365 и/или Power BI выполните указанные ниже действия.

#### <a name="office-365"></a>Office 365

[Согласие](https://aka.ms/office365germanymoveoptin) на миграцию под руководством корпорации Майкрософт сегодня. Когда вы будете готовы начать миграцию, то в центре администрирования Microsoft 365 мы проинформируем вас с помощью [Центра сообщений](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide).

#### <a name="dynamics-365-and-power-bi"></a>Dynamics 365 и Power BI

Присоединяйтесь к миграции под руководством корпорации Майкрософт для [Dynamics 365](https://aka.ms/D365ceOptIn) и [Power BI сегодня](https://aka.ms/PBIOptIn). Когда вы будете готовы начать миграцию, то в центре администрирования Microsoft 365 мы проинформируем вас с помощью [Центра сообщений](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide).

### <a name="will-the-price-change-for-the-office-services-that-i-use"></a>Будут ли изменяться цены для используемых мною служб Office?

Да, цены в глобальном облаке Майкрософт (в том числе в новых регионах центров обработки данных), как правило, меньше.

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Как получить помощь от корпорации Майкрософт, чтобы перейти на новый регион или ответить на вопросы о поддержке?

При наличии вопросов вы можете связаться с нами, выполнив указанные ниже действия, или через нашего партнера.

- В Azure можно отправлять [новые запросы в службу поддержки](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) на портале Azure.
- В Office 365 вы можете отправлять вопросы с помощью опции "Нужна помощь?". ссылка [Центра администрирования Microsoft 365](https://portal.office.de/).
- Для клиентов Dynamics 365 Customer Engagement и Power BI, у которых также есть Office 365, вы можете отправлять вопросы с помощью опции "Нужна помощь?". ссылка [Центра администрирования Microsoft 365](https://portal.office.de/). Варианты поддержки клиентов Dynamics 365 Customer Engagement доступны [здесь](https://docs.microsoft.com/dynamics365/get-started/support/). Варианты поддержки клиентов Power BI доступны [здесь](https://powerbi.microsoft.com/support/).

## <a name="more-information"></a>Дополнительные сведения

- [Помощь по миграции Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Как принять участие в миграции](https://aka.ms/office365germanymoveoptin)
- [Сведения о программе миграции Dynamics 365](https://aka.ms/d365ceoptin)
- [Сведения о программе миграции Power BI](https://aka.ms/pbioptin)
- [URL-адреса и диапазоны IP-адресов для Office 365](https://aka.ms/o365endpoints)
- [Мастер гибридной конфигурации Office 365](https://aka.ms/HybridWizard)
- [Начало перехода на Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
