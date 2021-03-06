---
title: ИТ-инфраструктура Contoso и бизнес-потребности
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Понимание базовой структуры локальной ИТ-инфраструктуры Contoso и того, как бизнес-потребности компании Microsoft 365 для предприятия.
ms.openlocfilehash: 72d502b5078a1e572eeba27832550af52907e209
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558410"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a>ИТ-инфраструктура Contoso и бизнес-потребности

Contoso переходит из локальной централизованной ИТ-инфраструктуры в облачную установку, которая включает в себя рабочие нагрузки и приложения на основе облачной личной производительности.

## <a name="existing-contoso-it-infrastructure"></a>Существующая ИТ-инфраструктура Contoso

В компании Contoso используется по большей части централизованная локальная ИТ-инфраструктура с центрами обработки данных приложений, находящимися в главном офисе в Париже.

Здесь расположен офис штаб-квартиры с центрами обработки данных приложений, dmZ и интернетом.

![Существующая ИТ-инфраструктура Contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

В локальных центрах обработки данных приложений размещены указанные ниже элементы. 

- Настраиваемые бизнес-приложения, которые используют SQL Server и другие базы данных Linux.
- Набор устаревших серверов SharePoint.
- Серверы уровня организации и групп для хранения данных.

Кроме того, в каждом региональном центральном офисе поддерживается набор серверов с похожими наборами приложений. Этими серверами управляют региональные ИТ-отделы.

Поиск приложений и данных в этих разрозненных центрах обработки данных, расположенных в разных регионах, сопровождается рядом сложностей.

В dmz штаб-квартиры Contoso различные наборы серверов обеспечивают:

- Размещение для государственного веб-сайта Contoso, на котором клиенты могут заказать продукты, части, материалы и службу.
- Хостинг для партнерской экстрасети компании Contoso, предназначенной для связи и сотрудничества с партнерами.
- Удаленный доступ на основе частной виртуальной сети (VPN) к интрасети компании Contoso и веб-прокси для сотрудников главного офиса в Париже.

## <a name="contoso-business-needs"></a>Потребности бизнеса Contoso

Потребности бизнеса Contoso подпадают под пять основных категорий:

**Производительность труда**

- Упрощение совместной работы

  Замените совместную работу на основе обмена электронной почтой и файлами на веб-модель, которая позволяет в режиме реального времени вносить изменения в документы, упрощать собрания в Интернете и захватывать потоки бесед.
- Повышение производительности труда удаленных и мобильных сотрудников

  Многие сотрудники, работающие из дома или на местах, заменяют узкое VPN-решение с возможностью выполнения доступа к данным и ресурсам Contoso в облаке.
- Повышение уровня креативности и инноваций

  Использование последних методов визуального обучения и разработки идей, включая рукописный ввод и трехмерную визуализацию.

**Безопасность**

- Управление идентификацией и доступом

  Обеспечение многофакторной и других форм проверки подлинности и защита учетных данных пользователей и администраторов.

- Защита от угроз

  Защита от внешних угроз безопасности, включая вредоносное программное обеспечение, проникающее через электронную почту и операционные системы.

- Защита информации

  Шифрование важных цифровых ресурсов, например данных клиентов, конструкторских и производственных спецификаций и сведений о сотрудниках, а также блокирование доступа к этим ресурсам.

- Управление безопасностью

  Отслеживайте положение в области безопасности и обнаруживать угрозы и реагировать на них в режиме реального времени.

**Удаленный доступ, доступ с мобильных устройств и работа с бизнес-партнерами**

- Повышение безопасности удаленных и мобильных сотрудников

  Реализация принесите собственное устройство (BYOD) и управление устройствами, которые принадлежат компании, чтобы обеспечить защищенный доступ, правильное поведение приложения и защиту данных компании.

- Уменьшение инфраструктуры удаленного доступа для сотрудников

  Снижение затрат на обслуживание и поддержку и повышение производительности для решения удаленного доступа путем перемещения ресурсов с обычным доступом в облако.

- Обеспечение лучшей возможности подключения и снижения накладных расходов для транзакций бизнес-к-susiness (B2B)

  Замените стареющую и дорогую партнерской экстрасети облачным решением с федерацией проверки подлинности.

**Соответствие требованиям**

- Соответствие требованиям региональных нормативных актов

  Обеспечение соответствия отраслевым и региональным правилам хранения данных, шифрования, конфиденциальности данных и персональных данных, таких как Общие правила защиты данных (GDPR) для Европейского союза.

**Управление**

- Снижение накладных расходов на ИТ для управления программным обеспечением, работающим на клиентских ПК и устройствах

  Автоматизация установки обновлений для Windows операционной системы и Приложения Microsoft 365 для предприятий всей организации.

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a>Сопоставление бизнеса Contoso необходимо Microsoft 365 для предприятия

ИТ-отдел Contoso определил следующее сопоставление бизнес-потребностей для Microsoft 365 E5 функций перед развертыванием:


| Category | Потребности бизнеса | Microsoft 365 для корпоративных продуктов или функций |
|:-------|:-----|:-----|
| Производительность труда |  |  |
|  | Упрощение совместной работы | Microsoft Teams, SharePoint, OneDrive |
|  | Повышение производительности труда удаленных и мобильных сотрудников | Рабочие нагрузки Microsoft 365 и облачные данные |
|  | Повышение уровня креативности и инноваций | Windows Ink, Кортана на рабочем месте, PowerPoint |
| Безопасность |  |  |
|  | Управление удостоверениями и доступом | Выделенные учетные записи глобального администратора с многофакторной проверкой подлинности Azure AD (MFA) и Azure AD управление привилегированными пользователями (PIM) <BR> Многофакторная проверка подлинности для всех учетных записей пользователей <BR> Условный доступ <BR> Windows Hello <BR> Credential Guard в Защитнике Windows |
|  | Защита от угроз | Advanced Threat Analytics <BR> Защитник Windows <BR> Defender для Office 365 <BR> Microsoft Defender для Office 365 <BR> Microsoft 365 расследования и реагирования на угрозы <BR> |
|  | Защита информации | Azure Information Protection <BR> Защита от потери данных (DLP) <BR> Windows Information Protection (WIP) <BR> Microsoft Cloud App Security <BR> Microsoft Intune |
|  | Управление безопасностью | Azure Defender  <BR> Центр безопасности Защитника Windows |
| Удаленный доступ, доступ с мобильных устройств и работа с бизнес-партнерами |  |  |
|  | Повышение уровня безопасности для удаленных и мобильных сотрудников | Microsoft Intune |
|  | Уменьшение инфраструктуры удаленного доступа для сотрудников | Рабочие нагрузки Microsoft 365 и облачные данные |
|  | Улучшение подключения и снижение накладных расходов для транзакций B2B | Федеративная проверка подлинности и облачные ресурсы |
| Соответствие требованиям |  |  |
|  | Соответствие требованиям региональных нормативных актов | Функции GDPR в Microsoft 365 |
| Управление |  |  |
|  | Снижение накладных расходов на ИТ для установки обновлений клиентов | Обновления Windows 10 Корпоративная <BR> Обновления приложений Microsoft 365 для предприятий |
||||

## <a name="next-step"></a>Следующий шаг

Узнайте о локальной [](contoso-networking.md) сети Корпорации Contoso и о том, как она была оптимизирована для доступа и задержки Microsoft 365 облачных ресурсов.

## <a name="see-also"></a>См. также

[Обзор Microsoft 365 для предприятий](microsoft-365-overview.md)

[Руководства по лаборатории тестирования](m365-enterprise-test-lab-guides.md)
