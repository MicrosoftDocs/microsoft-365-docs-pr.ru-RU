---
title: Миграция из Microsoft Cloud записей в службы Office 365 в новых регионах центра обработки данных на немецком языке
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
ms.openlocfilehash: 37bf052739bf15c1a0d3712539779e9dff31d9e8
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551538"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Миграция из Microsoft Cloud записей в службы Office 365 в новых регионах центра обработки данных на немецком языке

> [!NOTE]
> Эта статья относится только к подходящим пользователям Microsoft Cloud записей.

В августе 2018 Корпорация Майкрософт объявила о нашей намеренности доставить полную платформу Microsoft Cloud — Azure, Office 365, Dynamics 365 и Power, из новых облачных регионов в Германии, чтобы лучше было использовать цифровое преобразование наших клиентов. В августе 2019 г. мы объявили о том, что находимся в процессе открытия новых облачных регионов в Германии. После этого мы объявили о доступности Azure, Office 365, Dynamics 365 и платформы управления питанием.

Новые регионы предназначены для удовлетворения растущих потребностей немецких клиентов с более гибкими и новейшими интеллектуальными облачными службами, а также полным подключением к нашей облачной сети Microsoft 365 Services и размещению данных клиентов в Германии.

## <a name="how-to-migrate-to-the-new-german-regions"></a>Как перейти к новым регионам на немецком языке

Теперь существующие пользователи Microsoft Cloud записей могут начать переносить свои клиенты Office 365, Dynamics 365 и клиенты Power Platform. Первым шагом является [согласие на миграцию под руководством корпорации Майкрософт](https://aka.ms/office365germanymoveoptin) в наши новые регионы центров обработки данных в Германии.

Для организаций, которые хотят использовать подход, основанный на корпорации Майкрософт, предполагается, что миграция начинается на ранних 2021 и завершается 29 октября 2021 г. В результате миграции основные данные клиента и подписки перемещаются в новые регионы в Германии.

В этой статье представлен обзор ориентированного на Майкрософт подхода к миграции, ясности в работе как для пользователей, так и для администраторов во время и после миграции, а также для пользователей, использующих используемые рабочие нагрузки.

Указанные ниже службы будут перенесены в рамках программы под руководством корпорации Майкрософт:

- Azure Active Directory (Azure AD)
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive для бизнеса

- Skype для бизнеса Online\*\*
- Группы Office 365
- Dynamics 365/Power Platform\*\*\*

\*\*Во время миграции с Microsoft Cloud записей в регионы с немецкими центрами обработки данных, пользователи Skype для бизнеса Online будут переходить на Microsoft Teams. Дополнительные сведения см. в статье [Начало перехода на Microsoft Teams](https://aka.ms/SkypeToTeams-Home).

\*\*\*Необходимые условия и влияние миграции для этих служб описаны в статье [Dynamics 365 "участие клиента](https://aka.ms/d365ceoptin) ".

1 марта 2021 г. прекращается поддержка Office 365 Видео. Если вы решили перенести свой клиент Office 365 в новые регионы центров обработки данных в Германии, Office 365 Видео не будет поддерживаться после завершения миграции SharePoint Online. Дополнительные сведения см. в разделе [временная шкала Microsoft Cloud записей](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline).

## <a name="how-is-the-migration-organized"></a>Как организуется миграция?

На этом рисунке представлены различные компоненты Office 365 и Dynamics 365 в переходе на новые центры обработки данных на немецком языке.

![Компоненты Office 365 и Dynamics 365 при переходе на новые центры обработки данных в Германии](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Миграция выполняется по этапам, которые запускаются при выборе [для миграции](https://aka.ms/office365germanymoveoptin). Большая часть этапов миграции выполняется как серверные операции с минимальным участием клиента и выполняются на один этап после другого. Начало дополнительных задач с индикатором клиента и общее состояние миграции будут передаваться через центр сообщений центра администрирования Microsoft 365 в процессе миграции. Например, задачи могут включать в себя обновления DNS, которые управляются клиентами, перенастройка гибридной настройки для гибридных клиентов Exchange или миграция Azure.

Миграция не начинается сразу же после получения согласия пользователя. Ваша организация будет добавлена в список клиентов, для которых запланирована дальнейшая миграция. Вы можете приступить к этапам предварительной работы, так как они критически важны для обеспечения успешной миграции и использования после завершения:

- [Действия и влияние этапов миграции](ms-cloud-germany-transition-phases.md)
- [Дополнительные предварительные действия](ms-cloud-germany-transition-add-pre-work.md)

За одну неделю до начала миграции клиента вы получите уведомление в службе центра сообщений как Последнее предупреждение о том, что все необходимые компоненты должны быть завершены.

Миграция будет перемещена с клиента Azure AD из службы публичном Германия Azure AD в экземпляр служб Office 365 служб Azure AD в регионе ЕС.

Следующий этап — миграция подписок на клиента&#39;s и пользовательских лицензий из продуктов, относящихся к Германии.

После выполнения всех действий, включая миграцию Azure для клиента, ваш клиент завершается в службе Office 365 Services, а миграция помечается как завершенная. На этом шаге для вас предоставляется Последнее обновление центра сообщений. Теперь клиент не является полностью глобальной организацией Office 365.

Вы получаете уведомление о ходе миграции с помощью сообщений центра сообщений. Записи будут выполняться на определенных вехах, и они появятся как ход выполнения этапа, а также важную информацию о том, как их выполнять в зависимости от требований к процессу. Уведомления центра сообщений предоставляются на следующих этапах:

- Начало миграции (5 рабочих дней до начала миграции Azure AD)
- Миграция Azure AD завершена
- Миграция подписок и лицензий завершена
- Миграция SharePoint завершена
- Миграция Exchange завершена
- Skype для бизнеса завершен
- Выполнение Dynamics
- Power BI завершен
- Завершенные прямой службы завершены

## <a name="moving-to-the-new-german-regions"></a>Переход на новые регионы в Германии

Существующие пользователи Microsoft Cloud Германии (Microsoft Cloud записей) теперь могут начать миграцию клиентов Office 365, Dynamics 365 и клиентов Power Platform. Первым шагом является [согласие на миграцию под руководством корпорации Майкрософт](https://aka.ms/office365germanymoveoptin) в наши новые регионы центров обработки данных в Германии. При продлении подписки вы автоматически отказываетесь от использования Майкрософт для миграции. Корпорация Майкрософт будет уведомлять администраторов клиентов о наличии электронной почты и центра сообщений центра администрирования Microsoft 365, когда это произошло. Тем не менее, если вы предпочитаете запустить процесс сейчас, вы можете [согласиться](https://aka.ms/office365germanymoveoptin) непосредственно в центре администрирования Microsoft 365. Предполагается, что миграция начинается на раннем этапе 2021 и завершается 29 октября 2021 г. 

В результате миграции основные данные клиента и подписки перемещаются в новые регионы в Германии.

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Как подготовиться к миграции на службы Office 365 в новых регионах центров обработки данных в Германии

Первый шаг — сообщить корпорации Майкрософт о том, что у вас есть ваше разрешение на перенос подписок и данных из Microsoft Cloud записей в службы Office 365 в новых регионах центра обработки данных на немецком языке. Ознакомьтесь с инструкциями и обратите внимание [на то,](https://aka.ms/office365germanymoveoptin) что:

- Для всех миграций клиентов необходимо проверить возможность подключения к [URL-адресам и IP-адресам office 365](urls-and-ip-address-ranges.md)для служб Office 365, в том числе новых регионов центров обработки данных на немецком языке. Действие может привести к сбою служб и клиентов.
- Просмотрите список [предварительных](ms-cloud-germany-transition-add-pre-work.md) действий, чтобы обеспечить информирование Организации об изменениях и подготовить их к работе.
- Ознакомьтесь с описанием службы платформы Office 365, чтобы узнать, какие функции и службы станут доступны вашей организации после миграции в регион для немецкого языка.
- Пробные подписки не будут перенесены и будут блокировать перенос всех платных подписок. Перед началом миграции необходимо отменить все пробные или преобразованные подписки в платные подписки.

## <a name="where-do-i-go-from-here"></a>Где можно переходить отсюда?

Ознакомьтесь со следующими разделами часто задаваемых вопросов.

## <a name="frequently-asked-questions"></a>Вопросы и ответы

### <a name="is-migration-required"></a>Требуется ли миграция?

Корпорация Майкрософт предоставляет дополнительные возможности по переносу клиентов Office 365 с Microsoft Cloud записей на службы Office 365 в новых регионах центра обработки данных на немецком языке. Несмотря на то, что мы настоятельно рекомендуем вам переходить на новые регионы для немецкого центра обработки данных, мы будем продолжать предоставлять необходимые обновления для системы безопасности в записей области Microsoft Cloud.

Службы Office 365 в новых регионах центра обработки данных на немецком языке:

- Предложение конкурентоспособной рыночной цены для [Azure](https://azure.microsoft.com/pricing/calculator/), [Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), [Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/) и [Power BI](https://powerbi.microsoft.com/pricing/).
- Подключены к глобальной сети Microsoft&#39;s, предоставляя сотни сетевых пограничных сайтов, расположения для пиринга и конечные точки для обеспечения надежного взаимодействия с пользователем в любом месте мира.
- Помогают вам соответствовать местным требованиям о размещении данных в пределах Германии.
- Поставьте полноценное глобальное облачное предложение с последними версиями наших служб и новыми возможностями, в том числе Microsoft Teams и поддержкой нескольких регионов в Office 365. Сравните продукты по регионам для [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), [Office 365](o365-data-locations.md)и [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).
- Предлагают полный набор функций, обеспечение безопасности корпоративного уровня и широкие возможности, которые помогают клиентам удовлетворить нормативные требования.
- Доступны через существующие контракты веб-служб.

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>Какова доступность службы между различными предложениями облачных служб Office 365?
<h2 id="serv-avail"></h2>

В облачной службе Microsoft Cloud записей доступны следующие 15 служб. Мы не добавляем новые службы в Microsoft Cloud записей.

1. Exchange Online
2. Защищенное хранилище для пользователей (Exchange Online)
3. Группы (современные группы)
4. Профиль Delve
5. Exchange Online Protection
6. Защитник для Office 365
7. Advanced eDiscovery
8. Расширенное управление данными
9. SharePoint Online
10. Защищенное хранилище для пользователей (SharePoint Online)
11. OneDrive для бизнеса
12. Skype для бизнеса Online
13. Word Online, Excel Online, PowerPoint, OneNote, Visio Online
14. Office 365 профессиональный плюс
15. Outlook Mobile

В настоящее время пакет служб Office 365 в новых регионах центров обработки данных в Германии включает 29 служб. Новые функции и службы будут доступны в рамках глобальных служб Office 365 на постоянной основе.

1. Exchange Online
2. Защищенный клиент для Exchange Online
3. Группы Microsoft 365
4. Профиль Delve
5. MyAnalytics
6. Рабочая аналитика
7. Exchange Online Protection
8. Защитник для Office 365
9. Advanced eDiscovery
10. Расширенное управление безопасностью
11. Управление правами на доступ к данным
12. Расширенное управление данными
13. SharePoint Online
14. Служба защищенного хранилища для SharePoint Online
15. OneDrive для бизнеса
16. Microsoft Stream
17. Skype для бизнеса (будет перенесен в Microsoft Teams во время миграции)
18. Облачная УАТС
19. Конференц-связь через ТСОП
20. Вызовы ТСОП
21. Microsoft Teams
22. Отчеты администратора / Отчеты об использовании
23. Word Online, Excel Online, PowerPoint, OneNote и Visio Online
24. Планировщик
25. Sway
26. Приложения Microsoft 365
27. Outlook Mobile
28. Enterprise Mobility + Security (EMS) E3 (Azure AD Premium P1, Intune и служба управления правами)
29. Yammer Online

### <a name="when-will-migration-happen"></a>Когда произойдет миграция?

**Azure**

Если вы только клиент Azure, вы можете приступить к [переносу](https://docs.microsoft.com/azure/germany/germany-migration-main) ресурсов Azure в другой регион. 

Если у вас есть Azure с Office 365, Dynamics 365 или Power BI, необходимо выполнить процесс миграции, чтобы обеспечить успешную миграцию AzureAD, прежде чем приступать к самонаправленной миграции Azure. Перед закрытием службы необходимо выполнить миграцию Azure, чтобы поддерживать рабочие нагрузки Azure с вашей AzureAD и организацией Office 365.

**Office 365**

[Согласие](https://aka.ms/office365germanymoveoptin) на миграцию под руководством корпорации Майкрософт сегодня. Когда все будет готово к началу миграции, мы поможем вам пройти через центр сообщений в центре администрирования Microsoft 365.

**Dynamics 365 и Power BI**

Предгласитесь на миграцию на основе Майкрософт для [участия в Dynamics 365 для клиентов Dynamics](https://aka.ms/D365ceOptIn) и [Power BI](https://aka.ms/PBIOptIn) . Когда вы будете готовы начать миграцию, то в центре администрирования Microsoft 365 мы проинформируем вас с помощью Центра сообщений.

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>Будет ли изменена Цена для служб Office 365, которые я использую?

Да. Цены в глобальных облачных областях Microsoft&#39;s (в том числе новые области центра обработки данных), как правило, меньше.

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>Какие SKU и лицензии будут применены при миграции подписки для Организации и пользователей?

Во время миграции из Microsoft Cloud записей в службы Office 365, зависящие от службы SKU, заменяются глобальными версиями одинаковых или похожих SKU. В большинстве случаев SKU в службах Office 365 одинаковы, но существует небольшое количество замен, когда SKU в Германии больше не доступны в службах Office 365. Если вы хотите обновить номер SKU, назначенный вашей организации после завершения миграции, обратитесь к продавцу, чтобы добавить или изменить назначенные службы.

| Microsoft Cloud записей — SKU продукта (DE) | Глобальная версия Microsoft Cloud — SKU продукта (WW) |
| --- | --- |
| Служба защищенного хранилища \_ (de \_ ) | Защищенное хранилище клиента (защищенное хранилище) |
| Dynamics 365 Enterprise Edition — дополнительное хранилище базы данных \_ de (крмстораже \_ de) | Dynamics 365 Enterprise Edition — дополнительное хранилище баз данных (КРМСТОРАЖЕ) |
| Dynamics 365 Enterprise Edition — дополнительный нерабочий экземпляр \_ de (крмтестинстанце \_ de) | Dynamics 365 Enterprise Edition — дополнительный экземпляр, не являющийся рабочим (КРМТЕСТИНСТАНЦЕ) |
| Dynamics 365 для обслуживания клиентов корпоративный выпуск Enterprise Edition \_ de (DYN365 \_ Enterprise \_ \_ Service \_ de) | Dynamics 365 для обслуживания клиентов Enterprise Edition ( \_ Корпоративная \_ Служба клиентов DYN365 \_ ) |
| Dynamics 365 для продажи Enterprise Edition \_ de (DYN365 \_ Enterprise \_ Sales \_ de) | Dynamics 365 для Sales Enterprise Edition (DYN365 \_ Enterprise \_ Sales) |
| Dynamics 365 для участников группы корпоративный выпуск — \_ de ( \_ DYN365 \_ Корпоративный \_ член группы \_ de) | Dynamics 365 для участников группы корпоративный выпуск Enterprise Edition (для \_ корпоративных \_ участников группы DYN365 \_ ) |
| Dynamics 365 Plan 1 Enterprise Edition \_ de (DYN365 \_ Enterprise \_ PLAN1 \_ de) | Dynamics 365 Plan 1 Enterprise Edition (DYN365 \_ Корпоративный \_ PLAN1) |
| Службы ECAL (EOA, EOP, DLP) \_ de ( \_ службы ECAL \_ de) | Службы ECAL (EOA, EOP, DLP) ( \_ службы ECAL) |
| Enterprise Mobility + Security E3 \_ de (EMS \_ de) | Enterprise Mobility + Security E3 (EMS) |
| Exchange Online (план 1) \_ de (ексчанжестандард \_ de) | Exchange Online (план 1) (ЕКСЧАНЖЕСТАНДАРД) |
| Exchange Online (план 2) \_ de (ексчанжеентерприсе \_ de) | Exchange Online (план 2) (ЕКСЧАНЖЕЕНТЕРПРИСЕ) |
| Архивация на базе Exchange Online для Exchange Online \_ de ( \_ надстройка ексчанжеарчиве \_ de) | Архивация на базе Exchange Online для Exchange Online ( \_ надстройка ексчанжеарчиве) |
| Архивация на базе Exchange Online для Exchange Server \_ de (ексчанжеарчиве \_ de) | Архивация на базе Exchange Online для Exchange Server (ЕКСЧАНЖЕАРЧИВЕ) |
| Exchange Online Essentials \_ de (Exchange \_ S \_ Essentials \_ de) | Exchange Online Essentials (основные сведения о EXCHANGE \_ S \_ ) |
| Exchange Online для киоска \_ (ексчанжедесклесс \_ de) | Exchange Online киоск (ЕКСЧАНЖЕДЕСКЛЕСС) |
| Exchange Online Protection \_ de (EOP \_ Enterprise \_ de) | Exchange Online Protection (EOP \_ Enterprise) |
| Microsoft 365 бизнес Standard (O365 \_ бизнес \_ премиум) | Microsoft 365 бизнес Standard (O365 \_ бизнес \_ премиум) |
| Экземпляр Microsoft Dynamics CRM Online \_ de (крминстанце \_ de) | Экземпляр Microsoft Dynamics CRM Online (КРМИНСТАНЦЕ) |
| Office 365 a1 для преподавателей \_ de (стандардвоффпакк \_ факультет \_ de) | Office 365 a1 для преподавателей ( \_ факультет стандардвоффпакк) |
| Office 365 a1 для учащихся \_ de (стандардвоффпакк \_ Student \_ de) | Office 365 a1 для учащихся (СТАНДАРДВОФФПАКК \_ Student) |
| Office 365 Advanced соответствие \_ "de" (EQUIVIO \_ Analytics \_ de) | Соответствие требованиям Microsoft 365 ( \_ соответствие требованиям к защите информации \_ ) |
|Защитник Майкрософт для Office 365 (план 1) \_ de (ATP \_ Enterprise \_ de) |Защитник Майкрософт для Office 365 (план 1) (ATP \_ Enterprise) |
| Office 365 бизнес Essentials \_ de (O365 \_ бизнес \_ основные компоненты \_ de) | Microsoft 365 бизнес базовый (Office 365 \_ бизнес основные \_ компоненты) |
| Office 365 бизнес премиум \_ de (O365 \_ бизнес \_ премиум \_ de) | Microsoft 365 бизнес Standard (O365 \_ бизнес \_ премиум) |
| Office 365 для бизнеса \_ de (Office 365 для бизнеса \_ \_ de) | Приложения Microsoft 365 для бизнеса (Office 365 \_ бизнес) |
| Office 365 E1 \_ de (стандардпакк \_ de) | Office 365 E1 (СТАНДАРДПАКК) |
| Office 365 E3 без ProPlus \_ -de (ентерприсепакквисаутпроплус \_ de) | Office 365 E3 без ProPlus (ЕНТЕРПРИСЕПАККВИСАУТПРОПЛУС) |
| Office 365 E3 \_ de (ENTERPRISEPACK \_ de) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 корпоративный E1 \_ de (стандардпакк \_ de) | Office 365 корпоративный E1 (СТАНДАРДПАКК) |
| Office 365 корпоративный E3 \_ de (ENTERPRISEPACK \_ de) | Office 365 корпоративный E3 (ENTERPRISEPACK) |
| Дополнительное хранилище файлов Office 365 \_ (шарепоинтстораже \_ de) | Дополнительное хранилище файлов Office 365 (ШАРЕПОИНТСТОРАЖЕ) |
| Office 365 F1 \_ de (десклесспакк \_ de) | Office 365 F1 (ДЕСКЛЕССПАКК) |
| Office 365 профессиональный плюс для преподавателей \_ de (officesubscription находится \_ факультет \_ de) | Office 365 профессиональный плюс для преподавателей (OFFICESUBSCRIPTION находится \_ факультет) |
| Office 365 профессиональный плюс для студентов \_ de (officesubscription находится \_ Student \_ de) | Office 365 профессиональный плюс для учащихся (OFFICESUBSCRIPTION находится \_ Student) |
| Office 365 профессиональный плюс \_ de (officesubscription находится \_ de) | Office 365 профессиональный плюс (OFFICESUBSCRIPTION находится) |
| OneDrive для бизнеса (план 1) \_ de (ваконедривестандард \_ de) | OneDrive для бизнеса (план 1) (ВАКОНЕДРИВЕСТАНДАРД) |
| OneDrive для бизнеса (план 2) \_ de (ваконедривинтерприсе \_ de) | OneDrive для бизнеса (план 2) (ВАКОНЕДРИВИНТЕРПРИСЕ) |
| Power BI Pro для преподавателей \_ de ("Power \_ BI \_ Pro \_ факультет \_ de") | Power BI Pro для преподавателей ( \_ "Power BI \_ Pro \_ факультета") |
| Power BI Pro \_ de (Power \_ BI \_ Pro \_ de) | Power BI Pro (POWER \_ BI \_ Pro) |
| Project Online Essentials \_ de (прожектессентиалс \_ de) | Project Online Essentials (ПРОЖЕКТЕССЕНТИАЛС) |
| Project Online Premium \_ de (прожектпремиум \_ de) | Project Online Premium (ПРОЖЕКТПРЕМИУМ) |
| Project Online профессиональный \_ de (прожектпрофессионал \_ de) | Project Online профессиональный (ПРОЖЕКТПРОФЕССИОНАЛ) |
| План проекта 3 \_ de (прожектпрофессионал \_ de) | План проекта 3 (ПРОЖЕКТПРОФЕССИОНАЛ) |
| Office 365 E4 \_ de (ентерприсевисскал \_ de) | Office 365 E3 (ENTERPRISEPACK) |
| SharePoint Online (план 1) \_ de (шарепоинтстандард \_ de) | SharePoint Online (план 1) (ШАРЕПОИНТСТАНДАРД) |
| SharePoint Online (план 2) \_ de (SHAREPOINTENTERPRISE \_ de) | SharePoint Online (план 2) (SHAREPOINTENTERPRISE) |
| Skype для бизнеса Online (план 1) \_ de (мкоимп \_ de) | Office 365 E1 (СТАНДАРДПАКК) |
| Skype для бизнеса Online (план 1) \_ de (мкоимп \_ de) | Skype для бизнеса Online (план 1) (МКОИМП) |
| Skype для бизнеса Online (план 2) \_ de (мкостандард \_ de) | Skype для бизнеса Online (план 2) (МКОСТАНДАРД) |
| Skype для бизнеса Plus CAL \_ de (мкоплускал \_ de) | Skype для бизнеса Plus CAL (МКОПЛУСКАЛ) |
| Visio Online (план 1) для преподавателей \_ de (висиунлине \_ PLAN1 \_ фак \_ de) | Visio Online (план 1) для преподавателей (ВИСИУНЛИНЕ \_ PLAN1 \_ фак) |
| Visio Online (план 1 \_ de) (висиунлине \_ PLAN1 \_ de) | Visio Online (план 1) (ВИСИУНЛИНЕ \_ PLAN1) |
| Visio Online (план 2) для преподавателей \_ de (висиоклиент \_ факультет \_ de) | Visio Online (план 2) для преподавателей (ВИСИОКЛИЕНТ \_ факультет) |
| Visio Online (план 2 \_ de) (висиоклиент \_ de) | Visio Online (план 2) (ВИСИОКЛИЕНТ) |
| Visio, план 1 \_ de (висиунлине \_ PLAN1 \_ de) | Visio (план 1) (ВИСИУНЛИНЕ \_ PLAN1) |
| Visio, план 2 \_ de (висиоклиент \_ de) | Visio (план 2) (ВИСИОКЛИЕНТ) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Как получить помощь от корпорации Майкрософт, чтобы перейти на новый регион или ответить на вопросы о поддержке?

Если у вас возникнут вопросы, вы можете связаться с нами или вашим партнером:

- В Azure можно отправлять [новые запросы в службу поддержки](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) на портале Azure.
- Для Office 365 вы можете отдать вопросы с помощью &quot; &quot; ссылки на [центр администрирования Microsoft 365](https://portal.office.de/).
- Если вы используете Dynamics 365, а также клиент Power BI и Office 365, вы можете сообщить вопросы, используя ссылку на &quot; &quot; [центр администрирования Майкрософт 365](https://portal.office.de/). Варианты поддержки клиентов Dynamics 365 Customer Engagement доступны [здесь](https://docs.microsoft.com/dynamics365/get-started/support/). Варианты поддержки клиентов Power BI доступны [здесь](https://powerbi.microsoft.com/support/).


## <a name="next-step"></a>Следующий этап

[Согласие на миграцию](ms-cloud-germany-migration-opt-in.md)

## <a name="more-information"></a>Дополнительные сведения

Начало работы:

- [Помощь по миграции Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Как принять участие в миграции](ms-cloud-germany-migration-opt-in.md)
- [Взаимодействие с пользователем во время миграции](ms-cloud-germany-transition-experience.md)

Перемещение по переходу:

- [Действия и влияние этапов миграции](ms-cloud-germany-transition-phases.md)
- [Дополнительные предварительные действия](ms-cloud-germany-transition-add-pre-work.md)
- Дополнительные сведения о [службах](ms-cloud-germany-transition-add-general.md), [устройствах](ms-cloud-germany-transition-add-devices.md), [опыте](ms-cloud-germany-transition-add-experience.md)и службах [федерации Active Directory](ms-cloud-germany-transition-add-adfs.md).

Облачные приложения:

- [Сведения о программе миграции Dynamics 365](https://aka.ms/d365ceoptin)
- [Сведения о программе миграции Power BI](https://aka.ms/pbioptin)
- [Начало перехода на Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
