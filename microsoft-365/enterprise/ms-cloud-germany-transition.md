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
ms.openlocfilehash: 7e170967e1670433a7d28753430f0cb15818039b
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476641"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Миграция из Microsoft Cloud Deutschland в службы Office 365 в новых регионах центра обработки данных в Германии

> [!NOTE]
> Эта статья применяется только к подходящим клиентам Microsoft Cloud Deutschland.

В августе 2018 г. Корпорация Майкрософт объявила о намерении предоставить полное облако Microsoft Azure, Office 365, Dynamics 365 и Power Platform из новых облачных регионов в Германии, чтобы лучше включить цифровую трансформацию наших клиентов. В августе 2019 г. мы объявили о том, что находимся в процессе открытия новых облачных регионов в Германии. С тех пор мы объявили о доступности Azure, Office 365, Dynamics 365 и Power Platform.

Новые регионы предназначены для более гибкого решения меняющихся потребностей немецких клиентов, новейших интеллектуальных облачных служб и полного подключения к облачной сети служб Microsoft 365, а также для проживания данных клиентов в Германии.

## <a name="how-to-migrate-to-the-new-german-datacenter-regions"></a>Миграция в новые немецкие регионы центра обработки данных

Существующие клиенты Microsoft Cloud Deutschland теперь могут начать миграцию своих клиентов Office 365, Dynamics 365 и Power Platform. Первым шагом является [согласие на миграцию под руководством корпорации Майкрософт](./ms-cloud-germany-migration-opt-in.md) в наши новые регионы центров обработки данных в Германии.

Для организаций, которые выбирают подход, управляемый Корпорацией Майкрософт, миграция должна начаться в начале 2021 г. и будет завершена к 29 октября 2021 г. В результате миграции основные данные клиента и подписки перемещаются в новые регионы в Германии.

В этой статье представлен обзор подхода к миграции, основанного на microsoft, ясности в отношении работы как пользователей, так и администраторов во время и после миграции, а также действий, которые могут потребоваться для клиентов на основе рабочих нагрузок, которые вы используете.

Указанные ниже службы будут перенесены в рамках программы под руководством корпорации Майкрософт:

- Azure Active Directory (Azure AD)
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive для бизнеса

- Skype для бизнеса Online\*\*
- Группы Office 365
- Dynamics 365 / Power Platform\*\*\*

\*\*Во время миграции из Microsoft Cloud Deutschland в немецкие регионы центра обработки данных существующие клиенты Skype для бизнеса Online переходят в Microsoft Teams. Дополнительные сведения см. в статье [Начало перехода на Microsoft Teams](/microsoftteams/upgrade-start-here).

\*\*\*Предпосылки и последствия миграции для этих служб описаны в статье Взаимодействие с клиентами [Dynamics 365.](/dynamics365/get-started/migrate-data-german-region)

1 марта 2021 г. прекращается поддержка Office 365 Видео. Если вы решили перенести свой клиент Office 365 в новые регионы центров обработки данных в Германии, Office 365 Видео не будет поддерживаться после завершения миграции SharePoint Online. Дополнительные сведения см. в [графике Microsoft Cloud Deutschland.](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="how-is-the-migration-organized"></a>Как организована миграция?

На этом рисунке показаны десять этапов миграции в новые немецкие центра обработки данных.

![Десять этапов миграции в новые центр обработки данных в Германии](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Эти этапы начинаются при [отказе от переноса.](./ms-cloud-germany-migration-opt-in.md) Большинство этапов миграции выполняются в качестве операций back-end service с минимальным взаимодействием с клиентами и выполняются один этап за другим. Начало выполнения дополнительных задач под руководством клиента и общего состояния миграции будет сообщено через Центр сообщений центра администрирования Microsoft 365 во время процесса миграции. Пример задач может включать обновления DNS, управляемые клиентом, перенастройку гибридной установки для гибридных клиентов Exchange или миграцию Azure.

Миграция не сразу начинается при отказе. Ваша организация добавляется в список клиентов, запланированных для более поздней миграции. Вы можете начать этапы подготовки к работе, так как они имеют решающее значение для обеспечения успешной миграции и использования по завершении:

- [Действия и влияние этапов миграции](ms-cloud-germany-transition-phases.md)
- [Дополнительная предварительная работа](ms-cloud-germany-transition-add-pre-work.md)

За неделю до начала миграции клиента вы получите уведомление в службе Центра сообщений в качестве окончательного предупреждения о том, что все необходимые условия должны быть завершены.

Миграция будет перемещать клиента Azure AD из суверенной службы Azure AD Германии в экземпляр служб Office 365 Azure AD в регионе ЕС.

Следующим этапом является перенос подписок клиента&#39;и лицензий пользователей из продуктов, определенных для Германии, в глобальные продукты.

После завершения всех действий, включая миграцию клиента Azure, клиент завершает работу в службе служб Office 365, и миграция помечена как завершенная. На этом этапе вам предоставляется окончательное обновление центра сообщений. В настоящее время клиент является полностью глобальной организацией Office 365.

Вы уведомлены о ходе миграции с помощью сообщений центра сообщений. Сообщения будут возникать в определенных вехах и будут предоставлять рекомендации по прогрессу шага, а также важные сведения для клиентов действовать на основе требований процесса. Уведомления центра сообщений предоставляются в следующих вехах:

- Начало миграции (за 5 дней до начала миграции Azure AD)
- Миграция Azure AD завершена
- Миграция подписки и лицензий завершена
- Миграция SharePoint завершена
- Миграция Exchange завершена
- Завершение Skype для бизнеса
- Динамика завершена
- Power BI complete
- Окончательное сокращение служб завершено

После окончательного перехода Azure AD к всемирной службе ожидается, что все клиенты и приложения будут полностью перенаправляться для использования правильных конечных точек. Существует 30-дневное окно после завершаемого сокращения, в котором можно продолжить получение маркеров Azure AD из службы Microsoft Cloud Deutschland. По истечении 30-дневного окна клиенты и приложения больше не смогут получить доступ к конечным точкам Azure AD Microsoft Cloud Deutschland. Приложения или доступ к пользователю не удастся с этой точки зрения. Необходимо убедиться, что все пользователи и приложения будут перенесены в правильные конечные точки до закрытия этого окне времени. 

## <a name="moving-to-the-new-german-datacenter-regions"></a>Перемещение в новые немецкие регионы центра обработки данных

Существующие клиенты Microsoft Cloud Deutschland теперь могут начать перенос своих служб Office 365, Dynamics 365 и Power Platform. Первым шагом является [согласие на миграцию под руководством корпорации Майкрософт](./ms-cloud-germany-migration-opt-in.md) в наши новые регионы центров обработки данных в Германии. При продлении подписки вы автоматически выбираете миграцию с помощью Майкрософт. Корпорация Майкрософт уведомит об этом администраторов клиентов по электронной почте и в центре сообщений центра администрирования Microsoft 365. Однако, если вы предпочитаете начать этот [](./ms-cloud-germany-migration-opt-in.md) процесс сейчас, вы можете выбрать непосредственно в центре администрирования Microsoft 365 сегодня. Ожидается, что миграция начнется в начале 2021 г. и завершится к 29 октября 2021 г. 

В результате миграции основные данные клиентов и подписки перемещаются в новые немецкие регионы центра обработки данных.

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Как подготовиться к миграции на службы Office 365 в новых регионах центров обработки данных в Германии

Первым шагом является уведомление Корпорации Майкрософт, чтобы у нас было разрешение на перенос подписки и данных из Microsoft Cloud Deutschland в службы Office 365 в новых немецких регионах центра обработки данных. Обратитесь к [процессу выбора](./ms-cloud-germany-migration-opt-in.md) инструкций и обратите внимание, что:

- Все мигрирующие клиенты должны проверять подключение к URL-адресам Office [365 Services Office 365](urls-and-ip-address-ranges.md)и IP-адресам, в том числе к новым немецким регионам центра обработки данных. Бездействие может привести к сбою службы и клиента.
- Просмотрите список действий [перед работой,](ms-cloud-germany-transition-add-pre-work.md) чтобы убедиться, что организация информирована и подготовлена к изменениям.
- Необходимо просмотреть описание службы платформы Office 365, чтобы понять, какие функции и службы станут доступны вашей организации после миграции в немецкий регион.
- Пробные подписки не будут перенесены и будут блокировать миграцию всех платных подписок. Перед началом миграции необходимо отменить все пробные испытания или преобразовать их в платные подписки.

## <a name="where-do-i-go-from-here"></a>Куда мне идти дальше?

Просмотрите следующий раздел Часто задамые вопросы.

## <a name="frequently-asked-questions"></a>Вопросы и ответы

### <a name="is-migration-required"></a>Требуется ли миграция?

Корпорация Майкрософт предлагает миграцию клиентов Office 365 из Microsoft Cloud Deutschland в службы Office 365 в новых немецких регионах обработки данных без дополнительной платы. Хотя мы настоятельно рекомендуем вам отказаться от перехода в новые немецкие регионы центра обработки данных, мы продолжим предоставлять необходимые обновления безопасности в регион Microsoft Cloud Deutschland.

Службы Office 365 в новых немецких регионах центра обработки данных:

- Предложение конкурентоспособной рыночной цены для [Azure](https://azure.microsoft.com/pricing/calculator/), [Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), [Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/) и [Power BI](https://powerbi.microsoft.com/pricing/).
- Подключены к глобальной&#39;Microsoft, предлагая сотни веб-сайтов с сетевыми краями, расположения одноранговых сайтов и точки отступа, чтобы обеспечить надежный пользовательский интерфейс в любой точке мира.
- Помогают вам соответствовать местным требованиям о размещении данных в пределах Германии.
- Предоставление полного глобального облачного предложения с новейшими версиями наших служб и новыми возможностями, включая Microsoft Teams и Multi-Geo в Office 365. Сравните продукты по регионам для [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), [Office 365](o365-data-locations.md)и [Dynamics 365](/dynamics365/get-started/availability).
- Предлагают полный набор функций, обеспечение безопасности корпоративного уровня и широкие возможности, которые помогают клиентам удовлетворить нормативные требования.
- Доступны через существующие контракты веб-служб.

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>Какова доступность службы между различными предложениями облачных служб Office 365?
<h2 id="serv-avail"></h2>

Следующие 15 служб доступны в облачной службе Microsoft Cloud Deutschland. Мы не добавляем новые службы в Microsoft Cloud Deutschland.

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

В настоящее время в новых немецких регионах центра обработки данных доступны 39 служб в рамках служб Office 365. Новые функции и службы будут доступны в рамках глобальных служб Office 365 на постоянной основе.

1. Exchange Online
2. Lockbox клиента для Exchange Online
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
17. Skype для бизнеса (будет мигрировать в Microsoft Teams во время миграции)
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
28. Корпоративная мобильность и безопасность (EMS) E3 (Azure AD Premium P1, Intune и служба управления правами)
29. Yammer корпоративный
30. Microsoft Forms
31. Power Automate для Office 365
32. Виртуальные агенты Power для Office 365
33. PowerApps для Office 365
34. Microsoft Bookings
35. To-Do
36. Доска
37. Microsoft StuffHub
38. Microsoft Kaizala Pro
39. Списки

### <a name="when-will-migration-happen"></a>Когда произойдет миграция?

**Azure**

Если вы только клиент Azure, [](/azure/germany/germany-migration-main) вы можете приступить к переносу ресурсов Azure в другой регион уже сегодня. 

Если у вас есть Azure с Office 365, Dynamics 365 или Power BI, необходимо следовать процессу миграции, чтобы обеспечить успешную миграцию AzureAD, прежде чем приступить к самостоятельной миграции Azure. Перед закрытием службы необходимо завершить миграцию Azure, чтобы сохранить рабочие нагрузки Azure в вашей организации AzureAD и Office 365.

**Office 365**

[Согласие](./ms-cloud-germany-migration-opt-in.md) на миграцию под руководством корпорации Майкрософт сегодня. Когда мы будем готовы приступить к миграции, мы сообщим вам через Центр сообщений в центре администрирования Microsoft 365.

**Dynamics 365 и Power BI**

В настоящее время вы можете выбрать миграцию для [динамических 365](/dynamics365/get-started/migrate-data-german-region) клиентов и power BI, которая [управляется Корпорацией Майкрософт.](/power-bi/admin/service-admin-migrate-data-germany) Когда вы будете готовы начать миграцию, то в центре администрирования Microsoft 365 мы проинформируем вас с помощью Центра сообщений.

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>Изменится ли цена для служб Office 365, которые я использую?

Да. Цены в глобальных облачных&#39;Microsoft (включая новые регионы центра обработки данных) обычно ниже.

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>Во время миграции подписки какие skUs и Лицензии будут применены к моей организации и пользователям?

Во время миграции из Microsoft Cloud Deutschland в службы Office 365 SKU, определенные для службы Германии, заменяются глобальными версиями того же или аналогичного SKU. В большинстве случаев службы SKU в Office 365 являются одинаковыми, однако в службах Office 365 существует несколько замен, в которых SKU в Германии больше не доступен. Если вы хотите обновить SKU, назначенную вашей организации после завершения миграции, обратитесь к продавцу, чтобы добавить или изменить назначенные службы.

| Microsoft Cloud Deutschland — SKU продукта (DE) | Microsoft Cloud Global — SKU продукта (WW) |
| --- | --- |
| Lockbox \_ DE клиента (LOCKBOX \_ DE) | Lockbox клиента (LOCKBOX) |
| Dynamics 365 Enterprise Edition — дополнительное хранилище баз данных \_ DE (CRMSTORAGE \_ DE) | Dynamics 365 Enterprise Edition — дополнительное хранилище баз данных (CRMSTORAGE) |
| Dynamics 365 Enterprise Edition - Дополнительные непроизводимые \_ экземпляры DE (CRMTESTINSTANCE \_ DE) | Dynamics 365 Enterprise Edition — дополнительный экземпляр без производства (CRMTESTINSTANCE) |
| Dynamics 365 для корпоративных клиентов Edition \_ DE (DYN365 \_ ENTERPRISE CUSTOMER SERVICE \_ \_ \_ DE) | Dynamics 365 для корпоративного выпуска службы клиентов (DYN365 \_ \_ КОРПОРАТИВНЫЕ \_ СЛУЖБЫ КЛИЕНТОВ) |
| Dynamics 365 для отдела продаж Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE SALES \_ \_ DE) | Dynamics 365 for Sales Enterprise Edition (DYN365 \_ ENTERPRISE \_ SALES) |
| Dynamics 365 для членов команды Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE TEAM MEMBERS \_ \_ \_ DE) | Dynamics 365 для корпоративных участников группы (DYN365 \_ ENTERPRISE \_ TEAM \_ MEMBERS) |
| Dynamics 365 Plan 1 Enterprise Edition \_ DE (DYN365 \_ ENTERPRISE \_ PLAN1 \_ DE) | Dynamics 365 Plan 1 Enterprise Edition (DYN365 \_ ENTERPRISE \_ PLAN1) |
| ECAL Services (EOA, EOP, DLP) \_ DE (ECAL \_ SERVICES \_ DE) | ECAL Services (EOA, EOP, DLP) (ECAL \_ SERVICES) |
| Корпоративная мобильность + безопасность \_ E3 DE (EMS \_ DE) | Корпоративная мобильность + безопасность E3 (EMS) |
| Exchange Online (план 1) DE \_ (EXCHANGESTANDARD \_ DE) | Exchange Online (план 1) (EXCHANGESTANDARD) |
| Exchange Online (план 2) \_ DE (EXCHANGEENTERPRISE \_ DE) | Exchange Online (план 2) (EXCHANGEENTERPRISE) |
| архивация на базе Exchange Online Exchange Online \_ DE (EXCHANGEARCHIVE \_ ADDON \_ DE) | архивация на базе Exchange Online Exchange Online (EXCHANGEARCHIVE \_ ADDON) |
| архивация на базе Exchange Online для Exchange Server \_ DE (EXCHANGEARCHIVE \_ DE) | архивация на базе Exchange Online для Exchange Server (EXCHANGEARCHIVE) |
| Exchange Online Essentials \_ DE (EXCHANGE \_ S \_ ESSENTIALS \_ DE) | Основные инструменты Exchange Online (EXCHANGE \_ S \_ ESSENTIALS) |
| базовая подписка на Exchange Online DE \_ (EXCHANGEDESKLESS \_ DE) | базовая подписка на Exchange Online (EXCHANGEDESKLESS) |
| Exchange Online Protection \_ DE (EOP \_ ENTERPRISE \_ DE) | Exchange Online Protection (EOP \_ ENTERPRISE) |
| Бизнес-стандарт Microsoft 365 (O365 \_ BUSINESS \_ PREMIUM) | Бизнес-стандарт Microsoft 365 (O365 \_ BUSINESS \_ PREMIUM) |
| Microsoft Dynamics CRM Online \_ Экземпляр DE (CRMINSTANCE \_ DE) | Microsoft Dynamics CRM Online (CRMINSTANCE) |
| Office 365 A1 для факультета \_ DE (STANDARDWOFFPACK \_ FACULTY \_ DE) | Office 365 A1 для преподавателей (ФАКУЛЬТЕТ STANDARDWOFFPACK) \_ |
| Office 365 A1 для студентов \_ DE (STANDARDWOFFPACK \_ STUDENT \_ DE) | Office 365 A1 для студентов (STANDARDWOFFPACK \_ STUDENT) |
| Office 365 Advanced Compliance \_ DE (EQUIVIO \_ ANALYTICS \_ DE) | Соответствие требованиям Microsoft 365 E5 \_ (СООТВЕТСТВИЕ ТРЕБОВАНИЯМ \_ ЗАЩИТЫ ИНФОРМАЦИИ) |
|Microsoft Defender для Office 365 (план 1) \_ DE (ATP \_ ENTERPRISE \_ DE) |Microsoft Defender для Office 365 (план 1) (ATP \_ ENTERPRISE) |
| Office 365 Business Essentials \_ DE (O365 \_ BUSINESS \_ ESSENTIALS \_ DE) | Microsoft 365 Business Basic (O365 \_ BUSINESS \_ ESSENTIALS) |
| Office 365 Business Premium \_ DE (O365 \_ BUSINESS \_ PREMIUM \_ DE) | Бизнес-стандарт Microsoft 365 (O365 \_ BUSINESS \_ PREMIUM) |
| Office 365 Business \_ DE (O365 \_ BUSINESS \_ DE) | Приложения Microsoft 365 для бизнеса (O365 \_ BUSINESS) |
| Office 365 E1 \_ DE (STANDARDPACK \_ DE) | Office 365 E1 (STANDARDPACK) |
| Office 365 E3 без ProPlus \_ DE (ENTERPRISEPACKWITHOUTPROPLUS \_ DE) | Office 365 E3 без ProPlus (ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 Enterprise E1 \_ DE (STANDARDPACK \_ DE) | Office 365 Enterprise E1 (STANDARDPACK) |
| Office 365 Enterprise E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 Enterprise E3 (ENTERPRISEPACK) |
| Office 365 Extra File Storage \_ DE (SHAREPOINTSTORAGE \_ DE) | Дополнительные хранилища файлов Office 365 (SHAREPOINTSTORAGE) |
| Office 365 F1 \_ DE (DESKLESSPACK \_ DE) | Office 365 F1 (DESKLESSPACK) |
| Office 365 ProPlus для факультета \_ DE (OFFICESUBSCRIPTION \_ FACULTY \_ DE) | Office 365 ProPlus для преподавателей (OFFICESUBSCRIPTION \_ FACULTY) |
| Office 365 ProPlus для студентов \_ DE (OFFICESUBSCRIPTION \_ STUDENT \_ DE) | Office 365 ProPlus для студентов (OFFICESUBSCRIPTION \_ STUDENT) |
| Office 365 ProPlus \_ DE (OFFICESUBSCRIPTION \_ DE) | Office 365 ProPlus (OFFICESUBSCRIPTION) |
| OneDrive для бизнеса (план 1) \_ DE (WACONEDRIVESTANDARD \_ DE) | OneDrive для бизнеса (план 1) (WACONEDRIVESTANDARD) |
| OneDrive для бизнеса (план 2) \_ DE (WACONEDRIVEENTERPRISE \_ DE) | OneDrive для бизнеса (план 2) (WACONEDRIVEENTERPRISE) |
| Power BI Pro для \_ факультета DE (POWER \_ BI PRO \_ \_ FACULTY \_ DE) | Power BI Pro для преподавателей (POWER \_ BI \_ PRO \_ FACULTY) |
| Power BI Pro \_ DE (POWER \_ BI \_ PRO \_ DE) | Power BI Pro (POWER \_ BI \_ PRO) |
| Project Online Essentials \_ DE (PROJECTESSENTIALS \_ DE) | Project Online Essentials (PROJECTESSENTIALS) |
| Project Online Premium \_ DE (PROJECTPREMIUM \_ DE) | Project Online Premium (PROJECTPREMIUM) |
| Project Online Professional \_ DE (PROJECTPROFESSIONAL \_ DE) | Project Online Professional (PROJECTPROFESSIONAL) |
| Project Plan 3 \_ DE (PROJECTPROFESSIONAL \_ DE) | Project Plan 3 (PROJECTPROFESSIONAL) |
| Office 365 E4 \_ DE (ENTERPRISEWITHSCAL \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| SharePoint Online (план 1) DE \_ (SHAREPOINTSTANDARD \_ DE) | SharePoint Online (план 1) (SHAREPOINTSTANDARD) |
| SharePoint Online (план 2) \_ DE (SHAREPOINTENTERPRISE \_ DE) | SharePoint Online (план 2) (SHAREPOINTENTERPRISE) |
| Skype for Business Online (Plan 1) \_ DE (MCOIMP \_ DE) | Office 365 E1 (STANDARDPACK) |
| Skype for Business Online (Plan 1) \_ DE (MCOIMP \_ DE) | Skype для бизнеса Online (план 1) (MCOIMP) |
| Skype для бизнеса в Интернете (план 2) \_ DE (MCOSTANDARD \_ DE) | Skype для бизнеса Online (план 2) (MCOSTANDARD) |
| Skype для бизнеса Плюс CAL \_ DE (MCOPLUSCAL \_ DE) | Skype для бизнеса Плюс CAL (MCOPLUSCAL) |
| Visio Online Plan 1 для факультета \_ DE (VISIOONLINE \_ PLAN1 \_ FAC \_ DE) | Visio Online Plan 1 для преподавателей (FAC VISIOONLINE \_ \_ PLAN1) |
| Visio Online Plan 1 \_ DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio Online Plan 1 (VISIOONLINE \_ PLAN1) |
| Visio Online Plan 2 для факультета \_ DE (VISIOCLIENT \_ FACULTY \_ DE) | Visio Online Plan 2 для преподавателей (VISIOCLIENT \_ FACULTY) |
| Visio Online Plan 2 \_ DE (VISIOCLIENT \_ DE) | Visio Online Plan 2 (VISIOCLIENT) |
| Visio Plan 1 \_ DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio Plan 1 (VISIOONLINE \_ PLAN1) |
| Visio Plan 2 \_ DE (VISIOCLIENT \_ DE) | Visio Plan 2 (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Как получить помощь от корпорации Майкрософт, чтобы перейти на новый регион или ответить на вопросы о поддержке?

Если у вас есть вопросы, вы можете связаться с нами или вашим партнером:

- В Azure можно отправлять [новые запросы в службу поддержки](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) на портале Azure.
- Для Office 365 вы можете отправлять вопросы с помощью справки? ссылку центра администрирования &quot; &quot; Microsoft [365.](https://portal.office.de/)
- Если вы клиент Dynamics 365 и клиент Power BI, а также имеете Office 365, вы можете задать вопросы с помощью справки? ссылка центра администрирования &quot; &quot; Microsoft [365.](https://portal.office.de/) Варианты поддержки клиентов Dynamics 365 Customer Engagement доступны [здесь](/dynamics365/get-started/support/). Варианты поддержки клиентов Power BI доступны [здесь](https://powerbi.microsoft.com/support/).

### <a name="my-customer-already-has-a-m365-tenant-in-the-global-microsoft-cloud-in-addition-to-a-microsoft-cloud-deutschland-tenant-can-these-two-tenants-be-merged-into-one-as-part-of-the-migration"></a>У моего клиента уже есть клиент M365 в глобальном облаке Microsoft, а также клиент Microsoft Cloud Deutschland. Можно ли объединить этих двух клиентов в один в рамках миграции?

Нет, возможности объединения клиента не существует. Клиенты останутся отдельными и уникальными, так как каждый клиент имеет свое пространство имен и уникальный ID. Корпорация Майкрософт при желании перенаселит клиента Microsoft Cloud Deutschland в глобальное облако, иначе клиент может отменить его и отказаться от него.


### <a name="what-actions-are-required-to-be-done-by-most-end-users-as-part-of-the-migration"></a>Какие действия необходимо сделать большинству конечных пользователей в рамках миграции?
Миграция предназначена для минимального воздействия на конечных пользователей и клиентов.
- Убедитесь, что приложения Office запускают последние доступные версии. 
- Клиенты, использующие Skype для бизнеса, переходят в Teams в рамках миграции и, возможно, потребуется скачать и [установить Teams](/deployoffice/teams-install) на устройствах.
- Конечным пользователям может потребоваться выйти из приложений Office и войти обратно после завершения миграции. 
- Клиентам, работающим с клиентом Синхронизация OneDrive, необходимо выйти из рабочей станции и снова войти в систему, чтобы позволить клиенту OneDrive Sync войти в глобальную службу Azure Active Directory.
- Будьте в курсе новых глобальных URL-адресов после завершения миграции, в частности Outlook Web Access (пример: использование outlook.office365.com). Клиенты SharePoint Online продолжат успешно подключаться к пространству имен MCD с помощью существующего URL-адреса (пример: contoso.sharepoint.de).


### <a name="which-customers-are-affected-by-the-azure-active-directory-migration"></a>На каких клиентов влияет миграция Azure Active Directory? 

Все клиенты Office365 зависят от Azure Active Directory для проверки подлинности и хранения критически важных компонентов служб, необходимых для работы служб, на которых работает Корпорация Майкрософт. 


### <a name="what-are-the-impacts-of-the-azure-active-directory-migration"></a>Каковы последствия миграции Azure Active Directory?

Первоначальная миграция Azure Active Directory на ранней стадии не влияет на клиентскую активность. После заключительного этапа миграции все службы клиента-клиента полностью находятся в глобальной службе. После этого заключительного этапа служба Azure Active Directory в Microsoft Cloud Deutschland больше не может принимать запросы на авторизацию или предоставлять маркеры доступа к службам Office.


### <a name="what-does-it-mean-to-ensure-network-connectivity-to-office-365-services-urls-and-ip-addresses"></a>Что означает обеспечение подключения сети к URL-адресам служб [Office 365 и IP-адресам?](./urls-and-ip-address-ranges.md)

В этой статье описываются необходимые URL-адреса и IP-адреса, необходимые для надлежащей работы глобальной службы для обеспечения хорошего обслуживания клиентов. В относительно редких случаях некоторые клиенты пытаются настроить безопасность периметра сети таким образом, чтобы свести к минимуму потоки трафика и ограничить доступ к службам только в рамках IP-диапазонов служб Microsoft Cloud Deutschland.


### <a name="how-do-i-manage-the-dns-changes-for-exchange-online-so-mail-will-continue-to-flow"></a>Как управлять изменениями DNS для Exchange Online, чтобы почта продолжала поступать?

Диапазоны IP-адресов с управлением Майкрософт и зоны DNS переходят во время и в рамках миграции в глобальную службу. 

Клиент управляет DNS-зонами, такими как пользовательские записи MX домена, однако, чтобы упростить эту миграцию, клиентская запись управляемых MX указывает на конечную точку службы Office 365 в зоне office.de и Майкрософт управляет переносом этой конечной точки службы автоматически.


### <a name="how-do-i-manage-the-dns-changes-for-skype-for-business"></a>Как управлять изменениями DNS для Skype для бизнеса? 
 
Все клиенты Skype для бизнеса будут переходить в Microsoft Teams. Переход клиентской зоны DNS Skype не требуется при миграции в Teams. Клиенты смогут сразу же войти в Teams со всеми функциональными возможностями после миграции.
 

### <a name="will-outlook-for-ios-and-android-work-after-the-migration"></a>Будет ли Outlook для iOS и Android работать после миграции? 

Да. Рекомендация Корпорации Майкрософт — все клиенты запускают последние доступные версии клиентов Office, включая Outlook для клиентов с iOS и Android. После завершения миграции в глобальную службу Office 365 всем клиентам Office необходимо выйти и войти в систему, чтобы получить новый маркер доступа Azure Active Directory от глобальной службы. 



## <a name="next-step"></a>Следующий шаг

[Согласие на миграцию](ms-cloud-germany-migration-opt-in.md)

## <a name="more-information"></a>Дополнительные сведения

Начало работы:

- [Помощь по миграции Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Как принять участие в миграции](ms-cloud-germany-migration-opt-in.md)
- [Опыт работы с клиентами во время миграции](ms-cloud-germany-transition-experience.md)

Перемещение по переходу:

- [Действия и влияние этапов миграции](ms-cloud-germany-transition-phases.md)
- [Дополнительная предварительная работа](ms-cloud-germany-transition-add-pre-work.md)
- Дополнительные сведения [для Azure AD,](ms-cloud-germany-transition-azure-ad.md) [устройств,](ms-cloud-germany-transition-add-devices.md) [опытом](ms-cloud-germany-transition-add-experience.md)и [AD FS.](ms-cloud-germany-transition-add-adfs.md)

Облачные приложения:

- [Сведения о программе миграции Dynamics 365](/dynamics365/get-started/migrate-data-german-region)
- [Сведения о программе миграции Power BI](/power-bi/admin/service-admin-migrate-data-germany)
- [Начало перехода на Microsoft Teams](/microsoftteams/upgrade-start-here)