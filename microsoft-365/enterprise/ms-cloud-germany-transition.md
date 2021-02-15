---
title: Миграция из Microsoft Cloud Deutschland в службы Office 365 в новых регионах центра обработки данных в Германии
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
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
ms.openlocfilehash: d807637e9d5469131d3124d1ef8b6b1f874e81a1
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145419"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Миграция из Microsoft Cloud Deutschland в службы Office 365 в новых регионах центра обработки данных в Германии

> [!NOTE]
> Эта статья относится только к подходящим клиентам Microsoft Cloud Deutschland.

В августе 2018 г. корпорация Майкрософт сообщила о своем намерении предоставить полное облако Майкрософт ( Azure, Office 365, Dynamics 365 и Power Platform) из новых облачных регионов в Германии, чтобы улучшить цифровые преобразования наших клиентов. В августе 2019 г. мы объявили о том, что находимся в процессе открытия новых облачных регионов в Германии. С тех пор мы объявили о доступности Azure, Office 365, Dynamics 365 и Power Platform.

Новые регионы предназначены для более гибкого решения меняющихся потребностей немецких клиентов, новейших интеллектуальных облачных служб и полного подключения к нашей облачной сети служб Microsoft 365, а также для хранения данных клиентов в Германии.

## <a name="how-to-migrate-to-the-new-german-datacenter-regions"></a>Как перейти на новые регионы центра обработки данных в Германии

Существующие клиенты Microsoft Cloud Deutschland теперь могут начать перенос своих клиентов Office 365, Dynamics 365 Customer Engagement и Power Platform. Первым шагом является [согласие на миграцию под руководством корпорации Майкрософт](https://aka.ms/office365germanymoveoptin) в наши новые регионы центров обработки данных в Германии.

Для организаций, которые решили использовать подход, управляемый Корпорацией Майкрософт, миграция должна начаться в начале 2021 г. и завершиться до 29 октября 2021 г. В результате миграции основные данные клиента и подписки перемещаются в новые регионы в Германии.

В этой статье представлен обзор подхода, выполняемого корпорацией Майкрософт для миграции, четкость интерфейса для пользователей и администраторов во время и после миграции, а также действия, которые могут потребоваться клиентам на основе рабочих нагрузок, которые вы используете.

Указанные ниже службы будут перенесены в рамках программы под руководством корпорации Майкрософт:

- Azure Active Directory (Azure AD)
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive для бизнеса

- Skype для бизнеса Online\*\*
- Группы Office 365
- Dynamics 365 / Power Platform\*\*\*

\*\*Во время миграции из Microsoft Cloud Deutschland в регионы центра обработки данных в Германии существующие клиенты Skype для бизнеса Online переходят на Microsoft Teams. Дополнительные сведения см. в статье [Начало перехода на Microsoft Teams](https://aka.ms/SkypeToTeams-Home).

\*\*\*Необходимые условия и влияние миграции для этих служб описаны в статье [Dynamics 365 Customer engagement.](https://aka.ms/d365ceoptin)

1 марта 2021 г. прекращается поддержка Office 365 Видео. Если вы решили перенести свой клиент Office 365 в новые регионы центров обработки данных в Германии, Office 365 Видео не будет поддерживаться после завершения миграции SharePoint Online. Дополнительные сведения см. на [временной шкале Microsoft Cloud Deutschland.](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="how-is-the-migration-organized"></a>Как организована миграция?

На этом рисунке показаны девять этапов миграции в новые немецкие центр обработки данных.

![Девять этапов миграции в новые центр обработки данных в Германии](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Эти этапы начинаются [при отказе от миграции.](https://aka.ms/office365germanymoveoptin) Большинство этапов миграции выполняются как операции с обслуживанием во тыловом режиме с минимальным взаимодействием с клиентом и выполняются один этап за другим. Начало выполнения дополнительных задач под руководством клиента и общее состояние миграции будут сообщаться через Центр сообщений Центра администрирования Microsoft 365 во время процесса миграции. Пример задач может включать управляемые клиентом обновления DNS, перенастройку гибридной настройки для гибридных клиентов Exchange или миграцию Azure.

Миграция не сразу начинается при отказе. Организация добавлена в список клиентов, которые запланированы на более поздней миграции. Вы можете начать предварительные этапы, так как они критически важны для успешной миграции и использования после завершения:

- [Действия и влияние этапов миграции](ms-cloud-germany-transition-phases.md)
- [Дополнительная предварительная работа](ms-cloud-germany-transition-add-pre-work.md)

За неделю до начала миграции клиента вы получите уведомление в службе Центра сообщений в качестве окончательного предупреждения о том, что все необходимые условия должны быть завершены.

Миграция переместит клиент Azure AD из независимой службы Azure AD в Германии в экземпляр служб Office 365 Azure AD в регионе ЕС.

Следующий этап — миграция подписок&#39;и пользовательских лицензий из продуктов для Германии в глобальные продукты.

После выполнения всех действий, включая миграцию Клиента Azure, клиент будет завершен в службе служб Office 365, а миграция будет помечена как завершенная. На этом этапе вам предоставляется окончательное обновление центра сообщений. Клиент теперь является полностью глобальной организацией Office 365.

Вы будете уведомлены о ходе миграции с помощью записей Центра сообщений. Публикации будут происходить на определенных вехах и будут предоставлять рекомендации по ходу выполнения шага, а также важные сведения для клиентов, которые будут действовать на основе требований процесса. Уведомления центра сообщений предоставляются в следующих вехах:

- Начало миграции (за 5 дней до начала миграции Azure AD)
- Миграция Azure AD завершена
- Миграция с подпиской и лицензией завершена
- Миграция SharePoint завершена
- Миграция Exchange завершена
- Skype для бизнеса завершен
- Dynamics complete
- Power BI завершена
- Завершаемая переключеть службы завершена

## <a name="moving-to-the-new-german-datacenter-regions"></a>Переход на новые регионы центра обработки данных в Германии

Существующие клиенты Microsoft Cloud Deutschland теперь могут начать перенос своих служб Office 365, Dynamics 365 Customer Engagement и Power Platform. Первым шагом является [согласие на миграцию под руководством корпорации Майкрософт](https://aka.ms/office365germanymoveoptin) в наши новые регионы центров обработки данных в Германии. При продлении подписки вы автоматически подписались на миграцию с помощью Майкрософт. Корпорация Майкрософт уведомит администраторов клиентов по электронной почте и в Центре сообщений Центра администрирования Microsoft 365. Тем не менее, если вы хотите [](https://aka.ms/office365germanymoveoptin) начать процесс сейчас, вы можете сделать это непосредственно в Центре администрирования Microsoft 365. Миграция должна начаться в начале 2021 г. и завершится 29 октября 2021 г. 

В результате миграции основные данные клиентов и подписки перемещаются в новые регионы центра обработки данных в Германии.

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Как подготовиться к миграции на службы Office 365 в новых регионах центров обработки данных в Германии

Сначала необходимо уведомить корпорацию Майкрософт, чтобы у нас было разрешение на перенос вашей подписки и данных из Microsoft Cloud Deutschland в службы Office 365 в новых регионах центра обработки данных в Германии. Чтобы получить [инструкции, обратитесь](https://aka.ms/office365germanymoveoptin) к процедуре отказа и обратите внимание на то, что:

- Всем клиентам, которые переносят данные, необходимо проверить подключение к URL-адресам и IP-адресам Office 365 для служб [Office 365,](urls-and-ip-address-ranges.md)включая новые регионы центра обработки данных в Германии. Бездействие может привести к сбою службы и клиента.
- Просмотрите список [предварительных действий,](ms-cloud-germany-transition-add-pre-work.md) чтобы убедиться, что ваша организация в курсе изменений и подготовлена к изменениям.
- Просмотрите описание служб платформы Office 365, чтобы понять, какие функции и службы станут доступны вашей организации после миграции в немецкий регион.
- Пробные подписки не будут перенесены и будут блокировать миграцию всех платных подписок. Перед началом миграции необходимо отменить все пробные подписки или преобразовать их в платные подписки.

## <a name="where-do-i-go-from-here"></a>Куда я могу перейти?

Просмотрите следующий раздел "Вопросы и ответы".

## <a name="frequently-asked-questions"></a>Вопросы и ответы

### <a name="is-migration-required"></a>Требуется ли миграция?

Корпорация Майкрософт предлагает миграцию клиента Office 365 из Microsoft Cloud Deutschland в службы Office 365 в новых регионах центра обработки данных в Германии без дополнительной платы. Хотя мы настоятельно рекомендуем вам отказаться от миграции в новые регионы центра обработки данных в Германии, мы по-прежнему будем предоставлять необходимые обновления для системы безопасности в регионе Microsoft Cloud Deutschland.

Службы Office 365 в новых регионах центра обработки данных в Германии:

- Предложение конкурентоспособной рыночной цены для [Azure](https://azure.microsoft.com/pricing/calculator/), [Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), [Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/) и [Power BI](https://powerbi.microsoft.com/pricing/).
- Подключены к глобальной сети Microsoft&#39;, предлагая сотни сетевых сайтов, местоположений пиринга и точек выпада для обеспечения надежного пользовательского интерфейса в любой точке мира.
- Помогают вам соответствовать местным требованиям о размещении данных в пределах Германии.
- Предоставление полного глобального облачного предложения с новейшими версиями наших служб и новыми возможностями, включая Microsoft Teams и поддержку нескольких географических функций в Office 365. Сравните продукты по регионам для [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), [Office 365](o365-data-locations.md)и [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).
- Предлагают полный набор функций, обеспечение безопасности корпоративного уровня и широкие возможности, которые помогают клиентам удовлетворить нормативные требования.
- Доступны через существующие контракты веб-служб.

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>Какова доступность службы между различными предложениями облачных служб Office 365?
<h2 id="serv-avail"></h2>

В облачной службе Microsoft Cloud Deutschland доступны следующие 15 служб. Мы не добавляем новые службы в Microsoft Cloud Deutschland.

1. Exchange Online
2. Защищенное хранилище для пользователей (Exchange Online)
3. Группы (современные группы)
4. Профиль Delve
5. Exchange Online Protection
6. Defender для Office 365
7. Advanced eDiscovery
8. Расширенное управление данными
9. SharePoint Online
10. Защищенное хранилище для пользователей (SharePoint Online)
11. OneDrive для бизнеса
12. Skype для бизнеса Online
13. Word Online, Excel Online, PowerPoint, OneNote, Visio Online
14. Office 365 профессиональный плюс
15. Outlook Mobile

В настоящее время в составе служб Office 365 в новых регионах центра обработки данных в Германии доступно 39 служб. Новые функции и службы будут доступны в рамках глобальных служб Office 365 на постоянной основе.

1. Exchange Online
2. Клиентский lockbox для Exchange Online
3. Группы Microsoft 365
4. Профиль Delve
5. MyAnalytics
6. Рабочая аналитика
7. Exchange Online Protection
8. Defender для Office 365
9. Advanced eDiscovery
10. Расширенное управление безопасностью
11. Защита информации в Office 365 
12. Расширенное управление данными
13. SharePoint Online
14. Lockbox клиента для SharePoint Online
15. OneDrive для бизнеса
16. Microsoft Stream
17. Skype для бизнеса (будет перенесен в Microsoft Teams во время миграции)
18. Облачная УАТС
19. Конференц-связь через ТСОП
20. Вызовы ТСОП
21. Microsoft Teams
22. Отчеты администратора / Отчеты об использовании
23. Office в Интернете
24. Планировщик
25. Sway
26. Приложения Microsoft 365
27. Outlook Mobile
28. Enterprise Mobility + Security (EMS) E3 (Azure AD Premium P1, Intune и служба управления правами)
29. Yammer корпоративный
30. Microsoft Forms
31. Power Automate для Office 365
32. Виртуальные агенты Power Для Office 365
33. PowerApps для Office 365
34. Microsoft Bookings
35. To-Do
36. Доска
37. Microsoft StuffHub
38. Microsoft Kaizala Pro
39. Списки

### <a name="when-will-migration-happen"></a>Когда произойдет миграция?

**Azure**

Если вы только клиент Azure, [](https://docs.microsoft.com/azure/germany/germany-migration-main) вы можете начать перенос ресурсов Azure в другой регион уже сегодня. 

Если у вас есть Azure с Office 365, Dynamics 365 или Power BI, необходимо следовать процессу миграции, чтобы обеспечить успешную миграцию AzureAD перед началом самостоятельной миграции Azure. Необходимо завершить миграцию Azure до закрытия службы, чтобы поддерживать рабочие нагрузки Azure с azureAD и организацией Office 365.

**Office 365**

[Согласие](https://aka.ms/office365germanymoveoptin) на миграцию под руководством корпорации Майкрософт сегодня. Когда мы будем готовы начать миграцию, мы проинформим вас через Центр сообщений в Центре администрирования Microsoft 365.

**Dynamics 365 и Power BI**

Сегодня вы можете отказаться от миграции [dynamics 365 Customer Engagement](https://aka.ms/D365ceOptIn) и [Power BI](https://aka.ms/PBIOptIn) под управлением Майкрософт. Когда вы будете готовы начать миграцию, то в центре администрирования Microsoft 365 мы проинформируем вас с помощью Центра сообщений.

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>Изменится ли цена на службы Office 365, которые я использую?

Да. Цены в Microsoft&#39;глобальных облачных регионах (включая новые регионы центра обработки данных), как правило, ниже.

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>Какие номера номеров безопасности и лицензии будут применены к моей организации и пользователям во время миграции подписки?

Во время миграции из Microsoft Cloud Deutschland в службы Office 365 SKU для определенных служб в Германии заменяются глобальными версиями того же или аналогичного SKU. В большинстве случаев SKU в службах Office 365 один и тот же, но в службах Office 365 теперь мало замен, в которых SKU в Германии больше не доступен. Если вы хотите обновить SKU, назначенное вашей организации после завершения миграции, обратитесь к продавцу, чтобы добавить или изменить назначенную службу.

| Microsoft Cloud Deutschland — SKU продукта (DE) | Microsoft Cloud Global — SKU продукта (WW) |
| --- | --- |
| Customer Lockbox \_ DE (LOCKBOX \_ DE) | Lockbox (LOCKBOX) |
| Dynamics 365 Enterprise Edition — дополнительное хранилище базы данных \_ DE (CRMSTORAGE \_ DE) | Dynamics 365 Enterprise Edition — дополнительное хранилище базы данных (CRMSTORAGE) |
| Dynamics 365 Enterprise Edition — дополнительный непроизводивый экземпляр \_ DE (CRMTESTINSTANCE \_ DE) | Dynamics 365 Enterprise Edition — дополнительный непроизводский экземпляр (CRMTESTINSTANCE) |
| Dynamics 365 for Customer Service Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ CUSTOMER \_ SERVICE \_ DE) | Dynamics 365 for Customer Service Enterprise Edition (DYN365 \_ ENTERPRISE \_ CUSTOMER \_ SERVICE) |
| Dynamics 365 for Sales Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ SALES \_ DE) | Dynamics 365 for Sales Enterprise Edition (DYN365 \_ ENTERPRISE \_ SALES) |
| Dynamics 365 for Team Members Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ TEAM \_ MEMBERS \_ DE) | Dynamics 365 for Team Members Enterprise Edition (DYN365 \_ ENTERPRISE \_ TEAM \_ MEMBERS) |
| Dynamics 365 Plan 1 Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ PLAN1 \_ DE) | Dynamics 365 Plan 1 Enterprise Edition (DYN365 \_ ENTERPRISE \_ PLAN1) |
| ECAL Services (EOA, EOP, DLP) \_ DE (ECAL \_ SERVICES \_ DE) | ECAL Services (EOA, EOP, DLP) (ECAL \_ SERVICES) |
| Enterprise Mobility + Security E3 \_ DE (EMS \_ DE) | Enterprise Mobility + Security E3 (EMS) |
| Exchange Online (план 1) \_ DE (EXCHANGESTANDARD \_ DE) | Exchange Online (план 1) (EXCHANGESTANDARD) |
| Exchange Online (план 2) \_ DE (EXCHANGEENTERPRISE \_ DE) | Exchange Online (план 2) (EXCHANGEENTERPRISE) |
| архивация на базе Exchange Online exchange Online \_ DE (EXCHANGEARCHIVE \_ ADDON \_ DE) | архивация на базе Exchange Online exchange Online (EXCHANGEARCHIVE \_ ADDON) |
| архивация на базе Exchange Online для Exchange Server \_ DE (EXCHANGEARCHIVE \_ DE) | архивация на базе Exchange Online для Exchange Server (EXCHANGEARCHIVE) |
| Exchange Online Essentials \_ DE (EXCHANGE \_ S \_ ESSENTIALS \_ DE) | Exchange Online Essentials (EXCHANGE \_ S \_ ESSENTIALS) |
| базовая подписка на Exchange Online DE \_ (EXCHANGEDESKLESS \_ DE) | базовая подписка на Exchange Online (EXCHANGEDESKLESS) |
| Exchange Online Protection \_ DE (EOP \_ ENTERPRISE \_ DE) | Exchange Online Protection (EOP \_ ENTERPRISE) |
| Microsoft 365 бизнес стандарт (O365 \_ БИЗНЕС \_ ПРЕМИУМ) | Microsoft 365 бизнес стандарт (O365 \_ БИЗНЕС \_ ПРЕМИУМ) |
| Microsoft Dynamics CRM Online Instance \_ DE (CRMINSTANCE \_ DE) | Microsoft Dynamics CRM Online (CRMINSTANCE) |
| Office 365 A1 для преподавателей \_ DE (STANDARDWOFFPACK \_ FACULTY \_ DE) | Office 365 A1 для преподавателей (ПРЕПОДАВАТЕЛЬСКИЙ СОСТАВ STANDARDWOFFPACK) \_ |
| Office 365 A1 для учащихся \_ DE (STANDARDWOFFPACK \_ STUDENT \_ DE) | Office 365 A1 для учащихся (STANDARDWOFFPACK \_ STUDENT) |
| Office 365 Advanced Compliance \_ DE (EQUIVIO \_ ANALYTICS \_ DE) | Соответствие Требованиям Microsoft 365 E5 (СООТВЕТСТВИЕ \_ \_ ТРЕБОВАНИЯМ INFORMATION PROTECTION) |
|Microsoft Defender для Office 365 (план 1) \_ DE (ATP \_ ENTERPRISE \_ DE) |Microsoft Defender для Office 365 (план 1) (ATP \_ ENTERPRISE) |
| Office 365 бизнес essentials \_ DE (O365 \_ БИЗНЕС \_ ESSENTIALS \_ DE) | Microsoft 365 бизнес базовый (O365 \_ БИЗНЕС \_ БАЗОВЫЙ) |
| Office 365 бизнес премиум \_ DE (O365 \_ БИЗНЕС ПРЕМИУМ \_ \_ DE) | Microsoft 365 бизнес стандарт (O365 \_ БИЗНЕС \_ ПРЕМИУМ) |
| Office 365 бизнес \_ DE (O365 \_ BUSINESS \_ DE) | Приложения Microsoft 365 для бизнеса (O365 \_ БИЗНЕС) |
| Office 365 E1 \_ DE (STANDARDPACK \_ DE) | Office 365 E1 (STANDARDPACK) |
| Office 365 E3 без ProPlus \_ DE (ENTERPRISEPACKWITHOUTPROPLUS \_ DE) | Office 365 E3 без профессиональныйplus (ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 корпоративный E1 \_ DE (STANDARDPACK \_ DE) | Office 365 корпоративный E1 (STANDARDPACK) |
| Office 365 корпоративный E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 корпоративный E3 (ENTERPRISEPACK) |
| Office 365 Extra File Storage \_ DE (SHAREPOINTSTORAGE \_ DE) | Дополнительное хранилище файлов Office 365 (SHAREPOINTSTORAGE) |
| Office 365 F1 \_ DE (DESKLESSPACK \_ DE) | Office 365 F1 (DESKLESSPACK) |
| Office 365 профессиональныйplus для преподавателей \_ DE (OFFICESUBSCRIPTION \_ FACULTY \_ DE) | Office 365 профессиональныйplus для преподавателей (OFFICESUBSCRIPTION \_ FACULTY) |
| Office 365 профессиональныйplus для учащихся \_ DE (OFFICESUBSCRIPTION \_ STUDENT \_ DE) | Office 365 профессиональныйplus для учащихся (OFFICESUBSCRIPTION \_ STUDENT) |
| Office 365 профессиональныйplus \_ DE (OFFICESUBSCRIPTION \_ DE) | Office 365 профессиональныйplus (OFFICESUBSCRIPTION) |
| OneDrive для бизнеса (план 1) \_ DE (WACONEDRIVESTANDARD \_ DE) | OneDrive для бизнеса (план 1) (WACONEDRIVESTANDARD) |
| OneDrive для бизнеса (план 2) \_ DE (WACONEDRIVEENTERPRISE \_ DE) | OneDrive для бизнеса (план 2) (WACONEDRIVEENTERPRISE) |
| Power BI Pro для преподавателей \_ DE (POWER \_ BI PRO \_ \_ FACULTY \_ DE) | Power BI Pro для преподавателей (ПРЕПОДАВАТЕЛЬСКИЙ СОСТАВ POWER \_ BI \_ \_ PRO) |
| Power BI Pro \_ DE (POWER \_ BI \_ PRO \_ DE) | Power BI Pro (POWER \_ BI \_ PRO) |
| Project Online Essentials \_ DE (PROJECTESSENTIALS \_ DE) | Project Online Essentials (PROJECTESSENTIALS) |
| Project Online Premium \_ DE (PROJECTPREMIUM \_ DE) | Project Online premium (PROJECTPREMIUM) |
| Project Online \_ профессиональный DE (PROJECTPROFESSIONAL \_ DE) | Project Online профессиональный (PROJECTPROFESSIONAL) |
| Project Plan 3 \_ DE (PROJECTPROFESSIONAL \_ DE) | План 3 (PROJECTPROFESSIONAL) |
| Office 365 E4 \_ DE (ENTERPRISEWITHSCAL \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| SharePoint Online (план 1) \_ DE (SHAREPOINTSTANDARD \_ DE) | SharePoint Online (план 1) (SHAREPOINTSTANDARD) |
| SharePoint Online (план 2) \_ DE (SHAREPOINTENTERPRISE \_ DE) | SharePoint Online (план 2) (SHAREPOINTENTERPRISE) |
| Skype для бизнеса Online (план 1) \_ DE (MCOIMP \_ DE) | Office 365 E1 (STANDARDPACK) |
| Skype для бизнеса Online (план 1) \_ DE (MCOIMP \_ DE) | Skype для бизнеса Online (план 1) (MCOIMP) |
| Skype для бизнеса Online (план 2) \_ DE (MCOSTANDARD \_ DE) | Skype для бизнеса Online (план 2) (MCOSTANDARD) |
| Skype для бизнеса Plus CAL \_ DE (MCOPLUSCAL \_ DE) | Skype для бизнеса Plus CAL (MCOPLUSCAL) |
| Visio Online (план 1) для преподавателей \_ DE (VISIOONLINE \_ PLAN1 \_ FAC \_ DE) | Visio Online (план 1) для преподавателей (VISIOONLINE \_ PLAN1 \_ FAC) |
| Visio Online (план 1 \_ DE) (VISIOONLINE \_ PLAN1 \_ DE) | Visio Online (план 1) (VISIOONLINE \_ PLAN1) |
| Visio Online (план 2) для преподавателей \_ DE (VISIOCLIENT \_ FACULTY \_ DE) | Visio Online (план 2) для преподавателей (VISIOCLIENT \_ FACULTY) |
| Visio Online (план 2 \_ DE) (VISIOCLIENT \_ DE) | Visio Online (план 2) (VISIOCLIENT) |
| Visio (план 1 \_ DE) (VISIOONLINE \_ PLAN1 \_ DE) | Visio (план 1) (VISIOONLINE \_ PLAN1) |
| Visio (план 2 \_ DE) (VISIOCLIENT \_ DE) | Visio (план 2) (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Как получить помощь от корпорации Майкрософт, чтобы перейти на новый регион или ответить на вопросы о поддержке?

Если у вас возникли вопросы, вы можете связаться с нами или вашим партнером:

- В Azure можно отправлять [новые запросы в службу поддержки](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) на портале Azure.
- Для Office 365 вы можете отправлять вопросы, используя ссылку "Нужна помощь"? В Центре администрирования &quot; &quot; Microsoft [365.](https://portal.office.de/)
- Если вы клиент Dynamics 365 Customer Engagement и Power BI, а также у вас есть Office 365, вы можете отправлять вопросы по ссылке "Нужна помощь" в Центре администрирования &quot; &quot; Microsoft [365.](https://portal.office.de/) Варианты поддержки клиентов Dynamics 365 Customer Engagement доступны [здесь](https://docs.microsoft.com/dynamics365/get-started/support/). Варианты поддержки клиентов Power BI доступны [здесь](https://powerbi.microsoft.com/support/).

### <a name="my-customer-already-has-a-m365-tenant-in-the-global-microsoft-cloud-in-addition-to-a-microsoft-cloud-deutschland-tenant-can-these-two-tenants-be-merged-into-one-as-part-of-the-migration"></a>У моего клиента уже есть клиент M365 в глобальном облаке Майкрософт в дополнение к клиенту Microsoft Cloud Deutschland. Можно ли объединить эти два клиента в один в рамках миграции?

Нет, нет возможности объединения клиента. Клиенты останутся отдельными и уникальными, так как у каждого клиента есть собственное пространство имен и уникальный ИД. Корпорация Майкрософт при желании переносит клиент Microsoft Cloud Deutschland в глобальное облако, иначе клиент может отменить и отменить его.


### <a name="what-actions-are-required-to-be-done-by-most-end-users-as-part-of-the-migration"></a>Какие действия должны быть сделаны большинством конечных пользователей в рамках миграции?
Миграция предназначена для минимального воздействия на конечных пользователей и клиентов.
- Убедитесь, что приложения Office работают под управлением последних доступных версий. 
- Клиенты, использующие Skype для бизнеса, переходят на Teams в рамках миграции, и им может потребоваться скачать и [установить Teams](https://docs.microsoft.com/deployoffice/teams-install) на устройствах.
- Конечным пользователям может потребоваться выйти из приложений Office и войти обратно после завершения миграции. 
- Клиенты, работающие с клиентом синхронизации OneDrive, должны выйти из рабочей станции и снова войти в систему, чтобы разрешить клиенту синхронизации OneDrive войти в глобальную службу Azure Active Directory.
- Обратите внимание на новые глобальные URL-адреса после завершения миграции, в частности Outlook Web Access (пример: использование outlook.office365.com). Клиенты SharePoint Online продолжат успешно подключаться к пространству имен MCD с помощью существующего URL-адреса (пример: contoso.sharepoint.de).


### <a name="which-customers-are-affected-by-the-azure-active-directory-migration"></a>На каких клиентов влияет миграция Azure Active Directory? 

Все клиенты Office365 зависят от Azure Active Directory для проверки подлинности и хранения критически важных компонентов служб, необходимых для работы служб, хранимых в Майкрософт. 


### <a name="what-are-the-impacts-of-the-azure-active-directory-migration"></a>Каковы последствия миграции Azure Active Directory?

Начальная миграция Azure Active Directory на ранней стадии не оказывает влияния на впечатления клиентов. После заключительного этапа миграции все службы клиента полностью находятся в глобальной службе. На этом заключительном этапе служба Azure Active Directory в Microsoft Cloud Deutschland больше не может принимать запросы авторизации или предоставлять маркеры доступа службам Office.


### <a name="what-does-it-mean-to-ensure-network-connectivity-to-office-365-services-urls-and-ip-addresses"></a>Что означает обеспечение сетевого подключения к URL-адресам и IP-адресам служб [Office 365?](https://aka.ms/o365urls)

В этой статье описываются НЕОБХОДИМЫе URL-адреса и IP-адреса, необходимые для правильной работы глобальной службы, чтобы обеспечить хорошее качество обслуживания клиентов. В сравнительно редких случаях некоторые клиенты пытаются настроить безопасность периметра сети таким образом, чтобы свести к минимуму потоки трафика и ограничить доступ к службам только в составе диапазонов IP-адресов службы Microsoft Cloud Deutschland.


### <a name="how-do-i-manage-the-dns-changes-for-exchange-online-so-mail-will-continue-to-flow"></a>Как управлять изменениями DNS для Exchange Online, чтобы поток почты продолжает поступать?

Управляемые Корпорацией Майкрософт диапазоны IP-адресов и зоны DNS переносятся во время и в рамках миграции в глобальную службу. 

Тем не менее, клиент отвечает за управляемые клиентом зоны DNS, такие как записи MX пользовательского домена, чтобы упростить эту миграцию, в записи MX, управляемой клиентом, указывает на конечную точку службы Office 365 в зоне office.de, и Майкрософт автоматически управляет миграцией этой конечной точки службы.


### <a name="how-do-i-manage-the-dns-changes-for-skype-for-business"></a>Как управлять изменениями DNS для Skype для бизнеса? 
 
Все пользователи Skype для бизнеса будут перенаться в Microsoft Teams. Перенос зон DNS Skype для клиента не требуется при переходе на Teams. Клиенты смогут сразу же войти в Teams со всеми функциями после миграции.
 

### <a name="will-outlook-for-ios-and-android-work-after-the-migration"></a>Будет ли работать Outlook для iOS и Android после миграции? 

Да. Корпорация Майкрософт : все клиенты запускают последние доступные версии клиентов Office, включая outlook для iOS и Android. После завершения миграции на глобальную службу Office 365 все клиенты Office должны выйти и войти в систему, чтобы получить новый маркер доступа Azure Active Directory от глобальной службы. 



## <a name="next-step"></a>Следующий этап

[Согласие на миграцию](ms-cloud-germany-migration-opt-in.md)

## <a name="more-information"></a>Дополнительные сведения

Начало работы:

- [Помощь по миграции Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Как принять участие в миграции](ms-cloud-germany-migration-opt-in.md)
- [Опыт работы с клиентами во время миграции](ms-cloud-germany-transition-experience.md)

Переход:

- [Действия и влияние этапов миграции](ms-cloud-germany-transition-phases.md)
- [Дополнительная предварительная работа](ms-cloud-germany-transition-add-pre-work.md)
- Дополнительные сведения [для Azure AD,](ms-cloud-germany-transition-azure-ad.md) [устройств,](ms-cloud-germany-transition-add-devices.md) [функций](ms-cloud-germany-transition-add-experience.md)и [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Облачные приложения:

- [Сведения о программе миграции Dynamics 365](https://aka.ms/d365ceoptin)
- [Сведения о программе миграции Power BI](https://aka.ms/pbioptin)
- [Начало перехода на Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
