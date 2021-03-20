---
title: Новые возможности в Microsoft Defender для Office 365
description: Узнайте о новых возможностях и функциях, доступных в последнем выпуске Microsoft Defender для Office 365.
keywords: что нового в Office 365 atp, ga, как правило, доступны, возможности, доступные, новые
search.appverid: met150
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.date: 01/12/2021
ms.custom: seo-marvel-apr2020
ms.reviewer: vippand
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0e2885f4db67f1508f4e7a3f354e11fb361265a3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907956"
---
# <a name="whats-new-in-microsoft-defender-for-office-365"></a>Новые возможности в Microsoft Defender для Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

В этой статье перечислены новые возможности последнего выпуска Microsoft Defender для Office 365. Функции, которые в настоящее время находятся в предварительном просмотре, обозначаются **(предварительный просмотр).**

> [!TIP]
> Еще нет Microsoft Defender для Office 365? [Свяжитесь с продажами, чтобы начать пробную работу.](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)

## <a name="februarymarch-2021"></a>Февраль-март 2021 г. 

- Интеграция оповещений (поиск с помощью alert ID и Alert-Explorer навигации) в [опытом охоты](threat-explorer.md)
- Увеличение ограничений на экспорт записей с 9990 до 200 000 в [охотничьих опытах](threat-explorer.md)
- Расширение ограничения хранения и поиска данных Explorer (и обнаружения в режиме реального времени) для пробных клиентов с 7 (предыдущего ограничения) до 30 дней в ходе [охоты](threat-explorer.md)
- Новые поворотные точки охоты,  называемые импотенциозным доменом и обезличенным пользователем в explorer (и обнаружения в режиме реального времени) для поиска атак на защищенных пользователей или доменов.  Дополнительные сведения см. в [дополнительных сведениях.](threat-explorer.md#view-phishing-emails-sent-to-impersonated-users-and-domains) (Microsoft Defender для Office 365 Plan 1 или Plan 2)

## <a name="december-2020"></a>Декабрь 2020 г.

- [Безопасность по умолчанию в Office 365](secure-by-default.md)
- Автоматизированные улучшения в расследовании: общие оповещения для ручных расследований электронной почты, обработка изменений почтовых ящиков в качестве отдельной категории сущности, удаление избыточных действий блокировки URL-адресов и создание исходящие кластеры электронной почты для скомпрометизированных пользователями расследований.

## <a name="november-2020"></a>Ноябрь 2020 г.

- Обновленные ограничения экспорта в центре > действий > из журнала отправки почты и действий (Defender for Office 365 Plan 2)

## <a name="septemberoctober-2020"></a>Сентябрь-октябрь 2020 г.

- [Проверка политик с помощью анализатора конфигурации](configuration-analyzer-for-security-policies.md)
- Расширенные возможности в [Обозревателе](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) угроз, включая топ-пользователей, правила транспорта и соединители (сведения Defender for Office 365 в Обозревателе угроз [(электронная](threat-explorer.md) почта была разрешена/заблокирована политикой клиента/пользователя) (Defender for Office 365 Plan 2)
- Угрозы URL-адресов в [Обозревателе](threat-explorer.md#threats-in-urls) угроз (вредоносные программы, фишинг, спам или нет) (Defender for Office 365 Plan 2)
- [Улучшения обозревателя](threat-explorer.md#improvements-to-the-threat-hunting-experience-upcoming) угроз для охоты с обновлениями вокруг угроз, дополнительных действий, расположения доставки и обновленного представления временной шкалы (Defender for Office 365 Plan 2)

## <a name="julyaugust-2020"></a>Июль-август 2020 г.

- [Улучшение охоты](threat-explorer.md#improvements-to-threat-hunting-experience) (Microsoft Defender для Office 365 Plan 1 или Plan 2)
- [Легко применить рекомендуемые параметры с помощью заранее задав политики безопасности](preset-security-policies.md)

## <a name="marchapril-2020"></a>Март-апрель 2020 г.

- Теперь в [общем доступе](address-compromised-users-quickly.md) доступна возможность устранения скомпрометизированных учетных записей пользователей с помощью автоматического расследования и ответа. (Microsoft Defender для Office 365 Plan 2)

## <a name="januaryfebruary-2020"></a>Январь-февраль 2020 г.

- [Общая доступность представлений кампании в Microsoft Defender для Office 365](campaigns.md) (Microsoft Defender для Office 365 Plan 2)
- Усовершенствования в [Обозревателе](threat-explorer.md) угроз, позволяющие группам операций безопасности искать и фильтровать на нескольких полях при расследовании электронной [почты:](investigate-malicious-email-that-was-delivered.md)(Microsoft Defender для Office 365 Plan 2)
  - Расположение доставки и специальные действия
  - Directionality (входящий, исходящие или внутри-org)
  - Расширенные нефильтры (это расширенные параметры фильтрации, которые не содержат, не включают и т.д.)
  - Зернистые фильтры времени (день, час, полчаса)

- Виджет **Incidents** теперь является **виджетом Центра действий.** (Чтобы просмотреть виджеты безопасности в Центре & безопасности, перейдите к **управлению угрозами** \> **Обзор**.) (Microsoft Defender для Office 365 Plan 2)

- [Безопасные документы в Microsoft 365](safe-docs.md) **(предварительный просмотр)**

## <a name="december-2019"></a>Декабрь 2019 г.

- [Экспорт URL-адреса щелкните](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) данные для автономного анализа (Microsoft Defender для Office 365 Plan 1 или Plan 2)

- [Использование представлений кампании в Microsoft Defender для Office 365 **(предварительный** просмотр)](campaigns.md) (Microsoft Defender для Office 365 Plan 2)

## <a name="november-2019"></a>Ноябрь 2019 г.

- [Ознакомьтесь с новыми возможностями](address-compromised-users-quickly.md) обнаруженияи реагирования пользователей (предварительный просмотр) (Microsoft Defender для Office 365 Plan 2)

## <a name="september-2019"></a>Сентябрь 2019 г.

- [Использование возможностей автоматического](automated-investigation-response-office.md) расследования и реагирования (Microsoft Defender для Office 365 Plan 2)

- Интеграция с Microsoft Defender для автоматизированных событий расследования и реагирования Office 365 с помощью API управления [Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) (Defender for Office 365 Plan 2)

- [Просмотр заголовок электронной почты](investigate-malicious-email-that-was-delivered.md) и скачивание тела электронной почты (Microsoft Defender для Office 365 Plan 1 или Plan 2)

## <a name="august-2019"></a>Август 2019 г.

- [Просмотр временной шкалы электронной](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email) почты (Microsoft Defender для Office 365 Plan 1 или Plan 2)

## <a name="july-2019"></a>Июль 2019 г.

- [Проверьте действие доставки и расположение сообщений](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location) электронной почты (Microsoft Defender для Office 365 Plan 1 или 2)

## <a name="june-2019"></a>Июнь 2019 г.

- [Просмотр URL-адресов фишинга](threat-explorer.md#view-phishing-url-and-click-verdict-data) и щелкните данные вердикта (Microsoft Defender для Office 365 Plan 1 или Plan 2)

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Microsoft Defender для Office 365 (план 1 и план 2)

Знаете ли вы, что Microsoft Defender для Office 365 доступен в двух планах? [Узнайте больше о том, что включает в себя каждый план.](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)

## <a name="see-also"></a>См. также

[Дорожная карта Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap)

[Описание службы Microsoft Defender для Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)