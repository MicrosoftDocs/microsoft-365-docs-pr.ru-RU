---
title: Миграция из Microsoft Cloud Deutschland в Office 365 службы в новых немецких регионах центра обработки данных
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 05/12/2021
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
ms.openlocfilehash: 4162e51164120cecaa431ad6883d3ee112ad4880
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796010"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Миграция из Microsoft Cloud Deutschland в Office 365 службы в новых немецких регионах центра обработки данных

> [!NOTE]
> Эта статья применяется только к подходящим клиентам Microsoft Cloud Deutschland.

В августе 2018 г. корпорация Майкрософт объявила о намерении предоставить полное облако Microsoft Azure, Office 365, Dynamics 365 и Power Platform из новых облачных регионов в Германии, чтобы лучше включить цифровую трансформацию наших клиентов. В августе 2019 г. мы объявили о том, что находимся в процессе открытия новых облачных регионов в Германии. С тех пор мы объявили о доступности Платформы Azure, Office 365, Dynamics 365 и Power Platform.

Новые регионы предназначены для более гибкого решения меняющихся потребностей немецких клиентов, новейших интеллектуальных облачных служб и полного подключения к облачной сети Microsoft 365 служб, а также проживания данных клиентов в Германии.

## <a name="how-to-migrate-to-the-new-german-datacenter-regions"></a>Миграция в новые немецкие регионы центра обработки данных

Существующие клиенты Microsoft Cloud Deutschland теперь могут приступить к миграции Office 365, dynamics 365 Customer Engagement и Power Platform. Первым шагом является [согласие на миграцию под руководством корпорации Майкрософт](./ms-cloud-germany-migration-opt-in.md) в наши новые регионы центров обработки данных в Германии.

Для организаций, которые выбирают подход, управляемый Корпорацией Майкрософт, миграция должна начаться в начале 2021 г. и будет завершена к 29 октября 2021 г. В результате миграции основные данные клиента и подписки перемещаются в новые регионы в Германии.

В этой статье представлен обзор подхода к миграции, основанного на microsoft, ясности в отношении работы как пользователей, так и администраторов во время и после миграции, а также действий, которые могут потребоваться для клиентов на основе рабочих нагрузок, которые вы используете.

Указанные ниже службы будут перенесены в рамках программы под руководством корпорации Майкрософт:

- Azure Active Directory (Azure AD)
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- OneDrive для бизнеса
- Skype для бизнеса Онлайн\*\*
- Группы Office 365
- Dynamics 365 / Power Platform\*\*\*

\*\*Во время миграции из Microsoft Cloud Deutschland в немецкие регионы центра обработки данных существующие клиенты Skype для бизнеса Online будут Microsoft Teams. Дополнительные сведения см. в статье [Начало перехода на Microsoft Teams](/microsoftteams/upgrade-start-here).

\*\*\*Предпосылки и последствия миграции для этих служб описаны в статье Взаимодействие с клиентами [Dynamics 365.](/dynamics365/get-started/migrate-data-german-region)

1 марта 2021 г. прекращается поддержка Office 365 Видео. Если вы решили перенести свой клиент Office 365 в новые регионы центров обработки данных в Германии, Office 365 Видео не будет поддерживаться после завершения миграции SharePoint Online. Дополнительные сведения см. в [графике Microsoft Cloud Deutschland.](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="how-is-the-migration-organized"></a>Как организована миграция?

На этом рисунке показаны десять этапов миграции в новые немецкие центра обработки данных.

:::image type="content" alt-text="Десять этапов миграции в новые центр обработки данных в Германии" source="../media/ms-cloud-germany-migration-opt-in/migration-organization.png" lightbox="../media/ms-cloud-germany-migration-opt-in/migration-organization.png":::

Эти этапы начинаются при [отказе от переноса.](./ms-cloud-germany-migration-opt-in.md) Большинство этапов миграции выполняются в качестве операций back-end service с минимальным взаимодействием с клиентами и выполняются один этап за другим. Начало выполнения дополнительных задач под руководством клиента и общего состояния миграции будет сообщено через центр сообщений центра администрирования Microsoft 365 во время процесса миграции. Пример задач может включать обновления DNS, управляемые клиентом, перенастройку гибридной установки для гибридных клиентов Exchange или миграцию Azure.

Миграция не сразу начинается при отказе. Ваша организация добавляется в список клиентов, запланированных для более поздней миграции. Вы можете начать этапы подготовки к работе, так как они имеют решающее значение для обеспечения успешной миграции и использования по завершении:

- [Действия и влияние этапов миграции](ms-cloud-germany-transition-phases.md)
- [Дополнительная предварительная работа](ms-cloud-germany-transition-add-pre-work.md)

За неделю до начала миграции клиента вы получите уведомление в службе Центра сообщений в качестве окончательного предупреждения о том, что все необходимые условия должны быть завершены.

Миграция перемещает клиента Azure AD из суверенной службы Azure AD в Office 365 служб Azure AD в регионе ЕС.

Следующим этапом является перенос подписок клиента&#39;и лицензий пользователей из продуктов, определенных для Германии, в глобальные продукты.

После завершения всех действий, включая миграцию клиента Azure, клиент завершается в службе Office 365 и миграция помечена как завершенная. На этом этапе вам предоставляется окончательное обновление центра сообщений. В настоящее время клиент является полностью глобальной Office 365 организацией.

Вы уведомлены о ходе миграции с помощью сообщений центра сообщений. Сообщения будут возникать в определенных вехах и будут предоставлять рекомендации по прогрессу шага, а также важные сведения для клиентов действовать на основе требований процесса. Уведомления центра сообщений предоставляются в следующих вехах:

- Начало миграции (за 5 дней до начала миграции Azure AD)
- Миграция Azure AD завершена
- Миграция подписки и лицензий завершена
- SharePoint миграция завершена
- Exchange миграции завершена
- Skype для бизнеса завершена
- Динамика завершена
- Power BI завершен
- Окончательное сокращение служб завершено

После окончательного перехода Azure AD к всемирной службе ожидается, что все клиенты и приложения будут полностью перенаправляться для использования правильных конечных точек. Существует 30-дневное окно после завершаемого сокращения, в котором можно продолжить получение маркеров Azure AD из службы Microsoft Cloud Deutschland. По истечении 30-дневного окна клиенты и приложения больше не смогут получить доступ к конечным точкам Azure AD Microsoft Cloud Deutschland. Приложения или доступ к пользователю не удастся с этой точки зрения. Необходимо убедиться, что все пользователи и приложения будут перенесены в правильные конечные точки до закрытия этого окне времени. 

## <a name="moving-to-the-new-german-datacenter-regions"></a>Перемещение в новые немецкие регионы центра обработки данных

Существующие клиенты Microsoft Cloud Deutschland теперь могут приступить к переносу своих служб Office 365, Dynamics 365 и Power Platform. Первым шагом является [согласие на миграцию под руководством корпорации Майкрософт](./ms-cloud-germany-migration-opt-in.md) в наши новые регионы центров обработки данных в Германии. При продлении подписки вы автоматически выбираете миграцию с помощью Майкрософт. Корпорация Майкрософт уведомит администраторов клиентов по электронной почте и в центре сообщений центра администрирования Microsoft 365, когда это произошло. Однако, если вы предпочитаете начать этот [](./ms-cloud-germany-migration-opt-in.md) процесс сейчас, вы можете сделать выбор непосредственно Microsoft 365 центре администрирования. Ожидается, что миграция начнется в начале 2021 г. и завершится к 29 октября 2021 г. 

В результате миграции основные данные клиентов и подписки перемещаются в новые немецкие регионы центра обработки данных.

> [!NOTE]
> В этой статье содержатся рекомендации по миграции только Office 365 служб. Если в Microsoft Cloud Deutschland запущены дополнительные рабочие нагрузки Azure, см. в руководстве по миграции [для Azure Germany.](/azure/germany/germany-migration-main)

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Как подготовиться к миграции на службы Office 365 в новых регионах центров обработки данных в Германии

Первым шагом является уведомление Корпорации Майкрософт, чтобы у нас было разрешение на перенос подписки и данных из Microsoft Cloud Deutschland в Office 365 службы в новых немецких регионах центра обработки данных. Обратитесь к [процессу выбора](./ms-cloud-germany-migration-opt-in.md) инструкций и обратите внимание, что:

- Все мигрирующие клиенты должны проверять подключение к Office 365 services [Office 365 URL-адресам](urls-and-ip-address-ranges.md)и IP-адресам, в том числе к новым немецким регионам центра обработки данных. Бездействие может привести к сбою службы и клиента.
- Просмотрите список действий [перед работой,](ms-cloud-germany-transition-add-pre-work.md) чтобы убедиться, что организация информирована и подготовлена к изменениям.
- Необходимо просмотреть описание Office 365 платформы, чтобы понять, какие функции и службы станут доступны вашей организации после миграции в немецкий регион.
- Пробные подписки не будут перенесены и будут блокировать миграцию всех платных подписок. Перед началом миграции необходимо отменить все пробные испытания или преобразовать их в платные подписки.

## <a name="where-do-i-go-from-here"></a>Куда мне идти дальше?

Просмотрите следующий раздел Часто задамые вопросы.

## <a name="frequently-asked-questions"></a>Вопросы и ответы

### <a name="is-migration-required"></a>Требуется ли миграция?

Корпорация Майкрософт Office 365 миграцию клиентов из Microsoft Cloud Deutschland в Office 365 службы в новых немецких регионах центра обработки данных без дополнительной платы. Хотя мы настоятельно рекомендуем вам отказаться от перехода в новые немецкие регионы центра обработки данных, мы продолжим предоставлять необходимые обновления безопасности в регион Microsoft Cloud Deutschland.

Office 365 службы в новых немецких регионах центра обработки данных:

- Предложение конкурентоспособной рыночной цены для [Azure](https://azure.microsoft.com/pricing/calculator/), [Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), [Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/) и [Power BI](https://powerbi.microsoft.com/pricing/).
- Подключены к глобальной&#39;Microsoft, предлагая сотни веб-сайтов с сетевыми краями, расположения одноранговых сайтов и точки отступа, чтобы обеспечить надежный пользовательский интерфейс в любой точке мира.
- Помогают вам соответствовать местным требованиям о размещении данных в пределах Германии.
- Предоставление полного глобального облачного предложения с последними версиями наших служб и новыми возможностями, включая Microsoft Teams и Multi-Geo в Office 365. Сравните продукты по регионам для [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), [Office 365](o365-data-locations.md)и [Dynamics 365](/dynamics365/get-started/availability).
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

В настоящее время в новых немецких регионах центра обработки данных Office 365 39 служб. Новые функции и службы будут доступны в рамках глобальных служб Office 365 на постоянной основе.

1. Exchange Online
2. Блокировка клиента для Exchange Online
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
14. Блокировка клиента для SharePoint Online
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
28. Enterprise Mobility + Security E3 (Azure AD Premium P1, Intune и Служба управления правами)
29. Yammer корпоративный
30. Microsoft Forms
31. Power Automate для Office 365
32. Power Virtual Agents для Office 365
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

Если у вас есть Azure с Office 365, Dynamics 365 или Power BI, сначала необходимо следовать процессу миграции для Office 365 служб, чтобы обеспечить успешную миграцию Azure AD, прежде чем начать самонаправленную миграцию Azure. Необходимо завершить миграцию Azure перед завершением миграции клиента для поддержания рабочих нагрузок Azure с помощью Azure AD и Office 365 организации. Дополнительные сведения можно найти в отношении действий и последствий этапов миграции из [Microsoft Cloud Deutschland.](ms-cloud-germany-transition-phases.md)

**Office 365**

[Согласие](./ms-cloud-germany-migration-opt-in.md) на миграцию под руководством корпорации Майкрософт сегодня. Когда мы будем готовы приступить к миграции, мы сообщим вам через Центр сообщений в центре администрирования Microsoft 365 администратора.

**Dynamics 365 и Power BI**

В настоящее время вы можете выбрать миграцию для [клиента Dynamics 365](/dynamics365/get-started/migrate-data-german-region) Power BI [Microsoft.](/power-bi/admin/service-admin-migrate-data-germany) Когда вы будете готовы начать миграцию, то в центре администрирования Microsoft 365 мы проинформируем вас с помощью Центра сообщений.

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>Изменится ли цена для Office 365 служб, которые я использую?

Да. Цены в глобальных облачных&#39;Microsoft (включая новые регионы центра обработки данных) обычно ниже.

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>Во время миграции подписки какие skUs и Лицензии будут применены к моей организации и пользователям?

Во время миграции из Microsoft Cloud Deutschland в службы Office 365 службы, определенные службы Германии, заменяются глобальными версиями того же или аналогичного SKU. В большинстве случаев SKU в Office 365 службах является одним и тем же, однако существует несколько замен, в которых SKU в Германии больше не доступен в Office 365 службах. Если вы хотите обновить SKU, назначенную вашей организации после завершения миграции, обратитесь к продавцу, чтобы добавить или изменить назначенные службы.

| Microsoft Cloud Deutschland — SKU продукта (DE) | Microsoft Cloud Global — SKU продукта (WW) |
| --- | --- |
| Lockbox \_ DE клиента (LOCKBOX \_ DE) | Lockbox клиента (LOCKBOX) |
| Dynamics 365 выпуск Enterprise — дополнительные служба хранилища базы данных \_ DE (CRMSTORAGE \_ DE) | Dynamics 365 выпуск Enterprise — дополнительные служба хранилища базы данных (CRMSTORAGE) |
| Dynamics 365 выпуск Enterprise - Дополнительные непроизводимые \_ экземпляры DE (CRMTESTINSTANCE \_ DE) | Dynamics 365 выпуск Enterprise - Дополнительный экземпляр non-production (CRMTESTINSTANCE) |
| Dynamics 365 для службы выпуск Enterprise \_ de (DYN365 \_ ENTERPRISE CUSTOMER SERVICE \_ \_ \_ DE) | Dynamics 365 для службы выпуск Enterprise (DYN365 \_ ENTERPRISE \_ CUSTOMER \_ SERVICE) |
| Dynamics 365 для продаж выпуск Enterprise \_ DE (DYN365 \_ ENTERPRISE SALES \_ \_ DE) | Dynamics 365 для продаж выпуск Enterprise (DYN365 \_ КОРПОРАТИВНЫЕ \_ ПРОДАЖИ) |
| Dynamics 365 для членов выпуск Enterprise \_ de (DYN365 \_ ENTERPRISE TEAM MEMBERS \_ \_ \_ DE) | Dynamics 365 для членов выпуск Enterprise (DYN365 \_ ENTERPRISE \_ TEAM \_ MEMBERS) |
| Dynamics 365 Plan 1 выпуск Enterprise \_ DE (DYN365 \_ ENTERPRISE \_ PLAN1 \_ DE) | Dynamics 365 Plan 1 выпуск Enterprise (DYN365 \_ ENTERPRISE \_ PLAN1) |
| \_службы ECAL (EOA, EOP, DLP) DE (ECAL \_ SERVICES \_ DE) | службы ECAL (EOA, EOP, DLP) (ECAL \_ SERVICES) |
| \_Enterprise Mobility + Security E3 DE (EMS \_ DE) | Enterprise Mobility + Security E3 (EMS) |
| \_Exchange Online (план 1) DE (EXCHANGESTANDARD \_ DE) | Exchange Online (план 1) (EXCHANGESTANDARD) |
| \_Exchange Online (план 2) DE (EXCHANGEENTERPRISE \_ DE) | Exchange Online (план 2) (EXCHANGEENTERPRISE) |
| \_Exchange Online Archiving для Exchange Online DE (EXCHANGEARCHIVE \_ ADDON \_ DE) | Exchange Online Archiving для Exchange Online (EXCHANGEARCHIVE \_ ADDON) |
| \_Exchange Online Archiving для Exchange Server DE (EXCHANGEARCHIVE \_ DE) | Exchange Online Archiving для Exchange Server (EXCHANGEARCHIVE) |
| \_Exchange Online базовый DE (EXCHANGE \_ S \_ ESSENTIALS \_ DE) | Exchange Online базовый (EXCHANGE \_ S \_ ESSENTIALS) |
| \_базовая подписка на Exchange Online DE (EXCHANGEDESKLESS \_ DE) | базовая подписка на Exchange Online (EXCHANGEDESKLESS) |
| \_Exchange Online Protection DE (EOP \_ ENTERPRISE \_ DE) | Exchange Online Protection (EOP \_ ENTERPRISE) |
| Microsoft 365 бизнес стандарт (O365 \_ БИЗНЕС \_ ПРЕМИУМ) | Microsoft 365 бизнес стандарт (O365 \_ БИЗНЕС \_ ПРЕМИУМ) |
| Microsoft Dynamics CRM Online Экземпляр \_ DE (CRMINSTANCE \_ DE) | Microsoft Dynamics CRM Online Экземпляр (CRMINSTANCE) |
| Office 365 A1 для факультета \_ DE (STANDARDWOFFPACK \_ FACULTY \_ DE) | Office 365 A1 для преподавателей (ФАКУЛЬТЕТ STANDARDWOFFPACK) \_ |
| Office 365 A1 для студентов \_ DE (STANDARDWOFFPACK \_ STUDENT \_ DE) | Office 365 A1 для студентов (STANDARDWOFFPACK \_ STUDENT) |
| \_Office 365 Advanced Compliance DE (EQUIVIO \_ ANALYTICS \_ DE) | Соответствие требованиям Microsoft 365 E5 \_ (СООТВЕТСТВИЕ ТРЕБОВАНИЯМ ПО \_ ЗАЩИТЕ ИНФОРМАЦИИ) |
|Microsoft Defender для Office 365 (Plan 1) \_ DE (ATP \_ ENTERPRISE \_ DE) |Защитник Майкрософт для Office 365 (план 1) (ATP \_ ENTERPRISE) |
| \_Office 365 бизнес базовый DE (O365 \_ BUSINESS \_ ESSENTIALS \_ DE) | Microsoft 365 бизнес базовый (O365 \_ БИЗНЕС \_ ESSENTIALS) |
| \_Office 365 бизнес премиум DE (O365 \_ BUSINESS \_ PREMIUM \_ DE) | Microsoft 365 бизнес стандарт (O365 \_ БИЗНЕС \_ ПРЕМИУМ) |
| \_Office 365 бизнес DE (O365 \_ BUSINESS \_ DE) | Приложения Microsoft 365 для бизнеса (O365 \_ BUSINESS) |
| Office 365 E1 \_ DE (STANDARDPACK \_ DE) | Office 365 E1 (STANDARDPACK) |
| Office 365 E3 без ProPlus \_ DE (ENTERPRISEPACKWITHOUTPROPLUS \_ DE) | Office 365 E3 без ProPlus (ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 корпоративный E1 \_ DE (STANDARDPACK \_ DE) | Office 365 корпоративный E1 (STANDARDPACK) |
| Office 365 корпоративный E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 корпоративный E3 (ENTERPRISEPACK) |
| \_Office 365 с дополнительным хранилищем DE (SHAREPOINTSTORAGE \_ DE) | Office 365 с дополнительным хранилищем (SHAREPOINTSTORAGE) |
| \_Office 365 F1 DE (DESKLESSPACK \_ DE) | Office 365 F1 (DESKLESSPACK) |
| Office 365 профессиональный плюс \_ факультета DE (OFFICESUBSCRIPTION \_ FACULTY \_ DE) | Office 365 профессиональный плюс для факультета (ФАКУЛЬТЕТ OFFICESUBSCRIPTION) \_ |
| Office 365 профессиональный плюс для студентов \_ DE (OFFICESUBSCRIPTION \_ STUDENT \_ DE) | Office 365 профессиональный плюс для студентов (OFFICESUBSCRIPTION \_ STUDENT) |
| \_Office 365 профессиональный плюс DE (OFFICESUBSCRIPTION \_ DE) | Office 365 профессиональный плюс (OFFICESUBSCRIPTION) |
| \_OneDrive для бизнеса (план 1) DE (WACONEDRIVESTANDARD \_ DE) | OneDrive для бизнеса (план 1) (WACONEDRIVESTANDARD) |
| \_OneDrive для бизнеса (план 2) DE (WACONEDRIVEENTERPRISE \_ DE) | OneDrive для бизнеса (план 2) (WACONEDRIVEENTERPRISE) |
| Power BI Pro для факультета \_ DE (POWER \_ BI PRO \_ \_ FACULTY \_ DE) | Power BI Pro для преподавателей (POWER \_ BI \_ PRO \_ FACULTY) |
| \_Power BI Pro DE (POWER \_ BI \_ PRO \_ DE) | Power BI Pro (POWER \_ BI \_ PRO) |
| \_Project Online базовый DE (PROJECTESSENTIALS \_ DE) | Project Online базовый (PROJECTESSENTIALS) |
| \_Project Online расширенный DE (PROJECTPREMIUM \_ DE) | Project Online расширенный (PROJECTPREMIUM) |
| \_Project Online профессиональный DE (PROJECTPROFESSIONAL \_ DE) | Project Online профессиональный (PROJECTPROFESSIONAL) |
| \_Project, план 3 DE (PROJECTPROFESSIONAL \_ DE) | Project, план 3 (PROJECTPROFESSIONAL) |
| Office 365 E4 \_ DE (ENTERPRISEWITHSCAL \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| \_SharePoint Online (план 1) DE (SHAREPOINTSTANDARD \_ DE) | SharePoint Online (план 1) (SHAREPOINTSTANDARD) |
| \_SharePoint Online (план 2) DE (SHAREPOINTENTERPRISE \_ DE) | SharePoint Online (план 2) (SHAREPOINTENTERPRISE) |
| Skype для бизнеса Online (Plan 1) \_ DE (MCOIMP \_ DE) | Office 365 E1 (STANDARDPACK) |
| Skype для бизнеса Online (Plan 1) \_ DE (MCOIMP \_ DE) | Skype для бизнеса Online (Plan 1) (MCOIMP) |
| Skype для бизнеса Online (Plan 2) \_ DE (MCOSTANDARD \_ DE) | Skype для бизнеса Online (Plan 2) (MCOSTANDARD) |
| Skype для бизнеса Плюс CAL \_ DE (MCOPLUSCAL \_ DE) | Skype для бизнеса Плюс CAL (MCOPLUSCAL) |
| Visio Online Plan 1 для факультета \_ DE (VISIOONLINE \_ PLAN1 \_ FAC \_ DE) | Visio Online Plan 1 для преподавателей (FAC VISIOONLINE \_ \_ PLAN1) |
| Visio Online Plan 1 \_ DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio Online Plan 1 (VISIOONLINE \_ PLAN1) |
| Visio Online Plan 2 для \_ факультета DE (VISIOCLIENT \_ FACULTY \_ DE) | Visio Online Plan 2 для преподавателей (VISIOCLIENT \_ FACULTY) |
| Visio Online Plan 2 \_ DE (VISIOCLIENT \_ DE) | Visio Online Plan 2 (VISIOCLIENT) |
| \_Visio, план 1 DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio, план 1 (VISIOONLINE \_ PLAN1) |
| \_Visio, план 2 DE (VISIOCLIENT \_ DE) | Visio, план 2 (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Как получить помощь от корпорации Майкрософт, чтобы перейти на новый регион или ответить на вопросы о поддержке?

Если у вас есть вопросы, вы можете связаться с нами или вашим партнером:

- В Azure можно отправлять [новые запросы в службу поддержки](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) на портале Azure.
- Для Office 365, вы можете отправить вопросы с помощью справки? ссылку центра &quot; &quot; [администрирования Microsoft 365.](https://portal.office.de/)
- Если вы клиент Dynamics 365 и Power BI клиент, а также Office 365, вы можете отправить вопросы с помощью справки? ссылка центра администрирования &quot; &quot; Microsoft 365. [](https://portal.office.de/) Варианты поддержки клиентов Dynamics 365 Customer Engagement доступны [здесь](/dynamics365/get-started/support/). Варианты поддержки клиентов Power BI доступны [здесь](https://powerbi.microsoft.com/support/).

### <a name="my-customer-already-has-a-m365-tenant-in-the-global-microsoft-cloud-in-addition-to-a-microsoft-cloud-deutschland-tenant-can-these-two-tenants-be-merged-into-one-as-part-of-the-migration"></a>У моего клиента уже есть клиент M365 в глобальном облаке Microsoft, а также клиент Microsoft Cloud Deutschland. Можно ли объединить этих двух клиентов в один в рамках миграции?

Нет, возможности объединения клиента не существует. Клиенты останутся отдельными и уникальными, так как каждый клиент имеет свое пространство имен и уникальный ID. Корпорация Майкрософт при желании перенаселит клиента Microsoft Cloud Deutschland в глобальное облако, иначе клиент может отменить его и отказаться от него.


### <a name="what-actions-are-required-to-be-done-by-most-end-users-as-part-of-the-migration"></a>Какие действия необходимо сделать большинству конечных пользователей в рамках миграции?
Миграция предназначена для минимального воздействия на конечных пользователей и клиентов.
- Убедитесь, Office приложения запускают последние доступные версии. 
- Клиенты Skype для бизнеса переходят на Teams в рамках миграции и, возможно, потребуется скачать и [установить](/deployoffice/teams-install) Teams на устройствах.
- Конечным пользователям может потребоваться выйти из Office и войти обратно после завершения миграции. 
- Клиентам, OneDrive клиенту Sync, необходимо выйти из рабочей станции и снова войти, чтобы OneDrive Sync войти в глобальную службу Azure Active Directory.
- Будьте в курсе новых глобальных URL-адресов после завершения миграции, Outlook веб-доступа (пример: использование outlook.office365.com). SharePoint Интернет-клиенты будут продолжать успешно подключаться к пространству имен MCD с помощью существующего URL-адреса (пример: contoso.sharepoint.de).


### <a name="which-customers-are-affected-by-the-azure-active-directory-migration"></a>Какие клиенты подвержены Azure Active Directory миграции? 

Все клиенты Office 365 зависят от Azure Active Directory проверки подлинности и хранения критически важных компонентов служб, необходимых для работы служб, в которых хранятся службы Майкрософт. 


### <a name="what-are-the-impacts-of-the-azure-active-directory-migration"></a>Каковы последствия переноса Azure Active Directory?

Первоначальная миграция Azure Active Directory на ранней стадии не влияет на клиентскую среду. После заключительного этапа миграции все службы клиента-клиента полностью находятся в глобальной службе. После этого заключительного этапа служба Azure Active Directory Microsoft Cloud Deutschland больше не может принимать запросы на авторизацию или предоставлять маркеры доступа Office службам.


### <a name="what-does-it-mean-to-ensure-network-connectivity-to-office-365-services-urls-and-ip-addresses"></a>Что означает обеспечение подключения к сети для Office 365 url-адресов служб и [IP-адресов?](./urls-and-ip-address-ranges.md)

В этой статье описываются необходимые URL-адреса и IP-адреса, необходимые для надлежащей работы глобальной службы для обеспечения хорошего обслуживания клиентов. В относительно редких случаях некоторые клиенты пытаются настроить безопасность периметра сети таким образом, чтобы свести к минимуму потоки трафика и ограничить доступ к службам только в рамках IP-диапазонов служб Microsoft Cloud Deutschland.


### <a name="how-do-i-manage-the-dns-changes-for-exchange-online-so-mail-will-continue-to-flow"></a>Как управлять изменениями DNS для Exchange Online, чтобы почта продолжала поступать?

Диапазоны IP-адресов с управлением Майкрософт и зоны DNS переходят во время и в рамках миграции в глобальную службу. 

Клиент управляет DNS-зонами, такими как пользовательские записи MX домена, но для упрощения этой миграции клиентская запись управляемых MX указывает на конечную точку службы Office 365 в зоне office.de и Майкрософт управляет миграцией конечной точки службы автоматически.


### <a name="how-do-i-manage-the-dns-changes-for-skype-for-business"></a>Как управлять изменениями DNS для Skype для бизнеса? 
 
Все Skype для бизнеса в переходе на Microsoft Teams. Переход зон Skype DNS не требуется при переносе на Teams. Клиенты смогут сразу же войти в Teams со всеми функциональными возможностями после миграции.
 

### <a name="will-outlook-for-ios-and-android-work-after-the-migration"></a>Будет Outlook для iOS и Android после миграции? 

Да. Рекомендация Корпорации Майкрософт — все клиенты запускают последние доступные версии Office, включая Outlook для клиентов iOS и Android. После завершения миграции в глобальную службу Office 365 все Office клиенты должны выйти и войти в систему, чтобы получить новый маркер Azure Active Directory доступа от глобальной службы. 



## <a name="next-step"></a>Следующий этап

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
- [Начало перехода на Microsoft Teams](/microsoftteams/upgrade-start-here)
